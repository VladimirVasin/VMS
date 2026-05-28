# QA Test Report: ADO 23420 - Auto-Generate Job Position Questions on Job Position Creation

## Summary

| Field | Value |
| --- | --- |
| Test date | 2026-05-28 |
| Tester | Codex, using the authenticated Chrome/Dynamics session provided in the workspace |
| Environment | SANDBOX |
| Application | MSP - Vendor Management System Administration |
| Source work item | [ADO 23420 - Auto-Generate Job Position Questions on Job Position Creation](https://dev.azure.com/AvidSys/VMS/_workitems/edit/23420/) |
| Overall result | PASS, with one verification caveat |

The tested user story is ready from the main happy-path perspective: when a new Job Position/Job Posting is created, the system generated a Job Posting Question from a Global question reference and linked it back to the created Job Posting. A normal update to the same Job Posting did not create a duplicate generated question.

The remaining caveat is that the full source reference list could not be independently enumerated during this run. The generated question was verified against the visible Global reference record used by the automation, but the test did not prove that every Global reference in the environment was copied if more than one exists.

## Participating Records And Views

| Type | Name / Identifier | Link |
| --- | --- | --- |
| Azure DevOps item | 23420 - Auto-Generate Job Position Questions on Job Position Creation | [Open work item](https://dev.azure.com/AvidSys/VMS/_workitems/edit/23420/) |
| Dynamics app entry point | MSP - Vendor Management System Administration, Clients list URL originally provided for the session | [Open app/list](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entitylist&etn=av_client&viewid=0a7e19f1-6eec-4ea5-8e36-43cbb70751bb&viewType=1039) |
| Verification list view | Job Postings - All Job Postings (`av_requisition`) | [Open list view](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entitylist&etn=av_requisition&viewid=e820c494-361e-4031-9af9-d9f9296f8467&viewType=1039) |
| Verification list view | Job Posting Questions - Active Job Position Questions (`av_requisitionquestion`) | [Open list view](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entitylist&etn=av_requisitionquestion&viewid=27c6a288-bcc6-4aaf-9817-5cf70f1201ff&viewType=1039) |
| Created / updated record | Job Posting `REQ-26-1019` (`av_requisition`) | [Open record](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisition&id=f4c41a28-bd5a-f111-a825-3833c5d9bcac) |
| Generated child record | Job Posting Question `Skill-26-1107` (`av_requisitionquestion`) | [Open record](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisitionquestion&id=32e8282e-bd5a-f111-a825-3833c5d9bcac) |
| Reference/configuration record | Job Posting Question Reference `Test Global` (`av_question`) | [Open record](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_question&id=70cd6621-391d-f111-88b3-7c1e5267f8c3) |

## Requirement Under Test

Source: [ADO 23420](https://dev.azure.com/AvidSys/VMS/_workitems/edit/23420/)

Expected behavior from the user story:

- Trigger: a Job Position (`av_requisition`) record is created.
- The system retrieves all Job Position Question Reference records where `Scope = Global`.
- For each matching reference record, the system creates a new Job Position Question.
- The generated Job Position Question maps:
  - `Job Position` to the newly created Job Position.
  - `Job Position Question Reference` to the Global reference record.

## Test Plan

### Objective

Verify that creating a new Job Position/Job Posting automatically creates Job Posting Question records from Global reference questions, and verify that a normal update to the Job Posting does not create duplicate child questions.

### Scope

In scope:

- Create a new Job Posting record in the sandbox Dynamics app.
- Verify generated Application Questions on the created record.
- Open the generated child Job Posting Question record.
- Open the referenced Global question configuration record.
- Update the same Job Posting once and re-check the generated question count.

Out of scope for this run:

- Exhaustive validation against every Global and non-Global reference record, because the full reference list/table was not directly accessible during the session.
- Security-role validation.
- Cleanup/deletion of the created test record, because the record is retained as evidence for the QA report.

### Test Data

| Field | Value |
| --- | --- |
| Job Title | `QA 23420 Auto Questions 2026-05-28T17-45-45-348Z` |
| Pay Rate (Base) | `1` |
| Follow-up update field | `Hours/Units per day = 1` |
| Expected Global reference used by automation | `Test Global` |

## Test Execution

### TC-23420-001: Create a Job Posting and verify automatic question generation

| Field | Value |
| --- | --- |
| Status | PASS |
| Primary record | [REQ-26-1019](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisition&id=f4c41a28-bd5a-f111-a825-3833c5d9bcac) |
| Generated record | [Skill-26-1107](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisitionquestion&id=32e8282e-bd5a-f111-a825-3833c5d9bcac) |
| Reference record | [Test Global](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_question&id=70cd6621-391d-f111-88b3-7c1e5267f8c3) |

Steps performed:

1. Opened the sandbox Dynamics app.
2. Navigated to the Job Postings table/list view.
3. Started a new Job Posting record.
4. Entered `Job Title = QA 23420 Auto Questions 2026-05-28T17-45-45-348Z`.
5. Attempted to save and observed the required validation for `Pay Rate (Base)`.
6. Entered `Pay Rate (Base) = 1`.
7. Saved the record successfully.
8. Confirmed the created Job Posting was `REQ-26-1019` and remained in `Draft` status.
9. Opened the `Questionnaire & Screening` tab.
10. Inspected the `Application Questions` subgrid.
11. Opened the generated Job Posting Question row.
12. Verified that the generated row linked back to Job Posting `REQ-26-1019`.
13. Verified that the generated row referenced question `Test Global`.
14. Opened the `Test Global` reference/configuration record and verified it is a Global reference.

Expected result:

- Saving the new Job Posting creates one Job Posting Question per Global reference question.
- The generated question is linked to the newly created Job Posting.
- The generated question is linked to the Global reference question.

Actual result:

- A generated Application Question was visible on the created Job Posting.
- The generated child record was `Skill-26-1107`.
- `Skill-26-1107` had Job Posting lookup `REQ-26-1019`.
- `Skill-26-1107` had Question lookup `Test Global`.
- The `Test Global` reference/configuration record showed:
  - `Question = Test Global`
  - `Scope = Global`
  - `Question Type = Boolean`
  - `Required = No`

Result: PASS.

### TC-23420-002: Update the same Job Posting and verify no duplicate question is created

| Field | Value |
| --- | --- |
| Status | PASS |
| Primary record | [REQ-26-1019](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisition&id=f4c41a28-bd5a-f111-a825-3833c5d9bcac) |
| Generated record checked | [Skill-26-1107](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisitionquestion&id=32e8282e-bd5a-f111-a825-3833c5d9bcac) |

Steps performed:

1. Opened the existing Job Posting `REQ-26-1019`.
2. Updated `Hours/Units per day` to `1`.
3. Saved the Job Posting.
4. Reopened/checked the `Questionnaire & Screening` tab.
5. Inspected the `Application Questions` subgrid again.
6. Counted visible generated rows for `Test Global`.

Expected result:

- Updating an existing Job Posting should not re-run the create-only behavior in a way that creates duplicate Job Posting Questions.
- The `Application Questions` grid should still contain only the previously generated `Test Global` row for this Job Posting.

Actual result:

- The update saved successfully.
- The `Application Questions` subgrid still showed one `Test Global` row.
- No duplicate generated question was observed.

Result: PASS.

### TC-23420-003: Verify all Global references are copied and non-Global references are excluded

| Field | Value |
| --- | --- |
| Status | NOT FULLY VERIFIED |
| Related reference record verified | [Test Global](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_question&id=70cd6621-391d-f111-88b3-7c1e5267f8c3) |

Steps attempted:

1. Tried to identify the reference/configuration table directly from the app navigation and likely entity names.
2. Opened the generated question and then opened the referenced `Test Global` configuration record.
3. Verified that `Test Global` has `Scope = Global`.

Expected result:

- The set of generated Job Posting Questions should match all active Global reference questions.
- Non-Global reference questions should not be generated by this create trigger.

Actual result:

- The generated question was correctly linked to a Global reference.
- The complete reference set was not independently enumerated in this run.

Result: NOT FULLY VERIFIED.

## Additional Observations

- `Pay Rate (Base)` is required for saving a Job Posting in this environment, even though it is not part of the user story being tested.
- The relevant verification surface is `Questionnaire & Screening` -> `Application Questions`.
- The `Public Questions` tab showed an Opportunity Questions surface and was not the correct place to verify this story.
- Direct browser attempts against Dataverse API-style URLs were blocked in the current Chrome session, so the validation was completed through the Dynamics UI.

## Final Assessment

ADO 23420 can be considered passed for the main create-trigger behavior verified through the UI:

- New Job Posting created: [REQ-26-1019](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisition&id=f4c41a28-bd5a-f111-a825-3833c5d9bcac)
- Generated Job Posting Question created: [Skill-26-1107](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_requisitionquestion&id=32e8282e-bd5a-f111-a825-3833c5d9bcac)
- Global reference used: [Test Global](https://orgf00042a4.crm.dynamics.com/main.aspx?appid=02587e5b-187d-f011-b4cb-7c1e5217c8fa&forceUCI=1&pagetype=entityrecord&etn=av_question&id=70cd6621-391d-f111-88b3-7c1e5267f8c3)
- No duplicate question was created after a normal update to the same Job Posting.

Recommended follow-up before closing the story without caveats:

1. Confirm the complete active Global reference-question count in the environment.
2. Compare that count to the generated Application Questions count on a fresh Job Posting.
3. Add or expose a direct QA view for Job Position Question Reference records if the table is expected to be tested regularly.
