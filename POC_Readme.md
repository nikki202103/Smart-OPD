# Smart OPD — Proof of Concept

## Status: Building the first slice (in progress)
**Live link:** _[to be added once deployed]_
**Repo:** this repository — commits pushed as work progresses, not squashed

---

## What This POC Actually Is

The full Smart OPD concept (see `POC_Readme.md` for the original idea) covers many features — multi-channel registration, voice assistant, rural batch booking, dynamic rescheduling, etc.

**This POC does NOT attempt all of that.** Building the whole thing first and testing nothing is how projects like this fail. Instead, this POC picks **one narrow, end-to-end slice** and makes it real.

---

## The One Use Case This POC Solves

> **A patient can check if today's OPD session has room, register, and receive an arrival window — instead of an exact time or no information at all.**

### What this looks like in practice:
1. An admin (standing in for hospital staff) marks a session: "Available today, 9 AM–1 PM, capacity 20"
2. A patient opens the link, sees the session is open, and registers
3. The patient receives: "You are #7. Come between 10:15–10:30 AM" — a **window**, not a fixed appointment
4. If the admin marks the doctor delayed, the patient's window updates

### What this POC deliberately does NOT include (and why)
| Left out | Why |
|---|---|
| SMS notifications | Requires a paid gateway; doesn't change whether the core window-calculation idea works |
| Voice assistant | Large scope on its own, not needed to prove the core mechanism |
| Walk-in kiosk integration | Real integration problem, but secondary to proving the arrival-window math first |
| Rural batch registration | Depends on the core registration flow existing first |
| Real hospital data / real doctors | No hospital partnership yet — this POC uses simulated sessions |

This list will shrink as the POC grows. Each item removed here should reappear as its own future slice, not be quietly forgotten.

---

## What Already Exists (and how this differs)

Before building, this is what's already out there for government OPDs:

- **ORS (Online Registration System)** — NHP's government appointment booking system, used by AIIMS and others. Lets patients book a fixed appointment slot online.
- **eSanjeevani** — government telemedicine platform, mainly for remote consultations, not in-person OPD queue management.
- **ABDM (Ayushman Bharat Digital Mission)** — health ID and interoperability layer, not a queue/appointment tool itself.

**Gap these don't cover:** none of them assign a **capacity-based arrival window** — they let you book a slot, but everyone can still pick the same early slot, and there's no live adjustment when a doctor is delayed. That gap is what this POC's one use case targets.

*(This section will be expanded with direct testing/comparison once I've used ORS myself, not just read about it.)*

---

## Users

**Who I've shown this to so far:** _[fill in as you test — even one person]_

**What they did:**
- _[e.g., "Registered as a patient, got confused by the word 'window' — expected an exact time"]_

**Where they got stuck:**
- _[be specific and honest — this section is meant to have real friction in it, not a success story]_

*(This section is intentionally incomplete right now — it gets filled in only after a real person actually uses the live link, not before.)*

---

## Decisions Log

A running record of choices made while building this slice — not a clean final design, but the actual path taken.

```
[Date] - Decided to scope down to ONE use case (arrival window) instead of 
         building registration + queue + notifications together, because 
         Satendra's ask was for one working slice, not a full demo.

[Date] - Considered giving an exact appointment time, changed to a window 
         after realizing (in earlier design discussion) that exact times 
         create false promises when consultation length varies.

[Date] - <add entries as you actually build and change your mind>
```

---

## Where AI Helped — and Where It Was Wrong

Used Claude during design and planning. Being specific about both the useful parts and the mistakes:

**Where it helped:**
- Helped structure the arrival-window calculation logic (queue position × average consultation time + buffer)
- Helped identify that giving an exact time instead of a window was a weak design choice

**Where it took me somewhere worse, and I caught it:**
- Early version of the "doctor becomes unavailable" logic let every waiting patient freely choose to switch to another doctor. I pointed out that if everyone picks the same alternate doctor at once, that doctor's queue just gets overloaded — the chaos moves, it doesn't disappear. The logic was reworked to check the alternate doctor's actual spare capacity first, then assign (not invite) a limited number of patients.
- A later version of the same feature added a second, separate "urgent patients first" check inside the rescheduling logic — duplicating a priority decision that should only be made once, at registration. This risked two systems disagreeing with each other. Caught and simplified to a single priority rule.

**Where AI is used inside the actual POC (not just planning):**
- _[Currently: nowhere. The arrival-window calculation is a plain formula — average time × queue position + buffer — not a model. This is a deliberate choice: a plain rule is more transparent and predictable for patients than an AI prediction, and there isn't yet enough real consultation-time data to train anything meaningful.]_

---

## Tech Stack (for this slice only)

```
Frontend: [to be filled in as built]
Backend:  [to be filled in as built]
Database: [to be filled in as built]
Hosting:  [to be filled in once deployed]
```

---

## Next Steps

1. Build and deploy the arrival-window flow (admin marks session → patient registers → gets window)
2. Get at least one real person to use it, record where they got stuck
3. Expand "What Already Exists" with direct hands-on comparison to ORS
4. Push commits incrementally — this README updates as the POC evolves, not after it's finished

---

*This README describes a work in progress. The original full-system vision document is kept separately as `VISION.md` for context, but is not the deliverable — this POC is.*
