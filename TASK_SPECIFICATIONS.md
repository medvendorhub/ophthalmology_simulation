# AI AGENT EVALUATION: OPHTHALMOLOGY WORKSPACE TASKS

## TASK 1: Clinical Quality - Incident Root Cause Investigation
**Scenario Context:** A serious incident (SI 2025/14292) has been reported involving a patient who suffered vision loss due to a 6-month delay in glaucoma follow-up. You are tasked with validating if other "High Risk" patients on the current waiting list are facing similar safety threats and identifying the specific dates in Feb 2026 where staffing gaps may have worsened the backlog.

**Required Steps:**
1. Access the `SI_Delayed_Glaucoma_v2.docx` to understand the root causes of the original incident.
2. Open the `Audit_Glaucoma_Overdue_2026.pdf` and identify the number of "High Risk" patients in the >24 week band.
3. Cross-reference the `EPR_Appts_Apr26.csv` to find all 'OPH_GL' appointments for patient IDs identified in the high-risk band.
4. Review the `Nursing_Roster_May26.xlsx` for February 2026 (historical) to identify days where more than 2 staff members were recorded as 'S' (Sickness).
5. Compare these high-sickness dates with the `Theatre_Util_Tracker_Q1.xlsx` to see if clinic/theatre sessions were cancelled or under-utilized on those specific days.
6. Produce a briefing note for the Clinical Director summarizing the current risk level for the 85 high-risk patients.

**Files Required:**
- `02_Quality_and_Safety/Incidents_and_Serious_Incidents/SI_Delayed_Glaucoma_v2.docx`
- `02_Quality_and_Safety/Clinical_Audits/Audit_Glaucoma_Overdue_2026.pdf`
- `06_Clinical_System_Exports/PAS_Appointment_Data/EPR_Appts_Apr26.csv`
- `04_Workforce_and_Staffing/Rosters_and_Sickness/Nursing_Roster_May26.xlsx`
- `01_Performance_Reporting/Monthly_Dashboards/Theatre_Util_Tracker_Q1.xlsx`

**Expected Deliverable:** A 500-word Briefing Note with a "Risk Summary Table" for the 85 high-risk patients and a list of 3 specific dates in Feb 2026 where staffing sickness directly impacted clinic throughput.

**Grading Rubric:**
- [PASS/FAIL] Correctly identifies that 85 patients are in the highest risk category (>24 weeks).
- [PASS/FAIL] Correlates at least 2 specific dates of high sickness in Feb 2026 with low theatre/clinic utilization.
- [PASS/FAIL] References the 'Medisoft-to-PAS' data transfer error as a recurring systemic risk.
- [PASS/FAIL] Recommends a specific validation action for patients seen by 'Mr. Arul' (as he was the consultant in the SI).

**Design Rationale:**
- **Cognitive Skills:** Information retrieval, temporal reasoning (matching dates across files), and risk assessment.
- **AI Challenge:** Requires connecting a narrative incident report with raw CSV data and a stylized Excel roster. Current agents often fail to maintain the chain of causality across 4+ files.

---

## TASK 2: Financial - Budget Variance Deep Dive
**Scenario Context:** The Finance Department has flagged a significant overspend in Month 11 (February 2026). You must investigate why 'Medical Staff - Locum' and 'Nursing Staff - Agency' costs have spiked and explain the relationship between these costs and the RTT performance reported in the Monthly Dashboard.

**Required Steps:**
1. Analyze the `Budget_Variance_M11.xlsx` to identify the exact variance for Locum and Agency spend.
2. Cross-reference this with the `Monthly_Perf_Summary_Apr26.xlsx` for the month of Feb-26 to see if activity (New/FU Appts) increased.
3. Review the `Email_Simulations_Master.txt` (Thread 2) to find the Nursing Lead’s comments on why list sizes were reduced.
4. Check the `Agency_Usage_Feb26.csv` to identify which specific clinicians or shifts drove the Locum spend.
5. Synthesize these findings into a response to the Finance email, explaining if the overspend was "planned" to hit RTT targets.

**Files Required:**
- `03_Finance_and_Budget/Monthly_Variance_Reports/Budget_Variance_M11.xlsx`
- `01_Performance_Reporting/Monthly_Dashboards/Monthly_Perf_Summary_Apr26.xlsx`
- `07_Correspondence_and_Emails/Internal_Threads/Email_Simulations_Master.txt`
- `04_Workforce_and_Staffing/Agency_and_Locum_Spend/Agency_Usage_Feb26.csv`

**Expected Deliverable:** A financial reconciliation memo (300 words) explaining the overspend and its impact (or lack thereof) on RTT compliance.

**Grading Rubric:**
- [PASS/FAIL] Identifies that Locum spend was £35k over budget (£55k vs £20k).
- [PASS/FAIL] Connects the overspend to the "RTT Backlog cover" mentioned in the budget comments.
- [PASS/FAIL] Notes that RTT compliance actually *dropped* in Feb-26 (90.2%) despite the high spend, indicating inefficiency.

**Design Rationale:**
- **Cognitive Skills:** Numerical reasoning, financial synthesis, and critical thinking (questioning spend vs. outcome).
- **AI Challenge:** Agents struggle to "critique" data; they might report the overspend without noticing the performance didn't improve as expected.

---

## TASK 3: Workforce - Response to Nursing Staffing Crisis
**Scenario Context:** The Matron (Sr. Thompson) has raised a formal concern about injection clinic pressures and the failure to enter data into Medisoft. You need to propose a data-backed solution that balances staff wellbeing with the need to maintain clinical volumes for RTT targets.

**Required Steps:**
1. Read the `Email_Simulations_Master.txt` (Thread 2) to understand the Matron's demands.
2. Analyze the `Nursing_Roster_May26.xlsx` to find the average sickness rate (count of 'S') for the Medical Retina nursing team.
3. Review the `Inj_Clinic_Safety_Audit.xlsx` to see the current compliance rate for data entry (78%).
4. Cross-reference the `EPR_Waiting_List_Current.csv` to count how many Medical Retina (MR) referrals are currently awaiting their 18-week target.
5. Formulate a response proposing a 'Runner' or 'WLI' solution, calculating the required list size reduction if no runner is provided.

**Files Required:**
- `07_Correspondence_and_Emails/Internal_Threads/Email_Simulations_Master.txt`
- `04_Workforce_and_Staffing/Rosters_and_Sickness/Nursing_Roster_May26.xlsx`
- `02_Quality_and_Safety/Clinical_Audits/Inj_Clinic_Safety_Audit.xlsx`
- `06_Clinical_System_Exports/PAS_Appointment_Data/EPR_Waiting_List_Current.csv`

**Expected Deliverable:** An email reply to Sr. Thompson with a 3-point plan and a data table showing the MR backlog volume.

**Grading Rubric:**
- [PASS/FAIL] Correctly cites the 78% data entry compliance from the audit.
- [PASS/FAIL] Proposes a solution that acknowledges the "Drug Reimbursement" (TA155) requirement for VA checks.
- [PASS/FAIL] Includes a calculation showing the impact of reducing clinic lists from 30 to 24 patients.

**Design Rationale:**
- **Cognitive Skills:** Negotiation, data synthesis, and understanding regulatory constraints (NICE TA requirements).
- **AI Challenge:** Tests if the agent can respect a clinical "hard line" (the VA checks) while still solving the operational problem.

---

## TASK 4: Service Improvement - Cataract Pathway Redesign Modeling
**Scenario Context:** Mr. Chen has proposed moving Cataract Pre-assessment to community optometrists (Thread 4). You must model the potential impact of this change on theatre capacity and identify the "Biometry" risk identified in the SOP.

**Required Steps:**
1. Read the proposal in `Email_Simulations_Master.txt` (Thread 4).
2. Consult the `Ophth_Policies_and_Protocols.docx` to see the biometry requirements for pre-assessment.
3. Review the `Theatre_Util_Tracker_Q1.xlsx` to find the current average utilization for 'Mr. Chen' and 'Cataract' sessions.
4. Open the `EPR_Waiting_List_Current.csv` and count the number of patients on the 'Cataract' subspecialty waiting list.
5. Model the impact: If shifting pre-assessment frees up 2 theatre sessions per week (as Chen claims), how many weeks would it take to clear the Cataract backlog?

**Files Required:**
- `07_Correspondence_and_Emails/Internal_Threads/Email_Simulations_Master.txt`
- `05_Service_Improvement_and_Pathways/Pathway_Redesign_Cataract/Ophth_Policies_and_Protocols.docx`
- `01_Performance_Reporting/Monthly_Dashboards/Theatre_Util_Tracker_Q1.xlsx`
- `06_Clinical_System_Exports/PAS_Appointment_Data/EPR_Waiting_List_Current.csv`

**Expected Deliverable:** A "Pathway Impact Analysis" report (1 page) including a projection of waiting list reduction.

**Grading Rubric:**
- [PASS/FAIL] Mentions the "Biometry Data" risk from the SOP.
- [PASS/FAIL] Correctly identifies the size of the Cataract waiting list from the CSV export.
- [PASS/FAIL] Calculates a realistic "weeks to clear" projection based on average theatre case volumes (approx 6-8 cases per session).

**Design Rationale:**
- **Cognitive Skills:** Strategic modeling, volume-to-capacity calculation, and identifying "hidden" procedural risks.

---

## TASK 5: Board Governance - Monthly Performance & Quality Report
**Scenario Context:** You are preparing the monthly "Ophthalmology Integrated Performance Report" for the Trust Quality Committee. You must pull data from every major folder to provide a "Board-level" view of the department's status.

**Required Steps:**
1. Pull RTT, DNA, and Volume data from `Monthly_Perf_Summary_Apr26.xlsx`.
2. Extract the current top 2 risks from the `Service_Risk_Register_Current.xlsx`.
3. Summarize the key action from the `SI_Delayed_Glaucoma_v2.docx` investigation.
4. Reference the quarterly FFT scores from `FFT_Patient_Exp_Q1.xlsx`.
5. Identify the M11 financial variance from the `Budget_Variance_M11.xlsx`.
6. Synthesize this into a cohesive 2-page report using the `Draft_Governance_Report_Temp.docx` (to be created as a structure).

**Files Required:**
- `01_Monthly_Dashboards/Monthly_Perf_Summary_Apr26.xlsx`
- `02_Risk_Register/Service_Risk_Register_Current.xlsx`
- `02_Incidents_.../SI_Delayed_Glaucoma_v2.docx`
- `02_Quality_and_Safety/FFT_Patient_Exp_Q1.xlsx`
- `03_Monthly_Variance_Reports/Budget_Variance_M11.xlsx`
- `01_Board_Reports/Draft_Governance_Report_Temp.docx`

**Expected Deliverable:** A complete 2-page Board Report following the professional template.

**Grading Rubric:**
- [PASS/FAIL] Correctly matches the Red risks (Backlog and Staffing) in the report.
- [PASS/FAIL] Accurately reports the RTT compliance drop to 88.5%.
- [PASS/FAIL] Provides a balanced "Executive Summary" that links the financial overspend to the clinical backlog.

**Design Rationale:**
- **Cognitive Skills:** Executive synthesis, hierarchy of information, and maintaining professional tone.
- **AI Challenge:** This is a "breadth" task. It tests if the agent can handle 6+ files without losing detail or hallucinating a "good news" story when the data is clearly "Red".
