JIRA Summary:
Evaluate Feasibility of Asynchronous Logging for Trade Service

JIRA Description:
Currently, the Trade service relies on synchronous logging, which may contribute to performance bottlenecks due to blocking operations. This ticket aims to assess the feasibility of adopting asynchronous logging to optimize log processing without impacting service stability.

Scope of work:

Analyze the current logging mechanism and identify high-impact synchronous log points.
Evaluate potential asynchronous logging solutions (e.g., Log4j2 AsyncAppender, JUL async handlers) and their suitability for Trade service.
Assess the impact on performance, resource utilization, and log integrity.
Provide recommendations on whether to proceed with implementation.
