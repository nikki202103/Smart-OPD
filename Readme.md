# 🏥 Smart OPD

> **Don't just book an appointment. Know when to arrive.**

Smart OPD is a **patient-flow and queue management system** designed to reduce overcrowding and unnecessary waiting in government hospital OPDs.

## 🚨 Problem

Government OPDs often face:

* Long registration queues
* Patients arriving hours before the doctor
* Uncertain doctor availability
* Overcrowded waiting areas
* Unpredictable walk-ins
* Difficulties for patients travelling from rural areas

### Root Cause

```text
Everyone arrives early
        ↓
Crowding
        ↓
Long queues
        ↓
Long & unpredictable waiting
```

## 💡 Our Solution

Smart OPD doesn't just give patients an appointment — it manages **when they should arrive** based on the current hospital situation.

### 🔑 Key Features

* 👨‍⚕️ **Doctor Availability** — Check whether the doctor is available before travelling.
* 🕐 **Smart Arrival Windows** — Distribute patients across the OPD session instead of making everyone arrive early.
* 🎫 **Live Queue Tracking** — Token number, patients ahead, and estimated waiting time.
* 🔄 **Dynamic Rescheduling** — Recalculate queues when doctors are delayed or unavailable.
* 🚶 **Walk-in Support** — Walk-in patients join the same coordinated queue.
* ☎️ **Non-Digital Access** — Registration through hospital staff and telephone support.
* 🌾 **Rural Patient Support** — Consider travel and transport constraints.
* 📴 **Offline Fallback** — Basic queue operations can continue during connectivity issues.
* 🚨 **Safety Escalation** — Predefined warning signs can be flagged for medical-staff review.

## 🔄 How It Works

```text
Patient Registration
        ↓
Check Doctor Availability
        ↓
Arrival Window + Token
        ↓
Patient Arrives
        ↓
Live Queue Tracking
        ↓
Doctor Consultation
```

If something changes:

```text
Doctor Delay / Walk-in / Cancellation
              ↓
       Queue Recalculation
              ↓
        Patient Notification
```

## 🆚 What Makes It Different?

| Traditional Appointment        | Smart OPD               |
| ------------------------------ | ----------------------- |
| Books a slot                   | Manages patient flow    |
| Fixed appointment              | Dynamic arrival window  |
| Queue often handled separately | One coordinated queue   |
| Limited delay updates          | Live updates            |
| Mainly digital                 | Digital + phone + staff |
| Walk-ins may disrupt flow      | Walk-ins integrated     |

> **An appointment system schedules patients. Smart OPD manages how patients move through the hospital.**

## 🧪 Prototype

The MVP focuses on:

1. Patient Registration
2. Doctor Availability
3. Arrival Window Generation
4. Token & Queue Management
5. Live Queue Dashboard
6. Doctor Delay Simulation
7. Staff Dashboard

### Demo

```text
10 patients register
        ↓
System checks capacity
        ↓
Patients receive different arrival windows
        ↓
Patients enter the queue
        ↓
Doctor delay is simulated
        ↓
Queue automatically updates
```

## 🛠️ Tech Stack

* **Frontend:** React.js
* **Backend:** Python / Flask
* **Database:** PostgreSQL
* **APIs:** REST
* **Notifications:** SMS / Push
* **Deployment:** Cloud / Hospital infrastructure

## 🎯 Goal

Transform:

**Crowded → Unpredictable → Long Waiting**

into:

**Planned → Visible → Coordinated Patient Flow**

> **Smart OPD — Making hospital visits more predictable, one patient flow at a time.**
