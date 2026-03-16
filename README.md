# MG Santos Technical Support Specialist

## Project Overview
I built this mockup Portfolio Project to simulate troubleshooting I do in a Technical Support role. Instead of just reading about tools, I set up a local environment to show how I actually track down bugs across the server, database, and API layers.

## Tools Used
* **Windows IIS:** To host the local web environment.
* **PostgreSQL:** For querying and fixing backend data.
* **Linux (WSL/Ubuntu):** For digging through server logs via the command line.
* **Postman:** To verify API health and response data.

---

## Troubleshooting Scenarios

### 1. Confirming Server Uptime
**Problem:** Need to verify the local application server is responding to requests.
**Fix:** Enabled Internet Information Services (IIS) on my Windows machine and verified the `localhost` handshake was successful.

![IIS Screenshot](01_local_iis_server.png)

---

### 2. Finding a Billing Mismatch (SQL)
**Problem:** A user (`help_me@test.com`) reported they paid for an upgrade but are still stuck on the "Free" plan.
**Investigation:** I ran a `JOIN` query and found that the payment was "Success," but the user's plan type never updated.
**Resolution:** I executed an `UPDATE` command to manually sync the user to the "Premium" tier, resolving the access issue immediately.

![SQL Triage Screenshot](02_database_triage.png)

---

### 3. Log Diving for Root Cause (Linux)
**Problem:** Why didn't the billing sync work automatically?
**Investigation:** I used `grep` in the Ubuntu terminal to search `triage.log`. I found a `500 ERROR` showing a `DB_CONNECTION_TIMEOUT`.
**Resolution:** Identified that the database connection timed out during the write process. I reported the timeout trend to the DevOps team to adjust the connection string pool.

![Linux Terminal Screenshot](03_linux_log_analysis.png)

---

### 4. API Response Testing (Postman)
**Problem:** Testing if the user data is actually reachable by the front-end after the database fix.
**Action:** Ran a `GET` request to pull user details. Confirmed the server is returning a `200 OK` status.
**Resolution:** Verified the JSON payload correctly reflects the updated user status, ensuring the front-end can now display the "Premium" dashboard to the client.

![Postman Screenshot](04_api_verification.png)

---

## Final Thoughts
This project shows I can jump into different parts of a tech stack to find the root cause of a ticket. I don't just "guess"—I use logs and database queries to prove what's broken and ensure the fix is verified.
