# 🏥 Smart OPD: Integrated Patient Flow & Queue Management

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Status: Prototype](https://img.shields.io/badge/Status-Active_Development-brightgreen)
![Focus: Healthcare Tech](https://img.shields.io/badge/Domain-Healthcare_IT-red)

> **Transforming chaotic government hospital OPDs into efficient, predictable, and patient-centered care systems.**

Traditional appointment systems just book slots; **Smart OPD intelligently distributes patient arrivals.** By moving away from a "first-come-first-served" free-for-all, this system reduces patient wait times by 50-70%, ends peak-hour hospital crowding, and gives doctors a predictable, manageable workflow.

---

## 🚨 The Problem: Systemic OPD Overcrowding
* **Patients:** Arrive at 5 AM, wait 2+ hours just to register, and face massive uncertainty regarding doctor availability and queue position.
* **Hospitals:** Uncontrolled 8 AM crowding, registration bottlenecks, and inability to prioritize urgent medical cases over routine checkups.
* **The Root Cause:** Standard appointment booking systems don't manage *when* people arrive, leading to simultaneous arrivals and chaos.

## 💡 The Solution: Intelligent Arrival Distribution

Smart OPD calculates hospital capacity in real-time and tells patients exactly **when to come**, integrating both pre-booked and walk-in patients into a single, coordinated live queue.

### 🔄 Patient Flow: Traditional vs. Smart OPD

```mermaid
graph TD
    subgraph ❌ Traditional OPD Flow
        A1[100 Patients] -->|All arrive at 7 AM| B1(Massive Registration Queue)
        B1 --> C1{Doctor Available?}
        C1 -->|Yes| D1(Wait 2-4 Hours in Chaos)
        C1 -->|No| E1(Wasted Trip / Go Home)
    end

    subgraph ✅ Smart OPD Flow
        A2[Patient] -->|App/Kiosk/Call| B2(Checks Live Doctor Status)
        B2 --> C2(System Assigns 15-Min Arrival Window)
        C2 -->|Arrives at 10:30 AM| D2(Checks Live Queue Status)
        D2 --> E2(Consultation within 20 mins)
    end
