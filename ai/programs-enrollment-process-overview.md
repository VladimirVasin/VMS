# Programs&Enrollment Process Overview

Captured: 2026-05-28.

Source: Azure DevOps feature `24497 Programs&Enrollment` in AvidSys/VMS.

Detailed story text is stored in `azure-feature-24497-programs-enrollment.md`.

## High-Level Summary

The feature describes an end-to-end Vendor Management System lifecycle:

1. A vendor registers through a vendor-facing enrollment/application flow.
2. An internal user approves or declines the Vendor Registration Request.
3. Approval creates the Vendor, Primary Contact, optional Program Enrollment Application, B2C account, and welcome email.
4. A submitted Program Enrollment Application creates an Enrollment plus requirement assignments.
5. Requirement assignments drive application status.
6. Approved requirements move the Enrollment toward signature.
7. DocuSign sends the Enrollment contract to vendor and client.
8. When both parties sign, the Enrollment becomes Active.
9. Active enrollments can later be terminated manually or expired automatically.
10. Closing a Program cleans up unfinished applications and pending enrollments.

## Core Records

- `Vendor Registration Request`
- `Vendor`
- `Vendor Contact`
- `Program`
- `Program Milestone`
- `Program Enrollment Application`
- `Enrollment / av_vendorcontract`
- `Program Requirement`
- `Enrollment Requirement Assignment`
- `Program Certificate`
- `Payment Term`
- `Notification Template`
- DocuSign envelope/document records or integration state

## Vendor-Facing Application Flow

The prototype flow is for client `DC OCFO`.

Screens:

- Vendor Enrollment Landing Page
- Program Selection
- Vendor Application Form
- Payment Terms Selection
- Document Upload
- Submission Confirmation

This is the external-facing path that should create or feed the internal records used by the rest of the lifecycle.

## Vendor Registration Review

`Vendor Registration Request` has command bar actions:

- `Approve`
- `Decline`

Visibility:

- Buttons are visible only when `statuscode = Submitted`.
- Buttons are hidden or disabled after a decision is made.

Approve behavior:

- Opens a modal with optional `av_comment`.
- On confirm:
  - Set `statuscode = Approved`.
  - Set `Reviewed By` to current user.
  - Set `Reviewed On` to current date/time.
  - Save comment.

Decline behavior:

- Opens a modal with required `av_declinereason`.
- Requires comment.
- On confirm:
  - Set `statuscode = Declined`.
  - Set `Reviewed By` to current user.
  - Set `Reviewed On` to current date/time.
  - Save decline reason and comment.

## Post-Approval Vendor Provisioning

When a `Vendor Registration Request` is approved:

1. Create a `Vendor`.
2. Map request fields to vendor:
   - Vendor Name
   - EIN
   - Legal Name / Doing Business As
   - Classification
   - Individual/Sole Proprietor
   - Company Email Address
   - Website
   - Phone Number
   - Country
   - Street
   - City
   - State
   - Zip/Postal Code
3. Create a `Primary Contact`.
4. Map request fields to contact:
   - First Name
   - Last Name
   - Job Title
   - Email Address
   - Phone Number
   - Primary Contact = Yes
5. Update `Vendor.Primary Contact` to the created contact.
6. If the request contains a `Program`, create a `Program Enrollment Application` linked to the program and new vendor.
7. Create an Azure AD B2C account for the primary contact.
8. Send a welcome email to the primary contact using notification template `VendorPortalWelcome`.

## Program Lifecycle

Program command bar actions:

- `Start Program`
- `Close Program`

Start Program:

- Visible only when `statuscode = Draft`.
- On click:
  - Set Program `statuscode = Active`.
  - Save.

Close Program:

- Visible only when `statuscode = Active`.
- On click:
  - Set Program `statuscode = Closed`.
  - Save.

Program milestone scheduled job:

- Runs daily.
- Selects `Program Milestone` records where:
  - `Milestone Date <= Today`
  - Related Program exists
  - Program status is open/active according to the configured option set
- For each milestone:
  - Set `Program.Active Stage` from milestone type.
  - Set `Current Stage Start Date = Milestone Date`.
  - Find the next upcoming milestone for the same Program.
  - Set `Next Stage Start Date` to that date, or clear it when no next stage exists.

Open question:

- One story says Program status is `Active`; another says `Open`. Confirm real Dataverse option values before implementation or QA.

## Program Milestone Naming

For `av_programmilestone`:

- On create or update of `av_milestone`, set `av_programmilestone.av_name = av_milestone`.

This is data hygiene so milestone rows have a readable name.

## Application Submission and Enrollment Creation

When `Program Enrollment Application.statuscode = Submitted`:

1. Create `Enrollment / av_vendorcontract`.
2. Populate:
   - Vendor lookup
   - Program lookup
   - Application lookup
   - Status = Pending Activation
   - Start Date = Program.Start Date
   - End Date = Program.End Date
3. Update the Application with the created Enrollment lookup.
4. Retrieve active `Program Requirement` records where `Program = Application.Program`.
5. For each Program Requirement, create an `Enrollment Requirement Assignment` with:
   - Enrollment lookup
   - Vendor lookup
   - Status = Assigned
   - Description
   - File Required
   - Is Meeting

Open question:

- Stories `24517` and `24500` both describe creating an Enrollment from a submitted application. Decide whether this is one shared automation or whether one creates Enrollment and the other creates assignments.

## Requirement Assignment Status Feedback

Triggers:

- On Program Requirement Assignment creation.
- On Program Requirement Assignment `statuscode` update.

Rules:

- If all related assignments for a Program Enrollment Application have `statuscode = Verifying`, set application `statuscode = Verifying`.
- If a new assignment is created or an existing assignment changes to `Assigned`, set application `statuscode = Submitted`.
- If all related assignments have `statuscode = Approved`:
  - Set Program Enrollment Application `statuscode = Approved`.
  - Set related Enrollment `statuscode = Pending Signature`.
  - Set Enrollment Payment Term from Program Enrollment Application Payment Term.

Open question:

- Confirm the exact relationship path between `Enrollment Requirement Assignment` and `Program Enrollment Application`. The stories mention assignment to Enrollment and Vendor, but the status rollup is described against Application.

## Program Certificate Review

Program Certificate actions:

- `Verify`
- `Reject`

Placement:

- Program Certificate main form.
- Program Certificate grid/subgrid command bar.

Visibility:

- Visible only when `statuscode = Verifying`.

Verify:

- Set `statuscode = Verified`.
- Populate `Reviewed By`.
- Populate `Reviewed On`.

Reject:

- Set `statuscode = Rejected`.
- Populate `Reviewed By`.
- Populate `Reviewed On`.

Open question:

- The stories do not explicitly define how Program Certificate `Verified/Rejected` changes feed back into Requirement Assignment `Approved/Rejected/Verifying`.

## Enrollment Payment Term Discount

For `Enrollment / av_vendorcontract`:

Triggers:

- Record creation.
- Update of Payment Term field.

Rules:

- If Payment Term is not null:
  - Retrieve Discount % from selected Payment Term.
  - Populate Enrollment Discount %.
  - Save.
- If Payment Term becomes null:
  - Clear Enrollment Discount %.

This should cooperate with the requirement approval flow, because that flow copies Payment Term from Application to Enrollment.

## Contract Signature via DocuSign

This story was captured as `New`, so it is likely still pending implementation.

Button:

- `Send for Signature`

Placement:

- Enrollment main form.
- Enrollment grid.
- Enrollment sub-grid.

Visibility:

- Visible when `av_contract` is not blank and either:
  - Enrollment `statuscode = Pending Signature`, or
  - Enrollment `statuscode = Sent for Signature` and Signature Status is `Declined` or `Error`.

Send action:

1. Retrieve contract document from `Enrollment.av_contract`.
2. Create DocuSign envelope.
3. Add vendor signee.
4. Add client signee.
5. Send envelope for signature.
6. Update Enrollment:
   - `statuscode = Sent for Signature`
   - `Signature Status = Sent`
   - `Sent for Signature On = current date/time`

Status synchronization:

- Implement webhook/callback or recurring synchronization process.

Vendor signature:

- When vendor signs:
  - `Vendor Signature Status = Signed`
  - `Vendor Signed On = signature date/time`

Client signature:

- When client signs:
  - `Client Signature Status = Signed`
  - `Client Signed On = signature date/time`

Fully signed:

- When vendor and client signature statuses are both `Signed`:
  - Set `Enrollment Signature Status = Signed`.
  - Set Enrollment `statuscode = Active`.
  - Save fully executed signed document back to `av_contract`.

## Enrollment Termination and Expiration

Manual termination:

- Add `Terminate` button to Enrollment form.
- Visible only when Enrollment `statuscode = Active`.
- Opens modal with:
  - Termination Reason, required Choice
  - Termination Comments, required text
- On confirm:
  - Set Enrollment `statuscode = Terminated`.
  - Populate Termination Reason.
  - Populate Termination Comments.
  - Populate Terminated By.
  - Populate Terminated On.
  - Save.

Automatic expiration:

- Daily job finds Enrollment records where:
  - End Date < current date
  - Status Reason is not `Expired`
- For each match:
  - Set `statuscode = Expired`.
  - Save.

## Program Close Cleanup

When Program `statuscode = Closed`:

1. Retrieve related Program Enrollment Applications where status is:
   - Draft
   - Submitted
   - Under Review
2. Set each matching application to `Inactive`.
3. Retrieve related Enrollments where status is `Pending Activation`.
4. Set each matching enrollment to `Inactive`.

Open question:

- The story does not define behavior for `Pending Signature`, `Sent for Signature`, or `Active` enrollments when Program closes.

## Implementation Risks and Gaps

- Duplicate Enrollment creation may happen if `24517` and `24500` are implemented as separate triggers without idempotency.
- Program status names need option-set confirmation (`Open` vs `Active`).
- Requirement Assignment to Application relationship needs schema confirmation.
- Certificate review needs explicit linkage to assignment/application status.
- DocuSign is the largest pending piece and blocks the full happy path from reaching Active via signature.
- Program close cleanup may need explicit rules for signed or in-signature enrollments.
- All status-update automations should be idempotent and guard against repeated updates from the same trigger.

## Suggested Happy Path

1. Vendor submits registration/application through portal.
2. Internal reviewer approves Vendor Registration Request.
3. System creates Vendor, Primary Contact, B2C account, welcome email, and optional Program Enrollment Application.
4. Program is active and has configured Program Requirements and Program Milestones.
5. Vendor submits Program Enrollment Application.
6. System creates Enrollment and Requirement Assignments.
7. Vendor satisfies requirements and certificates/documents enter verification.
8. Reviewer verifies certificates/requirements.
9. All assignments become Approved.
10. Application becomes Approved.
11. Enrollment becomes Pending Signature and receives Payment Term.
12. Discount % populates from Payment Term.
13. Contract exists in `av_contract`.
14. User sends contract for signature via DocuSign.
15. Vendor signs.
16. Client signs.
17. Enrollment becomes Active and stores the fully executed contract.
18. Enrollment later expires by End Date or is manually terminated.

