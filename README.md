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

#### 🚦 [Traffic Control Service — Distributed Async Job Processing](https://github.com/Vishal-Sharma87/traffic-control-service)
*Fault-tolerant job processing system sustaining 33+ jobs/second with tier-based priority scheduling, heartbeat monitoring, and automated recovery.*

- **Stack:** Java · Spring Boot · Redis · MySQL · Docker
- 🏎️ **Priority Queue** — Redis ZSET with atomic Lua scripts — PAID jobs always execute before UNPAID and PUBLIC
- 📉 **Fault Tolerance** — Reduced recovery complexity from O(n) to O(log n) via Redis ZSET range queries
- 🔒 **Admission Control** — Distributed capacity enforcement via Redis atomic counter — multi-instance safe
- 💀 **Resilience** — Permanently failed jobs routed to Dead Letter Queue in MySQL after exhausting max retries
- 💓 **Heartbeat Monitor** — Detected crashed workers within 500ms via atomic score updates on every pulse

---

#### 🔗 [URL Shortener — Async Threat Pipeline & Verdict-Aware Redirection](https://github.com/Vishal-Sharma87/UrlShortener/tree/main)
*Kafka-driven backend reducing link creation from 18s to under 20ms via async VirusTotal scanning across 90+ security engines.*

- **Stack:** Java · Spring Boot · Kafka · MongoDB · Redis · JWT
- ⚡ **Threat Engine** — Offloaded malware scanning to async Kafka consumer pipeline — sub-20ms link creation
- 🛡️ **Redirection Engine** — Enforced 5 safety verdict states — from instant redirect to hard block
- 🔐 **Auth** — OTP-verified email at every sensitive operation — structurally eliminates bot registrations
- 🔁 **Abuse Loop** — 3 community reports auto-trigger re-scanning with zero admin intervention

---

### 📂 Public Repositories

#### 🧠 [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java)
*Structured DSA practice in Java — problems documented with brute force → memoization → tabulation → space optimized approaches.*

- **Topics Covered:** Arrays · Sorting · Binary Search · Strings · Linked Lists · Recursion · Heaps · Sliding Window · Monotonic Stack · Binary Trees · BST · Graphs · Dynamic Programming
- **Format:** Each solution includes JavaDoc, complexity analysis, and inline developer-style comments
- **Reference:** Striver's DSA Sheet

#### 🏗️ [LLD-Java](https://github.com/Vishal-Sharma87/low-level-design-java)
*Hands-on Low Level Design in Java — built concept by concept from OOP fundamentals to real system case studies.*

- **Blocks Completed:** OOP · SOLID Principles · Design Patterns (Creational, Structural, Behavioral)
- **Case Studies:** Parking Lot ✅ · Elevator System · Notification System · Library Management · Food Delivery · ATM Machine
- **Patterns Applied:** Singleton · Factory · Builder · Adapter · Decorator · Facade · Strategy · Observer · State

---


### 🧰 Tech Stack
 
<table>
  <tr>
    <td><b>Languages</b></td>
    <td><img src="https://skillicons.dev/icons?i=java,cpp" title="Java, C++" /></td>
  </tr>
  <tr>
    <td><b>Frameworks & Build</b></td>
    <td><img src="https://skillicons.dev/icons?i=spring,maven" title="Spring Boot, Maven" /></td>
  </tr>
  <tr>
    <td><b>Databases</b></td>
    <td><img src="https://skillicons.dev/icons?i=mysql,mongodb" title="MySQL, MongoDB" /></td>
  </tr>
  <tr>
    <td><b>Caching & Messaging</b></td>
    <td><img src="https://skillicons.dev/icons?i=redis,kafka" title="Redis, Apache Kafka" /></td>
  </tr>
    <tr>
    <td><b>Tools</b></td>
    <td><img src="https://skillicons.dev/icons?i=docker,git,postman" title="Docker, Git, Postman" /></td>
  </tr>
  <tr>
    <td><b>Testing</b></td>
    <td>
      <img src="https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white" title="JUnit 5" />
      <img src="https://img.shields.io/badge/Mockito-78A641?style=flat-square&logoColor=white" title="Mockito" />
    </td>
  </tr>
</table>


---

### 🐍 Contribution Activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
  <img alt="github contribution snake animation" src="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
</picture>

---

### 🤝 Let's Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/vishal-sharma87)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:vishalimp03@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Vishal-Sharma87)
