# Plug and Play × PMAI Hackathon: Rapid Response (#AIWeekNY)

Three emergency-response challenges, each solved in 45 minutes. Each challenge lives on its own branch, with its own README, screenshots and demo.

## The three challenges

| Round | Challenge | What we built | Branch |
|---|---|---|---|
| 1 | **Restaurant booking outage** | Resy Outage Playbook: a plan and tool to keep service running when the booking system goes down | [`resy-outage`](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/resy-outage) |
| 2 | **Real-time event alerting** | Event Mobility & Alerting: an operator console and public map that guide crowds home during city events | [`Real-Time-event-alerting`](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/Real-Time-event-alerting) |
| 3 | **911 call management** | Surge Triage: a dispatcher console that merges duplicate 911 calls and ranks incidents by life threat | [`911-call-management`](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/911-call-management) |

---

### 1. Resy Outage Playbook

**Problem:** A restaurant runs reservations, guest contacts and payments through one vendor, Resy. When Resy goes down during service, staff can't see who is coming, reach guests or take payments. The damage continues after Resy comes back, because offline changes conflict with its data.

**What we built:**
- A playbook that sorts every task by the **4 D's**: Do, Delegate, Defer, Delete. It answers "what do we do in the next 30 minutes?"
- A shared "Tonight's book" tool that serves as the single source of truth for bookings while Resy is down. Only one named decision-maker can change it.
- Five tenets, including "a confirmed reservation is always honored" and "no guest is charged twice or left unrefunded."

![Resy Outage Playbook overview](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/blob/resy-outage/resy-outage-slid.png?raw=true)

➡️ **[Open the resy-outage branch](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/resy-outage)**

---

### 2. Real-Time Event Mobility & Alerting

**Problem:** During large city events, updates about closures, transit and crowding are scattered across many sources. Operators and crowds find out too late.

**What we built:** One shared event engine that feeds two views.
- **Operator console:** a live map, a prioritized alert queue, a recommended response, and one-click publishing to app, push, SMS, social and signage, targeted by area or route.
- **Public view:** one clear recommendation for each person, such as "Avoid Fulton St. Walk 8 min to Chambers St and take the 1."
- **Trust model:** official data sets the truth. Public reports and social posts help spot problems early but are checked before they trigger major actions.

![Operator view](https://github.com/user-attachments/assets/f1364aa0-a416-4c7c-be02-9e68b325e095)

➡️ **[Open the Real-Time-event-alerting branch](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/Real-Time-event-alerting)** (includes the concept PDF)

---

### 3. 911 Surge Triage

**Problem:** After a major incident, 911 lines flood with repeat calls about the same event. The callers who need help most wait behind the duplicates.

**What we built:** A working dispatcher console.
- Merges duplicate calls into one incident when they match on **place** (within 300 m), **time** (within 15 min) and **content** (same emergency type or overlapping words).
- Scores each incident from 0 to 99 based on type and life threats such as trapped, unresponsive, shots fired or children present. Assigns each one to P1, P2 or P3.
- **Never drops a caller.** A repeat call that adds a new threat raises the score and flags the incident for a dispatcher.
- In the sample surge, 20 calls became 7 incidents. That's 65% less noise, with 4 incidents flagged as P1.

![Surge Triage dashboard](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/blob/911-call-management/Screenshot%202026-10-07%20at%207.30.37%E2%80%AFPM.png?raw=true)

[![Watch the Surge Triage demo](https://img.youtube.com/vi/9Z6D6FD1F6E/hqdefault.jpg)](https://youtu.be/9Z6D6FD1F6E)

➡️ **[Open the 911-call-management branch](https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY/tree/911-call-management)** (open `index.html` to run the demo)

---

## What the three solutions share

- **AI drafts, humans decide.** The software sorts, scores and recommends. A person approves anything that touches money, a guest's booking, a public alert or a dispatch.
- **One source of truth.** A single booking sheet, a single event model, or a single incident record replaces scattered updates.
- **Plan for recovery, not just the crisis.** Each design covers what happens after the emergency: reconciling records, expiring old alerts, and keeping every caller's report on file.

## How to browse this repo

The `main` branch holds only this overview. To see a solution, switch branches with the branch menu on GitHub, or click a branch link above. To clone a single challenge:

```bash
git clone -b 911-call-management https://github.com/siripranitha/Plug-and-Play-x-PMAI-Hackathon-Rapid-Response-AIWeekNY.git
```


| | |
|---|---|
| **Event** | Plug and Play × PMAI Hackathon: Rapid Response, part of AI Week NY |
| **Hosts** | Plug and Play and Pioneering Minds AI Group (PMAI) |
| **Where** | Civic Hall, 124 E 14th St, New York, NY |
| **When** | Wednesday, October 7, 2026, 5–9 PM |
| **Event page** | [luma.com/jp1ai4xe](https://luma.com/jp1ai4xe) |

## About the hackathon

Most hackathons give teams hours or days to solve one problem. Rapid Response took the opposite approach. Teams of 2–4 faced three emergency-response scenarios in three rounds of about 45 minutes each.

Each round tested how quickly a team could understand a problem, make decisions under pressure, build a working solution, and explain its thinking.
