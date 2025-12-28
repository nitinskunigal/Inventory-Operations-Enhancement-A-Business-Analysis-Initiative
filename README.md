# Inventory Operations Enhancement - Business Analysis Phase

## 1. Executive Summary

MapleDash Grocers, a simulated e-grocery retailer, operates a multi-warehouse fulfillment network across the Greater Toronto Area, supporting high-volume, time-sensitive customer demand. While core systems such as the Inventory Management System (IMS), Warehouse Management System (WMS), and Order Management System (OMS) are in place, inventory operations rely heavily on manual coordination, delayed updates, and supervisor-driven controls.

A data-driven assessment revealed that operational challenges stem not from missing systems, but from execution gaps between physical warehouse activities and system-recorded inventory states. These gaps manifest as inventory inaccuracies, ATP overselling, uneven stock distribution, frequent replenishment exceptions, and preventable picking disruptions.

This Business Analysis project defines a targeted IMS enhancement approach focused on system-directed execution, automated inventory updates, and exception-based human intervention across five core processes:
- Inbound Receiving  
- Putaway  
- Cycle Counting  
- Replenishment  
- Order Picking  

The solution deliberately avoids full system replacement or enterprise-grade integrations, aligning instead with MapleDash’s operational maturity and growth trajectory.

The outcome is a scalable, disciplined inventory execution model that improves inventory accuracy, fulfillment reliability, and operational efficiency without introducing unnecessary complexity or cost.

---

## 2. Problem Statement & Strategic Context

MapleDash’s fulfillment model depends on accurate inventory visibility, reliable replenishment, and disciplined execution across multiple warehouses. As order volumes and SKU complexity increased, operational processes failed to scale at the same pace.

The core problem is misalignment between physical inventory movements and system updates, leading to:

- Delayed or inconsistent inventory synchronization after receiving, putaway, replenishment, and cycle counting  
- Excessive supervisor intervention for routine discrepancies  
- SKU-level stock imbalances masked by healthy-looking aggregate KPIs  
- ATP overselling and pick-time shortages despite sufficient total inventory  
- Reactive replenishment behavior driven by execution gaps rather than demand signals  

Strategically, MapleDash does not need a full system replacement or advanced automation to resolve these challenges. What is required is stronger execution discipline, system-directed workflows for routine activities, and clear exception thresholds that focus human effort where it adds the most value.

This initiative directly addresses that need while remaining aligned with MapleDash’s size, maturity, and growth trajectory.

---

## 3. How Data Analysis Informed the Business Analysis

This Business Analysis initiative is evidence-led. A dedicated Data Analysis was conducted during discovery using Power BI dashboards and KPI diagnostics to establish a fact-based understanding of MapleDash’s current-state operations before defining requirements or solutions.

The data analysis did **not** propose solutions. Instead, it surfaced where execution breaks down and where operational risk accumulates, enabling informed BA decisions.

Key contributions of the data analysis phase included:

- Identifying inventory accuracy risk through ATP overselling, SKU-level stock imbalances, and delayed adjustments  
- Revealing demand volatility patterns using ABC–XYZ classification to highlight high-risk SKUs  
- Exposing uneven inventory distribution via Days of Cover vs. Median Sellable Coverage analysis  
- Highlighting warehouse-level throughput imbalance across fulfillment centers  
- Providing supplier reliability context (OTD%, lead time variability, supplier concentration) as an external risk factor, not a system failure  

These insights directly informed:

- TO-BE process design decisions  
- Business rules and exception thresholds  
- Automation boundaries  
- KPI selection and success metrics  
- Scope and constraints defined in the Business Case and BRD  

In short, data analysis diagnosed the problem space, while business analysis translated those signals into structured requirements and solution design. Together, the two phases form a closed loop that connects data-driven diagnosis to practical, scalable operational change.

🔗 **Data Analysis GitHub Repository:** *(insert link)*

---

## 4. Solution Approach (What Changed and Why)

The proposed solution is a **process-led IMS enhancement**, not a technology overhaul. It strengthens how inventory decisions are executed, validated, and recorded across the warehouse network.

### Core Design Principles

**System-Directed, Not System-Replaced**  
The IMS actively guides routine work such as receiving validation, putaway location selection, replenishment triggers, risk-based cycle count task generation, and automated pick task creation.

**Automation with Control Points**  
Inventory updates occur automatically only after validated execution steps, ensuring Quantity on Hand (QOH) and Available-to-Promise (ATP) reflect physical reality rather than assumptions.

**Exception-Based Human Intervention**  
Supervisors are engaged only when predefined tolerance thresholds are breached. Routine activities proceed without manual approval, reducing firefighting and cognitive load.

**Single Version of Inventory Truth**  
Inventory deductions and adjustments occur at clearly defined control points, eliminating duplicate updates and reconciliation confusion.

**Pragmatic Integration**  
Data synchronization between IMS, WMS, and OMS is lightweight and reliability-focused, avoiding real-time orchestration complexity.

Together, these principles convert inventory operations from reactive and manual to disciplined, scalable, and auditable while remaining appropriate for a mid-sized e-grocery organization.

---

## 5. Key Business Analysis Artifacts & Traceability

This repository contains a complete, industry-aligned set of Business Analysis artifacts demonstrating traceability from problem identification through solution validation.

### Core Deliverables

- **Business Requirements Document (BRD):** Business objectives, rules, requirements, and success metrics  
- **Process Maps (AS-IS & TO-BE):** Five core inventory processes  
- **Use Case Diagrams & Specifications:** Automation-first actor–system interactions  
- **Product Backlog:** Epics, user stories, acceptance criteria, ownership, and KPI alignment  
- **Traceability Matrix:** Business Requirements → Functional Requirements → User Stories → KPIs  
- **UAT Artifacts:** Scenarios, test cases, defect log, sign-off templates  
- **Low-Fidelity Wireframes:** Operational system interactions for requirement clarity  

### Traceability Approach

Every requirement and design decision is traceable back to:

- Data analysis insights  
- Defined business objectives  
- Measurable inventory KPIs  
- Validated operational risks  

This ensures the solution is evidence-driven, testable, and defensible.

---

## 6. KPIs and Value Alignment

The solution is aligned to a consistent KPI framework used across analysis, design, and validation.

### Inventory Accuracy & Availability
- % SKUs Oversold (ATP < 0)  
- Total ATP Quantity  
- Inventory Turnover  
- Days of Inventory  
- Days of Cover  
- Median Sellable Coverage  

### Replenishment & Stock Control
- % SKUs Below ROP  
- % SKUs Below Safety Stock  

### Risk & Loss Exposure
- Value Expiring < 30 Days  
- Avg Unit Cost  

### Demand & Fulfillment Context
- Total Orders  
- Total Order Quantity  
- Avg Daily Orders  
- Total Revenue  

### Supplier Risk Context (Observed, Not Controlled)
- On-Time Delivery %  
- Avg Lead Time  
- Top-3 Supplier Quantity Share %  

These KPIs form the basis for benefits realization tracking and post-implementation monitoring.

---

## 7. Why This Is a Realistic SMB Project

This initiative deliberately avoids overengineering:

- Supplier performance issues are observed and mitigated, not solved through sourcing changes  
- Automation is rule-based, not AI-driven  
- Integrations are lightweight, not real-time enterprise orchestration  
- Improvements focus on execution discipline, not organizational restructuring  

This makes the solution realistic, defensible, and achievable within MapleDash’s operational context.

---

## 8. Repository Navigation & Links

- Data Analysis Phase Repository  
- Power BI Dashboards  
- Business Case  
- Business Requirements Document (BRD)
- Stakeholder Analysis & Interview Guide
- Current State & Future State Process Maps
- System Context Diagram
- Product Backlog & UAT
- Use Case Diagrams, Use Case Specs, and Wireframes
