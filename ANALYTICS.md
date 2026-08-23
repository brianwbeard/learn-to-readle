# Learn To Readle — Analytics Specification

## Purpose
Learn To Readle uses privacy-focused analytics solely to understand how the game is being used and to help operate and improve it. Analytics are provided by Umami.

## Privacy Principles
Learn To Readle does not send analytics containing player guesses, solved-word history, player progress, anything typed by the player, names, email addresses, ages, or a Learn To Readle user ID.

Analytics are not used for advertising, marketing, contacting individual players, or creating individual player profiles. Browser Do Not Track is respected.

## Event Definitions

### `app_opened`
Fires once when Learn To Readle loads. This does not mean the visitor played a game.

### `game_started`
Fires when the player submits the first valid guess of a game. It does not fire when the app merely generates a game, an invalid word is entered, or a repeated guess is entered.

Properties: `length` (3–8), `mode` (`easy` or `hard`).

### `game_completed`
Fires when the answer is successfully guessed or the final available guess is used.

Properties: `length`, `mode`, `hints_used` (`true`/`false`).

Win/loss information is deliberately not collected.

### `new_game_after_completion`
Fires when the player submits the first valid guess of a new game after completing the previous game. It does not fire merely because New Word is tapped.

Properties: `length`, `mode`.

### `hint_used`
Fires only when the game successfully provides a useful hint.

Properties: `length`, `mode`.

### `settings_opened`
Fires when the Settings panel is opened.

### `progress_opened`
Fires when the Progress panel is opened.

### `about_opened`
Fires when About Learn To Readle is opened.

### `grownups_opened`
Fires when For Parents & Grown-Ups is opened. This does not indicate that the math gate was passed or that a contribution was made.

### `reset_progress`
Fires only after the player confirms YES on the Reset Progress confirmation.

## Interpreting the Main Funnel
Primary funnel: `app_opened` → `game_started` → `game_completed` → `new_game_after_completion`.

These are event counts, not counts of identified people.

## Visitors and Visits
Umami separately provides anonymous visitor and visit estimates. These should not be confused with Learn To Readle's custom events.

## Implementation Rules
- Analytics must never interfere with gameplay.
- If Umami is unavailable, blocked, offline, or disabled because Do Not Track is enabled, Learn To Readle must continue normally.
- Automatic Umami tracking is disabled.
- Learn To Readle sends only explicitly approved custom events.
- Learn To Readle does not call Umami `identify()` or assign a persistent analytics user ID.
- Update this file whenever an event definition changes.

Last updated: August 2026
