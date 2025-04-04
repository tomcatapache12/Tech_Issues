Epic: Enable TLS for Service-to-Service Authentication in Mosaic Services
Epic Name: Enable TLS for Internal Service Communication in Mosaic

Epic Description:
To enhance the security posture of Mosaic services, we aim to enable mTLS (Mutual TLS) for all internal service-to-service communications. This will ensure that only trusted services can communicate with each other, and all traffic is encrypted in transit.

🎯 Goals:
Enable TLS between all Mosaic backend services.

Use client-side certificates for mutual authentication.

Leverage secure keystore/truststore management (e.g., Vault, Kubernetes secrets).

Update service configurations to support mTLS (e.g., Spring Boot configs, RestTemplate/WebClient).

Roll out gradually with backward compatibility and fallback strategy.

Monitor traffic and alerting for mTLS handshake failures.

📦 Deliverables:
TLS certificates issued via <CA tool> (e.g., Vault/HashiCorp, AWS ACM).

Keystore and truststore mounted in pods/services.

Updated configs for:

RestTemplate/WebClient clients.

Server-side SSL config (Tomcat/Jetty/Netty).

Unit/integration tests for secure communication.

Updated documentation for future onboarding.

Monitoring dashboards and alerts on TLS metrics.

📍 Milestones / Stories:
[SPIKE] Feasibility study and impact analysis for enabling mTLS in Mosaic

Generate TLS certs using internal CA

Configure keystore/truststore in Mosaic backend services

Enable mTLS on server-side ports

Update all RestTemplate/WebClient clients to use TLS

Implement retry logic/fallback in case of handshake failure

Validate connectivity in lower environments (QA, UAT)

Add metrics/logging/alerts for TLS handshake and cert expiry

Rollout mTLS to production via feature flag

Update Confluence with setup and troubleshooting guide
