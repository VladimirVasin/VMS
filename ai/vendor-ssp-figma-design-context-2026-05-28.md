# Vendor SSP Figma Design Context

Captured: 2026-05-28.

Primary source:

- Figma file: [Vendor SSP](https://www.figma.com/design/VWo9J4UoYKcBrWF4h76aqo/Vendor-SSP?node-id=4870-9282&t=1eWfNhxuJVb6ts1I-0)

Supporting sources:

- Azure DevOps work item context captured in `azure-work-items-full-context-2026-05-28.md`.
- Programs and enrollment process context in `programs-enrollment-process-overview.md`.
- Final project synthesis in `final-project-overview-2026-05-28.md`.

Capture method and limits:

- Figma was inspected in a logged-in Chrome session with view/comment access.
- Screen-reader adaptation was enabled in Figma to expose page and layer structure where possible.
- No screenshots or raster exports are stored in this repository.
- The Figma file is view-only from this session; exact component internals, comments, and Dev Mode specs should still be checked in Figma when precision is required.
- Some layer names are generic, so this file combines visible design inspection, exposed Figma layer names, and already-captured Azure work item text.

## Executive Summary

Vendor SSP is the external self-service portal experience for vendors, vendor contacts, candidates/resources, and finance-facing vendor users. The design covers both unauthenticated onboarding/enrollment pages and authenticated operational portal pages.

The portal is broader than the empty Vendor Portal Wiki page suggests. It includes:

- Public vendor enrollment marketing/application flow.
- Vendor registration and enrollment application flow.
- Authenticated vendor dashboard/navigation.
- Program discovery and program detail pages.
- Company profile and vendor contact management.
- Candidate profile/list/detail areas.
- Job positions, candidate submission, and application tracking.
- Pending and active engagements.
- Solicitation response pages.
- Projects.
- Timesheets.
- Invoices.
- Payments.
- Document library and candidate documents.
- Candidate-specific application portal screens.
- Supporting document generation / reusable design references.

The design is strongly aligned with the work item backlog around Programs&Enrollment, Vendor Portal Dataverse connectivity, role-based action enforcement, candidates, applications, job positions, timesheets, invoices, payments, projects, solicitation, and document templates.

## Figma Page Map

Visible Figma pages:

1. `Vendor Application Design`
2. `Candidate Application Design`
3. `Vendor Enrollment Application Design`
4. `Previous version`
5. `web site`
6. `Document Generator`
7. `useful`

### Vendor Application Design

This is the main authenticated vendor portal design surface.

Observed screen clusters:

- Programs
- Company Information
- Company Information / Contacts
- Candidate / Candidates
- Manually Add Candidate
- Parse from CV
- Job Postings / Job Positions
- Applications
- Pending Engagements
- Active Engagements
- Solicitation
- Projects
- Timesheets
- Invoices
- Payments
- Document Library

Layer structure shows many 1920x1250 desktop frames plus repeated card/list/detail states. Several screens are connected to existing Azure work items via Figma node links.

### Candidate Application Design

This page appears to define a candidate/resource-facing portal surface.

Observed areas:

- Candidate sign-in variants.
- Candidate dashboard/profile pages.
- Personal information.
- Applications.
- Interviews.
- Application history.
- Compliance checks.
- Trainings.
- Timesheets.
- Certifications.
- Documents.

The candidate portal shares the same general visual language as the vendor portal but has candidate-specific navigation and data ownership.

### Vendor Enrollment Application Design

This page defines the public and semi-public enrollment flow for new vendors.

Observed frames:

- Vendor Enrollment Landing Page
- Program Requirements
- Sign In
- Vendor Registration Process, multiple steps/states
- New Vendor marker
- New Version marker

The work item `24424 - Vendor Enrollment Application Design` states this flow is for DC OCFO and should include a landing page, program selection, vendor application form, payment terms selection, document upload, and submission confirmation.

### Previous Version

This page contains older 1920x1250 portal screens and historical design groups. Use only as reference if the current pages are missing an edge case.

### web site

This page contains a small website/prototype reference, including `Frame 1000005200` and `uil:play`. It looks more like a supporting concept/prototype area than the main product surface.

### Document Generator

This page contains document-generation UI references, screenshots, a dialog, and frame/container references. It likely supports document template work and generated document flows rather than the main portal navigation.

### useful

This page contains reusable or supporting design references:

- CompleteCertificationDrawer
- Document Generation System UI
- Design Program Requirements Page
- Enhance Candidate Selection Page
- FAQ
- Card references
- Multiple 1920x1250 supporting frames

Use this page as a design reference bucket, not necessarily as production route inventory.

## Portal Information Architecture

### Public / Unauthenticated Area

The public entry points are built around enrollment and program discovery.

Main public pages:

- Vendor Enrollment Landing Page
- Program Requirements
- Vendor Sign In
- Vendor Registration Process

Design intent:

- Explain the staffing program and eligibility.
- Let a vendor inspect program requirements before applying.
- Guide vendors through registration and enrollment prerequisites.
- Push returning users to sign in.
- Keep Avid/MSP contact, terms, privacy, and social/footer information visible.

### Authenticated Vendor Area

The authenticated portal uses a persistent left sidebar and content area.

Primary navigation observed:

- Programs
- Company Information
- Candidates
- Job Positions
- Applications
- Pending Engagements
- Active Engagements
- Solicitation
- Projects
- Timesheets
- Invoices
- Payments
- Document Library

Design pattern:

- Left rail navigation is stable across operational pages.
- Current section is highlighted with a light blue selection state.
- Most pages use a pale blue app background with white cards, tables, or detail panels.
- Content pages are built as list/detail workflows, often with cards at list level and larger forms/tables at detail level.

### Candidate Area

The candidate-facing design uses a similar structure but with a candidate-specific menu.

Observed candidate navigation:

- Personal Information
- Applications
- Interviews
- Application History
- Compliance Checks
- Trainings
- Timesheets
- Certifications
- Documents

This implies candidates/resources have a narrower self-service portal than vendor contacts. Candidate pages should not expose vendor administration, billing, solicitation, or program application actions unless explicitly required.

## Visual System

### Layout

Common frame sizes:

- Authenticated portal: mostly 1920x1250 desktop frames.
- Candidate portal: mostly 1920x1250 desktop frames.
- Public enrollment pages: 1440px wide, variable height pages such as 1785px and 3794px.
- Sign-in pages: 1920px wide, around 1204px high.

Core layout patterns:

- Authenticated pages use left navigation plus a main content panel.
- Public pages use full-width website-style sections.
- Detail pages often use a two-column layout: primary content on the left and supporting cards on the right.
- Cards are white with subtle borders/shadows and small-radius corners.
- Forms are usually two-column inside the main form area, with a right-side instructional copy panel.

### Color And Tone

Observed colors:

- Main authenticated background: very light blue, exposed in Figma as `#F4F9FC`.
- Public page background: mostly white, exposed as `#FFFFFF`.
- Primary action blue: saturated royal/portal blue, used for main buttons and active states.
- Dark navy: used heavily in public footer and sign-in/footer sections.
- Light blue selection states: used for active sidebar item and selected timeline/date states.
- Green appears for positive statuses such as submitted/success-like states.
- Gray appears for disabled buttons, draft statuses, and inactive secondary states.

The overall tone is enterprise/government MSP: clean, restrained, operational, and information-heavy rather than marketing-heavy.

### Typography And Content Density

Typography is compact and dashboard-oriented:

- Small sidebar labels.
- Medium-weight page headings.
- Dense table and card metadata.
- Longer public program descriptions in readable paragraph blocks.

Avoid oversized marketing typography in authenticated areas. The public landing page can be more editorial, but still remains institutional and practical.

### Controls

Recurring controls:

- Primary blue buttons.
- Outline secondary buttons.
- Disabled gray buttons.
- Search input in list pages.
- Filters and dropdowns.
- Table columns with sort icons.
- Upload buttons.
- Status pills.
- Step/progress indicators.
- Accordions for FAQ.
- Timeline/date cards.
- Tooltips for document requirement explanations.
- Save/Submit pairs on transactional pages.
- Previous/Next buttons in multi-step flows.

## Public Vendor Enrollment Flow

### Vendor Enrollment Landing Page

Purpose:

- Introduce available enrollment programs.
- Let vendors start application/enrollment or inspect requirements.
- Provide prep guidance before beginning.

Observed content pattern:

- Program cards near the top.
- Each program card presents a program title, short description, and action buttons.
- A `Before You Start` section summarizes required preparation.
- FAQ appears near the bottom as accordion rows.
- A dark Avid footer closes the page.

Likely actions:

- `Request Enrollment`
- `View Requirements`
- Sign-in path for returning users

Related work items:

- `24735 - Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional`
- `24733 - Connect Vendor Enrollment Portal to Dataverse`
- `24706 - Program Application page add`
- `24590 - vendor enrollment home page`
- `24424 - Vendor Enrollment Application Design`

Implementation notes:

- Landing page should be data-driven from published/open programs.
- Program cards should not hardcode DC OCFO once connected to Dataverse.
- `Request Enrollment` should carry selected Program context into registration/application.
- `View Requirements` should open the program requirements page without requiring authentication, unless business rules say otherwise.

### Program Requirements Page

Purpose:

- Give vendors enough detail to decide whether to enroll.
- Explain program responsibilities, requirements, milestones, and location/contact context.

Observed content:

- Program overview text.
- Vendor responsibilities.
- Enrollment process.
- Program requirements.
- Required certifications.
- Right-side `Program Dates` card.
- Location / DC OCFO card with map.
- Dark Avid footer.

Program date pattern:

- Application Open
- Screening
- Interviewing
- Hiring
- Program Start
- Program End

The active stage is visually emphasized in blue. This aligns with Program milestone automation and active-stage work.

Related work items:

- `24489 - add program details page`
- `24499 - Update Program Active Stage Based on Milestone Date`
- `24735 - Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional`

Implementation notes:

- Treat Program Dates as milestone-derived data.
- The active milestone should reflect Program Active Stage.
- Program status naming should be normalized across `Open Enrollment`, `Active`, `Open`, and internal statuscode values.

### Sign In

Purpose:

- Entry point for existing vendor/candidate users.

Observed pattern:

- Full-bleed photographic mountain/sky background.
- Centered white sign-in card.
- Email field.
- Password field.
- Forgot password link.
- Primary `Sign In` button.
- Small note: authorized users only / activity monitored.
- Contact/vendor representative helper copy.
- Terms of Use and Privacy Policy links.

Implementation notes:

- Sign-in likely maps to Azure AD B2C/Auth0 style portal login.
- The card should remain narrow and focused; avoid adding unrelated portal content to the login screen.
- Public footer/legal links should remain accessible.

## Vendor Registration Process

The Figma page shows multiple `Vendor Registration Process` frames representing steps and states.

Core design pattern:

- Long public form pages on white background.
- Left/main form area.
- Right instructional text panel.
- Footer at bottom.
- `Previous` and `Next` navigation.
- Disabled `Next` state when required data/documents are incomplete.
- Blue active buttons and gray disabled buttons.
- Required fields marked with an asterisk.
- Inline guidance and validation states.

### Company Information Step

Observed fields:

- Legal company name.
- Doing Business As.
- EIN or tax identification.
- Classification / business classification dropdown.
- Company phone number.
- Company email address.
- Company website.
- Individual / Sole Proprietor checkbox.
- Country.
- State/Province.
- Address.
- City.
- Zip/Postal Code.

Right-side guidance explains that company details determine eligibility and application requirements, and should match official records.

Related data:

- Vendor Registration Request.
- Vendor.
- Vendor Contact after approval.

### Primary Contact Step

Observed fields:

- First name.
- Last name.
- Job title.
- Phone number.
- Email address.
- Confirm email address.

Right-side guidance explains that the primary contact receives communications about registration, application status, and ongoing program updates.

Implementation notes:

- Email confirmation validation must be explicit.
- The primary contact should be treated as the first portal user/account for the vendor.
- This aligns with post-approval processing that creates Vendor Contact and B2C account.

### Document Upload Step

Observed required documents:

- W-9 Form
- Certificate of Insurance
- Business License
- CBE Certificate (DC Only)

Observed states:

- `Uploaded` state for a completed document.
- Upload File buttons for missing documents.
- Icon controls near uploaded documents, likely replace/download/refresh/remove style actions.
- Disabled `Next` button when required documents are missing.
- Tooltip/info state for Certificate of Insurance requirements.

Observed Certificate of Insurance tooltip requirements:

- General Liability minimum coverage.
- Workers Compensation requirement.
- Employers Liability minimum coverage.
- Additional insured: District of Columbia must be listed.
- Policy must be active and not expired.

Observed right-side guidance:

- Required documents must be submitted before the application can be reviewed.
- Uploaded files should be clear, valid, and correspond to official records.
- Accepted formats include PDF, JPG, and PNG.
- File size has a maximum limit.
- Incomplete or invalid documents may delay enrollment review.

Related work items:

- `24668 - Vendor Registration Validation & Error Messages`
- `24591 - vendor enrollment registration form`
- `24528 - Post-Approval Processing for Vendor Registration Request`
- `24500 - Auto-Create Enrollment Requirement Assignments on Application Creation`

Implementation notes:

- Document requirements should be data-driven by Program Requirements when possible.
- Fixed requirements like W-9 and insurance may be global prerequisites, but CBE Certificate is program/client/location-specific.
- The UI should clearly distinguish uploaded, missing, invalid, and pending-review documents.

### Payment Terms Selection

The work item `24424` explicitly calls for Payment Terms Selection. The Figma registration process contains multiple frames, but the captured visible slices were strongest for company/contact/document steps.

Implementation expectation:

- Vendor selects a payment term during enrollment/application.
- Selected payment term is stored on Program Enrollment Application.
- Later requirement approval copies payment term to Enrollment and populates Enrollment Discount %.

Related work:

- `24558 - Auto-Populate Discount % on Enrollment`
- `24746 - Update Program Enrollment Application Status Based on Program Requirement Assignments`

### Submission Confirmation

The work item `24424` explicitly calls for a submission confirmation step.

Expected design behavior:

- Confirmation appears after successful submission.
- Vendor should be told that the application was submitted and is awaiting review or verification.
- Next step should explain document/requirement review and how the vendor will be notified.

## Authenticated Vendor Portal

### Global Shell

Observed left navigation includes:

- Programs
- Company Information
- Candidates
- Job Positions
- Applications
- Pending Engagements
- Active Engagements
- Solicitation
- Projects
- Timesheets
- Invoices
- Payments
- Document Library

The shell uses:

- A light app background.
- Fixed left sidebar.
- Icon plus text menu items.
- Active menu highlight.
- A compact footer/contact block near the bottom of the sidebar on some screens.

Implementation notes:

- Navigation visibility/actions must respect Vendor Contact role permissions.
- Vendor role enforcement is frontend action gating plus backend/API authorization.
- Menu-level hiding and action-level disabling should be consistent.

Related work item:

- `24769 - Enforce Vendor Contact Role Permissions in Vendor Portal`

### Programs List

Expected from design/work items:

- Programs are presented as cards/list items.
- Program cards likely include title, client/agency, status, date windows, and actions.
- Open/enrollable programs surface `Request Enrollment` / details actions.

Related work:

- `24488 - add programs list page`

Implementation notes:

- Program cards should be filterable by active/open/enrolled where applicable.
- Program status must reconcile Figma labels such as `Open Enrollment` with Dataverse option values.

### Program Details

Observed DC OCFO example:

- Main page title around `Contingent Workforce Staffing Program`.
- Main content section `Program Overview`.
- Text describes DC OCFO staffing support for temporary and contract-based workforce needs.
- `Required Certifications` list includes examples:
  - PMP Certification
  - Security+ Certification
  - AWS Certification
  - Scrum Master Certification
  - ITIL Foundation
  - CBE Certification
  - Certificate of Insurance
- `Vendor Responsibilities` list includes:
  - Sourcing and submitting qualified candidates.
  - Ensuring candidates meet position and compliance requirements.
  - Maintaining accurate candidate records.
  - Supporting onboarding/background check processes.
  - Complying with program policies and government regulations.
  - Providing ongoing communication with agency representatives.

Right column:

- `Important Information`
  - Program Status: Open Enrollment
  - Client: DC Government
  - Program Manager: Tom Felton
- `Program Dates`
  - Application Open
  - Screening
  - Interviewing
  - Hiring
  - Program Start
  - Program End

Related work:

- `24489 - add program details page`
- `24735 - Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional`

### Company Information

The design contains company information pages and contacts pages.

Expected content:

- Vendor profile/company details.
- Company address and contact details.
- Primary contact.
- Vendor contacts table/list.
- Contact roles and permissions.
- Edit/update actions.

Related work:

- `24485 - update company information pages`
- `24769 - Enforce Vendor Contact Role Permissions in Vendor Portal`

Implementation notes:

- Company profile edit should be role-gated.
- Vendor contact management should expose roles as multi-select or multiple assignments, because a contact can have multiple roles.
- Contact role changes affect portal navigation/action permissions.

### Candidates

Observed and work-item-backed design expectations:

- Candidate list page.
- Candidate cards/details.
- Candidate status management.
- Active Application count.
- Active Engagement count.
- Candidate creation/manage flow.
- Candidate documents, compliance, engagement history.

Status behavior from work item `24490`:

- Active Candidates filter includes statuscode active-like values.
- Change Status prompt offers:
  - Available
  - Limited Availability
  - Inactive
  - Blacklisted
  - Out of Market
- Current status should be excluded from transition options.
- Active Application count is computed on frontend from related applications.
- Active Engagement count is computed from related engagements.

Related work:

- `24490 - update candidates list`
- `24704 - Add Manually add candidate`
- `24677 - Candidate Engagement History`
- `24676 - Candidate documents`
- `24675 - Candidate compliance`

Implementation notes:

- Candidate list should support search/filter and status transitions.
- Counts should match Dataverse relationships to Application and Engagement.
- Avoid showing candidate financial/vendor admin actions in candidate context.

### Job Positions / Job Postings

Design and work items cover:

- Job position list/card updates.
- Job details renamed to Job Information in some work.
- Candidate submission.
- Select existing candidate.
- Manual candidate add.
- Compliance/certification sections.
- Application details tab for submitted candidates.

Related work:

- `24354 - update job(position) card and details to match figma`
- `24381 - rename position details to job information`
- `24679 - Job positions Select Existing Candidate`
- `24680 - Job position Candidates submitted Application Details Tab`
- `24681 - Job position compliance page add`
- `24682 - Job position certifications`

Implementation notes:

- Job Position detail should clearly separate job information, candidates/applications, compliance, certifications, and documents/questions.
- Candidate submission actions should be role-gated for Administrator and Staffing roles.
- Required questions/certifications should match Dataverse-generated job position question/certification records.

### Applications

Design and work items cover:

- Applications list page.
- Application cards.
- Application filters.
- Candidate name consistency.
- Application details.
- Documents styles.
- AI evaluation.
- Closing/canceling workflows.

Related work:

- `24683 - Applications page`
- `24699 - Update Applications filters`
- `24698 - Fix ApplicationsCard styling`
- `24355 - fix applications list candidate name`
- `24356 - fix application details documents styles`
- `24588 - Implement Application AI Evaluation`
- `24577 - Close Job Application and Cancel Pending Interviews`

Implementation notes:

- Application card/list data must be consistent with detail data, especially candidate full name.
- Status and filter labels must map exactly to Dataverse option values.
- Documents should use the same upload/view status language as candidate and enrollment documents where possible.

### Pending Engagements

Design expectations:

- Pending engagement list.
- Pending engagement details.
- Worker profile page/section.
- Onboarding/compliance items.

Related work:

- `24685 - Pending engagements list`
- `24687 - Pending engagements details add worker profile page`

Implementation notes:

- Pending Engagements should focus on pre-start onboarding, compliance, and readiness.
- It should not be confused with active timesheet/invoice workflows.

### Active Engagements

Design expectations:

- Active engagement list.
- Active engagement worker profile.
- Related candidate/resource data.
- Ongoing compliance, documents, timesheets, and offboarding visibility.

Related work:

- `24688 - Active engagement list`
- `24689 - Active engagement worker profile`

Implementation notes:

- Active engagements connect candidate/resource, vendor, job position, agency/client, and timesheets.
- Offboarding visibility should align with offboarding automation work items.

### Solicitation

Design expectations:

- Solicitation page/list/detail.
- Vendor response surface.
- Q&A support.

Related work:

- `24386 - solicitation page add`
- `24756 - Update Solicitation Active Stage Based on Milestone Date`
- `24757 - Generate Vendor Q&A Excel File on Solicitation`

Implementation notes:

- Solicitation stage/date behavior likely mirrors Program milestone logic.
- Vendor Q&A export should use the same questions/answers visible in the solicitation portal area.

### Projects

Design expectations:

- Projects list.
- Project details.
- Milestone-related content.

Related work:

- `24387 - projects page add`
- `24484 - projects list`
- `24762 - Projects Milestones`

Implementation notes:

- Project data should be role-visible to operations roles but not necessarily to billing-only users except read-only access where defined.

### Timesheets

Observed candidate/vendor timesheet design:

- Weekly timesheet table.
- Rows per engagement/assignment.
- Date columns for a week.
- Status column.
- Action column.
- Total work time row.
- `Add timesheet row` action.
- `Copy previous week` action.
- `Save` and `Submit` buttons.
- Draft/submitted style statuses.

Related work:

- `24483 - update timesheets page to match figma`
- `24691 - Timesheets list`
- `24602 - Update Timesheet Approval Process to Support Multi-Level Approval`

Implementation notes:

- Save vs Submit must remain distinct.
- Week details route should handle direct linking.
- Timesheet Manager and Billing Manager role access differ: Timesheet Manager reviews/monitors timesheets; Billing Manager can review timesheets as part of billing.
- Timesheet status transitions should align with invoice linkage and multi-level approval rules.

### Invoices

Design/work items cover:

- Invoice list and detail pages.
- Timesheet-Based invoice pages.
- Fixed Price invoice pages.
- InvoiceCard styling and horizontal scroll issue.
- Manual Add/Remove Timesheets from Invoice actions.

Related work:

- `24470 - update Invoice page`
- `24453 - Invoices page have horizontal scroll Issue with InvoiceCard component`
- `24465 - Add/Remove Timesheets to/from Invoice (Manual Actions)`
- `24463 - Link Timesheets to Invoice on Status Change`
- `24462 - Generate Invoices from Closed Pay Period`

Implementation notes:

- Invoice type is a first-class UI difference: Timesheet-Based vs Fixed Price.
- Invoice pages must expose linked timesheets for Timesheet-Based invoices.
- Billing Manager role can create/submit invoices; Timesheet Manager should not.

### Payments

Design/work items cover:

- Payments page.
- Payment detail page.
- Payment card styling.

Related work:

- `24388 - PaymentsPage add`
- `24692 - Payments`
- `24693 - Payment details`
- `24697 - Fix PaymentCard styling`

Implementation notes:

- Payments appear to be read/review-oriented for vendor users.
- Billing Manager can review payments; Timesheet Manager should not view payments according to role rules.

### Document Library

Observed in authenticated navigation.

Expected content:

- Vendor-level documents.
- Candidate documents.
- Enrollment/program documents.
- Generated documents where appropriate.

Related work:

- `24568 - Deploy Document Templates Solution`
- `24389 - candidate documents page add`
- `24356 - fix application details documents styles`

Implementation notes:

- Document states should be consistent across registration, candidate, application, and engagement surfaces.
- Document generation UI from Figma supporting pages may inform template/generation flows.

## Candidate Portal Design

Candidate Application Design appears to be a parallel self-service surface for candidates/resources.

Observed sign-in:

- Same full-bleed visual background style as vendor sign-in.
- White authentication card.
- Email and password fields.
- Forgot password.
- Primary sign-in button.
- Terms and privacy links.

Observed authenticated candidate sections:

- Personal Information
- Applications
- Interviews
- Application History
- Compliance Checks
- Trainings
- Timesheets
- Certifications
- Documents

Related work:

- `24389 - candidate documents page add`
- `24390 - candidate interviews page add`
- `24391 - candidate application history page add`
- `24600 - Candidate interview page, update interview details screen`
- `24599 - Candidate interview page, add cancel and accept options`
- `24598 - Candidate interview page, update rescheduling form`

Implementation notes:

- Candidate portal should scope all data to the logged-in candidate/contact.
- Candidate timesheets are likely resource-entry oriented, while vendor timesheets are oversight/review oriented.
- Candidate interviews must support accept, cancel, and reschedule actions from the relevant work items.

## Role-Based Portal Access

Source: work item `24769`.

Roles:

- Administrator
- Staffing
- Timesheet Manager
- Billing Manager

### Administrator

Full access to all Vendor Portal actions:

- Manage vendor profile/company details.
- Manage vendor contacts and roles.
- Apply to programs.
- Submit/manage applications.
- Submit candidates.
- Submit solicitation responses.
- Manage projects.
- Access onboarding/offboarding.
- Access timesheets, invoices, and payments.

### Staffing

Operational recruiting role.

Allowed:

- Create/manage candidate profiles.
- Submit candidates to job positions.
- Submit solicitation responses.
- Manage projects.
- Update candidate/application data.
- Coordinate interviews and onboarding/offboarding.

Denied:

- Manage vendor profile/settings.
- Manage vendor contacts.
- Manage bank details.
- View timesheets.
- View/submit invoices.
- View payments.
- Apply to programs.

### Timesheet Manager

Timesheet operations role.

Allowed:

- Review timesheets.
- Monitor submission statuses.
- Read-only access to other pages according to the work item.

Denied:

- Manage vendor profile/settings.
- Manage vendor contacts.
- Manage bank details.
- View/submit invoices.
- View payments.
- Apply to programs.
- Manage candidate profiles.
- Submit candidates.
- Submit solicitation responses.
- Manage projects.

### Billing Manager

Financial operations role.

Allowed:

- Create/submit invoices.
- Review payments.
- Review timesheets.
- Monitor submission statuses.
- Read-only access to other pages except active invoice permissions according to the work item.

Denied:

- Manage vendor profile/settings.
- Manage vendor contacts.
- Manage bank details.
- Apply to programs.
- Manage candidate profiles.
- Submit candidates.
- Submit solicitation responses.
- Manage projects.

Implementation notes:

- Role checks must apply at both navigation and action level.
- Read-only access should not expose misleading enabled buttons.
- Multiple roles per Vendor Contact are allowed, so permissions should be unioned unless business rules define precedence.

## Data Model Mapping

Figma pages map to these VMS records:

- Program
- Program Milestone
- Program Requirement
- Program Certificate
- Vendor Registration Request
- Vendor
- Vendor Contact
- Program Enrollment Application
- Enrollment / `av_vendorcontract`
- Enrollment Requirement Assignment
- Payment Term
- Candidate / Contact
- Job Position / Requisition
- Job Application
- Right to Represent
- Interview
- Engagement
- Offboarding
- Solicitation
- Project
- Timesheet
- Invoice
- Payment
- Document / generated document artifacts
- Notification Template

Important lifecycle mappings:

- Public Program card -> Program.
- Request Enrollment -> Program context passed into Vendor Registration Request or Program Enrollment Application.
- Vendor Registration Process -> Vendor Registration Request.
- Approval of Vendor Registration Request -> Vendor, Primary Contact, optional Program Enrollment Application, B2C account, welcome email.
- Submitted Program Enrollment Application -> Enrollment and Requirement Assignments.
- Requirement Assignment status -> Application status and Enrollment Pending Signature.
- DocuSign completion -> Enrollment Active.
- Candidate submission to Job Position -> Job Application and Right to Represent flows.
- Approved application -> Engagement creation.
- Timesheet submit/approval -> Invoice linkage/generation and payment lifecycle.

## Design/Backlog Cross-Reference

Key work items connected to this Figma design:

- `24424 - Vendor Enrollment Application Design`
- `24488 - add programs list page`
- `24489 - add program details page`
- `24485 - update company information pages`
- `24490 - update candidates list`
- `24354 - update job(position) card and details to match figma`
- `24381 - rename position details to job information`
- `24679 - Job positions Select Existing Candidate`
- `24680 - Job position Candidates submitted Application Details Tab`
- `24681 - Job position compliance page add`
- `24682 - Job position certifications`
- `24683 - Applications page`
- `24685 - Pending engagements list`
- `24687 - Pending engagements details add worker profile page`
- `24688 - Active engagement list`
- `24689 - Active engagement worker profile`
- `24386 - solicitation page add`
- `24387 - projects page add`
- `24483 - update timesheets page to match figma`
- `24470 - update Invoice page`
- `24388 - PaymentsPage add`
- `24692 - Payments`
- `24693 - Payment details`
- `24733 - Connect Vendor Enrollment Portal to Dataverse`
- `24735 - Make 'Request Enrollment' and 'View Requirements' buttons clickable/functional`
- `24769 - Enforce Vendor Contact Role Permissions in Vendor Portal`
- `24668 - Vendor Registration Validation & Error Messages`

Useful Figma node references already captured in work items:

- Programs list: `node-id=4843-8119`
- Program details: `node-id=4870-9281`
- Company information: `node-id=2902-27595`, `node-id=2902-28140`
- Candidates list: `node-id=2902-29047`
- Timesheets: `node-id=1398-1466`, `node-id=892-74047`, `node-id=892-75059`
- Invoice page: `node-id=917-83989`
- Payments: `node-id=892-76904`
- Projects: `node-id=2963-46395`
- Solicitation: `node-id=2935-44144`
- Job position card/details: `node-id=890-54043`, `node-id=2902-9162`
- Candidate documents: `node-id=2902-30374`
- Candidate interviews: `node-id=2902-30622`
- Candidate application history: `node-id=2902-30928`

## UX Principles Inferred From The Design

1. Keep vendor tasks self-service but guided.
   Public registration pages use right-side guidance to reduce failed submissions.

2. Separate public enrollment from authenticated operations.
   Landing/requirements/sign-in/register flows are website-like; operational pages are dashboard-like.

3. Use data cards for scannable summaries.
   Programs, invoices, payments, candidates, and projects are card/list friendly.

4. Use tables for transactional entry and review.
   Timesheets, invoice line items, and application/job-position grids need dense tabular layouts.

5. Surface dates and statuses prominently.
   Program dates, active stages, candidate statuses, timesheet statuses, document statuses, and enrollment/application states are core to the UX.

6. Make documents first-class.
   Registration, candidate, application, certification, and document library flows all rely on upload/review/document state.

7. Keep action availability explicit.
   Disabled Next states, role-gated actions, and status-gated actions are central to the user experience.

8. Preserve trust through institutional details.
   Public pages include contact info, office address, business hours, privacy/terms, and Avid branding.

## Open Questions And Follow-Ups

- Confirm exact Dataverse option labels for Program status: Figma uses labels like `Open Enrollment`; work items mention `Active` and `Open`.
- Confirm whether public `View Requirements` is anonymous or requires sign-in for some programs.
- Confirm whether `Request Enrollment` creates a Vendor Registration Request immediately or starts an unsaved wizard until final submit.
- Confirm which document requirements are global vendor requirements vs program-specific requirements.
- Confirm exact file size limit for uploads.
- Confirm whether Payment Terms are visible before or after document upload in the final wizard order.
- Confirm how returning vendors apply to additional programs: direct Program Enrollment Application vs new Vendor Registration Request.
- Confirm whether Candidate portal and Vendor portal share one authentication app or separate app entry points.
- Confirm whether candidate timesheets and vendor timesheet review pages share the same underlying route components.
- Confirm exact behavior for users with multiple Vendor Contact roles.
- Review Figma comments directly before implementation; comment badges are numerous and likely contain design decisions not exposed in the layer tree.

## Implementation Guidance

- Treat Figma as the UX source for layout, navigation, and interaction intent.
- Treat Dataverse schema, Azure work items, and live app behavior as source of truth for field names, option values, and business rules.
- Build portal pages around reusable shells:
  - Public website/enrollment shell.
  - Authenticated vendor shell.
  - Authenticated candidate shell.
- Keep role/action permission logic centralized and test it per role.
- Keep document upload state components reusable across registration, candidate documents, application documents, and certifications.
- Keep status pills and date/timeline components reusable across Programs, Applications, Engagements, Timesheets, Invoices, and Payments.
- Use the design's dense enterprise layout for operational pages; avoid marketing-style hero layouts inside authenticated portal screens.
- Use exact Figma Dev Mode values when implementing pixel-perfect UI, because this text context intentionally avoids storing image exports or full screenshots.
