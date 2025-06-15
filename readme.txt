# 📊 Charlotte Resiliency & Contingency Summary (BofA Onboarding – 2025)

This document outlines the **current state (2024)**, **2025 improvements (done/in-flight)**, and **future plans** across key flows in the Mosaic platform, with a focus on resiliency and contingency in light of BofA onboarding.

---

## 1. 🔁 Trading Flow Enhancements

| Aspect                      | 2024 State (Baseline)                                                                 | 2025 Improvements (Done / In-Flight)                                                                                             | Future Scope                                           |
|----------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|
| Trading Channels           | Mosaic UI, CITI API, EMS, File-Based; Serial via Obj Queue                            | Shifted to **CTP (Concert)** for EMS, File, CITI → **Parallel execution**                                                       | UI & SWIP trades to move to CTP                        |
| EMS & File-Based Trading   | Serial, 1 instance, long response                                                      | **CTP enabled**, **4 instances**, response time **1/4th** of earlier                                                             | Horizontal scaling on traffic                         |
| CITI API                   | Poller-based, single instance, ~30–35s latency                                        | **Multi-instance**, latency improved to **~500ms**                                                                              | Burst-resilient scaling                               |
| Instruct API               | Serial, ~2000ms                                                                        | Now **parallel**, latency ~**500ms**                                                                                            | Dynamic scaling                                       |
| Security/Protocols         | SOAP-based, no auth                                                                    | Migrated to **REST**, added **Spring Security**, **JWT**                                                                        | OAuth2/OpenID (optional)                              |
| CITI Contingency Flow      | Manual                                                                                 | Moved to CTP-backed file-based flow                                                                                             | —                                                      |
| Infra Limitations          | DB2 bottleneck, single point                                                           | Horizontal scaling now available, **DB still a bottleneck** but manageable                                                      | DB optimization/caching in future                     |
| Legacy Auth (DAS)          | Used by Mosaic, legacy                                                                 | Replacement work started due to complexity                                                                                      | Move to modern auth service                           |

---

## 2. 📑 Reporting Flow Enhancements

| Aspect                     | 2024 State                                                                                 | 2025 Improvements (Done / In-Flight)                                                                                             | Future Scope                                           |
|---------------------------|---------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|
| Report Types              | **SOA** (EOD) and **Intraday** (per-trade)                                                 | Same; BofA uses **SOA via DART (XML)**, **Intraday via Webhooks (JSON)**                                                         | Push-based client notification                        |
| Delivery Mechanism        | XML → DART/Calastone/CD                                                                    | JSON webhooks for Intraday, XML DART retained for SOA                                                                           | Extend Webhook framework                              |
| SOA Capacity              | Max 2,000 accounts/feed; 25 min avg for 400 feeds                                          | Now **5,000+ accounts/feed**, **1 min** avg using **CTP (32 concurrency)**                                                      | Dynamic per-client scaling                            |
| SOA Engine                | Serial via Keystone                                                                         | Now **parallel via CTP**                                                                                                        | Add client-specific config UI                         |
| Intraday Reporting        | Serial, manual configuration                                                               | **Parallel**, webhook push                                                                                                     | Push throttling, client config UI                     |
| Config Management         | Manual Keystone edits                                                                      | UI config screen under development                                                                                             | Circuit breaker + fallback handling                   |
| Performance Testing       | None                                                                                        | **Capacity testing done** for SOA                                                                                               | Extend to webhooks                                    |

---

## 3. 📈 Monitoring Enhancements

| Aspect                  | 2024 State                         | 2025 Improvements (Done / In-Flight)                              | Future Scope                          |
|------------------------|-------------------------------------|-------------------------------------------------------------------|---------------------------------------|
| Jaeger Tracing         | Not integrated                      | **Jaeger** added to critical backend services                     | 100% coverage                         |
| Grafana Metrics        | Missing for backend services        | **In-flight** for most backend services                          | Full metrics & alert pipelines        |
| Alerting               | Manual or log-based                 | SLO/SLA-based alerting being defined                             | Grafana dashboards + PagerDuty alerts |

---

## 4. 🛡️ Mosaic Contingency Platform

| Aspect                           | 2024 State                                                        | 2025 Improvements (In-Flight)                                                                                       | Future Scope                                           |
|----------------------------------|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|
| Trade Contingency Process       | Phone calls, manual DB lookup, CSV for TA                         | Building **Mosaic Contingency UI** for file upload + validation + transformation                                   | File generator for multiple clients                   |
| UI Capability                   | None                                                              | Minimal UI built (upload + parse + preview + transform)                                                             | Impacted trades dashboard                             |
| Offshore Support Tooling        | Manual calculation of net value                                   | Requirements under analysis                                                                                          | Build Onshore-style tool                              |
| TFA Trade State Automation      | Manual intervention, retransmit risk                              | Exploring **Calastone API** for automated state management                                                           | Prevent retransmits completely                        |
| Post-Reconciliation             | Manual                                                           | Functional scope defined                                                                                             | Reconciliation UI                                     |
| Impacted Trade Identification   | None                                                              | **Strategy under analysis**                                                                                          | Visual tracking dashboard                             |
| Deployment State                | Not applicable                                                    | In development; **not yet production-ready**                                                                         | UAT and phased rollout                                |

> 🔗 See full design here: [Mosaic Contingency Confluence](#) *(Insert actual Confluence link)*

---

