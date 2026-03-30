# 🚚 FedEx Delivery Process: Comprehensive Analysis

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Logistics](https://img.shields.io/badge/Logistics%20Analytics-4B0082?style=flat)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-FF6600?style=flat)

---

## Dashboard Preview

<img width="1050" height="591" alt="image" src="https://github.com/user-attachments/assets/d4c477f0-43a7-42b6-a2a1-eb0c50884973" />


> 2.76K deliveries analysed · 74.84% on-time · 25.16% delayed · Avg cost $857.36 · Complaint rate 16.68%

---

## Problem Statement

FedEx faces significant operational inefficiencies with **25.16% of packages experiencing delays** and **16.68% generating customer complaints**. Analysis of 2,760 deliveries reveals systematic performance gaps across regions and delivery modes, with weather-related disruptions creating predictable yet poorly managed bottlenecks.

The average delivery cost of **$857.36 per package** points to a substantial cost structure inefficiency, while the **3.70/5.0 customer rating** reflects eroding competitive positioning in an increasingly demanding e-commerce logistics market.

---

## Background

The logistics industry has shifted sharply in recent years, driven by the growth of e-commerce which has raised customer expectations for speed and reliability. Services once considered premium are now viewed as baseline standards. Competitors like Amazon have demonstrated that next-day and same-day delivery can operate at scale — reshaping what customers accept as normal.

In this context, FedEx's ~75% delivery reliability falls well below both customer expectations and competitor benchmarks. Many leading logistics providers consistently exceed 90% on-time performance. The gap is not marginal — it is structural, and this analysis sets out to understand where it comes from and what can be done about it.

The financial stakes are equally clear. Last-mile delivery is widely recognised as the most expensive stage of logistics operations, often accounting for more than half of total shipping costs. Failed first delivery attempts are especially costly: they force packages back into the system, multiplying labour, fuel, and time costs while further frustrating customers who face additional delays.

---

## Dataset

| Field | Detail |
|---|---|
| Source | Kaggle — Delivery Logistics Dataset |
| Total records | 25,000 deliveries across 9 partners |
| FedEx records analysed | 2,818 |
| Coverage | 5 regions · 6 weather conditions · 4 delivery modes |
| Variables | Delivery status, cost, rating, weather, region, vehicle type, package type |

---

## Current Condition

### Headline Performance Metrics

| Metric | Value |
|---|---|
| Total Deliveries | 2,760 |
| On-Time Delivery Rate | **74.84%** |
| Delayed Packages | **25.16%** |
| Failed Deliveries | 4.76% (134 packages) |
| Average Delivery Cost | **$857.36** |
| Average Customer Rating | **3.70 / 5.0** |
| Customer Complaint Rate | **16.68%** |

### Delivery Mode Distribution

All four delivery modes operate at nearly equal volume — a flat distribution that signals static capacity allocation rather than demand-responsive planning:

| Mode | Share |
|---|---|
| Same Day | 26.58% |
| Two Day | 25.51% |
| Standard | 24.24% |
| Express | 23.67% |

Same-day is also the most expensive mode at an average of **$913.09** vs. $824.79 for two-day — yet the volumes are nearly identical, suggesting customers are not being routed to cost-appropriate options.

### Weather as a Disruption Multiplier

Weather is the single most powerful predictor of delivery failure. Disruption rates (delays + failed deliveries) scale dramatically across conditions:

| Weather Condition | Disruption Rate |
|---|---|
| Stormy | **40.2%** |
| Rainy | **37.2%** |
| Foggy | **27.6%** |
| Hot | 17.1% |
| Cold | 15.1% |
| Clear | 13.4% |

A package moving in stormy conditions is **3× more likely to be disrupted** than one in clear weather. These are not random failures — they are predictable, patterned, and recurring. Yet the current process contains no weather-contingency routing, meaning the system absorbs these failures rather than anticipating them.

### Regional × Weather Disruption Matrix

The Power BI dashboard's stacked bar chart surfaces where weather vulnerability concentrates most severely across regions:

| Region | Clear | Foggy | Rainy | Stormy |
|---|---|---|---|---|
| West | 12.8% | 26.5% | 41.9% | **46.9%** |
| South | 12.3% | 31.8% | 33.7% | **42.9%** |
| North | 9.3% | 28.1% | 42.7% | 36.7% |
| Central | 17.4% | 25.8% | 38.3% | 37.6% |
| East | 14.9% | 26.3% | 29.6% | 37.4% |

The **West region is the most weather-exposed** — nearly half of all deliveries fail or are delayed during storms. The **North region shows the widest performance gap** between clear (9.3%) and rainy (42.7%) conditions, suggesting infrastructure that performs well in favourable conditions but has no resilience when conditions deteriorate.

### Process Bottlenecks (BPMN Analysis)

A three-lane process map (Customer → Operations Centre → Delivery Driver) reveals critical inefficiencies at key handoff points:

- **Transportation method selection** — manual decisions between air and road transport introduce unnecessary delay at the routing stage
- **Hub scan-and-sort operations** — throughput limits during peak periods create backlogs that cascade downstream
- **Failed delivery reattempt loop** — packages that fail first delivery re-enter the full system cycle, effectively doubling handling costs per failed attempt
- **No weather contingency routing** — the process map contains no dynamic adaptation pathway for adverse conditions despite weather being the leading disruption cause

---

## Root Cause Analysis

Four systemic causes drive the performance gaps identified in the data:

1. **Dependence on manual processes** during package sorting and route planning — introducing inconsistency and human bottlenecks at high-volume decision points
2. **Insufficient real-time operational visibility** across hubs — managers lack the data to make proactive decisions before delays materialise
3. **Static routing logic** that does not dynamically respond to changing demand or weather conditions — the system reacts to disruptions rather than anticipating them
4. **Inadequate last-mile coordination** between delivery personnel and customers — driving failed delivery rates and the costly reattempt loop

---

## Desired Condition

- On-time delivery rate exceeding 90%, in line with leading industry benchmarks
- Reduced average cost per delivery through fewer failed attempts and smarter mode allocation
- Weather-responsive routing that treats adverse conditions as a trigger for proactive rescheduling, not a post-hoc explanation for delays
- Demand-driven delivery mode distribution replacing the current flat 25% allocation
- Customer notification systems that improve first-attempt success rates at the last mile

---

## Recommendations

**1. Automated route optimisation**
Implement dynamic routing that adapts in real time to weather, traffic, and operational conditions. Given that stormy and rainy weather alone account for 37–40% disruption rates, weather-triggered re-routing would have the highest immediate impact on on-time performance.

**2. Predictive delay analytics**
Deploy predictive models that flag high-risk deliveries before dispatch — based on region, weather forecast, delivery mode, and historical patterns. Proactive rescheduling is cheaper than reactive recovery.

**3. Demand-responsive mode allocation**
Replace the static ~25% mode split with capacity planning driven by delivery urgency signals and regional demand. This addresses both cost efficiency (routing appropriate packages to standard vs. same-day) and customer experience (ensuring time-sensitive items reach same-day capacity).

**4. Real-time operational dashboards for hub managers**
The Power BI analysis here is retrospective — it diagnoses what happened. The operational step is deploying live dashboards so hub managers can act on emerging bottlenecks within the same shift, not the next reporting cycle.

**5. Customer notification and last-mile coordination**
Strengthening recipient communication during the final delivery window — via SMS, app notification, or time-slot confirmation — directly reduces the failed delivery rate (currently 4.76%) and the expensive reattempt loop it creates.

---

## Risks & Mitigation

| Risk | Mitigation |
|---|---|
| Integration complexity with legacy systems | Phased rollout with parallel running during transition |
| Employee resistance to process change | Change management programme with training and performance incentives |
| Data quality gaps limiting model accuracy | Data quality improvement initiative before model deployment |
| Slower-than-expected ROI | Pilot in highest-impact region (West) before full rollout; set clear KPI milestones |
| Security and data exposure | Regular audits and monitoring of new system access points |

---

## Tools & Skills Demonstrated

| Area | Detail |
|---|---|
| Data Analysis | Python (Pandas) — 25,000-row dataset, FedEx segment extraction, disruption matrix |
| Power BI | KPI cards, gauge chart, stacked regional × weather bar chart, delivery mode distribution |
| Process Analysis | BPMN process mapping — three-lane Customer / Operations / Driver workflow |
| Report Writing | Problem statement, root cause analysis, recommendations, risk framework |
| Business Context | Logistics operations, last-mile delivery economics, competitive benchmarking |

---

## References

- Delivery Attempts per Order. Alexander Jarvis. https://www.alexanderjarvis.com/what-is-delivery-attempts-per-order-in-ecommerce/
- Delivery Logistics Dataset. Kaggle. https://www.kaggle.com/datasets/ayeshaseherr/delivery-logistics-dataset
- Understanding The Challenges Of Last-Mile Delivery. Freight Systems. https://freightsystems.com.au/understanding-the-challenges-of-last-mile-delivery/
- What Has Amazon Done to Change Customers' Delivery Expectations? CX Today. https://www.cxtoday.com/customer-engagement-platforms/what-has-amazon-done-to-change-customers-delivery-expectations/

---

## About

Built by **Charles Edeki**
📧 charlesedeki093@gmail.com | [LinkedIn](https://www.linkedin.com/in/charles-edeki/) | [GitHub](https://github.com/CharlesEdeki)
