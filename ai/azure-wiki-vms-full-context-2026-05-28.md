# Azure DevOps Wiki Full Context

Captured: 2026-05-28.

Source: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/261/VMS-(MSP)-Solution-Overview

Scope: all 8 pages visible in the VMS.wiki tree from the Azure DevOps Wiki UI.

## VMS (MSP) Solution Overview

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/261/VMS-(MSP)-Solution-Overview

This solution supports management of Vendors, Programs, Candidates, and Enrollments across multiple Clients and Agencies.

Core Concepts
A Client represents an organization (e.g., government entity)
A Client can have multiple Agencies
Programs are defined under a Client and represent initiatives Vendors can enroll into
Vendors participate in Programs through Enrollments
Contacts (Candidates/Resources) can be associated with Vendors and participate in Engagements
Key Relationships
Client -> Agency (1:N)
Client -> Program (1:N)
Vendor -> Enrollment (1:N)
Program -> Enrollment (1:N)
Vendor -> Vendor Contact (1:N)
Vendor -> Candidate/Resource (1:N)
Contact (Candidate/Resource) -> Worker Profile -> Engagement

## Vendor Portal

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/274/Vendor-Portal

_No content body captured; page was visible but empty apart from metadata/comments._

## Vendor Registration & Enrollment Process

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/262/Vendor-Registration-Enrollment-Process

1. Entry Points

A Vendor can enter the system in two ways:

Option A: Direct Registration
Vendor submits Vendor Registration Request
Later applies to Programs
Option B: Registration via Program Application
Vendor selects a Program in the portal
Submits registration as part of application
System stores Program selection temporarily
Program Enrollment Application is NOT created yet
2. Vendor Registration Request

Vendor submits:

Vendor details
Primary Contact
Optional Program selection

Record created:

Vendor Registration Request
Status = Pending Review
3. Review and Decision
Approve

Triggers:

Vendor creation
Primary Contact creation
B2C account creation
Decline
Status = Declined
Reason + Comments required
4. Post-Approval Processing

On approval:

Create Vendor
Create Primary Contact
Link Contact to Vendor

If Program was selected:

Create Program Enrollment Application (Draft)
Use the Program selection captured during registration
5. Program Enrollment Application

Application lifecycle:

Draft
Submitted
Under Review
Approved
Rejected
6. Enrollment Application Questions

Questions are defined at the Program level and represent the questionnaire Vendors must complete during application.
Examples:

Business qualifications
Compliance declarations
Program-specific requirements
7. Enrollment Application Question Responses

When a Program Enrollment Application is created:

Create Enrollment Application Question Response records
One record per question defined on the Program
Each Response record:
Linked to Program Enrollment Application
Contains:
Question (copied as text)
Response (answer provided by Vendor)
Important Design Note
There is no lookup/reference to the original Question record
Question text is copied at the time of creation
Ensures historical consistency even if Program questions change later
8. Enrollment Requirements & Assignments

Requirements are defined at Program level.

Assignment Creation
Enrollment Requirement Assignments are created prior to Application approval
Created when:
Application is submitted

Each assignment:

Links Enrollment Requirement Assignment to the Program Enrollment Application
Tracks completion status (e.g., Assigned, Verifying, Approved, Rejected)
9. Application Submission -> Enrollment Creation

When Application is Submitted:

Create Enrollment with:
Status = Pending Activation
Vendor
Program
Link Enrollment Requirement Assignments to the Enrollment
10. Application Review

Internal users review Application:

Validate requirements completion
Approve or reject Application
11. Enrollment Activation

Once Application is approved:

Enrollment transitions from:
Pending Activation -> Active
12. Enrollment Lifecycle
Pending Activation
Active
Expired (auto when End Date reached)
Terminated (manual)
Termination

Requires:

Termination Reason

## Position-to-Engagement Process

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/266/Position-to-Engagement-Process

Overview

The process models how work demand (Job Positions) is created under a Program and fulfilled through Engagements (actual worker assignments).
At a high level:

Program defines the initiative
Job Position defines the demand (role/requisition)
Engagement represents the fulfillment (worker assigned)
Process Flow
1. Program Setup
Program is created under a Client
Defines timeframe and scope
2. Job Position Creation (Requisition)
Job Position is created under:
Program
Agency
Represents a role to be filled (e.g., Analyst, Developer)
3. Engagement Creation (Fulfillment)
When a worker is selected:
An Engagement is created
Engagement links:
Job Position
Vendor
Worker Profile
Agency
4. Worker Assignment
Each Engagement has exactly one Worker Profile
Worker Profile represents the individual performing the work
5. Lifecycle of Engagements

A Job Position can have:

One or more Engagements over time, for example:
Initial hire
Replacement (backfill)
Reassignment
This means:
Engagements are not strictly 1:1 with Job Position
They are time-based and sequential (or potentially parallel)

## Interview Scheduling Module

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/244/Interview-Scheduling-Module

The Interview Scheduling Module allows the HR team to schedule interviews with candidates based on interviewer availability configured in the system. The system automatically determines mutually available time slots across selected interviewers and presents those slots to the scheduler. The selected slot is then sent to the candidate through the Candidate Portal as an invitation.

Candidates can accept the proposed time or reject it and propose an alternative. Interviews can also be rescheduled from the Model Driven App when necessary. The module ensures interviews are scheduled using interviewer availability rules, avoids scheduling conflicts, and maintains a complete history of scheduling changes.

## Background Checks & Trainings Process

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/103/Background-Checks-Trainings-Process

Background Checks (BC) and Trainings (T) are defined once and reused across Agencies and Engagements; when a person completes a Requirement for one Engagement, matching Requirements on other Engagements move to Verifying and shared evidence is copied so each Agency can review and approve independently. This document explains the creation flow, data relationships, automated status transitions and expected behaviors.

## Timesheet Approval Process

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/270/Timesheet-Approval-Process

Overview

The Timesheet Approval process ensures that submitted Timesheets are reviewed and approved by the appropriate stakeholders based on the related Engagement configuration.
The process supports:

Single-level approval (Engagement Approver only)
Multi-level approval (Engagement Approver -> Program Manager)
Key Entities
Timesheet - record submitted by a Resource for work performed
Engagement - defines assignment and approval configuration
Program - used to identify Program Manager for final approval
Configuration
On Engagement
Approver - user responsible for Level 1 approval
Multi-level Approval Required (Yes/No)
On Program
Program Manager - user responsible for Level 2 approval
Process Flow
1. Timesheet Submission
Resource submits Timesheet
Status = Submitted
2. Level 1 Approval (Engagement Approver)
Timesheet is routed to Engagement Approver
Appears in view:
Timesheets To Approve
Available Actions
Approve
Reject
3. Approval Logic
If Multi-level Approval = No
On Approve:
Status -> Approved
Process completes
If Multi-level Approval = Yes
On Approve:
Status -> Pending Program Approval
Timesheet is routed to Program Manager
4. Level 2 Approval (Program Manager)
Applies only when Status = Pending Program Approval
Appears in view:
Timesheets Pending Final Approval
Available Actions
Approve
Reject
5. Final Outcome
Approve
Status -> Approved
Reject
Status -> Rejected
Manual Override

Authorized users (e.g., Program Manager, Client Approver, System Administrator) can override decisions:

Available when Status is:

Approved
Rejected
Pending Program Approval

Status -> Manual Override

Status Model
Draft
Submitted
Pending Program Approval
Approved
Rejected
Manual Override
Views
Timesheets To Approve
Status = Submitted
Engagement Approver = current user
Timesheets Pending Final Approval
Status = Pending Program Approval
Program Manager = current user
Notifications
Weekly Reminder (Monday)

Automated notifications are sent:

To Engagement Approvers:
List of Timesheets with Status = Submitted
To Program Managers:
List of Timesheets with Status = Pending Program Approval
Each notification includes:
Engagement
Resource
Timesheet period
Audit & Tracking

Each approval action captures:

Reviewed By (User)
Reviewed On (Date/Time)
Rejection / Override Reason (if applicable)
Key Business Rules
Only Engagement Approver can approve/reject at Level 1
Only Program Manager can approve/reject at Level 2
Multi-level approval must be respected when enabled
Timesheets cannot skip approval levels
All actions must be auditable
Summary Flow
Timesheet submitted
Engagement Approver reviews
If multi-level:
Routed to Program Manager
Final approval or rejection
Optional manual override

## Engagement Offboarding Process

Azure URL: https://dev.azure.com/AvidSys/VMS/_wiki/wikis/VMS.wiki/271/Engagement-Offboarding-Process

Overview

Offboarding ensures controlled and compliant disengagement of a Resource from an Engagement, including:

Work cessation
Access removal
Asset return (equipment, badges)
SLA adherence
Exit feedback collection
Tracking of removal reasons
The process is configurable per Client and fully auditable.
Process Flow
1. Offboarding Initiation

Offboarding is triggered when:

Engagement reaches end date
Resource is terminated early
Resource is deemed unqualified
Client directs removal or re-assignment

System actions:

Create Offboarding record

Capture:

Resource
Engagement

Set Status = Not Started

2. Task Assignment Generation

System retrieves Offboarding Tasks configured for the Client and creates:

Offboarding Task Assignments (one per task)

Each assignment includes:

Due Date (based on SLA Days)
Assigned To (Contact or User)
Status = Assigned
3. Offboarding Execution

Assigned users complete required tasks, such as:

Work cessation
Access removal
Equipment return
Badge return
4. SLA Enforcement

Each task is tracked against SLA. For example:

Onsite returns:
Must be completed by end of workday (SLA Days = 0)
Offsite returns:
Must be completed within defined SLA (default 7 business days)

If:

Current Date > Due Date AND Status != Completed -> mark as Overdue
5. Asset Compliance

If assets are not returned:

Task remains incomplete or overdue
Replacement cost responsibility applies
Flag for reporting and follow-up
6. Exit Feedback
Resource submits Exit Feedback
Stored on Offboarding record
Retained for audit
7. Offboarding Completion

Offboarding is completed when:

All required tasks are completed
System updates:
Status -> Completed
Completed On date populated

