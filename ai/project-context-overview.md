# VMS Project Context Overview

Captured: 2026-05-28 from Azure DevOps Work items -> Recently updated plus all visible Feature child lists.

The crawl captured 181 work items: 170 USER STORY, 10 FEATURE, 1 TASK.

## State Snapshot

- New: 44
- Completed: 20
- In Progress: 14
- Ready for QA: 96
- Testing: 3
- Removed: 4

## Main Product Areas

- Client & Contract Management: New module setup/reuse from HCM contracts. One child story was visible.
- Performance Review: Review schedules, AI goal generation, checkpoints, review form generation, overdue/notification handling, evaluation, and goal feedback.
- Job Application Management: Application pages, candidate/application details, submission, Right to Represent creation/expiration/emailing, approval to engagement creation, qualification/disqualification TBD, candidate compliance, AI screening, liveness, and document styling.
- Programs&Enrollment: Vendor enrollment portal, registration validation, program pages, enrollment requirements, certificates, application/enrollment automation, payment terms, DocuSign contract signature. See dedicated Programs&Enrollment files for deeper detail.
- System Security&General Administration: Vendor contact role permissions, document template deployment, shared auth/query plumbing, and shared UI/component cleanup.
- Procurement: Solicitation pages, solicitation milestones/stages, vendor Q&A Excel generation and document storage.
- Financials: Invoices, payments, payment details, timesheet-to-invoice linking, and financial UI/card fixes.
- Interview Scheduling: Interview scheduling, rescheduling, time slot configuration/generation, history, completion automation, candidate interview details, accept/cancel options.
- Engagement Management: Active/pending engagements, worker profile, offboarding creation/task assignment/status automation/manual termination, compliance/training requirements, timesheets, payments, and related detail/list pages.
- Requisition Management: Publishing requisitions, job generator behavior, AI prompt/question generation, requisition-to-engagement data propagation, and Job Title lookup settings.

## Important Notes

- The Azure DevOps project uses `Feature` and `User Story` much more than strict `Task`; only one captured item had Work Item Type `TASK`. In conversation, treat "tasks" as colloquial unless the user explicitly says Work Item Type = Task.
- `Recently updated` alone missed 20 visible child work items, so the final capture also opened every captured Feature and merged its visible children.
- The dedicated Programs&Enrollment context remains in `programs-enrollment-process-overview.md` and `azure-feature-24497-programs-enrollment.md`.
- `azure-work-items-full-context-2026-05-28.md` is the detailed human-readable dump.
- `azure-work-items-recently-updated-2026-05-28.json` is the machine-readable captured source.
- Some work items have empty Description fields in Azure DevOps; those are preserved as empty rather than inferred.
