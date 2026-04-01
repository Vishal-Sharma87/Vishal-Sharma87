# Hi there, I'm Vishal Sharma! 👋
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=24&pause=1000&color=0077B5&center=true&vCenter=true&width=435&lines=Java+Backend+Developer;Spring+Boot+Enthusiast;System+Design+Learner;Problem+Solver" alt="Typing SVG" />
</p>

### 🛠️ About Me

I am a final-year B.Tech IT student focused on building **scalable, distributed backend systems**. I enjoy deconstructing complex architecture into simple, efficient solutions.

* 🚀 **Currently:** Building event-driven, async backend systems with job queuing, retry logic, and worker orchestration.
* 🧠 **Learning:** Distributed systems (Consistency, Fault Tolerance) and Cloud Infrastructure (AWS/Docker).
* 🎯 **Goal:** Developing production-ready APIs and mastering system design for large-scale applications.
* 🧩 **DSA:** Solving **300+ problems** on LeetCode — actively documenting solutions with production-style clarity in my [DSA-Revision-Java](https://github.com/Vishal-Sharma87/DSA-Revision-Java) repo.

---

### 🚀 Featured Projects

### 🚦 [Traffic Control Service – Async Job Processing Backend](https://github.com/Vishal-Sharma87/traffic-control-service)
*A production-inspired async request processing system that handles high-throughput workloads through intelligent job queuing, worker orchestration, and fault-tolerant retry mechanisms.*

- **Tech Stack:** Java, Spring Boot, Redis, MySQL
- **Key Features:**
  - ⚙️ **Async request processing** — requests are accepted instantly and processed in the background, keeping the API non-blocking
  - 📋 **Job Queue with Retry Logic & Dead Letter Queue** — failed jobs are retried with backoff; unrecoverable jobs are moved to DLQ for inspection, not silently dropped
  - 🩺 **WorkerHeartBeatService** — tracks active workers using `ConcurrentHashMap` + `ScheduledExecutorService`; detects stale/dead workers and cancels them cleanly via `AtomicBoolean` + `Future.cancel(true)` with graceful `@PreDestroy` shutdown
  - 🔍 **Metadata-first result fetching** — clients always query job metadata first; the system hits the database to fetch the actual result **only when status is `COMPLETED`**, avoiding unnecessary DB calls for in-progress or failed jobs

---
 
### 🔗 [URL Shortener – Analytics, Safety Verdicts & Secure Redirection](https://github.com/Vishal-Sharma87/UrlShortener/tree/main)
*A backend-driven URL shortening service that enforces safety verdicts on every redirect, tracks click analytics non-blocking, and secures all APIs with stateless JWT authentication.*
 
- **Tech Stack:** Java, Spring Boot, Spring Security, Apache Kafka, Redis, MongoDB, JavaScript
- **Key Features:**
  - 🛡️ **Three-tier safety verdict system** — every redirect is evaluated as `SAFE`, `SUSPICIOUS`, or `MALICIOUS`; suspicious links show a user confirmation page, malicious links are blocked entirely
  - 📊 **Non-blocking click analytics** — an intermediate HTML page uses JavaScript to capture device, browser, viewport, and timezone data before redirecting; tracking failure never blocks the user
  - 🔐 **Stateless JWT authentication** — all APIs secured with short-lived 10-minute Bearer tokens; no server-side sessions
  - ⚡ **Redis caching** for high-speed short URL lookups and redirection
  - 📨 **Kafka-driven analytics pipeline** — click events published asynchronously, keeping the redirection path low-latency
  - ⚙️ **Environment-based config management** — default config acts as a blueprint; environment variables drive all environment-specific values with no codebase changes needed
 
---

## 💻 Tech Stack

| Category | Tools & Technologies |
| :--- | :--- |
| **Languages** | ![Java](https://img.shields.io/badge/-Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![C++](https://img.shields.io/badge/-C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white) |
| **Frameworks** | ![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white) |
| **Databases** | ![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) |
| **Caching** | ![Redis](https://img.shields.io/badge/-Redis-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Messaging** | ![Apache Kafka](https://img.shields.io/badge/-Apache%20Kafka-231F20?style=flat-square&logo=apache-kafka&logoColor=white) |
| **Concepts** | REST APIs, Event-Driven Architecture, Async Job Processing, Worker Orchestration, Dead Letter Queue, Rate Limiting, Caching, Microservices basics |
| **Tools** | ![Git](https://img.shields.io/badge/-Git-F05033?style=flat-square&logo=git&logoColor=white) ![Maven](https://img.shields.io/badge/-Maven-C71A36?style=flat-square&logo=apache-maven&logoColor=white) |
| **Problem Solving** | Data Structures & Algorithms (Java, C++) |

---

### 🤝 Let's Connect!

I'm always open to collaborating on open-source projects or discussing backend architecture.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/vishal-sharma87)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/_vishal.sharma03)
[![Gmail](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:vishalimp03@gmail.com)

<p align="right">(<a href="#top">Back to top</a>)</p>
