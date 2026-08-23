LEARN TO READLE — PWA VERSION

FILES
- index.html
- dictionary.js
- manifest.webmanifest
- service-worker.js
- icon-180.png
- icon-192.png
- icon-512.png

WHAT CHANGED
- Installable on iPhone/iPad Home Screen.
- Opens in standalone app mode when launched from Home Screen.
- App files are cached for offline use after the first successful load.
- On mobile, the hint/message area stays visible near the top while scrolling.
- The on-screen keyboard also stays anchored to the bottom on mobile.

HOSTING
Upload every file in this folder to the same GitHub Pages repository/folder.
Do not omit the manifest, service worker, or icons.

IPHONE INSTALL
1. Open the hosted Learn To Readle URL in Safari.
2. Use Share > Add to Home Screen.
3. Launch it from the new Home Screen icon.
4. After the first successful load, the app should continue to work offline.


VERSION 2 UPDATE
- On mobile, the most recently submitted guess stays sticky directly below the hint/message area.
- Older guesses continue to scroll normally.
- The service worker now checks for updates whenever the app opens.
- Navigation uses a network-first strategy so newly deployed versions appear faster.
- Offline support remains available using the cached app shell.
- The cache version was bumped to learn-to-readle-v2.


VERSION 3 — WORD DATA EXPANSION
- Secret-word bank expanded from 216 to 1,600 possible answers.
- Counts: 3-letter 150, 4-letter 300, 5-letter 320, 6-letter 320, 7-letter 280, 8-letter 230.
- answers.js is separate from dictionary.js and index.html.
- Answers come from a higher-frequency, more selective pool than accepted guesses.
- Guess validation dictionary is broadened by combining the previous dictionary with
  an additional spelling/frequency lexicon.
- ORATE and DEBAR are explicitly included and verified.
- All secret answers are guaranteed to be accepted as guesses.
- Service worker cache bumped to v3 and now caches answers.js.


VERSION 4 — COLLAPSIBLE SETTINGS
- Added a settings gear immediately to the left of the top New Word button.
- Word-length and Easy/Hard controls are hidden by default.
- Tapping the gear opens the settings panel.
- Tapping the gear again closes it.
- The existing settings controls and styling are otherwise unchanged.


VERSION 5 — MOBILE STICKY ROWS + KEYBOARD SPACING
- The on-screen keyboard now stays slightly above the iPhone bottom safe area,
  preventing the rounded screen corners from clipping Enter/Backspace.
- The active/current guess row is now sticky on mobile.
- Before the first guess, the active row sits below the hint/message area.
- After a guess is submitted, the latest submitted row remains sticky and the
  active next-guess row stacks directly below it.


VERSION 6 — MOBILE POLISH
- Raised the sticky keyboard farther above the iPhone bottom edge/safe area.
- The active/current guess row now has a subtle light-gray background, outline,
  rounded corners, and a slight shadow so it reads as an intentional sticky input area.
- Latest submitted guesses retain their normal tile appearance.


VERSION 7 — GAMEPLAY POLISH
- Added sequential tile-flip animation after each submitted guess.
- Hints avoid repeating information already known from prior tiles or hints.
- Added a loss popup after the final incorrect guess:
  “Better luck next time! The word was [WORD].”
- Win popup headings now vary randomly between several celebratory messages.
- Input is locked during tile-flip animation.


VERSION 8 — PLAYER PROGRESS + ANSWER ROTATION
- Added an anonymous on-device progress tracker using browser localStorage.
- Tracks unique solved words separately for each word length.
- Shows progress as solved / current secret-answer count for 3–8 letters plus an overall total.
- Does not track win percentage, streaks, losses, or average guesses.
- Added a chart button beside Settings; chart and Settings panels are mutually exclusive.
- Tracks a separate seen-word history for each word length.
- A secret answer will not repeat within a word-length cycle.
- The seen cycle resets only after every CURRENT secret answer of that length has been presented.
- Solved history never resets.
- On startup, saved seen/solved lists are reconciled against the current answers.js:
  removed answers are pruned automatically and newly added answers become eligible automatically.
- Storage uses an internal schema version so future migrations can preserve player progress.


VERSION 9 — GAMEPLAY SAFEGUARDS + PROGRESS CONTROLS
- Repeated guesses are rejected without consuming a turn.
- Repeated-guess feedback: “You already guessed that word.”
- Added RESET to the Progress panel.
- RESET requires explicit YES/NO confirmation.
- Confirming RESET clears both local Solved and Seen histories.
- Resetting progress does not change the answer bank or game settings.
- No hint-logic changes in this release; the possible hint edge case remains an investigation item.


VERSION 11 — PRIVACY-FIRST USAGE ANALYTICS
- Added Umami Cloud analytics with automatic tracking disabled.
- Browser Do Not Track is respected.
- Added only the approved custom usage events documented in ANALYTICS.md.
- No guesses, solved-word history, progress, typed input, names, ages, or Learn To Readle user IDs are sent.
- Added a Privacy section in Settings with the finalized privacy notice.
- Analytics failures do not affect gameplay.
