# CareClaim - Health Insurance Claim Tracking System Application

An enterprise health insurance claim tracking system application featuring **three distinct, synchronized portals** tailored for **Patients / Policyholders**, **Claims Adjudication Officers**, and **System Administrators**.

All application files are located on your Desktop at:
`C:\Users\MSI\Desktop\HealthInsuranceClaimSystem`

---

## 🚀 Portals Architecture & Feature Matrix

### 👤 Portal A: Patient / Policyholder Portal
- **User Registration and Login:**
  - Create a new account with legal name, email, password, phone, date of birth, residential address, and insurance plan selection.
  - Login using email and password, with 1-click instant demo logins for fast evaluation.
  - Forgot password option to securely reset password with registered email.
- **Policy Management:**
  - View insurance policy details (plan name, insurer, cashless hospital network).
  - Check policy number, validity dates, and coverage status.
  - View coverage amount and remaining balance with dynamic live progress bar that updates as claims are disbursed.
- **Submit New Claim:**
  - Enter patient details (patient name, age, gender, relation: Self, Spouse, Child, Parent).
  - Enter hospital details (hospital name, city, room category, admission & discharge dates).
  - Enter itemized treatment expenses (hospital room charges, surgeon/doctor fees, pharmacy & medicines, diagnostic tests, other fees -> auto-calculated total).
  - Upload medical bills and reports (file selector, categorized document tags for Hospital Bill, Medical Report, Discharge Summary, and Doctor Prescription).
- **Track Claim Status:**
  - Live 6-stage milestone tracker & status badge:
    1. `Submitted`
    2. `Under Review`
    3. `Documents Required`
    4. `Approved`
    5. `Rejected`
    6. `Payment Completed`
  - Complete chronological audit history timeline.
  - Printable certified Claim Settlement Voucher.
- **Notifications:**
  - Real-time notification drawer with unread count badge.
  - Claim status change updates.
  - Urgent missing document alerts with a direct "Upload Documents Now" button.
  - Official reimbursement approval and payment disbursement notifications.

---

### 🩺 Portal B: Claim Officer Portal
- **Officer Login:**
  - Dedicated clinical adjudicator login with 1-click demo logins for medical audit officers.
- **View Assigned Claims:**
  - Triage queue showing claims specifically routed to this officer.
  - Quick filtering by status (`All`, `Under Review`, `Documents Required`, `Payment Completed`).
- **Verify Uploaded Documents:**
  - Inspect attached hospital invoices, diagnostic labs, and physician notes.
  - Toggle "Mark Verified" or "Flag Discrepancy" with auditor notes.
- **Check Claim Details and Expenses:**
  - Audit itemized billing breakdown against hospitalization records and diagnosis.
- **Request Additional Documents:**
  - Request specific missing documents (e.g. itemized pharmacy bills, operative surgical notes), which automatically transitions the claim to `Documents Required` and pushes an urgent notification to the patient.
- **Recommend Approval or Rejection:**
  - Submit clinical recommendations (`RECOMMEND_APPROVAL`, `RECOMMEND_REJECTION`, `NEED_DOCUMENTS`) with recommended payable amounts and clinical reasoning.
- **Update Claim Status & Add Patient Remarks:**
  - Direct remarks for patients displayed on the patient's claim tracker.

---

### 🛡️ Portal C: Admin Portal
- **Admin Login:**
  - Secure administrative authentication.
- **View All Registered Users:**
  - Comprehensive registry of policyholders, claim officers, and administrators with linked policies and claim counts.
- **View All Submitted Claims:**
  - Global claims list with multi-parameter filtering across all policyholders.
- **Assign Claims to Claim Officers:**
  - Select unassigned claims and route them to designated officers with custom instructions.
- **Approve or Reject Claims:**
  - Authorize settlement amounts, factor in deductible and copay deductions, and execute payouts.
  - Marking `Payment Completed` automatically generates a Payment Transaction Reference, updates the policy remaining balance, and notifies the patient.
  - Reject claims with formal policy exclusion grounds (e.g. cosmetic exclusions, pre-existing waiting periods).
- **Manage Insurance Policies:**
  - Create new policies and edit coverage sums, deductibles, copay rates, and validity periods.
- **Generate Claim Reports:**
  - Download complete claim registry in CSV format (`claims_audit_report.csv`).
  - Print certified executive audit reports.
- **View Dashboard Statistics:**
  - Executive KPI cards: Total Claims, Total Claimed Value, Total Settled Reimbursements, Settlement Rate, Pending Reviews.
  - Visual analytics: Status distribution bar charts and officer audit workload breakdown.

---

## 🔑 Demo Login Credentials

| Portal | Role | Email | Password | Username |
|---|---|---|---|---|
| **Patient Portal** | Patient | `john.doe@example.com` | `user123` | `johndoe` |
| **Patient Portal** | Patient | `sarah.smith@example.com` | `user123` | `sarahsmith` |
| **Patient Portal** | Patient | `robert.chen@example.com` | `user123` | `robertchen` |
| **Officer Portal** | Claim Officer | `officer.michael@healthclaim.com` | `officer123` | `officer.michael` |
| **Officer Portal** | Claim Officer | `officer.sarah@healthclaim.com` | `officer123` | `officer.sarah` |
| **Admin Portal** | Administrator | `admin@healthclaim.com` | `admin123` | `admin` |

---

## 🖥️ How to Launch the Portals

### Method 1: Desktop Batch Launcher (Recommended)
Double-click `Launch_Health_Insurance_Portals.bat` directly on your Desktop, or inside `HealthInsuranceClaimSystem`:
```cmd
C:\Users\MSI\Desktop\Launch_Health_Insurance_Portals.bat
```
This automatically starts the backend server and launches all 3 portals in your default web browser:
1. **Portal Hub:** `http://localhost:8080/index.html`
2. **Patient Portal:** `http://localhost:8080/patient_portal.html`
3. **Claim Officer Portal:** `http://localhost:8080/officer_portal.html`
4. **Admin Portal:** `http://localhost:8080/admin_portal.html`

### Method 2: Direct File Access (Zero-Config Offline Mode)
You can also open the HTML files directly in any web browser without running the server:
- Patient Portal: `file:///C:/Users/MSI/Desktop/HealthInsuranceClaimSystem/portals/patient_portal.html`
- Officer Portal: `file:///C:/Users/MSI/Desktop/HealthInsuranceClaimSystem/portals/officer_portal.html`
- Admin Portal: `file:///C:/Users/MSI/Desktop/HealthInsuranceClaimSystem/portals/admin_portal.html`

*Note: Real-time synchronization is fully supported across all tabs via `BroadcastChannel` in both server and offline modes!*
