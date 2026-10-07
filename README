### 🎯 Problem Statement

> Our restaurant depends on a single third-party system (Resy) for reservations, guest contact data, and payments. When it fails during operating hours, we can't see who is coming, reach guests, or protect revenue. This causes **double-bookings, no-shows, payment errors, and lost guest trust**, and the damage continues after the system comes back because our offline actions conflict with Resy's data.

---

### 🧭 Tenets (how we make decisions)

1. **A confirmed reservation is always honored.** The guest should never pay for our outage.
2. **There is always one source of truth**, even if it's a paper sheet.
3. **We tell guests before they have to ask.**
4. **No guest is charged twice or left unrefunded.**
5. **We design for recovery, not just the outage.**

---

### 👥 Stakeholders & Pain Points (consolidated)

| **Stakeholder** | **What they need to get done** | **Pain points** |
|---|---|---|
| 🧑‍🤝‍🧑 **Guests (existing booking)** | Show up and be seated as booked | Unsure if the booking is still valid · Can't reach us · Can't change time, party size, or contact info · Can't cancel or get a refund · Special requests (allergies, occasions) may be lost |
| 🚶 **Guests (new / walk-in)** | Get a table tonight | Can't book · No confirmation · No waitlist |
| 💼 **Owner** | Protect revenue and reputation | No guest list · Double-booking risk · Can't charge deposits or no-show fees · Staffing decisions are guesswork · Review risk |
| 🛎️ **Front of house (host, servers)** | Seat guests smoothly | No floor plan or table assignments · Guest notes lost · No waitlist tool · No shared script |
| 🍳 **Kitchen** | Prep for the right volume | Unknown cover count |
| 🔗 **Booking channels (Google, partners)** | Send bookings in | Bookings may still arrive, or fail silently |
| 💳 **Payment processor** | Settle transactions correctly | Deposits, fees, and refunds stuck or duplicated |
| 🖥️ **Resy (vendor)** | Restore service | Unclear on: duration · data sync · automatic guest messages on restore · payment state · SLA credits |

---

### 🔄 The Problem Across 3 Phases

| **Phase** | **Key question** |
|---|---|
| 🚨 **Detect** | How fast do we know, and who declares the outage? |
| 🛠️ **Operate** | How do we reach guests, check availability, and confirm bookings without Resy? |
| ♻️ **Recover** | How do we reconcile our records, fix payments, and stop conflicting messages? |

---

### 🌱 Root Cause

- **Single point of failure**: everything lives inside one vendor.
- **No offline copy** of tonight's bookings.
- **Guest contact data is owned by the vendor**, not by us.

---

### 📏 Success Metrics

- ✅ **100%** of tonight's confirmed guests contacted within **[X] min** of declaring the outage
- ✅ **0** double-bookings
- ✅ **0** payment errors after recovery
- ✅ No-show rate at or below **normal baseline**
- ✅ Records reconciled within **[X] hours** of restore
- ✅ No drop in **review rating**

---

### 🚫 Out of Scope

- Replacing Resy
- Long-term vendor strategy (a follow-up decision)

---

### ❓ Open Questions

1. Do we have an **export of tonight's bookings**?
2. Will Resy **sync or auto-message guests** when it comes back?
3. What's the **state of pending payments**?
4. **Who owns** the outage decision on-site?
5. What does our **Resy contract (SLA)** promise?

---

### ⚡ TL;DR

**Tonight's service is the only thing that matters right now.** Everything else waits until it's over or Resy comes back.

**The 4 D's:**

- 🔴 **Do**: urgent and only you can own it
- 🟡 **Delegate**: urgent, but someone else can run it
- 🔵 **Defer**: important, but not for tonight
- ⚫ **Delete**: not worth effort right now

---

### 🔴 DO (Owner / GM, Next 30 Min)

| **#** | **Action** | **Pain point it solves** |
|---|---|---|
| 1 | **Declare the outage** and name one decision-maker | No one in charge |
| 2 | **Build tonight's booking list** from exports, confirmation emails, screenshots, and partner channels | No guest list |
| 3 | **Create one shared sheet** (or paper book) as the single source of truth | Double-bookings |
| 4 | **Set the rule**: every confirmed booking is honored, and no new bookings for tonight until the list is verified | Overbooking, guest trust |

👉 **Why first:** Nothing else works without a guest list and one place to log changes.

---

### 🟡 DELEGATE (In Parallel, Assign an Owner to Each)

| **Owner** | **Action** | **Pain point it solves** |
|---|---|---|
| 🛎️ **Host / FOH** | Call or text tonight's guests with **one script**: confirm time and party size, ask about allergies or occasions | Guest uncertainty, lost special requests |
| 🛎️ **Host** | Run a **paper waitlist** for walk-ins and call-ins | No waitlist, walk-ins |
| 📣 **Marketing / Manager** | Update **voicemail, Instagram, and Google profile**: "Booking system down, call/text us at ___" | Guests can't reach us |
| 🍳 **Chef** | Plan prep from the **verified cover count**, plus a walk-in buffer | Kitchen prep |
| 💼 **Manager** | Contact **Resy**: ETA, will it sync, will it auto-message guests? | Vendor unknowns |
| 💼 **Manager** | Make the **staffing call** by **[X] pm**, once the list is confirmed | Staffing guesswork |

---

### 🔵 DEFER (After Service / After Resy Is Back)

- ♻️ **Reconcile** the shared sheet against Resy data
- 💳 **Process refunds and cancellations** from tonight
- 🧾 **Check for double charges** with the payment processor
- 📝 **Respond to reviews** about the outage
- 🛡️ **Fix the root cause**: daily export of bookings, own guest contact data
- 📄 **Claim SLA credits** from Resy
