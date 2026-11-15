# AETHER — Astronaut Health Evaluation, Tracking & Early Response

**NASA Space Apps Challenge 2026** · *Create Health Monitoring Software for Astronauts on Space Missions*

AETHER is an offline-first **decision-support prototype** exploring how crew-entered health observations, synthetic sample trends and mission-environment context could be brought together in one interface. It is a demonstration concept—not a deployed spacecraft system.

## Run the prototype

1. Download or clone this repository.
2. Open `index.html` in a modern browser. For the service worker and full offline/PWA behavior, serve the folder over localhost or HTTPS (for example, `python3 -m http.server 8080`).
3. Open `http://localhost:8080`.
4. Review the safety notice before entering the demo.

No build step or account is required. Health entries are stored in the browser's local storage.

## What the prototype demonstrates

- **Crew check-ins:** seven indicators—resting heart rate, systolic blood pressure, sleep, body temperature, mood/readiness, fasting glucose and exercise.
- **Synthetic trend comparison:** readings are compared with a demonstration baseline and broad reference bands. These thresholds are illustrative, not clinically validated.
- **Mission Context Intelligence:** combines patterns across indicators with simulated cabin context and public NASA space-weather event information where available. Each insight displays confidence, limitations and reference links.
- **Measurement Guide:** explains measurement considerations and why each indicator may matter during spaceflight.
- **Mission environments:** spacecraft, space station, rover and lunar/Mars base profiles change the contextual emphasis.
- **Crew and Medical views:** review queue, acknowledgements, local audit trail, and JSON/CSV/print exports.
- **Offline-capable interface:** app shell and locally entered records remain available in the browser. There is **no health-record server sync** in this version.
- **Demonstration scenario:** injects synthetic sleep and cabin-CO₂ changes to illustrate how contextual insights appear.
- **NASA Updates and Assistant:** attempts to retrieve public NASA research/media feeds; the assistant uses a built-in reference set and can optionally connect to a user-configured external language-model provider.

## Data provenance — read before interpreting anything

| Data | What it actually represents |
|---|---|
| Crew vitals | Synthetic demonstration data, not astronaut measurements |
| Cabin environment | Synthetic demonstration data, not spacecraft telemetry |
| Crew check-ins | Manually entered by the person using the prototype |
| Demo scenario | Synthetic scenario generated locally |
| NASA DONKI | Public solar/space-weather event context, when the API is reachable; **not** an onboard radiation-dose measurement |
| NASA NTRS / NASA Image Library | Public research metadata and media search results when reachable; not clinical recommendations |

The NASA APIs provide context only. A solar flare or SEP event is not a direct measurement of the dose received by a crew member inside a shielded vehicle.

## Safety, limitations and privacy

- AETHER is **not a medical device**, does not diagnose or treat, and has not been clinically validated or tested with astronauts.
- Generic adult reference bands and z-score thresholds are illustrative placeholders. They are not mission-approved limits and must not be used for real medical decisions.
- The personal baseline in this demo is derived from generated sample data. A real system would require validated, individual pre-flight baselines and clinician-approved interpretation.
- Simulated cabin CO₂ and radiation values must not be mistaken for real environmental sensor readings. No onboard sensor integration is implemented.
- Records, API keys and optional AI-provider settings are stored in browser local storage. They are not sent to a health-record server. If the optional external AI feature is enabled, prompts and selected context are sent to the provider configured by the user. Avoid entering sensitive information.
- Follow mission medical procedures and the flight medical team's instructions in any real situation.

## NASA and partner references

- [NASA Human Research Program — Hazards](https://www.nasa.gov/hrp/hazards/)
- [NASA Human Research Program — Risks](https://www.nasa.gov/hrp/risks/)
- [NASA HRP — Ongoing Research](https://www.nasa.gov/hrp/ongoing-hrp-research/)
- [NASA Open APIs / DONKI](https://api.nasa.gov/)
- [NASA Open Science Data Repository](https://osdr.nasa.gov/)
- [Canadian Space Agency — Monitoring Radiation for Astronaut Health](https://www.asc-csa.gc.ca/eng/news/articles/2026/2026-02-26-monitoring-radiation-astronaut-health.asp)

## Current implementation status

Implemented in this prototype: browser-based dashboard, synthetic sample data, manual check-ins, local trend visualizations, rule-based contextual insights, NASA API fetch attempts, local exports and offline app-shell caching.

Not implemented: validated clinical algorithms, real wearable/ECLSS connections, onboard radiation dosimetry, authenticated multi-user access, secure server-side storage, delay-tolerant mission communications, or operational flight-surgeon workflows.

## Roadmap

1. Validate requirements with spaceflight medical and human-factors experts.
2. Replace synthetic inputs with clearly permissioned, authenticated telemetry adapters and quality checks.
3. Integrate curated NASA OSDR datasets with documented provenance and reproducible analysis.
4. Develop clinician-reviewed alert logic and uncertainty reporting.
5. Design secure, role-based data governance and delay-tolerant synchronization.
6. Conduct usability, accessibility, reliability and safety testing before any operational use.

## Challenge submission

See [`docs/SUBMISSION.md`](docs/SUBMISSION.md) for the project summary, problem framing, innovation, current limitations and suggested live-demo sequence.

## Project structure

- `index.html` — application interface and prototype logic
- `privacy.html` — privacy notice
- `sw.js` — offline app-shell service worker
- `knowledge.json` — optional updateable assistant knowledge pack
- `feed-snapshot.json` — optional static NASA feed snapshot
- `docs/` — pitch, testing notes and publishing guidance
- `tests/` — optional Playwright browser checks (requires Playwright installed)
