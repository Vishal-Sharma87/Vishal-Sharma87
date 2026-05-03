# Hi there, I'm Vishal Sharma! 👋

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=24&pause=1000&color=0077B5&center=true&vCenter=true&width=500&lines=Distributed+Systems+Engineer;Fault-Tolerant+Backend+Architect;Java+%C2%B7+Spring+Boot+%C2%B7+Redis+%C2%B7+Kafka" alt="Typing SVG" />
</p>

---

### 🛠️ About Me

I architect fault-tolerant backend infrastructure built for scale and reliability.

- 🚀 **Currently:** Building distributed async job processing systems with Redis-backed priority queues, atomic Lua scripts, and recovery schedulers
- 🎯 **Targeting:** SDE-1 roles at product companies and mid-to-unicorn startups
- 🧩 **DSA:** 300+ problems solved across Graphs, DP, Backtracking, Trees, and Binary Search

---

### 🚀 Featured Projects

### 🚦 [Traffic Control Service — Distributed Async Job Processing](https://github.com/Vishal-Sharma87/traffic-control-service)
*Fault-tolerant job processing system sustaining 33+ jobs/second with tier-based priority scheduling, heartbeat monitoring, and automated recovery.*

- **Stack:** Java · Spring Boot · Redis · MySQL · Docker
- **Key Features:**
  - 🏎️ **Priority Queue** — Redis ZSET with atomic Lua scripts — PAID jobs always execute before UNPAID and PUBLIC
  - 📉 **Fault Tolerance** — Reduced recovery complexity from O(n) to O(log n) via Redis ZSET range queries — two independent schedulers detect heartbeat expiry and max processing time breaches
  - 🔒 **Admission Control** — Distributed capacity enforcement via Redis atomic counter — multi-instance safe without JVM-local synchronization
  - 💀 **Resilience** — Permanently failed jobs routed to Dead Letter Queue persisted in MySQL after exhausting tier-specific max retries
  - 💓 **Heartbeat Monitor** — Detected crashed workers within 500ms by atomically updating processing store scores on every pulse

---

### 🔗 [URL Shortener — Async Threat Pipeline & Verdict-Aware Redirection](https://github.com/Vishal-Sharma87/UrlShortener/tree/main)
*Kafka-driven backend reducing link creation from 18s to under 20ms via async VirusTotal scanning across 90+ security engines.*

- **Stack:** Java · Spring Boot · Kafka · MongoDB · Redis · JWT
- **Key Features:**
  - ⚡ **Threat Engine** — Offloaded malware scanning to async Kafka consumer pipeline — reduced link creation from 18s to under 20ms across 90+ security engines
  - 🛡️ **Redirection Engine** — Enforced 5 safety verdict states — from instant redirect to hard block — via hash-based routing
  - 🔐 **Auth** — Structurally eliminated bot registrations by enforcing OTP-verified email at every sensitive operation
  - 🔁 **Abuse Loop** — 3 OTP-verified community reports automatically trigger re-scanning, requiring zero admin intervention

---

### 🧰 Tech Stack

**Languages**

[![Languages](https://skillicons.dev/icons?i=java,cpp)](https://skillicons.dev)

**Frameworks & Build**

[![Frameworks](https://skillicons.dev/icons?i=spring,maven)](https://skillicons.dev)

**Databases**

[![Databases](https://skillicons.dev/icons?i=mysql,mongodb)](https://skillicons.dev)

**Caching & Messaging**

[![Caching and Messaging](https://skillicons.dev/icons?i=redis,kafka)](https://skillicons.dev)

**Tools**

[![Tools](https://skillicons.dev/icons?i=docker,git,postman,idea)](https://skillicons.dev)

---

### 🐍 Contribution Activity

<picture>
  <source media="(prefers-color-scheme: dark)"  srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
  <img alt="github contribution snake animation" src="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
</picture>

---

### 🤝 Let's Connect

I'm always open to collaborating on open-source projects or discussing backend architecture.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/vishal-sharma87)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:vishalimp03@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Vishal-Sharma87)
