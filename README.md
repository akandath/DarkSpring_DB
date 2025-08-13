# Dark Springs – Database System for Efficient Water Delivery Operations

## 📌 Overview
Dark Springs provides **reliable, hassle-free water delivery services** to businesses, schools, and healthcare facilities.  
This project implements a **robust database system** to streamline operations, automate billing, enforce business rules, and ensure financial accuracy.


## 🚀 Value Proposition
We deliver **efficiency** by:
- **Optimizing Operations**: Streamlining transactions, automating processes, and enforcing business rules.
- **Leveraging Data & Insights**: Providing actionable analytics for tailored solutions and improved operations.


## 🛠 Core Functionalities

### 1. **Contract Management**
- Create, renew, and terminate contracts (1-year duration auto-handled).
- Locate contracts expiring within 30 days.
- Link multiple delivery locations to a single contract.

### 2. **Sales & Delivery Process**
- Create and update sales records with inventory updates.
- Assign deliveries to exactly one delivery person.
- Enforce cooler rental before large bottle purchases.

### 3. **Billing & Payments**
- Automatic late fee application (10%).
- Pro-rated monthly billing on the 1st of each month.
- Partial payment tracking linked to specific billing cycles.
- Referral discount application via triggers.

### 4. **Employee Evaluation & Records Management**
- Weekly performance evaluations for drivers.
- Automated performance scoring for bonuses/promotions.
- Automatic deletion of records 3 years after exit.


## 📏 Business Rules & Automation
- **Late Fees**: 10% applied via scheduled job.
- **Referral Discount**: $25 discount auto-applied upon lead approval.
- **Contract Enforcement**: Purchases allowed only with active contracts.
- **Delivery Rules**: One driver per delivery; multiple stops allowed.
- **Cooler Rental Requirement**: Mandatory before certain purchases.
- **Data Integrity**: Constraints, triggers, and stored procedures ensure consistency.


## 📊 Database Structure Highlights
- **Indexes**:
  - Unique: `DELIVERY_MANAGER_PK`, `DELIVERY_PERSON_PK`.
  - Non-Unique: `IDX_DELIVERY_EMPLOYEE`, `IDX_DELIVERY_PERSON` for faster name searches.
- **Denormalization**:
  - `DEL_PER_MGR` table for faster lookups, reduced joins, and optimized reporting.
- **Data Warehouse Migration**:
  - Fact and dimension tables (`ORDERS_FACT`, `ZIP_CODE_DIM`, `ITEM_TYPE_DIM`, `DESCRIPTION_DIM`).


## 📈 Reports Generated
1. **Awaiting Bill Status** – Identifies overdue accounts for payment reminders.
2. **High Performance Delivery Persons** – Recognizes top performers for incentives.


## 🧰 Tech Highlights
- **Triggers** for automation (discounts, deposit deductions, contract dates).
- **Stored Procedures** for performance scoring and complex calculations.
- **Scheduled Jobs** for billing and late fee applications.
- **Validation Checks** for enforcing operational rules.


## 📄 Roles & Permissions
- **CHRO Role**: View-only access to evaluations.
- **Delivery Manager Role**: Modify and review evaluations.


