Contingency Design: Handling UI Downtime with SFTP-Based Processing
Problem Statement
When the Mosaic UI is down, clients need an alternative way to send trades. The proposed contingency solution allows clients to upload files via SFTP, which are then processed and pushed to the backend Mosaic APIs. The design ensures scalability, extensibility, and supports future integrations with other trade channels like EMS queues, REST APIs, or additional file-based systems.

Proposed Workflow
SFTP File Upload:

Clients upload trade files to a secure SFTP server.
File Ingestion Service:

Monitors the SFTP server for new files.
Validates files (e.g., format, size, metadata).
Passes files and metadata to the Transformation Service.
Transformation Service:

Parses the file and identifies the format (e.g., CSV, JSON, XML).
Transforms the data into a standard trade object or payload.
Sends the transformed object to the Dispatcher Service.
Dispatcher Service:

Implements the Publisher-Subscriber Pattern to publish transformed data as an event to a queue or topic.
Enriches the event with metadata, such as:
Channel: e.g., MOSAIC_DOWN, EMS, FILE_BASED.
Event Type: e.g., CONTINGENCY, REAL_TIME.
Queue/Topic:

Serves as a decoupling layer between the dispatcher and consumer services.
Ensures durability, scalability, and retry mechanisms.
Consumer Service:

Implements the Strategy Pattern to dynamically process events based on the Channel and Event Type.
Processes the event using a Plugin-Based Architecture:
Example:
If channel = MOSAIC_DOWN, it calls Mosaic APIs to resume trade processing.
If channel = EMS, it routes the trade to the EMS queue.



Event Metadata
Each event published by the Dispatcher Service contains critical metadata for routing and processing:

Trade ID: Unique identifier for the trade.
Channel: The source or method of trade (e.g., MOSAIC_DOWN, EMS, FILE_BASED).
Event Type: Describes the event's purpose (e.g., CONTINGENCY, REAL_TIME).
Payload:
Transformed trade details.
Additional file metadata (if applicable).
Example Metadata:


{
    "tradeId": "123456",
    "clientId": "7890",
    "eventType": "CONTINGENCY",
    "channel": "MOSAIC_DOWN",
    "payload": {
        "tradeDetails": { ... },
        "fileMetadata": { ... }
    }
}


Design Patterns Used
Strategy Pattern:

Used in the Consumer Service to dynamically process events based on Channel and Event Type.
Publisher-Subscriber Pattern:

Implemented in the Dispatcher Service and Queue layer for event-driven communication.
Plugin-Based Architecture:

Allows easy integration of new trade channels (e.g., EMS, REST APIs) by adding new consumer plugins.
Key Advantages
Scalability:

Queues ensure the system can handle high loads and bursts of events.
Extensibility:

Adding support for new trade channels (e.g., EMS, REST APIs) requires minimal effort by creating new plugins.
Fault Tolerance:

The queue/topic layer ensures durability, retry mechanisms, and resilience against temporary failures.
Dynamic Routing:

Dispatcher Service enriches events with metadata, enabling consumers to route and process them dynamically.
Decoupled Architecture:

Each service operates independently, allowing easy maintenance and updates.
Future Enhancements
Add support for new trade channels, such as:
REST APIs for real-time trades.
Additional file-based systems.
Integrate monitoring and alerting using tools like Prometheus and Grafana.
Implement advanced queue configurations (e.g., Dead Letter Queues, Priority Queues).
