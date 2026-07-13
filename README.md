# Policy Pulse Dashboard

A Power BI dashboard built for **Prism Insurance Pvt. Ltd.** to monitor policy performance and claims activity across customers, providing a quick view of premiums, coverage, and claim outcomes for underwriting and claims teams.

## 📊 Overview

The report analyzes customer-level policy and claim records to answer questions like:
- How much premium and coverage is currently underwritten?
- What's the claim volume and status breakdown (approved / rejected / pending)?
- How do premiums vary by policy type, and claims by age group?
- What share of policies are active vs. inactive?

## 🗂️ Pages

| Page | Contents |
|------|----------|
| **Page 1 – Overview** | KPI cards (Total Premium, Total Coverage, Total Claim Amount, Customer Count), Number of Claims by Claim Status (ribbon chart), Premium Amount by Policy Type (bar chart), Claim Amount by Age Group (line chart), Active vs. Inactive Policies (donut chart), a Policy Type × Claim Status pivot table, and slicers for Policy Number, Claim Number, and Customer ID |
| **Page 2 – Record Detail** | A detailed drill-through table listing every policy/claim field for granular record-level review, with a back button to return to the overview |

## 🧮 Data Model

Single fact table — **InsuranceData** — with the following fields:

| Field | Description |
|-------|-------------|
| PolicyNumber | Unique policy identifier |
| CustomerID | Unique customer identifier |
| ClaimNumber | Unique claim identifier |
| Age | Customer age |
| Gender | Customer gender |
| CoverageAmount | Sum insured / coverage value |
| PremiumAmount | Premium paid for the policy |
| PolicyStartDate / PolicyEndDate | Policy validity period |
| PolicyType | Type of insurance policy |
| ClaimDate | Date the claim was filed |
| ClaimAmount | Amount claimed |
| ClaimStatus | Status of the claim (e.g., Approved, Rejected, Pending) |
| Age Groups | Calculated column bucketing customers by age band |
| Active/Inactive | Calculated column flagging policy status |

## 🛠️ Tools & Techniques

- **Power BI Desktop** — data modeling, DAX calculated columns/measures, report design
- **DAX** — used for `Age Groups` and `Active/Inactive` derived fields, and summary measures (Sum of Premium/Coverage/Claim Amount)
- **Interactive filtering** — slicers on Policy Number, Claim Number, and Customer ID
- **Drill-through** — Page 2 acts as a detail view for record-level inspection

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `Policy_Pulse_Dashboard.pbix` | The complete Power BI report (data model + visuals) |

## ▶️ How to Use

1. Download `Policy_Pulse_Dashboard.pbix`.
2. Use the slicers on Page 1 to filter by Policy Number, Claim Number, or Customer ID.
3. Click into a data point and use the back button on Page 2 to view/return from record-level detail.
---
*Built as part of a data analytics portfolio project.*
