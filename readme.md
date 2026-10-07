
# Surge Triage

After a major incident, 911 lines flood with repeat calls about the same event. Dispatchers lose time sorting duplicates while the callers who need help most wait in the queue.

Surge Triage merges duplicate calls into incidents by place, time and content, then ranks each incident by life threat. New information from a repeat caller is never lost.

Built in 45 minutes at the **Plug and Play x PMAI Hackathon: Rapid Response** (#AIWeekNY, Civic Hall, NYC, Oct 7 2026).

## Demo

With the sample surge (an East Village apartment fire, a car crash, shots fired and unrelated calls):

| | |
|---|---|
| Calls received | 20 |
| Incidents after dedup | 7 |
| Duplicates merged | 13 (65% of call load) |
| P1 incidents | 4 |

**Controls**
- **Replay surge**: streams the sample calls in one at a time.
- **Show all calls**: loads the full surge at once.
- **Add a call**: type a transcript, pick a location, and see where it lands.
- **Acknowledge**: clears a "new info" alert once a dispatcher has reviewed it.

## How it works

### 1. Duplicate detection

A new call joins an existing incident only if all of these hold:

- **Place:** within 300 m of the incident's center
- **Time:** within 15 minutes of the incident's most recent call
- **Content:** the same emergency type, or clearly overlapping words (Jaccard similarity ≥ 0.3)

Calls of different known types stay separate unless their wording strongly overlaps. For example, a car break-in reported 90 m from the fire becomes its own incident.

Each match shows a confidence score that blends distance, time gap and content similarity.

### 2. Priority score (0–99)

| Component | Example |
|---|---|
| Base score by type | Fire 40, shots fired 40, medical 40, crash 25, property crime 15, noise 5 |
| Life threats heard on any call | Trapped +30, breathing/cardiac +30, unresponsive +28, weapon +25, bleeding +15, children +12, elderly +10, escalating +10 |
| Silent line | +15 (the caller may not be able to speak) |
| Corroboration | Up to +12 as more independent callers report the same incident |

Tiers: **P1** ≥ 70 (dispatch now), **P2** ≥ 45 (urgent), **P3** below 45 (routine).

### 3. Never drop a caller

A duplicate call is never discarded. If it adds a new life threat (for example, "I'm on the 5th floor and can't get out, my kids are with me"), the incident's score rises and a **New info** alert appears for a dispatcher to review. Every call stays attached to its incident and can be read in full.

## Project structure

```
index.html   Single-file app: UI, sample data, dedup and scoring logic
README.md
```

The app is plain HTML, CSS and JavaScript with no dependencies. Fonts load from Google Fonts.

## Limitations and next steps

- Type and threat detection use keyword rules. A production version would use speech-to-text plus an LLM or classifier to extract incident type, location and threats.
- Locations are simulated on a grid. Real input would come from ANI/ALI or device location data.
- The thresholds (300 m, 15 min) are fixed. They should adapt to incident type, since a wildfire covers far more ground than a car crash.
- Integration with CAD (computer-aided dispatch) systems.
- Dispatcher feedback (merge or split incidents) could tune the matching over time.