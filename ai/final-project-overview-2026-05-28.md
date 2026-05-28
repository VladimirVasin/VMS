# Final VMS Project Overview

Captured: 2026-05-28.

Sources:

- Azure DevOps Wiki: `VMS.wiki`, all 8 visible pages.
- Azure DevOps work items: 181 captured items from Recently updated plus visible Feature child lists (170 USER STORY, 10 FEATURE, 1 TASK).

## Executive Summary

VMS is an MSP-style Vendor Management System for managing Clients, Agencies, Programs, Vendors, Candidates/Resources, Enrollments, Job Positions/Requisitions, Engagements, Interviews, Compliance Requirements, Timesheets, Financials, Procurement/Solicitations, and Offboarding. The Wiki describes the intended business process backbone. The work items describe the implementation backlog and reveal several additions/refinements beyond the Wiki, especially DocuSign signature gating, Right to Represent automation, offboarding task automation, frontend portal/page work, and shared UI/auth cleanup.

## Canonical Domain Model

- Client owns Agencies and Programs.
- Programs define initiatives that Vendors can enroll into.
- Vendors have Vendor Contacts and Candidate/Resource contacts.
- Program Enrollment Applications and Enrollments connect Vendors to Programs.
- Job Positions/Requisitions define work demand under Programs/Agencies.
- Candidate/Resource contacts become Worker Profiles and are placed into Engagements.
- Engagements drive interviews, compliance/background/training requirements, timesheets, financial records, and offboarding.

## End-to-End Operating Flow

1. Program/client setup: Clients, Agencies, Programs, Program Milestones, Program Requirements, Program Questions, and certificate/requirement definitions are configured.
2. Vendor entry: Vendor can register directly or start from a Program application in the portal. If a Program was selected during registration, that selection is preserved until approval.
3. Vendor registration review: internal users approve or decline Vendor Registration Requests, capturing reviewer/date and decline reason/comments when needed.
4. Post-approval provisioning: approval creates Vendor, Primary Contact, B2C account, welcome email, and optionally a Draft Program Enrollment Application.
5. Enrollment application: vendor completes Program-specific application questions and submits the Program Enrollment Application.
6. Requirement assignment: submission creates Enrollment Requirement Assignments for Program requirements and creates/links Enrollment.
7. Requirement/certificate review: assignments and certificates move through Assigned/Verifying/Approved/Rejected style states; all-approved requirements approve the application.
8. Contracting/signature: work items refine the Wiki by adding Pending Signature and DocuSign before Enrollment becomes Active.
9. Active enrollment: active enrollments can expire automatically on End Date or be manually terminated. Closing a Program inactivates unfinished applications/pending enrollments.
10. Position-to-engagement: Programs/Agencies create Job Positions/Requisitions; candidate selection creates Engagements tied to Job Position, Vendor, Worker Profile, and Agency.
11. Interview scheduling: HR schedules interviews based on interviewer availability; candidates accept/reject/propose alternatives; history and rescheduling are tracked.
12. Compliance: background checks/trainings/certifications are reusable requirements, with evidence reuse and agency-specific review.
13. Timesheets/financials: resources submit timesheets; approval can be single-level or Program Manager final approval; approved timesheets feed invoice/payment flows.
14. Offboarding: engagement end, early termination, unqualification, client-directed removal, or reassignment creates offboarding and task assignments; completion requires all required tasks.

## Wiki vs Work Items Alignment

- Strong alignment: Wiki areas map directly to captured Feature/work item groups: Programs&Enrollment, Requisition Management, Job Application Management, Engagement Management, Interview Scheduling, Financials/Timesheets, Procurement, Performance Review, System Security/Admin, and Client & Contract Management.
- The Wiki is process-level and stable; work items are implementation-level and include frontend pages, buttons, status automations, integration hooks, and QA/cleanup tasks.
- Work items add concrete implementation detail that the Wiki omits: command-bar actions, modal requirements, Dataverse field mappings, notification templates, scheduled jobs, DocuSign state sync, Right to Represent, offboarding task assignment/status automation, invoice/timesheet linkage, and shared component/auth updates.

## Important Reconciliation Notes

- Vendor Registration Request status naming differs: Wiki says `Pending Review`, while work items use `Submitted` for approve/decline button visibility. Confirm real Dataverse option values.
- Enrollment activation differs: Wiki says approved application moves Enrollment from Pending Activation to Active. Work items add `Pending Signature` and DocuSign; treat DocuSign/Pending Signature as the newer implementation detail unless product owners say otherwise.
- Program Enrollment Application creation timing needs care: Wiki says Draft application can be created after vendor approval if Program was selected; work items also create Enrollment/Requirement Assignments when application is Submitted. These are separate lifecycle moments and should stay idempotent.
- Requirement assignment relationships need schema confirmation: Wiki says assignments link to Program Enrollment Application; work items also mention Enrollment/Vendor links. Rollups should define the exact relationship path.
- Program status naming differs between `Active`, `Open`, and `Closed` wording across stories. Confirm actual statuscode options before implementation/QA.
- Vendor Portal Wiki page is empty, while work items contain substantial portal/page work. Use work items and design links as source for portal behavior until Wiki is filled.

## Product Areas and Backlog Evidence

### Programs & Enrollment / Vendor Portal

Captured matching work items: 19.

  - 24773 New: Project, Program requirements and certifications sections with its actions
  - 24770 Completed: Add Verify / Reject Actions to Program Certificate
  - 24761 New: Send Enrollment Contract for Signature via DocuSign
  - 24746 Completed: Update Program Enrollment Application Status Based on Program Requirement Assignments
  - 24735 In Progress: Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional
  - 24733 New: Connect Vendor Enrollment Portal to Dataverse
  - 24706 In Progress: Program Application page add
  - 24668 Ready for QA: Vendor Registration Validation & Error Messages
  - 24591 Ready for QA: vendor enrollment registration form
  - 24590 Ready for QA: vendor enrollment home page
  - 24558 Completed: Auto-Populate Discount % on Enrollment
  - 24531 Completed: Add Terminate Action on Enrollment

### Requisition, Job Application, RtR, Candidate Flow

Captured matching work items: 36.

  - 24732 Ready for QA: Send RtR Request Email Notification to Candidate
  - 24731 Completed: Set Right to Represent Status to Expired
  - 24730 Completed: Create Right to Represent Record When Application Is Created
  - 24704 In Progress: Add Manually add candidate
  - 24682 Ready for QA: Job position certifications
  - 24681 Ready for QA: Job position comliance page add
  - 24680 In Progress: Job position Candidates submitted Application Details Tab
  - 24679 In Progress: Job positions Select Existing Candidate
  - 24677 New: Candidate Engagement History
  - 24676 New: Candidate documents
  - 24675 New: Candidate compliance
  - 24608 Ready for QA: Implement Job Application Approval & Engagement Creation

### Engagement & Offboarding

Captured matching work items: 18.

  - 24700 New: Pending Engagements Offboarding page
  - 24689 New: Active engagement worker profile
  - 24688 New: Active engagement list
  - 24687 In Progress: Pending engagements details add worker profile page
  - 24685 New: Pending engagements list
  - 24677 New: Candidate Engagement History
  - 24608 Ready for QA: Implement Job Application Approval & Engagement Creation
  - 24607 Completed: Update Offboarding Status Based on Tasks
  - 24606 Ready for QA: Manage Offboarding Task Assignment Status (Overdue Detection)
  - 24605 Completed: Generate Offboarding Task Assignments
  - 24604 Completed: Add Manual Offboarding (Terminate Engagement)
  - 24603 Completed: Auto-Create Offboarding on Engagement End

### Interview Scheduling

Captured matching work items: 17.

  - 24747 Completed: Automatically Set Interview Status to Completed
  - 24610 Ready for QA: Implement Interview Feedback Collection + COI Attestation & Daily Reminders
  - 24600 Ready for QA: Candidate interview page, update interview details screen
  - 24599 Ready for QA: Candidate interview page, add cancel and accept options
  - 24598 Ready for QA: Candidate interview page, update rescheduling form
  - 24577 Ready for QA: Close Job Application and Cancel Pending Interviews
  - 24550 New: Schedule Interview: Time slots configuration/generation
  - 24548 New: Schedule Interview History
  - 24543 Ready for QA: Implement AI Screening Question Generation on Interview
  - 24537 Ready for QA: Schedule Interview: Reschedule
  - 24536 Ready for QA: Schedule Interview Cancelation
  - 24535 In Progress: Schedule Interview: New

### Compliance, Background Checks, Trainings, Certifications

Captured matching work items: 7.

  - 24773 New: Project, Program requirements and certifications sections with its actions
  - 24682 Ready for QA: Job position certifications
  - 24675 New: Candidate compliance
  - 24398 Ready for QA: certifications - pending engagements
  - 23540 Ready for QA: Implement Compliance Check Requirement Automation
  - 23539 Ready for QA: Implement Training Requirement Automation Flow
  - 23484 Ready for QA: Generate Engagement-Related Compliance Check and Training Requirements

### Timesheets & Financials

Captured matching work items: 15.

  - 24697 Ready for QA: Fix PaymentCard styling
  - 24693 New: Payment details
  - 24692 New: Payments
  - 24691 In Progress: Timesheets list
  - 24602 Ready for QA: Update Timesheet Approval Process to Support Multi-Level Approval
  - 24545 Ready for QA: Update payments and projects entity to use baseQueryWithReauthAuth0
  - 24483 In Progress: update timesheets page to match figma
  - 24470 New: update Invoice page
  - 24465 New: Add/Remove Timesheets to/from Invoice (Manual Actions)
  - 24463 Ready for QA: Link Timesheets to Invoice on Status Change
  - 24462 Ready for QA: Generate Invoices from Closed Pay Period
  - 24453 Ready for QA: Invoices page have horizontal scroll Issue with InvoiceCard component

### Procurement / Solicitation

Captured matching work items: 3.

  - 24757 New: Generate Vendor Q&A Excel File on Solicitation
  - 24756 Ready for QA: Update Solicitation Active Stage Based on Milestone Date
  - 24386 Ready for QA: solicitation page add

### Security, Admin, Shared UI/Auth

Captured matching work items: 23.

  - 24769 New: Enforce Vendor Contact Role Permissions in Vendor Portal
  - 24735 In Progress: Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional
  - 24725 Ready for QA: Update shared buttons
  - 24708 Ready for QA: Remove avoid SecondaryButton replace everywhere with new OutlineButton
  - 24573 Ready for QA: add menu type buttons
  - 24568 Ready for QA: Deploy Document Templates Solution
  - 24554 Ready for QA: add global rule for box sixing according to storybook
  - 24545 Ready for QA: Update payments and projects entity to use baseQueryWithReauthAuth0
  - 24519 Ready for QA: update search and dropdown fields to latest version of storybook
  - 24518 Ready for QA: Add SuccessScreen reusable component from storybook into VMS project
  - 24503 New: update sidepanel component
  - 24487 Testing: Update usage of getDateFormat in every component in codebase

## Current Project State Snapshot

- New: 44
- Completed: 20
- In Progress: 14
- Ready for QA: 96
- Testing: 3
- Removed: 4

## Source Files

- `azure-wiki-vms-full-context-2026-05-28.md`: full readable Wiki capture.
- `azure-wiki-vms-pages-2026-05-28.json`: machine-readable Wiki capture.
- `azure-work-items-full-context-2026-05-28.md`: full readable work item capture.
- `azure-work-items-recently-updated-2026-05-28.json`: machine-readable work item capture.
- `programs-enrollment-process-overview.md`: deeper Programs&Enrollment process summary.
