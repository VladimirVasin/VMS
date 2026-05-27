# Azure DevOps Work Items Full Context

Captured: 2026-05-28.

Sources:

- https://dev.azure.com/AvidSys/VMS/_workitems/recentlyupdated/
- Feature child lists opened from all 10 captured Feature records

Scope: Captured 161 unique work item links exposed by the Azure DevOps Recently updated Work items hub after clearing filters, then opened all 10 Feature records and added 20 additional child work items that were visible in Feature child lists but missing from the recent hub crawl. Final capture: 181 work items.

Total captured: 181.

## 24773 - Project, Program requirements and certifications sections with its actions

Type: USER STORY

State: New

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24773

Updated: 4h ago by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5207-1763&t=NJ8VYuFjXunFyYOZ-4

### Related Work

Add an existing work item as a parent

## 24772 - Set up Client Contract Management module (re-utilize HCM Contracts module)

Type: USER STORY

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24772

Updated: Yesterday by Kristina Strashkulych

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24771 - Client & Contract Management

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24771

Updated: Yesterday by Kristina Strashkulych

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24770 - Add Verify / Reject Actions to Program Certificate

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24770

Updated: 11h ago by Vladimir Vasin

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24769 - Enforce Vendor Contact Role Permissions in Vendor Portal

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24769

Updated: Yesterday by Kristina Strashkulych

### Description

Implement front-end role-based action enforcement in the Vendor Portal based on the Vendor Contact role selected during Vendor Contact creation/management.

Important! A single Vendor Contact may be assigned multiple roles if additional access or responsibilities are required.
Roles
1. Administrator

Full access to all Vendor Portal actions.

Can perform:

Manage Vendor profile/company details
Manage Vendor Contacts and roles
Apply to Programs
Submit/manage Applications
Submit Candidates
Submit Solicitation Responses
Manage Projects
Access to onboarding/offboarding activities
Access to Timesheet and Billing (Invoices, Payments)
2. Staffing

Operational recruiting role.

Can perform:

Create/manage Candidate profiles
Submit Candidates to Job Positions
Submit Solicitation Responses
Manage Projects
Update candidate/application data
Coordinate interviews and onboarding/offboarding activities

Should NOT be able to:

Manage Vendor profile/settings
Manage Vendor Contacts
Manage Bank Details
View Timesheets
View/submit invoices
View Payments
Apply to Programs
3. Timesheet Manager

Timesheet operations role.

Can perform:

Review Timesheets
Monitor submission statuses

Should NOT be able to:

Manage Vendor profile/settings
Manage Vendor Contacts
Manage Bank Details
View/submit invoices
View payments
Apply to Programs
Manage Candidate profiles
Submit Candidates
Submit Solicitation Responses
Manage Projects
 *read-only access to all pages
4. Billing Manager

Financial operations role.

Can perform:

Create/submit invoices
Review Payments
Review Timesheets
Monitor submission statuses

Should NOT be able to:

Manage Vendor profile/settings
Manage Vendor Contacts
Manage Bank Details
Apply to Programs
Manage Candidate profiles
Submit Candidates
Submit Solicitation Responses
Manage Projects
*read-only access to all pages accept for the Invoices

### Related Work

Add an existing work item as a parent

## 24762 - Projects Milestones

Type: USER STORY

State: In Progress

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24762

Updated: 4h ago by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=7320-38129&m=dev

### Related Work

Add an existing work item as a parent

## 24761 - Send Enrollment Contract for Signature via DocuSign

Type: USER STORY

State: New

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24761

Updated: пятница by Kristina Strashkulych

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24757 - Generate Vendor Q&A Excel File on Solicitation

Type: USER STORY

State: New

Assigned To: Iryna Hrytsai

Parent: 24407 - Procurement

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24757

Updated: 14m ago by Raman Mukha

### Description

Implement functionality to manually generate an Excel file containing all Opportunity Questions and Answers related to a Solicitation.

Button: Generate Vendor Q&A

Place:

Solicitation Main Form

Action

When button is clicked:

Retrieve all related Opportunity Questions for the Solicitation
Generate Excel file with the following columns:
Column	Definition
#	Sequential number
Question	av_opportunityquestion.av_question
Answer	av_opportunityquestion.av_answer
Sorting
Sort by Created On ascending
File Requirements
Generate .xlsx file
File name format:

Solicitation_<SolicitationID>_Vendor_QA.xlsx

Document Storage

Automatically create related record in:

Solicitation Document

Populate:

Solicitation
Document Type = Vendor Q&A (485580004)
File / Attachment
Name

### Comments

Raman Mukha
commented 14m ago
@Iryna Hrytsai Empty Excel when you download it from Solicitation Documents

### Related Work

Parent
24407
Procurement
Updated 1 мая
New

## 24756 - Update Solicitation Active Stage Based on Milestone Date

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24407 - Procurement

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24756

Updated: четверг by Iryna Hrytsai

### Description

Automatically update the Active Stage on Solicitation (av_solicitation) when a defined Solicitation Milestone date is reached.

Trigger: scheduled (daily)

 1. Select Solicitation Milestones where:

Date ≤ Today
Related Solicitation (av_solicitation) exists
Solicitation.statuscode = Published

 2. Set Solicitation.Active Stage (av_activestage) based on Solicitation Milestone

### Related Work

Parent
24407
Procurement
Updated 1 мая
New

## 24752 - update ProgramMilestonesCard

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24752

Updated: 20 мая by Alexander Lisetskii

### Description

make a component shared and add to the solicitation page

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=7093-19808&m=dev

add to projects page and solicitations page

### Related Work

Add an existing work item as a parent

## 24747 - Automatically Set Interview Status to Completed

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24747

Updated: 25m ago by Raman Mukha

### Description

Trigger
Recurring scheduled process (recommended: every 3 hours)
Logic

Find Interview records where:

statuscode = Scheduled
Scheduled End < Current Date/Time

For each matching Interview:

Update:
statuscode = Completed

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24746 - Update Program Enrollment Application Status Based on Program Requirement Assignments

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24746

Updated: 6h ago by Vladimir Vasin

### Description

Trigger
On Program Requirement Assignment statuscode update
On Program Requirement Assignment creation
1. Set Program Enrollment Application status to “Verifying”

When:

All related Program Requirement Assignments for the Program Enrollment Application
Have:
statuscode = Verifying

Then:

Update related Program Enrollment Application
Set:
statuscode = Verifying
2. Set Application Back to “Submitted”

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24735 - Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional

Type: USER STORY

State: In Progress

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24735

Updated: понедельник by Raphael Serobiani

### Main Flow

Blocked by https://dev.azure.com/AvidSys/VMS/_boards/board/t/VMS%20Team/Stories?workitem=24734

### Related Work

Add an existing work item as a parent

## 24734 - Create new page View Requirements by the desing

Type: USER STORY

State: New

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24734

Updated: понедельник by Raphael Serobiani

_No rich text description captured._

### Comments

Ognjen Pandurevic
commented 14 мая

### Related Work

Add an existing work item as a parent

## 24733 - Connect Vendor Enrollment Portal to Dataverse

Type: USER STORY

State: New

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24733

Updated: понедельник by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24732 - Send RtR Request Email Notification to Candidate

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24732

Updated: 15 мая by Iryna Hrytsai

### Description

When RtR is created with Status = Pending, send email notification to the Candidate with actions to approve or decline the Right to Represent request.

Use Notification Template Right to Represent Request.

Candidate should be able to:

Approve RtR
Decline RtR
Review request details in Candidate Portal

If Candidate approves:

RtR Status = Approved
Related Application RtR Status = Approved

If Candidate declines:

RtR Status = Declined
Related Application RtR Status = Declined

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24731 - Set Right to Represent Status to Expired

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24731

Updated: 26m ago by Raman Mukha

### Description

Implement scheduled process to update RtR records to Expired.

Logic:

Find RtR records where:
statuscode = Pending
Expires On < current date/time

For each matching RtR:

Set RtR Status = Expired
Update related Application:
RtR Status = Expired

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24730 - Create Right to Represent Record When Application Is Created

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24730

Updated: 26m ago by Raman Mukha

### Description

When Application (av_application) is created, automatically create a related Right to Represent (RtR) record.

Populate RtR with:

Application
Candidate
Vendor
Job Position
Status = Pending
Name = [Candidate Full Name] - [Application ID]
Requested On = current date/time
RtR Statement / Consent Text copied from Program SLA Configuration record (av_slaconfiguration.av_program eq current av_requisition.av_program via av_application.av_requisition lookup)
Expires On = calculated based on configured validity period (av_slaconfiguration.av_rtrconsentsladays)

Update Application:

Right to Represent lookup = created RtR record

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24727 - Vendor enrollent update

Type: USER STORY

State: In Progress

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24727

Updated: 14 мая by Ognjen Pandurevic

### Description

Integration
Connect portal to Dataverse API
Programs Page
Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional
Registration Form Updates

a. Move 'Individual/Sole Proprietor' checkbox next to 'Company Name'

If set to Yes:
Hide 'EIN'
Show 'SSN' field instead
'SSN' should be required

b. Remove arrows/icons from dropdown and lookup columns

c. Country-based logic:

If 'Country' eq US → show 'State' lookup column
If 'Country' ne US → show 'Province' text column

### Related Work

Add an existing work item as a parent

## 24725 - Update shared buttons

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24725

Updated: 11h ago by Raphael Serobiani

### Description

currently disabled prop makes buttons invisible ( primary,outlined,transparent)

update styles for disabled buttons
add width prop since default width is 100% and will be often changed

add disabled styles for menu button

### Related Work

Add an existing work item as a parent

## 24709 - Submit to application

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24709

Updated: понедельник by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=890-56638&m=dev

### Related Work

Add an existing work item as a parent

## 24708 - Remove avoid SecondaryButton replace everywhere with new OutlineButton

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24708

Updated: 8 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24707 - Remove word "Pages" from breadcrums

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24707

Updated: 8 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24706 - Program Application page add

Type: USER STORY

State: In Progress

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24706

Updated: понедельник by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5238-10146&m=dev

### Related Work

Add an existing work item as a parent

## 24705 - Set Program Milestone Name

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24705

Updated: 8h ago by Vladimir Vasin

### Description

Table: av_programmilestone

When a record is created or av_milestone is updated, set the av_programmilestone.av_name to av_milestone.

### Related Work

Add an existing work item as a parent

## 24704 - Add Manually add candidate

Type: USER STORY

State: In Progress

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24704

Updated: 12 мая by Ucha Minadze

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-32160&m=dev

add page with panels

UPDATE:
https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-29490&m=dev

### Related Work

Add an existing work item as a parent

## 24700 - Pending Engagements Offboarding page

Type: USER STORY

State: New

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24700

Updated: 11 мая by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=6080-334&m=dev

### Related Work

Add an existing work item as a parent

## 24699 - Update Applications filters

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24699

Updated: 6 мая by Alexander Lisetskii

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24698 - Fix ApplicationsCard styling

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24698

Updated: 5 мая by Raphael Serobiani

### Description

Also Fonts, View Details button

### Related Work

Add an existing work item as a parent

## 24697 - Fix PaymentCard styling

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24697

Updated: 5 мая by Raphael Serobiani

### Description

Also Fonts, View Details button

### Related Work

Add an existing work item as a parent

## 24696 - Fix ProjectCard styling

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24696

Updated: 5 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24695 - add program listing page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24695

Updated: 7 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24693 - Payment details

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24693

Updated: 6 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=892-77740&m=dev

fix values not being displayd in table

### Related Work

Add an existing work item as a parent

## 24692 - Payments

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24692

Updated: 6 мая by Alexander Lisetskii

### Description

update values for the cards

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2910-37755&m=dev

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5478-5455&m=dev

### Related Work

Add an existing work item as a parent

## 24691 - Timesheets list

Type: USER STORY

State: In Progress

Assigned To: Arsenii Goriushkin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24691

Updated: 14 мая by Arsenii Goriushkin

### Description

fix rate display

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=1399-2364&m=dev

### Related Work

Add an existing work item as a parent

## 24690 - Timsheets by resource

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24690

Updated: 8 мая by Ucha Minadze

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=892-74047&m=dev

fix layout - button and horizontal scroll
fix filters not working

### Related Work

Add an existing work item as a parent

## 24689 - Active engagement worker profile

Type: USER STORY

State: New

Assigned To: Ognjen Pandurevic

Parent: 24687 - Pending engagements details add worker profile page

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24689

Updated: 20 мая by Alexander Lisetskii

### Description

add worker profile page

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5707-11608&m=dev

same as
https://dev.azure.com/AvidSys/VMS/_workitems/edit/24687

### Related Work

Parent
24687
Pending engagements details add worker profile page
Updated 8 мая
In Progress
Related
24687
Pending engagements details add worker profile page
Updated 8 мая
In Progress

## 24688 - Active engagement list

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24688

Updated: понедельник by Arsenii Goriushkin

### Description

add button to download selected engagements ( export to xlsx)
https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=891-67950&m=dev

### Related Work

Add an existing work item as a parent

## 24687 - Pending engagements details add worker profile page

Type: USER STORY

State: In Progress

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24687

Updated: 8 мая by Ognjen Pandurevic

### Description

add worker profile page

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4686-4733&m=dev

### Related Work

Add an existing work item as a parent
Child
24689
Active engagement worker profile
Updated 20 мая
New
Related
24689
Active engagement worker profile
Updated 20 мая
New

## 24685 - Pending engagements list

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24685

Updated: понедельник by Arsenii Goriushkin

### Description

update fields

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=891-64933&m=dev

### Related Work

Add an existing work item as a parent

## 24684 - Project details page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24684

Updated: 8 мая by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2966-46865&m=dev

update layout, add expenses block with request expense and view details panels

### Related Work

Add an existing work item as a parent

## 24683 - Applications page

Type: USER STORY

State: In Progress

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24683

Updated: 11h ago by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=891-63366&m=dev

update api after Raphels pr regarding applications history

### Related Work

Add an existing work item as a parent

## 24682 - Job position certifications

Type: USER STORY

State: Ready for QA

Assigned To: Oleksii Ovsiannikov

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24682

Updated: Yesterday by Oleksii Ovsiannikov

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-35205&m=dev

update layout add menu button

### Related Work

Add an existing work item as a parent

## 24681 - Job position comliance page add

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24681

Updated: 8 мая by Ucha Minadze

### Description

background checks for given position

reuse background checks list just provide different request

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-34991&m=dev

### Related Work

Add an existing work item as a parent

## 24680 - Job position Candidates submitted Application Details Tab

Type: USER STORY

State: In Progress

Assigned To: Oleksii Ovsiannikov

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24680

Updated: 19 мая by Oleksii Ovsiannikov

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-33840&m=dev

add missing blocks ( same as in candidate overview page)

### Related Work

Add an existing work item as a parent

## 24679 - Job positions Select Existing Candidate

Type: USER STORY

State: In Progress

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24679

Updated: 12 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2127-2570&m=dev

update cards layout

### Related Work

Add an existing work item as a parent

## 24678 - Updates shared card contents

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24678

Updated: 4 мая by Alexander Lisetskii

### Description

longer labels should be wrapped in multiple lines

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-8474&m=dev

### Related Work

Add an existing work item as a parent

## 24677 - Candidate Engagement History

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24677

Updated: 12 мая by Alexander Lisetskii

### Description

add view details panel

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-31244&m=dev

### Related Work

Add an existing work item as a parent

## 24676 - Candidate documents

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24676

Updated: 6 мая by Alexander Lisetskii

### Description

add menu button and api calls

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-30541&m=dev

### Related Work

Add an existing work item as a parent

## 24675 - Candidate compliance

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24675

Updated: 12 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4591-13485&m=dev

sort by engagements

show history panel

add status coloring

### Related Work

Add an existing work item as a parent

## 24668 - Vendor Registration Validation & Error Messages

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24668

Updated: 8 мая by Ognjen Pandurevic

### Description

I. If the user wants to proceed without filling in the required information, each column missing the value should be highlighted with the message:

Company Name
“Company Name is required.”
EIN
“Employer Identification Number (EIN) is required.”
Classification
“Please select a Company Classification.”
Company Phone
“Company Phone Number is required.”
Company Email
“Company Email Address is required.”
Country
“Country is required.”
State/Province
“State/Province is required.”
Address
“Street Address is required.”
City
“City is required.”
Primary Contact – First Name
“First Name is required.”
Primary Contact – Last Name
“Last Name is required.”
Primary Contact – Phone
“Phone Number is required.”
Primary Contact – Email
“Email Address is required.”
Confirm Email
“Please confirm your Email Address.”

 II. Format & Pattern Validations

Email
“Enter a valid email address (e.g., name@company.com).”
“Email and Confirm Email must match.”
“Personal email domains (e.g., Gmail, Yahoo) are not allowed for Company Email.”
Phone Number
“Enter a valid phone number (e.g., (202) 456-1234 or +1 202-456-1234).”
EIN (Critical)
“Enter a valid EIN in the format XX-XXXXXXX.”
“EIN must contain 9 digits.”
Website
“Enter a valid URL (e.g., https://www.company.com).”
ZIP Code
“Enter a valid ZIP/Postal Code.”
(Optional US-specific)
“ZIP Code must be 5 digits or ZIP+4 format.”

 III. Business Rules

If Individual / Sole Proprietor = checked:

“EIN is not required for Individual/Sole Proprietors.” (or switch to SSN logic if applicable)
“Company Name must match legal individual name.”

### Related Work

Add an existing work item as a parent

## 24621 - Set Review Schedule to Overdue (Recurring)

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24621

Updated: 14 мая by Marharyta Khovanova

### Description

Scheduled process (daily):

For each Review Schedule:

If:
Review Date < Today
Status ≠ Completed

→ Set Status = Overdue

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24620 - Handle Review Date Changes

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24620

Updated: 14 мая by Marharyta Khovanova

### Description

When Checkpoint Review Date is updated:

Retrieve related Review Forms:
Completed
Not Completed
Update statuses:
Completed → remain Completed
Not completed:
If past due → Overdue
If upcoming → In Progress

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24619 - Update Review Schedule Status

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24619

Updated: 14 мая by Marharyta Khovanova

### Description

Automatically update Review Schedule status based on:
Related Review Form statuses

Examples:

All completed → Completed
Some completed → In Progress

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24618 - Create Goal Feedback from Review Form

Type: USER STORY

State: Testing

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24618

Updated: Yesterday by Vladimir Vasin

### Description

On Review Form submission:

Create Goal Feedback records
Link:
Goal
Review Form
Reviewer

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24617 - Review Form Notifications

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24617

Updated: понедельник by Marharyta Khovanova

### Description

Send notifications:
When Review Form is created
Reminder notifications before due date
Overdue reminders
Reuse existing flows where possible

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24616 - Evaluate Plan on Review Completion

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24616

Updated: 14 мая by Marharyta Khovanova

### Description

When Review Form = Completed:
Trigger evaluation logic
Reuse existing AI model / scoring logic
Update:
Goal performance
Overall Plan status / score

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24615 - Generate Checkpoints

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24615

Updated: 14 мая by Marharyta Khovanova

### Description

Create Checkpoints based on:
Number provided in configuration
Link:
Checkpoints to Review Schedule
Checkpoints to Goals

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24614 - Generate Goals (AI-based)

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24614

Updated: 13 мая by Iryna Hrytsai

### Description

Implement AI-driven goal generation
Inputs:
Selected Categories
Required number of goals
Default prompt
Output:
Structured Goal records linked to Plan / Review Schedule
Adjustment:
each goal can be re-generated separately by providing the individual prompt
Refer to the 'Interview Question Generation' (page) process Viacheslav built for VMS.

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24613 - Generate Review Forms & Questions

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24611 - Performance Review

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24613

Updated: 12 мая by Alexander Lisetskii

### Description

Convert Review Forms & Questions to Web Resource
Replace existing Page-based Review Form UI with Web Resource
Ensure:
Review Form is generated per:
Reviewer
Checkpoint
Questions are generated per:
Goal

### Related Work

Parent
24611
Performance Review
Updated 1 мая
New

## 24611 - Performance Review

Type: FEATURE

State: New

Assigned To: Marharyta Khovanova

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24611

Updated: 1 мая by Marharyta Khovanova

### Description

@Marharyta Khovanova

The related child user stories are for migration / setup / minor adjustments of the Performance Review module from an existing solution. No need for full rebuild, reuse flows, AI components, and logic where applicable. Canvas pages should be replaced with Web Resources.

HCM solution to refer to:
https://make.powerapps.com/environments/d5fa4c4e-427a-4535-9584-e10f44d6f174/solutions/a770c0b8-39e3-ef11-8eea-6045bd039f3f/objects/all

### Related Work

Add an existing work item as a parent
Child
24618
Create Goal Feedback from Review Form
Updated Yesterday
Testing
24616
Evaluate Plan on Review Completion
Updated 14 мая
Ready for QA
24620
Handle Review Date Changes
Updated 14 мая
Ready for QA
24617
Review Form Notifications
Updated понедельник
Ready for QA
24621
Set Review Schedule to Overdue (Recurring)
Updated 14 мая
Ready for QA
24619
Update Review Schedule Status
Updated 14 мая
Ready for QA
Show more
(6 of 9)
Not shown: Child (3)

## 24610 - Implement Interview Feedback Collection + COI Attestation & Daily Reminders

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24610

Updated: 12 мая by Alexander Lisetskii

### Description

Enable automated collection of Interview Feedback from all Interviewers via Microsoft Teams message with actionable inputs.
Trigger
When Interview Status = Completed
Action: Send Teams Message

Send a Teams message (Adaptive Card) to all users in:

Interview – User (av_interviewers) N:N relationship
Message Content

Include the following details:

Job Position ID (av_requisition.av_name)
Job Position Title
Application ID (av_application.av_name)
Vendor
Candidate Name
Interview Type
Interview Date & Time
Inputs (Adaptive Card)

Include:

Vote (required)
Yes
No
Feedback (Multiline text input, required or optional based on config)
Conflict of Interest Attestation (required)
Checkbox (required):

☐ I confirm that I have no conflict of interest or personal relationship with this candidate that could influence my evaluation.

Disclosure Details (conditional):

If you have a conflict of interest or personal relationship, please disclose details below:

Multiline text input
Required only if checkbox is NOT selected

Submit button

When user submits:

Create Interview Feedback record

Populate:

Interview (lookup)
Interviewer (User)
Vote (Yes/No)
Feedback (Text)
Submitted On (DateTime)
Validation
Prevent duplicate submissions:
One feedback per Interviewer per Interview
If already submitted:
Disable or replace card with “Feedback already submitted”
Daily Reminder Logic
Scheduled Process
Run daily

For each Interview where:

Status = Completed

For each Interviewer:

If no Interview Feedback record exists:

→ Resend Adaptive Card

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24609 - TBD Application Qualification/Disqualification Process

Type: USER STORY

State: New

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24609

Updated: 12 мая by Alexander Lisetskii

_No rich text description captured._

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24608 - Implement Job Application Approval & Engagement Creation

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24608

Updated: 13 мая by Iryna Hrytsai

### Description

Button: Approve Application

Place:

Application Main Form
Application Grid (command bar)

Visibility:

Status Reason (statuscode) = Submitted or Qualified
Current user has permission to approve (System Administrator, MSP Program Manager, Client Program Manager, Client Hiring Manager)

Action (on click)
Show blocking confirmation modal. Only one checkbox can be selected; if the second one is checked, disclosure details are required; do not allow to proceed until anything is selected:

Conflict of Interest Confirmation

Before approving this candidate, please confirm:

Do you have any conflict of interest or personal relationship with this candidate that could affect your decision?

(checkbox ) I confirm that I have no conflict of interest or personal relationship with this candidate

( checkbox) I disclose that I have a conflict of interest or personal relationship (please provide details below)

Details (required if disclosed):

[Text input]

[Confirm & Continue] [Cancel]

Action (on confirm)
Update Application
Set Status Reason (statuscode) = Approved
Set Application Stage (av_applicationstage) = Approval Notification
Set Closure Reason (av_closurereason) = Hired (Engagement Created)
Populate:
Closed By (current user)
Closed On (current date)
Create Engagement Record

Populate fields:

Contact ← from Application
Vendor ← from Application
Agency ← from Job Position
Approver ← from Job Position.Contract Manager
Compliance Check Set ← from Job Position
Training Set ← from Job Position
Program ← from Job Position
Job Position ← from Application
Job Position Title ← from Job Position
Start Date ← from Job Position.Position Open Date
End Date ← from Job Position.Position Close Date
Rate ← from Application.Offered Rate
Days per Week ← from Job Position
Employment Type  ← from Job Position
Hours/Units per Day ← from Job Position
Work Arrangement ← from Job Position
Work Location ← from Job Position
If No Conflict
COI Status = Confirmed – No Conflict
If Disclosed
COI Status = Disclosed
COI Disclosure Details

    3. Create Worker Profile Record
set Engagement lookup to recently created Engagement
set Contact to Engagement.Contact
update Engagement.Worker Profile lookup
set name to [Contact.Full Name] - [Engagement Id (av_name)]

### Comments

Kristina Strashkulych
commented 13 мая
@Iryna Hrytsai When a Worker Profile is created, set av_name to [Contact.Full Name] - [Engagement Id (av_name)]

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24607 - Update Offboarding Status Based on Tasks

Type: USER STORY

State: Completed

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24607

Updated: 26m ago by Raman Mukha

### Description

Implement logic (plugin or flow) triggered on Offboarding Task Assignment updates:

 1) Set Offboarding = In Progress
If at least one Offboarding Task Assignment:
Status = Completed
 2) Set Offboarding = Overdue
If any Offboarding Task Assignment:
Status = Overdue
 3) Set Offboarding = Completed
If all Required (Offboarding Task.Is Required = 'Yes') Offboarding Task Assignments:
Status = Completed
Offboarding.Completed On = current date

### Related Work

Add an existing work item as a parent

## 24606 - Manage Offboarding Task Assignment Status (Overdue Detection)

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24606

Updated: 24 апр. by Evgeniy Malyutin

### Description

Implement scheduled process:

Run daily

Logic:

For all Offboarding Task Assignments where:
Status does not equal Completed
Current Date > Due Date

→ Update:

Status = Overdue

Ensure:

Do not overwrite Completed tasks

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 24605 - Generate Offboarding Task Assignments

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24605

Updated: 26m ago by Raman Mukha

### Description

When Offboarding is created:

Retrieve all Offboarding Tasks where:
Client = av_agency.av_client via av_engagement.av_client lookup
statecode eq Active

For each task:

Create Offboarding Task Assignment (OTA)
Populate:
Offboarding
Offboarding Task
Assigned To
If Offboarding Task.Assignee = Resource:
Set Assigned To = Resource (Contact) from Engagement

If Offboarding Task.Assignee = Program Manager:
Retrieve Program Manager from:
Engagement → Job Position → Program Manager
Set Assigned To = Program Manager (User)

### Comments

Kristina Strashkulych
commented 27 апр.
@Iryna Hrytsai Updated Engagement.Client reference definition.

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 24604 - Add Manual Offboarding (Terminate Engagement)

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24604

Updated: 26m ago by Raman Mukha

### Description

Add “Terminate Engagement” button on Engagement form.

Visibility:

When Engagement is Active (statuscode = Active)

On click:

Open modal:
Reason for Termination (required)
Offboarding Type (required)

Comments (optional)

On confirm:

Create Offboarding record (same logic as auto)
Set:
Offboarding.Type = selected Offboarding Type
Update Engagement statuscode to Terminated
Set:
Engagement.Reason for Termination
Termination Comments
Terminated On

Ensure:

Prevent multiple active Offboarding records per Engagement

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 24603 - Auto-Create Offboarding on Engagement End

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24603

Updated: 26m ago by Raman Mukha

### Description

Trigger:

When Engagement End Date ≤ current date
(scheduled job)

On trigger:

Create Offboarding record
Populate:
Engagement
Resource
Type = Planned End

Ensure:

Do not create duplicate Offboarding records for the same Engagement

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 24602 - Update Timesheet Approval Process to Support Multi-Level Approval

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24602

Updated: 27 апр. by Iryna Hrytsai

### Description

Enhance the existing Timesheet approval logic to support two-level approval (Engagement Approver → Program Manager) and adjust current functionality accordingly.

Previous task: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23541
Business logic description: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/270/Timesheet-Approval-Process

Turn OFF / Update Existing Logic
Remove ability for Program Manager / Client Approver / System Administrator to approve/reject Timesheets when:
Status = Submitted
(This should be handled only by Engagement Approver)
Update existing Approve action:
Do NOT always set Status = Approved
Update Reviewed By (Program Admin) field:
Replace with generic Reviewed By (User)
Update Approve Action

When user clicks Approve:

If Engagement.Multi-level Approval Required = No:
Set Status = Approved
If Yes:
Set Status = Pending Program Approval
Assign to Program Manager
Update Visibility Rules
Level 1 (Engagement Approver)

Approve / Reject visible when:

Status = Submitted
Engagement.Approver = current user
Level 2 (Program Manager)

Approve / Reject visible when:

Status = Pending Program Approval
Current user = Program Manager
Update Reject Action
Allow Reject when:
Status = Submitted OR Pending Program Approval
Keep existing behavior:
Prompt for Rejection Reason
Set Status = Rejected
Populate Reviewed By / Reviewed On
Weekly Notifications

Create scheduled flow:

Trigger: Weekly (Monday)
For Engagement Approvers:
Send list of Timesheets:
Status = Submitted
For Program Managers:
Send list of Timesheets:
Status = Pending Program Approval

Include:

Engagement
Resource
Timesheet period
Manual Override
Keep existing functionality
Allow when Status =:
Approved, Rejected, (optionally Pending Program Approval)
No change to logic

### Related Work

Add an existing work item as a parent
Related
23541
Timesheets Approval flow and buttons
Updated 22 апр.
Removed

## 24601 - update company contacts page

Type: USER STORY

State: Ready for QA

Assigned To: Oleksii Ovsiannikov

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24601

Updated: 8 мая by Oleksii Ovsiannikov

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-28233&m=dev

### Related Work

Add an existing work item as a parent

## 24600 - Candidate interview page, update interview details screen

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24600

Updated: 5 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24599 - Candidate interview page, add cancel and accept options

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24599

Updated: 5 мая by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24598 - Candidate interview page, update rescheduling form

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24598

Updated: 5 мая by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5952-388&t=kY4eddd5TzUtzpyZ-4

### Related Work

Add an existing work item as a parent

## 24592 - open positions - recommendations

Type: USER STORY

State: In Progress

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24592

Updated: 6 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2126-2092&m=dev

add a button that will access Viacheslav's endpoint ad provide recommended list of candidates for a given position

### Related Work

Add an existing work item as a parent

## 24591 - vendor enrollment registration form

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24591

Updated: 8 мая by Ognjen Pandurevic

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4780-362&m=dev

### Related Work

Add an existing work item as a parent

## 24590 - vendor enrollment home page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24590

Updated: 28 апр. by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4820-4370&m=dev

### Related Work

Add an existing work item as a parent

## 24588 - Implement Application AI Evaluation

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24588

Updated: 6 мая by Iryna Hrytsai

### Description

Implement AI-based screening for Application (av_application) to evaluate and score candidates based on multiple data sources.

Trigger:

automatically on Application submission (statuscode eq Submitted)
Inputs for Analysis

AI should analyze the following:

Application Question Responses
Application fields (av_application):
Can the candidate start immediately if selected?
Candidate agrees to the Background Check process?
Candidate agrees to submit NDA?
Earliest Available Start Date
Was Candidate ever contracted by Client?
If yes, specify the Employment Type
If yes, when did the last employment end?

If yes, why did the employment end?

If yes, details previous contract/employment at client:

Resume
Candidate (contact) responses to questions:
Permanent Residency Status
Legally Authorized to Work in the US
Has a valid government-issued ID
Comparing to the information on the Job Position:
Job Description
Responsibilities
Requirements
Preferred Qualifications
Required Skills (related)
Employment Type
Requires NDA
Processing

Send collected data to AI service to:

Calculate Overall Score
Range: 0–100
Based on relevance, completeness, and fit
Calculate Relative Score
Compare current Application against other Applications for the same Program
Output normalized/relative ranking
Generate AI Summary
Include structured analysis such as:
Fit Assessment (skills, experience, alignment)
General Compliance (requirements, completeness)
Strengths
Risks / Gaps
Recommendation
Outputs (Fields on Application)

Populate:

AI Score (0–100)
Relative Score (0-100)
AI Summary

### Comments

Kristina Strashkulych
commented 28 апр.
@Iryna Hrytsai Please, work together with @Marharyta Khovanova

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24585 - update shared cards responsive design

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24585

Updated: 4 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5023-867&m=dev

### Related Work

Add an existing work item as a parent

## 24578 - Close Job Position and Cascade Application Closure

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24578

Updated: 27 апр. by Iryna Hrytsai

### Description

Enable users to close a Job Position (av_requisition) via a structured action, capturing closure details and informing users about the impact on related Job Applications before confirming.

Add a button “Close Position” on the Job Position (av_requisition) Main Form. The action should be available when the position is not already Closed or Cancelled.

Closure Dialog
When triggered, display a modal dialog requiring:

Status (statuscode) — selectable values limited to:
Closed
Cancelled
Closure Reason (required)
Closure Comments (optional)

Within the same dialog, retrieve and display the number of related Job Applications:

Show total number of Open Applications where statuscode = New or In Progress statuscode = Draft, Submitted, Qualified
Present a message indicating impact:
If Closed selected → Related Applications will be closed with reason: “Position Filled (another candidate(s) selected)”
If Cancelled selected → Related Applications will be closed with reason: “Position Cancelled”

Prompt the user to Confirm or Cancel the action.

Job Position Update
On confirmation, update av_requisition:

statuscode = selected value (Closed or Cancelled)
av_closurereason = selected value
av_closurecomments = entered value
av_closedon = current date/time
av_closedby = current user

Application Handling
Retrieve all related Job Applications (av_application) and update those with statuscode = New or In Progress statuscode = Draft, Submitted, Qualified:

If Job Position = Closed → set:
statuscode = Rejected
av_closurereason = Position Filled (another candidate(s) selected)
If Job Position = Cancelled → set:
statuscode = Rejected
av_closurereason = Position Cancelled
Set Application Stage (av_applicationstage) = Approval Notification

### Comments

Kristina Strashkulych
commented 27 апр.
@Iryna Hrytsai Added:
Set Application Stage (av_applicationstage) = Approval Notification

Kristina Strashkulych
commented 21 апр.
@Iryna Hrytsai Updated Open Application statuses.

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 24577 - Close Job Application and Cancel Pending Interviews

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 23474 - Job Application Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24577

Updated: 27 апр. by Iryna Hrytsai

### Description

Table: Application (av_application)
Main Form, Grid, sub-grid (record(s) selected)
Add Close Application button
Visible when av_application.statuscode eq New or In Progress Qualified
When clicked, display a modal window prompting to select Closure Reason (required)

Job Application Update
On confirmation, update av_application:

If Closure Reason = Hired → set statuscode = Approved
If any other Closure Reason → set statuscode = Rejected
av_closurereason = selected value
av_closedon = current date/time
av_closedby = current user
Set Application Stage (av_applicationstage) = Rejection Notification

Retrieve all Interview records related to the Job Application and update only those where statuscode is:

Draft
Pending Confirmation
Scheduled

Set their statuscode to Cancelled.

### Comments

Kristina Strashkulych
commented 27 апр.
@Iryna Hrytsai Added:
Set Application Stage (av_applicationstage) = Approval Notification

Kristina Strashkulych
commented 21 апр.
@Iryna Hrytsai Updated button visibility rule.

### Related Work

Parent
23474
Job Application Management
Updated 1 мая
New

## 24573 - add menu type buttons

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24573

Updated: 22 апр. by Raphael Serobiani

### Description

add shared menu button from storybook

update components using it

### Related Work

Add an existing work item as a parent

## 24568 - Deploy Document Templates Solution

Type: USER STORY

State: Ready for QA

Assigned To: Stanislau Viaroukin

Parent: 24467 - System Security&General Administration

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24568

Updated: 30 апр. by Stanislau Viaroukin

### Description

Implement functionality to generate documents based on configurable Document Templates with dynamic placeholder replacement.

Behavior:

Store document templates in the system (dedicated Document Template table)
Allow templates to include placeholders using syntax:
{{entity.column}}
{{entity.lookup.column}}
@Stanislau Viaroukin Add more if applicable

On document generation:

Select template
Replace all placeholders with corresponding values from the related record
Support lookup field resolution
Handle missing/null values

Ensure:

Support adding static assets (e.g., logos, headers, branding) within templates
Allow multiple templates per entity (e.g., Enrollment, Vendor, Program)
Output generated document (PDF/Word) and store or attach to the record

### Related Work

Parent
24467
System Security&General Administration
Updated 1 мая
New

## 24567 - Deploy Email Placeholder Replacement Logic

Type: USER STORY

State: Ready for QA

Assigned To: Stanislau Viaroukin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24567

Updated: 30 апр. by Stanislau Viaroukin

### Description

Implement functionality to dynamically replace placeholders in Notification Template records (Subject and Body) with actual data values.

Supported placeholder syntax:

{{entity.column}}
{{entity.lookup.column}}
@Stanislau Viaroukin Add more if applicable

Behavior:

When sending an email based on a Notification Template:
Parse Subject and Body for placeholders
Replace each placeholder with the corresponding value from the related record

Examples:

{{contact.firstname}} → Contact First Name
{{enrollment.program.name}} → Program Name from Enrollment → Program lookup

Ensure:

Support for multi-level lookup resolution (one level deep)
Handle missing/null values gracefully (replace with empty string or default)
Do not break email generation if a placeholder cannot be resolved

### Related Work

Add an existing work item as a parent

## 24559 - Implement Address Autocomplete for Work Location using Azure Maps

Type: USER STORY

State: New

Assigned To: Aleksei Andreev

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24559

Updated: 21 апр. by Ucha Minadze

### Description

https://learn.microsoft.com/en-us/rest/api/maps/search/get-geocode-autocomplete?view=rest-maps-2026-01-01&tabs=HTTP

Trigger:

When user starts typing in Street Address field

Behavior:

Show a dropdown with suggested addresses based on user input
Limit number of suggestions (e.g., top 5–10 results)

On selection:

Auto-populate:
Street Address
City
State (if US) or Province
ZIP/Postal Code
Country
Latitude
Longitude

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 24558 - Auto-Populate Discount % on Enrollment

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24558

Updated: Yesterday by Vladimir Vasin

### Description

Table: Enrollment (av_vendorcontract)

Trigger on:

Record creation
Update of Payment Term field

Condition:

Payment Term ≠ null

On trigger:

Retrieve Discount % from selected Payment Term
Populate Enrollment.Discount % with that value
Save the record
Clear Discount % if Payment Term becomes null

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24554 - add global rule for box sixing according to storybook

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24554

Updated: 21 апр. by Ucha Minadze

### Description

clear styles duplicating border-box rule

### Related Work

Add an existing work item as a parent

## 24551 - Check if functionality completed

Type: TASK

State: New

Assigned To: Marharyta Khovanova

Parent: 24550 - Schedule Interview: Time slots configuration/generation

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24551

Updated: 28 апр. by Kristina Strashkulych

_No rich text description captured._

### Related Work

Parent
24550
Schedule Interview: Time slots configuration/generation
Updated 21 апр.
New

## 24550 - Schedule Interview: Time slots configuration/generation

Type: USER STORY

State: New

Assigned To: Aleksei Andreev

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24550

Updated: 21 апр. by Ucha Minadze

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24551
Check if functionality completed
Updated 28 апр.
New

## 24548 - Schedule Interview History

Type: USER STORY

State: New

Assigned To: Aleksei Andreev

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24548

Updated: 21 апр. by Ucha Minadze

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24549
Create a plugin for Interview Scheduling History
Updated 16 апр.
Completed

## 24545 - Update payments and projects entity to use baseQueryWithReauthAuth0

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24545

Updated: 19 апр. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24543 - Implement AI Screening Question Generation on Interview

Type: USER STORY

State: Ready for QA

Assigned To: Viacheslav Borisov

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24543

Updated: 21 апр. by Ucha Minadze

### Description

Add Generate Questions action available on:

Interview main form
Interview Screening Item subgrid

Button visible only when Interview Type = AI Screening.

On click:

Open modal window to capture:
Prompt (additional instructions / focus areas for AI)
Number of Questions

On confirm:

Send prompt and parameters to AI service
Generate questions
Create Interview Screening Item records for each question with:
Interview (lookup)
Question text
Scope = AI

Allow regeneration of individual questions:

Add Regenerate action on Interview Screening Item (row command)
On click:
Prompt for optional additional instruction (or reuse existing prompt)
On confirm:
Call AI service to regenerate only that question
Update Question text

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24537 - Schedule Interview: Reschedule

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24537

Updated: 11 мая by Marharyta Khovanova

### Description

Add Reschedule Interview button on Interview form.

Visible when Interview Status (statuscode) = Scheduled or Pending Confirmation
It opens a page component right side form

On click:

Same logic as new scheduling
If there are Interview Reschedule Requests in “Unprocessed” (table av_interviewreschedulerequest) statuscode:
among other aHighlight the Proposed Date & Time Preferred Days and Preferred Time Blocks in the UI
Indicate whether the slot is available for all Interviewers
Allow user to:
Accept one of the proposed slots, or
Select a different available slot

On confirm:

Update Interview Date&Time (Scheduled Start/Scheduled End)
Set Interview Status (statuscode) = Scheduled Pending Confirmation
Reset Reschedule Requested flag (set to "No")
Mark Reschedule Request as Processed
Save the record

Interview Schedule History record is created

### Comments

Kristina Strashkulych
commented 30 апр.
@Marharyta Khovanova
Kristina Strashkulych
commented 21 апр.
@Aleksei Andreev Updated task description.

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24536 - Schedule Interview Cancelation

Type: USER STORY

State: Ready for QA

Assigned To: Aleksei Andreev

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24536

Updated: 30 апр. by Kristina Strashkulych

### Description

Add Cancel Interview button on Interview form.

Visible when Interview Status (statuscode) = Scheduled

On click:

a modal window with an edit form ( create a new one with 2 inputs)

Cancellation Reason (Choice)
Cancellation Comment (Text)

On confirm:

Set Interview Status (statuscode) = Cancelled
Save Reason and Comment

Interview Schedule History record is created

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New
Child
24552
Create cancelation form
Updated 16 апр.
Completed

## 24535 - Schedule Interview: New

Type: USER STORY

State: In Progress

Assigned To: Aleksei Andreev

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24535

Updated: 30 апр. by Kristina Strashkulych

### Description

Add Schedule Interview button on the Interview form (assuming interview record exists and created outside of interview scheduling scope)

Button enabled when Interview is not yet Scheduled
On click:
Page component right side form is opened.
Invite is shown as read only (preselected)
interview date is a date picker allowing to select desire date (past dates are disabled)

Interviewers selection. Many can be selected

Interviewers options are pre-filtered by interview date (at least one related time slot matches)

If no Interviewers available for selected date, add message 'Please try a different date' or Suggest Available - which is an action button
matching (OR Suggest Available - closest to the selected date/time) time slots are shown on the second screen. Only the time slots that are available for all selected interviews are displayed (date/time matches pairs) (i.e., only the time slots that match across all interviews).
time slots should be grouped together (as they are Identical) and displayed as one.

On confirm:

Set Interview Date/Time from selected slot (Scheduled Start/Scheduled End)
Set Interview Status (statuscode) = Scheduled Pending Confirmation
Relate selected time slots(a pair) to the current Interview

Save the record
Interview Schedule History record is created

### Comments

Kristina Strashkulych
commented 30 апр.
@Marharyta Khovanova
Aleksei Andreev
commented 12 апр.
Work done by @Ledjana Doci

What's completed :

1. Cloud Flows – Time Slot Generation

The following cloud flows were created to automatically generate Time Slot records based on user configurations:

- TIME SLOT | Create records | Generate new records for month for all configurations
- TIME SLOT | Create records | Generate new records for month for specific configuration
- TIME SLOT | Create records | Generate new records for a day for specific configuration

2. Custom Pages

The following custom pages have been implemented to support the interview scheduling process:

- Schedule Interview Time - visible from the Application entity in VMS Admin(Not sure which app it should appear)
- Cancel Interview - visible from Interview entity
- Reschedule Meeting - Page has been created; confirmation is still required on whether this functionality will be included

3. Supporting Cloud Flows

The following flows support interview creation, scheduling, and status management:

INTERVIEW | Update | Create Appointment
INTERVIEW INVITATION | Update | Set interview to Cancelled and Update TimeSlots
INTERVIEW INVITATION | Update | Set Interview to Scheduled and Update TimeSlots
INTERVIEW TIMESLOT | Manual | Set TS Status to Available

4. Remaining Work
Implement Interviewer selection on the first scheduling screen

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New
Child
24547
Create/Change Meeting Scheduling application (Page Component)
Updated 11 мая
Completed

## 24534 - Manage visibility of AI Screening Details Tab

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24534

Updated: 21 апр. by Ucha Minadze

### Description

Update the Interview form to conditionally display the AI Screening Details tab.

Show the tab only when Interview Type = AI Screening
Hide the tab for all other Interview Types or if Interview Type is not selected

Implement using JavaScript that triggers on:

Form load
Change of Interview Type field

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24532 - Handle Related Records When Program is Closed

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24532

Updated: 8h ago by Vladimir Vasin

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24531 - Add Terminate Action on Enrollment

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24531

Updated: Yesterday by Vladimir Vasin

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24530 - Auto-Expire Enrollment Based on End Date

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24530

Updated: Yesterday by Vladimir Vasin

### Description

Trigger daily
Find Enrollment records where:
End Date < current date
Status Reason (statuscode) ne Expired

For each matching record:

Set Status Reason (statuscode) eq Expired
Save the record

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24529 - Add Start and Close Actions on Program

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24529

Updated: Yesterday by Vladimir Vasin

### Description

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

### Comments

Vladimir Vasin
commented Yesterday
Closed - inactive status

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24528 - Post-Approval Processing for Vendor Registration Request

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24528

Updated: 8h ago by Vladimir Vasin

### Description

When a Vendor Registration Request is set to Approved (statuscode), automatically perform the following:

 1. Create a Vendor record.

Map fields from Vendor Registration Request → Vendor
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

Map fields from Vendor Registration Request → Vendor Contact
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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24527 - Add Approve / Decline Actions for Vendor Registration Request

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24527

Updated: Yesterday by Vladimir Vasin

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24519 - update search and dropdown fields to latest version of storybook

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24519

Updated: 21 апр. by Ucha Minadze

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24518 - Add SuccessScreen reusable component from storybook into VMS project

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24518

Updated: 19 апр. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24517 - Create Vendor Enrollment on Application Submission

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24517

Updated: 21 апр. by Ucha Minadze

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24506 - update forms with country input

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24506

Updated: 21 апр. by Evgeniy Malyutin

### Description

for all forms where country input is present, update as following

if country usa - states dropdown should be present, options should be taken from states table
if any other country - no state input should be present in form, and not passed as payload on submit

### Related Work

Add an existing work item as a parent

## 24504 - fix submenu route matching

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24504

Updated: 28 апр. by Raphael Serobiani

### Description

fix submenu route matching and active item highlighting. matcher needs to support cases like /a/1/b/2/c, not only /a/b/1/2  (numbers are meant as ids)

### Related Work

Add an existing work item as a parent

## 24503 - update sidepanel component

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24503

Updated: 2 апр. by Alexander Lisetskii

### Description

update sidepanel component to use latest version from storybook

update usage throughout the project, including clearing excessive useEffect calls that were used to reset the values, since side panel calls on close by itself

### Related Work

Add an existing work item as a parent

## 24500 - Auto-Create Enrollment Requirement Assignments on Application Creation

Type: USER STORY

State: Completed

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24500

Updated: 5h ago by Vladimir Vasin

### Description

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

### Comments

Kristina Strashkulych
commented понедельник
@Iryna Hrytsai Updated the task (highlighted with green).

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24499 - Update Program Active Stage Based on Milestone Date

Type: USER STORY

State: Ready for QA

Assigned To: Iryna Hrytsai

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24499

Updated: 21 апр. by Ucha Minadze

### Description

Automatically update the Active Stage, Current Stage Start Date, and Next Stage Start Date on Program (av_program) when a defined Program Milestone date is reached.

Trigger: scheduled (daily)

 1. Select Program Milestones where:

Milestone Date ≤ Today
Related Program (av_program) exists
Program.statuscode = Open

 2. For each matching milestone:

Get:
Program (av_program)
Milestone (av_milestone)

a) Set Program.Active Stage (av_activestage) based on Milestone:

Example mapping:
Application Open Date → Active Stage = Application Open
Screening Date → Active Stage = Screening
b) Set Current Stage Start Date = Milestone Date

 3. Retrieve the next upcoming milestone for the same Program where:
Milestone Date (the nearest one)> Current Milestone Date
 4. a) If next milestone exists:
Set Next Stage Start Date = next milestone date
    b) If current stage is the last stage:
Clear Next Stage Start Date

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24497 - Programs&Enrollment

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24497

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24770
Add Verify / Reject Actions to Program Certificate
Updated 11h ago
Completed
24558
Auto-Populate Discount % on Enrollment
Updated Yesterday
Completed
24761
Send Enrollment Contract for Signature via DocuSign
Updated пятница
New
24705
Set Program Milestone Name
Updated 8h ago
Completed
24746
Update Program Enrollment Application Status Based on Program Requirement Assignments
Updated 6h ago
Completed
24424
Vendor Enrollment Application Design
Updated 27 апр.
Completed
Show more
(6 of 15)
Not shown: Child (9)

## 24490 - update candidates list

Type: USER STORY

State: Ready for QA

Assigned To: Evgeniy Malyutin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24490

Updated: 24 апр. by Evgeniy Malyutin

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-29047&m=dev

clear latestapplicationstatus

employmenttype - av_positionpreference (multi-select choice)

should be counted on frontend
Active Application = count av_application where statuscode eq 1 or 485580001 and av_candidate eq current contact
Active Engagements = count av_engagement where statuscode eq 485580001 and av_contact eq current contact

on Change Status prompt the user to select one of the following: Available, Limited Availability, Inactive, Blacklisted, Out of Market. On submit update contact.statuscode; exclude the current status from the list of available status transition options.
Active Candidates filter checked:  statuscode eq 1 or 485580001

### Related Work

Add an existing work item as a parent

## 24489 - add program details page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24489

Updated: 7 мая by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4870-9281&m=dev

### Related Work

Add an existing work item as a parent

## 24488 - add programs list page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24488

Updated: 8 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4843-8119&m=dev

### Related Work

Add an existing work item as a parent

## 24487 - Update usage of getDateFormat in every component in codebase

Type: USER STORY

State: Testing

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24487

Updated: 2 апр. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24485 - update company information pages

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24485

Updated: 7 мая by Arsenii Goriushkin

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-27595&m=dev

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-28140&m=dev
update data in cards

### Related Work

Add an existing work item as a parent

## 24484 - projects list

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24484

Updated: 4 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=5478-5371&m=dev
update fields

### Related Work

Add an existing work item as a parent

## 24483 - update timesheets page to match figma

Type: USER STORY

State: In Progress

Assigned To: Arsenii Goriushkin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24483

Updated: 13 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=1398-1466&m=dev

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=892-74047&m=dev
https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=892-75059&m=dev

updates cardfields displayed, check out comments

2) fix hooks error on a specific week timesheet page

example url
http://localhost:6420/timesheets/resource/36365c66-0199-f011-bbd3-7c1e52671625/week/71a31291-b688-f011-b4cc-6045bdfe3fc6/details

### Related Work

Add an existing work item as a parent

## 24471 - update itemcard component for all pages

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24471

Updated: 14 мая by Ognjen Pandurevic

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24470 - update Invoice page

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24470

Updated: 13 мая by Alexander Lisetskii

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=917-83989&m=dev

add
Timesheet-Based
and
Fixed Price
pages

update lists and forms

### Related Work

Add an existing work item as a parent

## 24468 - MDA Security Roles Setup

Type: USER STORY

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24468

Updated: 27 апр. by Kristina Strashkulych

### Description

System Administrator (MSP)

Responsible for overall system configuration, security, and governance. Manages roles, settings, templates, and has full access to all data and override capabilities.

MSP Program Manager
Oversees the entire program across all clients, agencies, and vendors. Manages contracts, monitors performance, and ensures compliance with program objectives.

MSP Finance
Responsible for managing financial operations on behalf of the MSP. Handles invoice generation, adjustments, and reconciliation of timesheets and expenses. Ensures accurate billing to clients and proper financial tracking.

Client Program Manager
Manages contracts and vendor performance from the client perspective. Oversees program execution within their organization and ensures alignment with business needs.

Client Hiring Manager
Responsible for managing specific engagements and resources. Works directly with vendors and contractors, and typically reviews work progress and deliverables.

Client Approver
Reviews and approves operational transactions such as timesheets and expenses. Focused on validation and authorization of submitted work.

Client Finance
Responsible for reviewing and processing invoices from the MSP. Oversees payment validation, financial approvals, and ensures alignment with client financial policies and budgets.

Agency Manager
Oversees vendor activity and engagements within a specific agency. Ensures proper staffing, compliance, and operational performance at the agency level.

Department Manager
Manages engagements and resources within a specific department. Provides more granular oversight and may participate in approvals and day-to-day coordination.

### Related Work

Add an existing work item as a parent

## 24467 - System Security&General Administration

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24467

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24568
Deploy Document Templates Solution
Updated 30 апр.
Ready for QA
24567
Deploy Email Placeholder Replacement Logic
Updated 30 апр.
Ready for QA
24468
MDA Security Roles Setup
Updated 27 апр.
New

## 24465 - Add/Remove Timesheets to/from Invoice (Manual Actions)

Type: USER STORY

State: New

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24465

Updated: 28 апр. by Kristina Strashkulych

### Description

Button: Add to Invoice

Place:

Timesheet Grid (command bar)
Timesheet Form

Visibility Rules:

Visible when:
Timesheet statuscode = Submitted, Approved, or Manual Override
Timesheet Invoice = null
current user security role eq 'MSP Finance' or 'Client Finance' or 'System Administrator'

Action:

For selected Timesheet(s):
Find and prompt selection of target Invoice (Payment Status = Not Processed or Next Payroll)
Set Timesheet → Invoice (lookup)
Recalculate Invoice Amount
 2. Button: Remove from Invoice

Place:

Invoice Form → Timesheets subgrid
Timesheet Form

Visibility Rules:

Visible when:
Timesheet is linked to an Invoice
Invoice.Payment Status = Not Processed or Next Payroll
current user security role eq 'MSP Finance' or 'Client Finance' or 'System Administrator'

Action:

Remove link:
Clear Timesheet → Invoice (lookup)
Recalculate Invoice Amount

### Related Work

Add an existing work item as a parent

## 24463 - Link Timesheets to Invoice on Status Change

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24460 - Financials

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24463

Updated: 1 мая by Marharyta Khovanova

### Description

Trigger: When a Timesheet record is updated

Condition: statuscode changes to:
Submitted
Approved
Manual Override
Step 1: Find the Invoice

Search for existing Invoice where:

Vendor = Timesheet Vendor
Engagement = Timesheet Engagement
Timesheet.Saturday Date within the Pay Period
Invoice Status = Draft or Submitted
Invoice.Payment Status = Not Processed or Next Payroll
Step 2: Link Timesheet to Invoice
Set Timesheet → Invoice (lookup)
Step 3: Update Invoice Totals
Recalculate:
Total Amount based on all linked Timesheets

### Related Work

Parent
24460
Financials
Updated 1 мая
New

## 24462 - Generate Invoices from Closed Pay Period

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24460 - Financials

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24462

Updated: 27 апр. by Marharyta Khovanova

### Description

Trigger: Pay Period.Pay Period Status changed to 'Closed'

Select Timesheets where:

Saturday Date is within the triggering Pay Period
Status = Submitted, Approved, Manual Override
Invoice = null
Group Timesheets by: Engagement

Create Invoice
For each group:
Agency
Vendor
Engagement
Resource
Pay Period
Invoice Date = Today
Invoice Due Date = Invoice Date +30 days
Invoice Type = 'Timesheet-Based'
Status = Submitted
Amount = sum of Timesheet.Timesheet Amount
Update Timesheets
For each included Timesheet:
Set Invoice (lookup)

### Related Work

Parent
24460
Financials
Updated 1 мая
New

## 24461 - Automate Pay Period Closure

Type: USER STORY

State: Ready for QA

Assigned To: Marharyta Khovanova

Parent: 24460 - Financials

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24461

Updated: 23 апр. by Marharyta Khovanova

### Description

Trigger: Scheduled (daily)

Select Pay Period records where:

Pay Period Status = Open
End Date < Today

For each matching Pay Period:

Set Pay Period Status = Closed

### Related Work

Parent
24460
Financials
Updated 1 мая
New

## 24460 - Financials

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24460

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24459 - Interview Scheduling

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24459

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24747
Automatically Set Interview Status to Completed
Updated 19m ago
Completed
24543
Implement AI Screening Question Generation on Interview
Updated 21 апр.
Ready for QA
24610
Implement Interview Feedback Collection + COI Attestation & Daily Reminders
Updated 12 мая
Ready for QA
24536
Schedule Interview Cancelation
Updated 30 апр.
Ready for QA
24535
Schedule Interview: New
Updated 30 апр.
In Progress
24537
Schedule Interview: Reschedule
Updated 11 мая
Ready for QA
Show more
(6 of 12)
Not shown: Child (6)

## 24458 - Fix Pending Engagements Card to fix horizontal scroll issue on page

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24458

Updated: 24 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24457 - Update OutlineButton component in project and update it's usage in parent components

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24457

Updated: 31 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24456 - Update TransparentButton component in project and update it's usage in parent components

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24456

Updated: 31 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24455 - Update PrimaryButton component in project and update it's usage in parent components

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24455

Updated: 26 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24454 - fix candidate requests

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24454

Updated: 15 апр. by Raphael Serobiani

### Description

currently

av_agencycontracts
and
contacts requests are failing

### Comments

Alexander Lisetskii
commented 31 мар.

update requests ti return candidate pages present to the working state

### Related Work

Add an existing work item as a parent

## 24453 - Invoices page have horizontal scroll Issue with InvoiceCard component

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24453

Updated: 24 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24449 - Overlap style issue with DateField component

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24449

Updated: 24 мар. by Raphael Serobiani

### Description

theres something overlaps with input borders

### Related Work

Add an existing work item as a parent

## 24429 - Contract api update

Type: USER STORY

State: Ready for QA

Assigned To: Arsenii Goriushkin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24429

Updated: 7 апр. by Arsenii Goriushkin

### Description

Everywhere we currently display "CONTRACT: [xyz]", please remove the word “Contract” and keep only the value (e.g., "[xyz]").
The Contract data model has changed:

The lookup "av_contract.av_agency" has been removed.
The relationship is now reversed: Agency now contains the Contract lookup → "av_agency.av_contract".

### Related Work

Add an existing work item as a parent

## 24425 - Bulk Create Interviews from Applications

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24425

Updated: 30 мар. by Ledjana Doci

### Description

Recruiters often need to schedule interviews for several candidates who applied to the same job position. Instead of opening each application individually, the system should allow the recruiter to select multiple applications from the Applications subgrid and create interviews in one action.

The created interviews must automatically link to the Application, Candidate, and Job Position associated with each selected application.

1) A new button should be available on the Applications subgrid.

2) The button should only be visible when one or more application records are selected.
3) Button label: Create Interviews

User Flow
Recruiter opens a Job Position record.
On the Applications subgrid, the recruiter selects one or more applications.
Recruiter clicks Create Interviews.
A modal window opens.
In the modal window, the recruiter selects:
Interview Type
Interviewers
Recruiter confirms the action.
The system creates one Interview record for each selected application.

Interview Creation Logic

For every selected application, the system must create a new Interview record with the following relationships automatically populated:
Application - Selected Application
Candidate - From Application
Job Position - From Application
Interview Type - Selected in modal
Interviewers - Selected in modal

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 24424 - Vendor Enrollment Application Design

Type: USER STORY

State: Completed

Assigned To: Ekaterina Gorbunova

Parent: 24497 - Programs&Enrollment

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24424

Updated: 27 апр. by Kristina Strashkulych

### Description

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

### Related Work

Parent
24497
Programs&Enrollment
Updated 1 мая
New

## 24418 - Centralize notifications component from Storybook / does-ui

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24418

Updated: 24 мар. by Raphael Serobiani

### Description

Description:

Currently, notification messages (success, error, warning, info) are implemented in different places with duplicated logic and inconsistent UI usage. To improve maintainability and consistency, we should refactor the implementation and centralize the notification system.

Scope of work:

Replace custom notification implementations with the Notification component from Storybook / does-ui.

Create a shared notification utility/service that can be reused across the application.

Refactor existing places where notifications are triggered to use the centralized notification functionality.

Ensure consistent styling, behavior, and positioning of notifications across the application.

Goal:

Eliminate duplicated notification logic, align with the design system, and provide a centralized and reusable notification mechanism.

### Related Work

Add an existing work item as a parent

## 24417 - Centralize attachment download functionality using shared API and Download Button

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24417

Updated: 24 мар. by Raphael Serobiani

### Description

Description:

Currently, the download functionality is duplicated across multiple components. To improve maintainability and consistency, we should refactor the implementation and centralize the download logic.

Scope of work:

Replace existing custom download buttons with the Download Button component from Storybook / does-ui.

Implement a shared API method for downloading attachments in the shared API layer.

Refactor existing components to reuse the centralized download functionality instead of duplicating logic.

Ensure the download behavior is consistent across all places where attachments are downloaded.

Goal:

Reduce code duplication, improve consistency with the design system, and centralize download-related logic for easier maintenance.

### Related Work

Add an existing work item as a parent

## 24409 - Add “Publish Question” Button to Opportunity Question

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24409

Updated: 21 апр. by Ucha Minadze

### Description

Entity

Opportunity Question (av_opportunityquestion)

Button

Label: Publish on Portal

Visibility

Show when:

Publicly Available (av_publiclyavailable) = No

Validation

Before publishing:

av_answer IS NOT NULL

If empty show:

"An answer must be provided before the question can be published on the Vendor portal."

Confirmation Popup

Title:
Publish Question

Message:
"This question and answer will be publicly visible to all vendors on the portal.
Do you want to continue?"

Buttons:

Confirm

Cancel

Action on Confirm

Update fields:

av_publiclyavailable = Yes

### Related Work

Add an existing work item as a parent

## 24408 - Generate Invoice PDF Upon Invoice Creation

Type: USER STORY

State: Removed

Assigned To: Marharyta Khovanova

Parent: 24460 - Financials

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24408

Updated: 28 апр. by Kristina Strashkulych

### Description

!!! LOGIC REMOVED

Automatically generate a PDF version of the Invoice when a new Invoice (av_invoice) record is created. The PDF should be based on a predefined template and include Agency and Vendor logos.

Trigger

Event: Record Created

Table: Invoice (av_invoice)

Process
Step 1: Determine Invoice Type
Read Invoice Type field:
Fixed-Price
Timesheet-Based
Step 2: Retrieve Common Fields (Both Types)

From av_invoice:

Agency
Vendor
Project
Invoice #
Invoice Date
Due Date
Amount
Step 3: Retrieve Logos
Agency Logo → av_agency.av_logo
Vendor Logo → av_vendor.av_logo
Step 4: Type-Specific Data Handling
Fixed-Price Invoice

Include:

Period of Performance
Timesheet-Based Invoice

Include:

Engagement
Resource
Pay Period (instead of Period of Performance)
Total Hours
Invoice Line Items (Timesheet-Based Only)

Retrieve all related Timesheets where:

Timesheet.Invoice = current Invoice

Add them as Invoice Line Items in the PDF.

Columns:

Timesheet ID
Week #
Saturday Date

Total Hours
Rate
Timesheet Amount
Step 5: Populate PDF Template
Use predefined template
Inject:
Common fields
Type-specific fields
Logos
Line items (for Timesheet-based)
Step 6: Generate PDF
Render finalized document as PDF
Step 7: Save PDF
Attach generated PDF to:
Invoice record (av_invoice)
Store in:
av_file

Preferred implementation option:

Server-side plugin using PDF generation library

Suggested PDF template attached.

### Related Work

Parent
24460
Financials
Updated 1 мая
New

## 24407 - Procurement

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24407

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24409
Add “Publish Question” Button to Opportunity Question
Updated 21 апр.
Ready for QA
24757
Generate Vendor Q&A Excel File on Solicitation
Updated 20m ago
New
24756
Update Solicitation Active Stage Based on Milestone Date
Updated четверг
Ready for QA

## 24406 - Update AI Job Description Generator – Add Step 4 (Rates)

Type: USER STORY

State: Ready for QA

Assigned To: Mykyta Stronhin

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24406

Updated: 23 апр. by Mykyta Stronhin

### Description

Extend the AI Job Description Generator widget by adding Step 4: Rates to assist users in defining the Job Position Base Rate using recommended and industry benchmark data.

 1. New Step in Generator Workflow
Step 4: Rates
This step appears after the Job Description generation step and before final confirmation.

 2. Displayed Fields

Recommended Base Hourly Rate
Source: Job Title table
Column: Recommended Base Hourly Rate
Display: Read-only
Purpose: Provide the system-recommended base rate for the selected Job Title.
Industry Median Rate
Source: External web lookup - INTEGRATION WITH THIRD-PARTY SOFTWARE
Input Parameter: Work Location (State / Area)
Behavior: System queries web sources for the median hourly rate for the selected Job Title in the specified location.
Display label: Industry Median Rate (based on market data for selected location)
Job Position Base Rate
Column: Base Hourly Rate
Default Value: Automatically populated with Recommended Base Hourly Rate.
 3. Validation Rule

User may adjust the Base Hourly Rate but cannot exceed the Recommended Base Hourly Rate.

Validation condition:
Base Hourly Rate ≤ Recommended Base Hourly Rate
If exceeded:
Show error:
"Base Hourly Rate cannot exceed the Recommended Base Hourly Rate for this Job Title."

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 24403 - Implement Job Position Approval Workflow

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24403

Updated: 9 апр. by Kristina Strashkulych

### Description

Table: Job Position (av_requisition)

 1. Request Approval Button (Vendor Management System Operations MDA)

Button Label:

Request Approval

Visible When:

App = Vendor Management System MDA

Approval Status = Blank OR Rejected

On Click:

Set Approval Status = Pending Approval

Save record

Show confirmation toast: “Approval request submitted.”

 2. Approve / Reject Buttons (MSP - Vendor Management System Administration MDA)
Buttons:

Approve

Reject

Visible When:

App = Vendor Management System Administration MDA

Approval Status = Pending Approval

2.1. Modal Window (Both Approve & Reject)

On click of either button:

Open modal dialog with:

Approval Comments (Multiline Text, optional)

Buttons:

Confirm

Cancel

On Confirm:

If Approve →

Set Approval Status = Approved

If Reject →

Set Approval Status = Rejected

Save Approval Comments

Close modal

On Cancel:

Close modal

No changes saved

### Comments

Ledjana Doci
commented 6 мар.
@Kristina Strashkulych This is ready to be tested

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 24398 - certifications - pending engagements

Type: USER STORY

State: Ready for QA

Assigned To: Arsenii Goriushkin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24398

Updated: 30 мар. by Arsenii Goriushkin

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24392 - candidate engagement history page add

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24392

Updated: 9 мар. by Ucha Minadze

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-31244&m=dev

### Related Work

Add an existing work item as a parent

## 24391 - candidate application history page add

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24391

Updated: 5 мая by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-30928&m=dev

### Related Work

Add an existing work item as a parent

## 24390 - candidate interviews page add

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24390

Updated: 22 апр. by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-30622&m=dev

### Related Work

Add an existing work item as a parent

## 24389 - candidate documents page add

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24389

Updated: 31 мар. by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-30374&m=dev

### Related Work

Add an existing work item as a parent

## 24388 - PaymentsPage add

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24388

Updated: 26 мар. by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=892-76904&m=dev

### Related Work

Add an existing work item as a parent

## 24387 - projects page add

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24387

Updated: 11 мар. by Raphael Serobiani

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2963-46395&m=dev

### Related Work

Add an existing work item as a parent

## 24386 - solicitation page add

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24386

Updated: 11 мая by Ucha Minadze

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2935-44144&m=dev

### Comments

Ucha Minadze
commented 16 мар.
Adding Solicitation page layout
Ucha Minadze
commented 9 мар. (edited)
Adding api for all screens needed for Solicitation page - under review

### Related Work

Add an existing work item as a parent

## 24381 - rename position details to job information (on job positions and in submenu and breadcrumbs)

Type: USER STORY

State: Ready for QA

Assigned To: Raphael Serobiani

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24381

Updated: 11 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24356 - fix application details documents styles

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24356

Updated: 27 февр. by Ucha Minadze

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24355 - fix applications list candidate name

Type: USER STORY

State: Ready for QA

Assigned To: Ucha Minadze

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24355

Updated: 27 февр. by Ucha Minadze

### Description

fix applications list candidate name is not the same as shown on application details (must be Jones Jr, Gina, but shows Jones, Gina for APP-2025-23-12-100011, while the api returns `"fullname":  "Gina Jones Jr"` for application's candidate expand).

### Related Work

Add an existing work item as a parent

## 24354 - update job(position) card and details to match figma

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24354

Updated: 27 февр. by Ognjen Pandurevic

### Description

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=890-54043&m=dev

https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=2902-9162&m=dev

### Related Work

Add an existing work item as a parent

## 24353 - change submenu left spacing, the text must start on the same line as of the parent menu text

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24353

Updated: 19 февр. by Ognjen Pandurevic

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24352 - fix menu icons as per designs (pull in the icons that are not a part of fluentui from figma into shared icons)

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24352

Updated: 19 февр. by Ognjen Pandurevic

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24351 - rename

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24351

Updated: 27 февр. by Ognjen Pandurevic

### Description

rename position details to job information (on job positions and in submenu and breadcrumbs)

rename Open positions to Job Positions

### Related Work

Add an existing work item as a parent

## 24350 - fix sidepanel width as per design (find a way to style it and add a param to change sidepanel width)

Type: USER STORY

State: Ready for QA

Assigned To: Ognjen Pandurevic

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24350

Updated: 24 февр. by Ognjen Pandurevic

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 24349 - fix (parsing resume result) tabs styles (underline width), fix globally

Type: USER STORY

State: Ready for QA

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/24349

Updated: 11 мар. by Raphael Serobiani

_No rich text description captured._

### Related Work

Add an existing work item as a parent

## 23800 - update layout to latest design

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23800

Updated: 17 мар. by Alexander Lisetskii

### Description

DONE company information to submenu
DONE company information bank details
candidates list - deactivate button
background checks to compliance
candidate - button - save instead of submit
IN PROGRESS job position - asceding/descending using application deadline + added filters (checkboxes default - false)
job position card - my submission / per vendor - two separate columns
job position details - new fields in fob information
job position details skills - required column - required\nice to have instead of nubmers
job position details - question block + will be added q+a block ( wait design )

open positions - eligibility values taken from candidate
general eligibility + fit - scopes
open positions - dynamic questions from api

application card - sort by submitted date - check fields for card
DONE pending engagements - top card - wait for new design
WORKING pending + certifications
DONE active engagements - top card - wait for new design
DONE active + trainings and compliance

### Related Work

Add an existing work item as a parent

## 23765 - Combined Front-End Task List

Type: USER STORY

State: New

Assigned To: Alexander Lisetskii

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23765

Updated: 2 апр. by Alexander Lisetskii

### Main Flow

24352 - fix menu icons as per designs (pull in the icons that are not a part of fluentui from figma into shared icons) ✔
24353 - change submenu left spacing, the text must start on the same line as of the parent menu text ✔

### Related Work

Add an existing work item as a parent

## 23573 - AI Screening Face Liveness detection

Type: USER STORY

State: In Progress

Assigned To: Viacheslav Borisov

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23573

Updated: 30 мар. by Kristina Strashkulych

_No rich text description captured._

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 23541 - Timesheets Approval flow and buttons

Type: USER STORY

State: Removed

Assigned To: Iryna Hrytsai

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23541

Updated: 22 апр. by Kristina Strashkulych

### Description

Approve

Place:

Timesheet Main Form
Timesheet Grid (command bar)

Visibility Rules:

Visible when statuscode = Submitted
Engagegement.Approver = current user or current user security role eq 'MSP Program Manager' or 'Client Approver' or 'System Administrator'

Action:

Set statuscode = Approved
Populate:
Reviewed By (Program Admin)
Reviewed On
2. Reject

Place:

Timesheet Main Form
Timesheet Grid (command bar)

Visibility Rules:

Visible when statuscode = Submitted
Engagegement.Approver = current user or current user security role eq 'MSP Program Manager' or 'Client Approver' or 'System Administrator'

Action:

Prompt for Rejection Reason
Set statuscode = Rejected
Populate:
Reviewed By (Program Admin)
Reviewed On
 3. Manual Override

Place:

Timesheet Main Form
Timesheet Grid (command bar)

Visibility Rules:

Visible when:
statuscode = Approved OR Rejected
current user security role eq 'MSP Program Manager' or 'Client Approver' or 'System Administrator'

Action:

Prompt for Override Reason
Set statuscode = Manual Override
Populate:
Reviewed By (Program Admin)
Reviewed On

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New
Related
24602
Update Timesheet Approval Process to Support Multi-Level Approval
Updated 27 апр.
Ready for QA

## 23540 - Implement Compliance Check Requirement Automation

Type: USER STORY

State: Ready for QA

Assigned To: Mykyta Stronhin

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23540

Updated: 31 мар. by Mykyta Stronhin

### Description

Implement automation for Compliance Check Requirements and Compliance Check Assignments. The same cloud flows and plugins already exist in the HCM / PSC eHR environments and may be copied from there.

1. Create Compliance Check Assignment when Compliance Check Requirement is created

When a Compliance Check Requirement record is created, automatically create a Compliance Check Assignment record linked to:

the Compliance Check Requirement
the Contact from the Requirement
the Compliance Check Type

Set the Compliance Check Assignment Status to Assigned.

2. Auto-approve Compliance Check Assignment when completion is submitted

When Compliance Check Assignment Date Taken is updated and Compliance Check Assignment Status equals Verifying, validate the following:

Compliance Check Date must be earlier than Compliance Check Requirement Next Check Date.
If Compliance Check Type Require File = Yes, verify that Compliance Check Assignment File is not empty.
If Compliance Check Type Require File = No, skip the file validation.

If the validation passes, update the records as follows.

Update Compliance Check Assignment:

Status → Auto-Approved
Reviewed On → utcNow()
Completed Date → utcNow()

Update Compliance Check Requirement:

Check Status → Completed
Last Check Date → Compliance Check Assignment.Date Taken

3. Create next Compliance Check Assignment for recurring checks

If the Compliance Check Requirement Frequency is Annual, Semiannual, or Custom, automatically create the next Compliance Check Assignment.

The assignment should be created Remind Days Before days prior to Compliance Check Requirement Next Check Date, using the value defined on the Compliance Check Type.

4. Add manual review buttons

Add the following buttons on the Compliance Check Assignment form when the Status equals Verifying:

Verify Completion
Reject Completion

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 23539 - Implement Training Requirement Automation Flow

Type: USER STORY

State: Ready for QA

Assigned To: Mykyta Stronhin

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23539

Updated: 31 мар. by Mykyta Stronhin

### Description

Implement automation for Training Requirements and Training Assignments. The same cloud flows and plugins already exist in the HCM / PSC eHR environments and may be copied from there.

1. Create Training Assignment when Training Requirement is created

When a Training Requirement record is created, automatically create a Training Assignment record linked to:

the Training Requirement
the Contact from the Training Requirement
the Training Type

Set the Training Assignment Status to Assigned.

2. Auto-approve Training Assignment when completion is submitted

When Training Assignment Date Taken is updated and the Training Assignment Status equals Verifying, validate the following:

Date Taken must be earlier than Training Requirement Retake On.
If Training Type Require File Upload = Yes, verify that Training Assignment File is not empty.
If Training Type Require File Upload = No, skip the file validation.

If the validation passes, update the records as follows.

Update Training Assignment:

Status → Auto-Approved
Reviewed On → utcNow()
Completed Date → utcNow()

Update Training Requirement:

Training Status → Completed
Last Date Taken → Training Assignment.Date Taken

3. Create next Training Assignment for recurring trainings

If the Training Requirement Frequency is Annual, Semiannual, or Custom, automatically create the next Training Assignment.

The new assignment should be created Remind Days Before days prior to Training Requirement Retake On using the value defined on the Training Type.

4. Add manual review buttons

Add the following buttons on the Training Assignment form when the Status equals Verifying:

Verify Completion
Reject Completion

These buttons allow administrators to manually approve or reject a submitted training completion.

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 23498 - Copy Requisition Screening Items to Interview

Type: USER STORY

State: Ready for QA

Assigned To: Kristina Strashkulych

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23498

Updated: 30 мар. by Kristina Strashkulych

### Description

Trigger:
A new Interview is created; av_interviewtype = 485580000 (AI Screening) AND av_requisition ne null.

Action:
Query all active Requisition Screening Items on the Requisition.
For each, create an Interview Screening Item:
Copy Question Text/Prompt and Do Not Proceed On Negative Answer
Set Interview (av_interview) lookup
Set Provenance (av_provenance) = Requisition (485580000)

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 23486 - Copy Requisition Properties to Engagement on Creation

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23486

Updated: 4 мар. by Ledjana Doci

### Description

1. Trigger:

Engagement is created.

Engagement.Requisition ne null.

2. System Action:

Map the following column values from Requisition → Engagement:

Job Title (av_requisition.av_jobtitle → av_engagement.av_jobtitle)
Agency (av_requisition.av_agency → av_engagement.av_agency)
Work Location (av_requisition.av_worklocation → av_engagement.av_worklocation)
Work Arrangement (av_requisition.av_workarrangement → av_engagement.av_workarrangement)
Employment Type (av_requisition.av_employmenttype → av_engagement.av_employmenttype)
Hours/Units per Day (av_requisition.av_housunitsperday → av_engagement.av_hoursunitsperday)
Days per Week (av_requisition.av_daysperweek → av_engagement.av_daysperweek)
Start Date (av_requisition.av_startdate → av_engagement.av_startdate)
End Date (av_requisition.av_enddate → av_engagement.av_enddate)
Background Check Set (av_requisition.av_backgroundcheckset → av_engagement.av_backgroundcheckset)
Training Set (av_requisition.av_trainingset → av_engagement.av_trainingset)

3. Behavior:

Copy occurs only once at creation time (no ongoing sync).

Changes to Requisition after Engagement creation do not back-propagate.

### Comments

Ledjana Doci
commented 4 мар.
Hey @Kristina Strashkulych,

This is ready for testing.

FYI - I couldnt find the Agency field anywhere in Engagement. The field name is av_client and I have already mapped that to the one in Job position, but that is not in the form.

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 23485 - AI Screening MVP

Type: USER STORY

State: Testing

Assigned To: Viacheslav Borisov

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23485

Updated: 30 мар. by Kristina Strashkulych

_No rich text description captured._

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 23484 - Generate Engagement-Related Compliance Check and Training Requirements

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 23483 - Engagement Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23484

Updated: 6 мар. by Ledjana Doci

### Description

1. On Update of Compliance Check Set (on Engagement)

When Background Check Set changes (new value selected):

Retrieve all Compliance Check Types linked to the selected Set.

For each Type → Create Compliance Check Requirement record linked to the Engagement. Fields mapping:

av_backgroundchecktype → current Compliance Check Type
av_resource → av_engagement.av_contact
av_engagement → Current Engagement
av_backgroundchecktype.av_recurrence → av_backgroundcheckrequirement.av_recurrence
av_checkstatus → Assigned

Prevent duplication: do not create duplicates if Requirements already exist for that Reference.

2. On Update of Training Set (on Engagement)

When Training Set changes (new value selected):

Retrieve all Trainings linked to the selected Set.

For each Training → Create Training Requirement record linked to the Engagement.

av_training → Current Training
av_resource → av_engagement.av_contact
av_engagement → Current Engagement
av_training.av_recurrence → av_trainingrequirement.av_recurrence
av_trainingstatus → Assigned

Prevent duplication: do not create duplicates if Requirements already exist for that Reference.

### Related Work

Parent
23483
Engagement Management
Updated 1 мая
New

## 23483 - Engagement Management

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23483

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24604
Add Manual Offboarding (Terminate Engagement)
Updated 21m ago
Completed
24603
Auto-Create Offboarding on Engagement End
Updated 21m ago
Completed
24605
Generate Offboarding Task Assignments
Updated 21m ago
Completed
24606
Manage Offboarding Task Assignment Status (Overdue Detection)
Updated 24 апр.
Ready for QA
23541
Timesheets Approval flow and buttons
Updated 22 апр.
Removed
24607
Update Offboarding Status Based on Tasks
Updated 21m ago
Completed
Show more
(6 of 10)
Not shown: Child (4)

## 23479 - Interview Scheduling based on user Configurations

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 24459 - Interview Scheduling

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23479

Updated: 9 апр. by Kristina Strashkulych

### Description

Wiki https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/244/Interview-Scheduling-Module

Implement logic to support interviewer availability configuration, automatic generation of interview time slots, and identification of available slots for scheduling.

Use the User Configuration table to store interviewer availability with the following fields:

Day of Week
Available Start Time
Available End Time
Effective Start Date / End Date
Slot Duration (minutes)

Generate Interview Time Slot records by:

Filtering configurations by effective date range
Splitting each availability window into time slots based on Slot Duration
Creating records in the Interview Time Slot table for each generated interval (Start Time / End Time / Interviewer reference)

Ensure slot generation avoids duplicates and respects existing Interview Time Slot records if already generated for the same configuration and date range.

### Related Work

Parent
24459
Interview Scheduling
Updated 1 мая
New

## 23474 - Job Application Management

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23474

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24730
Create Right to Represent Record When Application Is Created
Updated 22m ago
Completed
24588
Implement Application AI Evaluation
Updated 6 мая
Ready for QA
24608
Implement Job Application Approval & Engagement Creation
Updated 13 мая
Ready for QA
24732
Send RtR Request Email Notification to Candidate
Updated 15 мая
Ready for QA
24731
Set Right to Represent Status to Expired
Updated 21m ago
Completed
24609
TBD Application Qualification/Disqualification Process
Updated 12 мая
New
Show more
(6 of 7)
Not shown: Child (1)

## 23473 - Publish button for Requisitions

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23473

Updated: 5 мар. by Ledjana Doci

### Description

Application: Vendor Management Application
Table: Job Position (av_requisition)
Form: Information (main form)

Add a Publish button to the Requisition form.

Button only visible when Status = Draft and Approval Status = Approved.

On click → change Requisition Status = Open, capture Published On.

Save and refresh the page.

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 23420 - Auto-Generate Job Position Questions on Job Position Creation

Type: USER STORY

State: Ready for QA

Assigned To: Ledjana Doci

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23420

Updated: 13 мая by Kristina Strashkulych

### Description

Trigger

Event: Record Created

Table: Job Position (av_requisition)

Logic

Retrieve all records from Job Position Question Reference where:

Scope = Global

For each retrieved record, create a new Job Position Question record.

Job Position Question Record Mapping
Field	Value
Job Position	Newly created Job Position
Job Position Question Reference	Reference record from step 1

### Comments

Ledjana Doci
commented 11 мар.
@Kristina Strashkulych This is ready to be tested

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

## 23414 - Requisition Management

Type: FEATURE

State: New

Assigned To: Kristina Strashkulych

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23414

Updated: 1 мая by Marharyta Khovanova

_No rich text description captured._

### Related Work

Add an existing work item as a parent
Child
24578
Close Job Position and Cascade Application Closure
Updated 27 апр.
Ready for QA
24559
Implement Address Autocomplete for Work Location using Azure Maps
Updated 21 апр.
New
24403
Implement Job Position Approval Workflow
Updated 9 апр.
Ready for QA
23473
Publish button for Requisitions
Updated 5 мар.
Ready for QA
24406
Update AI Job Description Generator – Add Step 4 (Rates)
Updated 23 апр.
Ready for QA
23409
Update the Job Generator PCF control settings to reference the Job Title Lookup
Updated 9 мар.
Completed
Show more
(6 of 7)
Not shown: Child (1)

## 23412 - Job Generator: update the AI Prompt to use information from the Job Title Reference (Catalog)

Type: USER STORY

State: Removed

Assigned To: Mykyta Stronhin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23412

Updated: 3 сент. 2025 г. by Kristina Strashkulych

### Description

When generating Summary and Qualifications, reference to the Job Title Reference (av_jobtitle) table columns: av_jobsummary, av_entryqualifications as a priority.

### Related Work

Add an existing work item as a parent

## 23410 - Job Generator: update the 'Title' lookup column behavior

Type: USER STORY

State: Removed

Assigned To: Mykyta Stronhin

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23410

Updated: 3 сент. 2025 г. by Kristina Strashkulych

### Description

Table: Requisition (av_requisition)
Form: Information
Control Property: Name (av_name)
Add 'Category' selection - lookup to 'Job Category Reference' (av_jobcategory) table
Update the 'Title' lookup column to lookup for the records in the 'Job Title Reference' (av_jobtitle) table by the keyword (user input) filtered by the 'Category' selected)

### Related Work

Add an existing work item as a parent

## 23409 - Update the Job Generator PCF control settings to reference the Job Title Lookup

Type: USER STORY

State: Completed

Assigned To: Mykyta Stronhin

Parent: 23414 - Requisition Management

Azure URL: https://dev.azure.com/AvidSys/VMS/_workitems/edit/23409

Updated: 9 мар. by Kristina Strashkulych

### Description

Current behavior: The 'name' property references the Single line of text column.

Expected behavior: Configure the Job Generator PCF control for the 'name' property to reference the 'Job Title' (av_requisition.av_jobtitle) lookup column.

### Related Work

Parent
23414
Requisition Management
Updated 1 мая
New

