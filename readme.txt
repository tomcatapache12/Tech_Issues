OKR Theme	OKR Statement	Context/Details	Non-Negotiable	Negotiable/Flexible
Stability, Monitoring & Health Checks	All core services should have a heartbeat, health check & structured observability	- Identify missing heartbeats
- Onboard infra to SRE repo
- Splunk & API-based checks
- Grafana alerts
- Jaeger integration
- Request ID in logs
- Good log coverage	✅ Heartbeat & health check for all core services
✅ Grafana alerting
✅ Request ID in logs
✅ Jaeger integration	🔹 Centralized dashboard
🔹 Advanced alerting rules
🔹 Enhanced log structure
Performance, Scalability & Reliability	End-to-end critical flows should be tested for capacity & resilience	- Define scope & targets
- Strategy for services & web perf testing
- Load tests for backend & UI
- Guardrails in performance tests
- Blast radius reduction (GTEM/Mosaic)	✅ Performance test strategy & execution
✅ Backend & UI load testing
✅ QA ownership of performance
✅ GTEM process split across multiple hosts	🔹 Synchronous vs. async test tools
🔹 Further redundancy measures
CI/CD, Environments & Deployment Stability	Stable & scalable environments with clean CI/CD practices	- QA, Perf & UAT stability
- External connectivity for UAT
- Separate demo env for product team
- GitLab-based deployment for GTEM & Trade Service
- Non-prod deployment cleanliness	✅ Stable QA, Perf, UAT environments
✅ CI/CD pipeline optimizations
✅ Clean automated deployments	🔹 Demo environment setup
🔹 Separate performance environment
Contingency & Incident Recovery	Mosaic core flows should have contingency mode	- Identify core contingency flows
- Design & implement contingency plans
- Deploy solutions first in non-prod, then prod	✅ Contingency strategy for core flows
✅ Non-prod testing of contingency solutions	🔹 Additional redundancy layers
Modernization & Tech Debt Cleanup	Legacy systems should be removed & replaced	- Apache migration to Kong
- CGI script alternatives
- Angular to React
- Experience API decommission
- GitLab repo cleanup	✅ Apache decommissioned
✅ Experience API removed
✅ Kong gateway in place	🔹 Further GitLab repo cleanup
🔹 Full React migration timeline
Standardization & Dependency Management	Consistent dependencies & artifacts across platforms	- Identify common artifacts
- Use BOM for consistency
- Ensure artifact stability across services	✅ Core artifacts standardized
✅ BOM usage enforced	🔹 Standardization beyond core services
