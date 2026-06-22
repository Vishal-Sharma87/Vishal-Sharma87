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

#### 🔗 [URL Shortener — Async Threat Pipeline & Verdict-Aware Redirection](https://github.com/Vishal-Sharma87/UrlShortener/tree/main)

_Kafka-driven backend reducing link creation latency from 18s to under 20ms via async VirusTotal scanning._

- Malware scanning offloaded to async Kafka consumer pipeline — link creation stays sub-20ms regardless of scan duration
- Five-tier safety verdict system controls redirection — from instant pass-through to hard block
- OTP-verified email at every sensitive operation — structurally eliminates bot registrations
- Three community abuse reports auto-trigger re-scanning with zero admin intervention

---

### 📂 Other Repositories

| Repo                                                                              | What's inside                                                                                                                                                                       |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java)       | Problems across Arrays, Trees, Graphs, DP, and more — each with detailed problem breakdown, clean readable code, and documentation explaining the _why_ behind every logic decision |
| [low-level-design-java](https://github.com/Vishal-Sharma87/low-level-design-java) | OOP, SOLID, design patterns (Creational, Structural, Behavioral), and case studies — Parking Lot, Elevator System                                                                   |

---

### 🧰 Tech Stack

<table>
  <colgroup>
    <col width="220">
    <col>
  </colgroup>

  <tr>
    <th align="left">Category</th>
    <th align="left">Skills</th>
  </tr>

  <tr>
    <td><b>Languages</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=java" width="48"><br>
            <sub>Java</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=cpp" width="48"><br>
            <sub>C++</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td><b>Frameworks & Build</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=spring" width="48"><br>
            <sub>Spring Boot</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=maven" width="48"><br>
            <sub>Maven</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=hibernate" width="48"><br>
            <sub>Hibernate</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td><b>Databases</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=mysql" width="48"><br>
            <sub>MySQL</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=mongodb" width="48"><br>
            <sub>MongoDB</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td><b>Caching & Messaging</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=redis" width="48"><br>
            <sub>Redis</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=kafka" width="48"><br>
            <sub>Kafka</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td><b>Tools</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=docker" width="48"><br>
            <sub>Docker</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=git" width="48"><br>
            <sub>Git</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://go-skill-icons.vercel.app/api/icons?i=postman" width="48"><br>
            <sub>Postman</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td><b>Testing</b></td>
    <td>
      <table>
        <tr>
          <td align="center">
            <img src="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/main/icons/Junit%20logo.png" width="48"><br>
            <sub>JUnit5</sub>
          </td>
          <td width="20"></td>
          <td align="center">
            <img src="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/main/icons/Mockito%20Logo.png" width="48"><br>
            <sub>Mockito</sub>
          </td>
        </tr>
      </table>
    </td>
  </tr>

## </table>

### 🐍 Contribution Activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
  <img alt="github contribution snake animation" src="https://raw.githubusercontent.com/Vishal-Sharma87/Vishal-Sharma87/output/github-snake.svg" />
</picture>

---

### 📬 Connect With Me

🔗 LinkedIn: https://linkedin.com/in/vishal-sharma87

📧 Email: vishalimp03@gmail.com
