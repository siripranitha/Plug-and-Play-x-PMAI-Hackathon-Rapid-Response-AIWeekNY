# Real-Time Event Mobility & Alerting

**Fragmented city updates left operators and crowds reacting late. Built one system to monitor disruptions, push targeted alerts, and guide people home with live, crowd-aware routing.**

---

## 1. Admin Console — Monitor, Decide, Publish

The admin page should answer three questions:

> **What’s happening? What needs intervention? What should we tell people?**

### Core Modules

- **Live operational map:** Street closures, transit disruptions, crowd density, incidents, viewing-zone capacity, emergency vehicle access.
- **Alert queue:** Automatically flags conditions like:
  - `Zone A >90% capacity`
  - `Fulton St station bypassed`
  - `Crowd expanding outside perimeter`
  - `Travel time +20 min`
- **Recommended action:** System proposes the operational response and public message, but an authorized admin approves, edits, or publishes.
- **Multi-channel publishing:** One action pushes adapted messages to:
  - Public web/app
  - Push notifications
  - SMS
  - Social media
  - Digital signage
  - Agency/operator feeds
- **Audience targeting:** Publish by geography, route, station, event zone, or traveler type rather than blasting everyone.
- **Message status:** `Drafted → Approved → Published → Superseded/Expired`, with an audit trail.

### Suggested Layout

| Left | Center | Right |
|---|---|---|
| Map and live conditions | Prioritized incident/alert feed | Recommended intervention + message composer + channel controls |

### Core Workflow

**Signal → Validate → Assess Impact → Recommend Response → Approve → Distribute → Measure Response**

---

## 2. Public Visual — “What Should I Do Right Now?”

This should be dramatically simpler. People in a crowd will not read an operations dashboard.

The main visual is a **live mobility map** showing:

- 🟢 **Green:** Normal / recommended
- 🟡 **Yellow:** Congestion developing
- 🔴 **Red:** Avoid / closed / at capacity
- Closed streets and stations
- Full viewing zones
- Safe exits
- Recommended alternative stations/routes

### Primary Recommendation

At the top, give the person **one highly visible recommendation**:

> **Avoid Fulton St.**  
> Heavy crowding and station restrictions.
>
> **Best route home:** Walk 8 min north to Chambers St → take the 1.
>
> Adds 4 min walking, saves ~18 min overall.

Then underneath:

- **What changed:** Fulton entrance closed at 1:42 PM
- **What to do:** Use Chambers St
- **Next update:** Automatically refreshed as conditions change

The user should **never have to interpret ten separate alerts**.

---

## Shared Intelligence Layer

Both pages should run from the same event model:

### Inputs

Official closure feeds + MTA/transit feeds + police/emergency operations + event capacity + sensors/cameras/counting systems + validated public reports/social signals

↓

### Event Engine

Normalizes signals, detects anomalies, calculates severity, predicts crowd movement, and identifies affected populations.

↓

### Decision Layer

Determines:

**Who is affected → What action is appropriate → When to notify → Which channel**

↓

### Distribution

Admin console + public map + push/SMS/social/signage

---

## Data Confidence & Trust

The critical distinction is that **social media should be a supporting signal, not automatically trusted operational truth**.

- **Official data:** Higher confidence and operational authority.
- **Public reports:** Useful for identifying situations before an agency formally updates its feed.
- **Social signals:** Useful for detecting emerging incidents, crowd sentiment, or potential disruptions, but should be validated before triggering high-impact operational actions.

This creates a system where **official sources establish truth, while public signals improve detection speed**.

<img width="512" height="275" alt="nyc-monitoring" src="https://github.com/user-attachments/assets/53d31420-c7b7-47cf-8b9a-1071eecb5b16" />

Operator view of the application:
<img width="1768" height="932" alt="image" src="https://github.com/user-attachments/assets/f1364aa0-a416-4c7c-be02-9e68b325e095" />

User view of the application:
<img width="1768" height="2677" alt="image" src="https://github.com/user-attachments/assets/ed74267a-1750-4b6f-839a-a431208429c5" />

