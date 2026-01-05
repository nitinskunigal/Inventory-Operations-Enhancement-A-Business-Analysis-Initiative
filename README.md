# Inventory Operations Enhancement - A Business Analysis Initiative

## Table of Contents

- [1. Executive Summary](#1-executive-summary)
- [2. Problem Statement and Strategic Context](#2-problem-statement-and-strategic-context)
- [3. How Data Analysis Informed the Business Analysis](#3-how-data-analysis-informed-the-business-analysis)
- [4. Solution Approach](#4-solution-approach)
- [5. KPIs and Value Alignment](#5-kpis-and-value-alignment)
- [6. Estimated Benefits and Expected Outcomes](#6-estimated-benefits-and-expected-outcomes)
- [7. Limitations, Constraints, and Future Enhancement Opportunities](#7-limitations-constraints-and-future-enhancement-opportunities)
- [8. Key Business Analysis Artifacts and Traceability](#8-key-business-analysis-artifacts-and-traceability)
- [9. Repository Navigation and Links](#9-repository-navigation-and-links)

## 1. Executive Summary

MapleDash Grocers, a simulated e-grocery retailer, operates a multi-warehouse fulfillment network across the Greater Toronto Area, supporting high-volume, time-sensitive customer demand. While core systems such as the Inventory Management System (IMS), Warehouse Management System (WMS), and Order Management System (OMS) are in place, inventory operations rely heavily on manual coordination, delayed updates, and supervisor-driven controls.

A data-driven assessment revealed that operational challenges stem not from missing systems, but from execution gaps between physical warehouse activities and system-recorded inventory states. These gaps manifest as inventory inaccuracies, ATP overselling, uneven stock distribution, frequent replenishment exceptions, and preventable picking disruptions.

This Business Analysis project defines a targeted IMS enhancement approach focused on system-directed execution, automated inventory updates, and exception-based human intervention across five core processes:
- Receiving  
- Putaway  
- Cycle Counting  
- Replenishment  
- Order Picking  

The solution deliberately avoids full system replacement or enterprise-grade integrations, aligning with MapleDash’s operational maturity and growth trajectory.

The outcome is a disciplined, scalable inventory execution model that improves inventory accuracy, fulfillment reliability, and operational efficiency without introducing unnecessary complexity or cost.

---

## 2. Problem Statement and Strategic Context

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

In short, data analysis diagnosed the problem space, while business analysis translated those signals into structured requirements and solution design. 

🔗 **[Data Analysis GitHub Repository](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Data-Analysis-Phase)**

---

## 4. Solution Approach

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

## 5. KPIs and Value Alignment

KPI alignment ensures that the proposed solution delivers measurable business value, not just process improvement. The IMS enhancements are explicitly designed to influence execution-driven KPIs that reflect inventory accuracy, availability, and operational stability.

### How the Solution Impacts Key KPIs

- **Inventory Accuracy & Availability**:
Improved execution discipline and controlled inventory updates reduce ATP overselling, stabilize Total ATP Quantity, and improve Inventory Turnover, Days of Inventory, Days of Cover, and Median Sellable Coverage.

- **Replenishment & Stock Control**:
System-driven replenishment triggers and exception thresholds reduce the percentage of SKUs falling below Reorder Point (ROP) and Safety Stock.

- **Risk & Loss Exposure**:
Better putaway discipline, FEFO enforcement, and timely adjustments reduce expiry exposure and protect unit economics.

- **Demand & Fulfillment Context**:
Improved execution stability supports consistent fulfillment performance under volatile demand without overreactive manual intervention.

- **Supplier Risk Context (Observed, Not Controlled)**:
Supplier OTD%, lead time, and concentration metrics are monitored as external risk indicators that inform execution safeguards, not as levers controlled by this project.

These KPIs form the basis for post-implementation monitoring and benefits realization tracking.

---

## 6. Estimated Benefits and Expected Outcomes

Based on current-state baselines identified during data analysis, the proposed solution is expected to deliver measurable operational improvements within six months of implementation, assuming disciplined adoption.

### Key Expected Outcomes

- **Improved Inventory Turnover:** Inventory Turnover is expected to increase from 6.5x to approximately 8.0x, driven by better alignment between demand velocity and stock placement, reduced overstocking in slow-moving categories, and faster  execution cycles.  
- **Reduced ATP Overselling:** The percentage of SKUs oversold (ATP < 0) is expected to drop from 2.9% to below 1%, as inventory updates are synchronized with validated execution events.  
- **Lower Replenishment Risk:** SKUs below Reorder Point (ROP) are expected to reduce from 17.3% to under 10%, reflecting more timely and consistent replenishment triggers.  
- **Lean Inventory Position:** Days of Inventory are expected to decrease from 56 days to 50 days or less, improving working capital efficiency without increasing stockout risk.  
- **Tighter SKU-Level Coverage:** Median Sellable Coverage is expected to reduce from 33 days to approximately 30 days, indicating more balanced inventory distribution across SKUs.  

These outcomes represent execution efficiency gains, not demand growth assumptions, and are consistent with the scope and responsibility of an IMS-led process enhancement initiative.

---

## 7. Limitations, Constraints, and Future Enhancement Opportunities

This Business Analysis initiative was intentionally scoped to address execution discipline, inventory accuracy, and operational reliability within MapleDash’s current systems landscape and organizational maturity. While the proposed solution delivers measurable benefits within a short horizon, it does not attempt to solve every adjacent opportunity. The following outlines key limitations by design, followed by realistic next steps aligned with MapleDash’s longer-term strategy.

### 7.1 Intentional Limitations and Scope Constraints

Several areas were deliberately excluded to ensure feasibility, adoption, and time-to-value:

- **No full system replacement or ERP consolidation**: The project assumes continued use of existing IMS, WMS, and OMS platforms. Replacing or consolidating systems was deemed high-risk, cost-intensive, and misaligned with MapleDash’s current growth stage.
- **No real-time or enterprise-grade integrations**: Data synchronization focuses on reliability and control points rather than real-time orchestration. This avoids architectural complexity while still improving execution accuracy.
- **No advanced forecasting, AI, or optimization engines**: Demand forecasting, predictive replenishment, and machine-learning-based optimization were intentionally excluded. The root issues identified were execution-driven, not forecast-driven.
- **Supplier behavior not treated as a controllable lever**: Supplier reliability metrics were used strictly as inbound risk context. Contract renegotiation, sourcing strategy changes, or supplier performance improvement initiatives fall outside this project’s mandate.
- **Power BI used as a diagnostic and monitoring tool, not a decision engine**: Dashboards support visibility and monitoring but do not replace operational workflows or system-directed controls.
These constraints ensure the solution remains practical, implementable, and defensible within a six-month horizon.

### 7.2 Near-Term Enhancements (Post-Stabilization)

Once execution discipline and system trust are stabilized, MapleDash can extend value through incremental enhancements:

- **Operationalized BI monitoring**: Transition Power BI dashboards from diagnostic use to operational governance, including alerting for ATP risk, replenishment exceptions, and expiry exposure.
- **Rule refinement and tuning**: Fine-tune tolerance thresholds, exception rules, and category-specific replenishment logic based on post-implementation performance trends.
- **Expanded KPI governance**: Introduce formal KPI ownership, escalation paths, and review cadences to sustain benefits realization beyond initial rollout.
- **Improved data pipelines**: Move from CSV-based extracts toward database-driven reporting and scheduled refresh pipelines as analytical maturity increases.

### 7.3 Medium-Term Strategic Opportunities

With execution foundations in place, MapleDash can pursue broader capability improvements:

- **Advanced replenishment logic**: Incorporate demand seasonality, promotion calendars, and lead time variability into replenishment planning once baseline accuracy is achieved.
- **Supplier segmentation and risk scoring**: Use observed performance data to inform procurement strategy, supplier tiering, and buffer differentiation without immediate contract changes.
- **Network-level inventory balancing**: Introduce systematic inventory rebalancing across fulfillment centers to reduce throughput concentration risk and improve service resilience.
- **Warehouse execution analytics**: Extend analytics into labor productivity, task cycle times, and exception frequency to further optimize warehouse operations.

### 7.4 Long-Term Vision Alignment

In the long term, this initiative positions MapleDash to evolve toward:

- More automated and predictive inventory decision-making
- Tighter integration between planning and execution layers
- Scalable analytics and reporting infrastructure
- Reduced dependency on manual supervision as volume grows

Crucially, these future enhancements build on a stable execution foundation rather than attempting to leap directly to advanced automation. This staged approach ensures MapleDash’s inventory operations evolve in line with business maturity, risk tolerance, and strategic priorities.

---

## 8. Key Business Analysis Artifacts and Traceability

This repository contains a complete, industry-aligned set of Business Analysis artifacts demonstrating traceability from problem identification through solution validation.

### Core Deliverables

- **Business Requirements Document (BRD):** Business objectives, rules, requirements, and success metrics  
- **Process Maps (AS-IS & TO-BE):** Five core inventory processes  
- **Use Case Diagrams & Specifications:** Automation-first actor–system interactions  
- **Product Backlog:** Epics, user stories, acceptance criteria, ownership, and KPI alignment  
- **Traceability Matrix:** Business Requirements → Functional Requirements → User Stories → KPIs  
- **UAT Artifacts:** Scenarios, test cases, defect log, sign-off templates  
- **Low-Fidelity Wireframes:** Operational system interactions for requirement clarity  

### Core Deliverables

Every requirement and design decision is traceable back to:

- Data analysis insights
- Defined business objectives
- Measurable inventory KPIs
- Validated operational risks

This ensures the solution is evidence-driven, testable, and defensible.

---

## 9. Repository Navigation and Links

- **[Data Analysis Phase Repository](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Data-Analysis-Phase)**  
- **[Interactive Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZmRmNGRhOGEtN2IyNi00ZWNjLTkxN2YtMmYyMzJhNzNhN2NmIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)**
- **[Business Case](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/blob/main/BA%20Deliverables/Business%20Case.pdf)**  
- **[Business Requirements Document (BRD)](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/blob/main/BA%20Deliverables/Business%20Requirements%20Document%20(BRD).pdf)**
- **[Stakeholder Analysis & Interview Guide](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/blob/main/BA%20Deliverables/Stakeholder%20Analysis%20%26%20Interview%20Guide.pdf)**
- **[Current State & Future State Process Maps](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/tree/main/BA%20Deliverables/Current%20State%20%26%20Future%20State%20Process%20Maps)**
- **[System Context Diagram](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/blob/main/BA%20Deliverables/System%20Context%20Diagram.png)**
- **[Product Backlog & UAT](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/tree/main/BA%20Deliverables/Product%20Backlog%20%26%20UAT)**
- **[Use Case Diagrams, Use Case Specs, and Wireframes](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Business-Analysis-Phase/tree/main/BA%20Deliverables/Use%20Case%20Diagrams%2C%20Use%20Case%20Specs%2C%20and%20Wireframes)**
