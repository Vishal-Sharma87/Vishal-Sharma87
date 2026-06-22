# Vishal Sharma — Backend Engineer

> **Currently thinking about:** If a job fails 5 times — first 4 due to heartbeat loss, last one due to timeout — should the DLQ store the final cause, or the full failure history? Does losing those 4 causes matter when logs have already rotated out?

---

### 🚀 Featured Projects

#### 🚦 [Traffic Control Service — Distributed Async Job Processing](https://github.com/Vishal-Sharma87/traffic-control-service)

_Fault-tolerant job scheduling engine with Redis-backed priority queues, atomic recovery, and crash detection._

- Tier-based priority scheduling — PAID jobs always execute before UNPAID and PUBLIC, enforced atomically via Lua scripts on Redis ZSET
- Crash recovery complexity dropped from O(n) to O(log n) by switching from linear scan to ZSET range queries
- Distributed admission control via Redis atomic counters — enforced consistently across multiple instances
- Heartbeat monitor detects crashed workers within 500ms via atomic score updates on every pulse
- Terminal failures routed to MySQL Dead Letter Queue after exhausting max retries
- **Known gap identified post-build:** DLQ stores only the final failure cause — intermediate causes are permanently lost once logs rotate. Redesigning failure-cause tracking to persist per-attempt history for production diagnostics.

---

#### 🔗 URL Shortener — Threat Analysis, Analytics & Verdict-Aware Redirection

_Kafka-driven backend reducing link creation latency from 18s to under 20ms through asynchronous threat analysis and event-driven processing._

- Malware scanning offloaded to an asynchronous Kafka pipeline — link creation remains sub-20ms regardless of VirusTotal scan duration
- Verdict-driven redirection engine enforces five safety states (SAFE, SUSPICIOUS, UNVERIFIED, PENDING_REVERIFICATION, MALICIOUS), ranging from instant redirection to permanent blocking
- Analytics capture fully decoupled from user navigation — click telemetry is collected via an intermediate tracking layer and forwarded asynchronously without impacting redirect latency
- Community-driven abuse reporting workflow automatically escalates suspicious links into re-verification pipelines after configurable report thresholds are reached

---

### 📂 Other Repositories

| Repo                                                                              | What's inside                                                                                                                                                                       |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java)       | Problems across Arrays, Trees, Graphs, DP, and more — each with detailed problem breakdown, clean readable code, and documentation explaining the _why_ behind every logic decision |
| [low-level-design-java](https://github.com/Vishal-Sharma87/low-level-design-java) | OOP, SOLID, design patterns (Creational, Structural, Behavioral), and case studies — Parking Lot, Elevator System                                                                   |

---

### 🧰 Tech Stack

| Category                | Skills                          |
| ----------------------- | ------------------------------- |
| **Languages**           | Java • C++                      |
| **Frameworks & Build**  | Spring Boot • Hibernate • Maven |
| **Databases**           | MySQL • MongoDB                 |
| **Caching & Messaging** | Redis • Kafka                   |
| **Tools**               | Docker • Git • Postman          |
| **Testing**             | JUnit5 • Mockito                |

---

### 📬 Connect With Me

🔗 LinkedIn: https://linkedin.com/in/vishal-sharma87

📧 Email: [vishalimp03@gmail.com](mailto:vishalimp03@gmail.com)
