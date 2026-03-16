SaaS Application Infrastructure & Triage Lab

📌 Project Overview
This project simulates a Tier-2 Technical Support environment. I have built a local "sandbox" to demonstrate how I identify, investigate, and resolve technical issues across the stack. This lab focuses on root-cause analysis rather than just surface-level fixes.

🛠️ Tech Stack
Web Server: Local IIS (Internet Information Services) environment

Database: PostgreSQL 16 (Managed via pgAdmin 4)

OS/Terminal: Linux (Ubuntu 22.04 via WSL)

API Testing: Postman

🚀 Support Scenarios & Resolutions
1. Web Server Environment Setup
Scenario: Establishing a local hosting environment to mimic a company's application server.

Action: Configured and enabled Internet Information Services (IIS) locally to handle web requests.

Proof of Work:

2. Database Triage: Billing Sync Failure (SQL)
Scenario: A customer (help_me@test.com) reported a plan mismatch. They paid for an upgrade, but the system still shows them on the "free" tier.

Investigation: Performed a JOIN query in the saas_platform database between support_users and payments to identify the sync error.

Resolution: (Next Step) Execute an UPDATE command to synchronize the plan_type based on the verified payment.

Proof of Work:

3. Log Diving: Server-Side Error Identification (Linux)
Scenario: Users reported "Unexpected Errors" during the upgrade process.

Investigation: Used the Linux command line to parse triage.log. Utilized grep to isolate a 500 ERROR which revealed a DB_CONNECTION_TIMEOUT.

Command Used: grep "ERROR" triage.log

Proof of Work:

4. API Health Verification (Postman)
Scenario: Confirming the application's backend is responding correctly to data requests.

Action: Sent a GET request to the user endpoint. Verified the system returned a 200 OK status and valid JSON metadata.

Proof of Work:

🏁 Conclusion
This lab demonstrates my ability to navigate different technical layers—server, database, and API—to solve customer-facing problems. By using these tools together, I can provide faster resolutions and more accurate technical reporting.
