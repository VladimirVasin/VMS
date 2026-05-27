# Azure DevOps Feature 24497: Programs&Enrollment

Captured: 2026-05-28 from Azure DevOps project AvidSys/VMS.

Source feature: 24497, Programs&Enrollment. The user originally pointed at 24517, which is one child user story under this feature.

## Story Status Snapshot

- Total child user stories: 15
- Completed: 12
- Ready for QA: 2
- New: 1

| ID | State | Title |
| --- | --- | --- |
| 24527 | Completed | Add Approve / Decline Actions for Vendor Registration Request |
| 24529 | Completed | Add Start and Close Actions on Program |
| 24531 | Completed | Add Terminate Action on Enrollment |
| 24770 | Completed | Add Verify / Reject Actions to Program Certificate |
| 24500 | Completed | Auto-Create Enrollment Requirement Assignments on Application Creation |
| 24530 | Completed | Auto-Expire Enrollment Based on End Date |
| 24558 | Completed | Auto-Populate Discount % on Enrollment |
| 24517 | Ready for QA | Create Vendor Enrollment on Application Submission |
| 24532 | Completed | Handle Related Records When Program is Closed |
| 24528 | Completed | Post-Approval Processing for Vendor Registration Request |
| 24761 | New | Send Enrollment Contract for Signature via DocuSign |
| 24705 | Completed | Set Program Milestone Name |
| 24499 | Ready for QA | Update Program Active Stage Based on Milestone Date |
| 24746 | Completed | Update Program Enrollment Application Status Based on Program Requirement Assignments |
| 24424 | Completed | Vendor Enrollment Application Design |

## Descriptions

### 24527 - Add Approve / Decline Actions for Vendor Registration Request

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24527

Description:

Add Approve and Decline buttons to the command bar on the Vendor Registration Request form. Buttons should be visible only when Status (statuscode) = Submitted and hidden/disabled after a decision is made.

1. Approve button behavior:

Open modal dialog with Comment field (optional) (av_comment)
On confirm:
Set statuscode = Approved
Set Reviewed By (current user)
Set Reviewed On (current date/time)
Save comment

2. Decline button behavior:

Open modal dialog with:
Decline Reason (required) (av_declinereason)
Comment (required)
On confirm:
Set statuscode = Declined
Set Reviewed By (current user)
Set Reviewed On (current date/time)
Save Decline Reason and Comment

### 24529 - Add Start and Close Actions on Program

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24529

Description:

Add two buttons on the Program (av_program) main form:

1. Start Program
Visible only when Status Reason (statuscode) = Draft
On click:
Set Program Status (statuscode) = Active
Save the record

2. Close Program
Visible only when Status Reason (statuscode) = Active
On click:
Set Program Status (statuscode) = Closed
Save the record

### 24531 - Add Terminate Action on Enrollment

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24531

Description:

Add a Terminate button to the Enrollment form.

Button visible only when Status Reason (statuscode) = Active

On click:

Open a modal dialog with:
Termination Reason (Choice, required)
Termination Comments (text, required)

On confirm:

Set Status Reason (statuscode) = Terminated
Populate:
Termination Reason
Termination Comments
Terminated By (current user)
Terminated On (current date/time)
Save the record

### 24770 - Add Verify / Reject Actions to Program Certificate

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24770

Description:

Buttons
Verify
Reject
Placement
Program Certificate Main Form
Program Certificate Grid/Subgrid (command bar)
Visibility Rules

Visible only when:

statuscode = Verifying
Verify Action

On click:

Set:
statuscode = Verified
Populate:
Reviewed By
Reviewed On
Reject Action

On click:

Set:
statuscode = Rejected
Populate:
Reviewed By
Reviewed On

### 24500 - Auto-Create Enrollment Requirement Assignments on Application Creation

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24500

Description:

Automatically create Enrollment Requirement Assignment records when a new Program Enrollment Application is created, ensuring all required program requirements are tracked per Vendor and Application.

Trigger: Program Enrollment Application is submitted (statuscode eq 'Submitted')

I. Create Enrollment (av_vendorcontract) record with:
Vendor (lookup)
Program (lookup)
Application (lookup)

II. Retrieve Program Requirements where:

Program = Application.Program
statecode = Active

III. For each Program Requirement:

Create Enrollment Requirement Assignment with:

Enrollment (lookup)
Vendor (lookup)
Status = Assigned
Description
File Required
Is Meeting

### 24530 - Auto-Expire Enrollment Based on End Date

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24530

Description:

Trigger daily
Find Enrollment records where:
End Date < current date
Status Reason (statuscode) ne Expired

For each matching record:

Set Status Reason (statuscode) eq Expired
Save the record

### 24558 - Auto-Populate Discount % on Enrollment

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24558

Description:

Table: Enrollment (av_vendorcontract)

Trigger on:

Record creation
Update of Payment Term field

Condition:

Payment Term != null

On trigger:

Retrieve Discount % from selected Payment Term
Populate Enrollment.Discount % with that value
Save the record
Clear Discount % if Payment Term becomes null

### 24517 - Create Vendor Enrollment on Application Submission

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24517

Description:

Trigger:
Program Enrollment Application updated
Condition: statuscode = Submitted

Create new Vendor Enrollment record with:

Vendor (lookup)
Program (lookup)
Application (lookup)
Status = Pending Activation
Start date = Program.Start Date
End Date = Program.End Date

Update Application:

Set Enrollment (lookup)

### 24532 - Handle Related Records When Program is Closed

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24532

Description:

When a Program record is updated and Status Reason (statuscode) = Closed, trigger logic to update related records.

1. Retrieve all Program Enrollment Applications related to the Program where Status Reason (statuscode) is:

Draft
Submitted
Under Review

For each record:

Set Status Reason (statuscode) = Inactive
Save the record

2. Retrieve all Enrollments related to the Program where Status Reason (statuscode) = Pending Activation

For each record:

Set Status Reason (statuscode) = Inactive
Save the record

### 24528 - Post-Approval Processing for Vendor Registration Request

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24528

Description:

When a Vendor Registration Request is set to Approved (statuscode), automatically perform the following:

1. Create a Vendor record.

Map fields from Vendor Registration Request to Vendor
Map fields:

Vendor Name
EIN
Legal Name (Doing Business As)
Classification
Individual/Sole Proprietor
Company Email Address
Website
Phone Number
Country
Street
City
State
Zip/Postal Code

2. Create a Primary Contact record.

Map fields from Vendor Registration Request to Vendor Contact
Map fields:
First Name
Last Name
Job Title
Email Address
Phone Number
Primary Contact = Yes

3. Update the Vendor.Primary Contact lookup with the created Contact record.

4. If Vendor Registration Request contains a value in Program, create a Program Enrollment Application record with:

Lookup to Program (from Vendor Registration Request)
Lookup to Vendor (newly created)

5. Create an Azure AD B2C account for the Primary Contact using their email address.

6. Send a Welcome Email to the Primary Contact email address including:

Portal link
Login credentials and setup instructions

6.1. Use the email template from the Notification Template table - VendorPortalWelcome

### 24761 - Send Enrollment Contract for Signature via DocuSign

State: New

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24761

Description:

Implement DocuSign integration for Enrollment contract signing.

The contract document is stored in:

Enrollment.av_contract

The signing process must support signatures from:

Vendor
Client

Button: Send for Signature

Place:

Enrollment Main Form / Enrollment grid / Enrollment sub-grid

Visibility:

Visible when:
statuscode = Pending Signature OR
statuscode = Sent for Signature and Signature Status = Declined / Error
av_contract is not blank

Action

When button is clicked:

Retrieve contract document from:
Enrollment.av_contract
Create DocuSign envelope
Add signees:
Vendor signee
Client signee
Send envelope for signature
Update Enrollment:
statuscode = Sent for Signature
Signature Status = Sent
Sent for Signature On = current date/time

DocuSign Status Synchronization

Implement callback/webhook or recurring synchronization process to update Enrollment based on DocuSign envelope status.

Logic: Vendor Signature

When Vendor signs:

Update:
Vendor Signature Status = Signed
Vendor Signed On = signature date/time

Logic: Client Signature

When Client signs:

Update:
Client Signature Status = Signed
Client Signed On = signature date/time

Logic: Fully Signed

When both:

Vendor Signature Status = Signed
Client Signature Status = Signed

Then:

Set:
Enrollment Signature Status = Signed
Enrollment statuscode = Active

Save fully executed signed document to:
Contract field (av_contract)

### 24705 - Set Program Milestone Name

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24705

Description:

Table: av_programmilestone

When a record is created or av_milestone is updated, set the av_programmilestone.av_name to av_milestone.

### 24499 - Update Program Active Stage Based on Milestone Date

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24499

Description:

Automatically update the Active Stage, Current Stage Start Date, and Next Stage Start Date on Program (av_program) when a defined Program Milestone date is reached.

Trigger: scheduled (daily)

1. Select Program Milestones where:

Milestone Date <= Today
Related Program (av_program) exists
Program.statuscode = Open

2. For each matching milestone:

Get:
Program (av_program)
Milestone (av_milestone)

a) Set Program.Active Stage (av_activestage) based on Milestone:

Example mapping:
Application Open Date -> Active Stage = Application Open
Screening Date -> Active Stage = Screening
b) Set Current Stage Start Date = Milestone Date

3. Retrieve the next upcoming milestone for the same Program where:
Milestone Date (the nearest one)> Current Milestone Date
4. a) If next milestone exists:
Set Next Stage Start Date = next milestone date
b) If current stage is the last stage:
Clear Next Stage Start Date

### 24746 - Update Program Enrollment Application Status Based on Program Requirement Assignments

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24746

Description:

Trigger
On Program Requirement Assignment statuscode update
On Program Requirement Assignment creation
1. Set Program Enrollment Application status to "Verifying"

When:

All related Program Requirement Assignments for the Program Enrollment Application
Have:
statuscode = Verifying

Then:

Update related Program Enrollment Application
Set:
statuscode = Verifying
2. Set Application Back to "Submitted"

When:

A new Program Requirement Assignment is created
OR
Existing Program Requirement Assignment statuscode changes to:
Assigned

Then:

Update related Program Enrollment Application
Set:
statuscode = Submitted
3. Set Application to Approved and Activate Enrollment

When all related Program Requirement Assignments for the Program Enrollment Application have:

statuscode = Approved

Then:

Update Program Enrollment Application:
statuscode = Approved
Update related Enrollment:
statuscode = Pending Signature
Payment Term = Program Enrollment Application.Payment Term

### 24424 - Vendor Enrollment Application Design

State: Completed

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24424

Description:

Design a Vendor Enrollment application flow for the Vendor Management System (VMS). The application will allow staffing vendors to register and enroll in government contracts managed by the MSP. This application is conceptually similar to the CAI ServiceNow vendor portal, where vendors can submit applications to participate in government staffing programs.

For the prototype, focus on designing the flow for:

Client:
DC OCFO

Design the following screens:

Vendor Enrollment Landing Page

Program Selection (DC OCFO)

Vendor Application Form

Payment Terms Selection

Document Upload

Submission Confirmation
