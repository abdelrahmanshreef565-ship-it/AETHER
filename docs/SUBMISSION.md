# AETHER — NASA Space Apps Challenge 2026 Submission Brief

## Challenge
Create Health Monitoring Software for Astronauts on Space Missions.

## One-sentence concept
AETHER is an offline-first astronaut health decision-support prototype bringing crew-entered health observations, synthetic demonstration trends, mission-environment context and public NASA space-weather information into one interface.

## Problem framing
Spaceflight can expose crews to interacting health and human-performance risks, including altered gravity, isolation and confinement, circadian disruption, radiation and environmental constraints. Health observations and mission context can be difficult to interpret together, particularly when communications are delayed or unavailable.

## Proposed approach
- Crew check-ins for resting heart rate, systolic blood pressure, sleep, body temperature, mood/readiness, fasting blood glucose and exercise.
- Trend visualizations against generated demonstration baselines and broad illustrative reference bands.
- Mission-context view highlighting patterns across indicators and simulated cabin conditions.
- Profiles for spacecraft, space station, pressurized rover and lunar/Mars base contexts.
- Separate Crew and Medical views, local review/acknowledgement workflow, and JSON/CSV/print exports.
- Built-in reference assistant and NASA research/media feed retrieval when external services are reachable.
- Service-worker app shell intended to support offline access after a successful first load.

## What is novel in this prototype
AETHER explores a unified, delay-aware workflow rather than isolated vital-sign cards. It makes data provenance visible, keeps locally entered records on-device by default, and distinguishes NASA space-weather context from an actual onboard radiation measurement.

## Data provenance and implementation boundaries
**This is a demonstration prototype, not a deployed spacecraft system.** Crew vital-sign trends and cabin environment values are synthetic. User check-ins are manually entered and stored in browser local storage. Demo scenarios are synthetic. NASA DONKI may provide public solar/space-weather event context when reachable; DONKI events are not direct measurements of crew radiation dose inside a spacecraft. NASA NTRS and NASA Image Library requests are public research metadata/media lookups, not clinical recommendations.

No live astronaut telemetry, wearable integration, ECLSS sensor integration, onboard dosimeter integration, validated clinical prediction, secure multi-user server, or operational flight-surgeon workflow is implemented. The prototype has not been clinically validated or tested with astronauts and must not be used for real medical decisions.

## Suggested demo sequence
1. Open the public site and review the safety notice.
2. Show Overview and explain that initial crew/environment trends are synthetic.
3. Switch between Crew and Medical views.
4. Demonstrate a manually entered check-in using sample values only.
5. Run the built-in synthetic scenario and explain it illustrates interface behavior, not a validated prediction.
6. Show Mission Environment and distinguish simulated cabin values from NASA DONKI event context.
7. Refresh NASA Updates while online.
8. Demonstrate JSON and CSV export using non-sensitive demo records.
9. If practical, test offline behavior after the app shell has been cached.

## Limitations and future work
Future work requires review with spaceflight medical experts, validated and individually approved thresholds, documented permissioned data adapters, curated NASA OSDR analysis, secure role-based data governance, delay-tolerant synchronization, accessibility/usability evaluation, and formal safety and reliability testing.

## Public project
- Live prototype: https://abdelrahmanshreef565-ship-it.github.io/AETHER/
- Source repository: https://github.com/abdelrahmanshreef565-ship-it/AETHER

## Team
The Solo Challenger — one participant.
