# SaaS Application Infrastructure & Triage Lab

## 📌 Project Overview
This project simulates a Tier-2 Technical Support environment. I have built a live "sandbox" to demonstrate how I identify, investigate, and resolve complex technical issues across the entire SaaS stack.

## 🛠️ Tech Stack
* **Web Server:** IIS (Internet Information Services)
* **Database:** PostgreSQL (pgAdmin 4)
* **OS/Terminal:** Linux (Ubuntu/WSL)
* **API Testing:** Postman

---

## 🚀 Support Scenarios & Resolutions

### 1. Database Triage: Billing Sync Failure (SQL)
* **Scenario:** A customer reported a plan mismatch after a successful payment.
* **Investigation:** Performed a `JOIN` query between `support_users` and `payments` tables to identify records where `payment_status` was 'success' but `plan_type` remained 'free'.
* **Resolution:** Executed a targeted `UPDATE` statement using the unique User ID to synchronize the account status.

### 2. Log Diving: Server-Side Error Identification (Linux)
* **Scenario:** Application logs indicated intermittent "500 Internal Server Errors."
* **Investigation:** Used Linux command-line tools (`grep`, `tail`) in a WSL environment to parse IIS access logs and isolate specific error timestamps and request paths.
* **Command Used:** `grep "500" app.log | tail -n 5`

### 3. API Health Verification (Postman)
* **Scenario:** Investigating potential connectivity issues between the front-end and back-end.
* **Action:** Built a Postman collection with automated test scripts to verify 200 OK status codes and validate JSON response integrity for core user endpoints.

---

## 📈 How to Navigate This Repo
* `/scripts`: Contains the PostgreSQL DDL and DML scripts used in the lab.
* `/logs`: Sample IIS logs used for troubleshooting practice.
* `/postman`: Exported JSON collection for API testing.

## 🏁 Conclusion
This lab proves I don't just "know" these tools—I know how to use them together to reduce Ticket Resolution Time (TRT) and improve customer satisfaction through technical accuracy.
