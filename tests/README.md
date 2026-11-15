# AETHER browser smoke-test checklist

These are manual acceptance checks, not automated clinical or flight-readiness tests.

## Before testing
- Use a current desktop browser and a narrow/mobile viewport.
- Open the public site over HTTPS.
- Do not enter real personal or medical information; use demonstration values only.
- Review the safety notice before using the prototype.

## Functional checks
- [ ] Safety notice appears on a fresh browser profile; Enter stays disabled until acknowledgement is checked.
- [ ] Overview renders without a blank screen or visible JavaScript error.
- [ ] Navigation opens the available views: Overview, Health, Environment, Intelligence, Guide, Assistant, Updates, Settings, Body, Routine, Medical and About.
- [ ] Crew selector changes the selected crew member.
- [ ] Crew/Medical role switch changes the view and navigation state.
- [ ] Health check-in accepts sample values and reports that the entry was saved locally.
- [ ] Reloading preserves the manually entered check-in in the same browser profile.
- [ ] JSON export downloads a file that parses as JSON.
- [ ] CSV export downloads a file with a header and data rows.
- [ ] Demo scenario adds synthetic records and is clearly identified as a scenario.
- [ ] NASA Updates refresh shows results or a clear empty/unavailable state.
- [ ] Assistant responds using the built-in knowledge base when external AI is disabled.
- [ ] Settings and local-data deletion behave as described; use disposable demo data only.

## Offline / PWA checks
- [ ] Load online and wait for service-worker registration to complete.
- [ ] In developer tools, confirm the service worker is activated for the /AETHER/ scope.
- [ ] Confirm app-shell assets are present in Cache Storage.
- [ ] Switch browser to offline mode and reload; confirm cached interface opens.
- [ ] Confirm NASA API-backed features report unavailable/offline rather than implying fresh data.
- [ ] Restore connectivity and confirm the app remains usable.

## Responsive and accessibility checks
- [ ] At a narrow viewport, navigation remains reachable and content does not require horizontal page scrolling.
- [ ] Keyboard users can reach navigation, form controls and action buttons.
- [ ] Focus indicators are visible.
- [ ] Reduced-motion preference suppresses decorative animation.

## Record results honestly
For each check, record PASS, FAIL or NOT TESTED, browser/version, date and a short note. A successful page load or GitHub Pages deployment does not prove every feature works. These checks do not establish clinical validity, cybersecurity certification or flight readiness.
