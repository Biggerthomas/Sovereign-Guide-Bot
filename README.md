Sovereign-Guide: Hardware-Adaptive Onboarding Framework
The Business Problem
Hardware and OS-migration companies lose significant revenue and man-hours on repetitive technical support calls. Non-technical users (55+) often struggle with device-specific BIOS/Boot triggers, leading to "Time-to-Success" delays and increased churn.

The Solution
Sovereign-Guide is a logic-driven, data-centric automation framework. Instead of static, hard-coded conversations, it uses a relational database to serve device-specific instructions (Lenovo, Dell, HP, etc.) based on real-time user metadata.

Key Technical Features
Metadata-Driven Personalization: Automatically extracts user names and hardware profiles from URL parameters (e.g., ?name=Herbert&brand=Dell) to skip redundant questions.

Data-Driven Architecture: Utilizes an internal hardware_db table. This allows the system to scale to thousands of device models without changing a single line of flow logic.

Pre-Flight Security Diagnostics: Includes a mandatory "Safety Gate" for BitLocker Disk Encryption to prevent data loss during OS migrations.

Privacy-First (GDPR): Designed for On-Premise Deployment via Docker. No data is sent to US-based LLM providers unless explicitly configured (supports European models like Mistral).

Automated Handover: Generates a structured JSON/Text summary of the setup session for integration into ERP systems (e.g., ERPNext).

System Architecture
Ingestion: JavaScript "Execute Nodes" parse browser metadata.

Logic Gate: Validates security requirements (BitLocker/Secure Boot).

Database Query: Dynamic SQL-style lookup to fetch the correct Boot_Key and Instruction_GIF.

Feedback Loop: Verification nodes ensure the user successfully reached the target state before closing the ticket.

Repository Structure
/flows: Contains the .bpz / JSON export of the Botpress Logic.

/scripts: Clean JavaScript snippets used for metadata extraction and table querying.

/docs: Detailed architecture diagrams and GDPR compliance statements.

Author & Background
[Peter Adelekan]
Specializing in Autonomous AI Agents and Automated Technical Support for high-security environments. I build tools that solve complex human-hardware friction points.
