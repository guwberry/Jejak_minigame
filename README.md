# Jejak! — A Malaysian Heritage Adventure

Double-click **Jejak.html** to play the standalone offline game. If it is already open, refresh the tab after an update. No installation, account, internet connection or server is needed. The editable source is index.html + style.css + game.js; rebuild the standalone file after edits.

## Playing

Each question appears centrally for two seconds, then floats at the top with its answers. Inputs stay locked during the reveal; there is no answering deadline. Five hearts are shared across all three games. Each wrong answer costs one heart; the fifth miss ends the run. Restarting restores five hearts. Selecting an answer or trying to catch from too far away does not cost a heart. Answer positions shuffle for each new question and new run, while remaining stable during retries; a random shuffle can repeat by chance.

- **A Famosa Fort:** choose a track and Ride. Correct routes collect sparkles and automatically advance to the next question. Wrong routes hit a spike trap, tumble the cart back, eliminate that answer and give a hint. Remaining hearts carry into the next game.
- **Sultan Abdul Samad Building:** each NPC carries an answer above its head. Only the player-selected NPC glows and shows YOUR PICK; the solution is not highlighted. Start the chase, move the explorer yourself, then press E or Catch nearby. Clicking an answer never moves or catches automatically. Catching a wrong NPC gives a hint; being near a correct NPC is required to finish.
- **Kellie's Castle:** choose an orb to walk over and collect it, then throw with E or the button. Incorrect orbs bounce off the shield. Correct hits produce recoil, impact sparks and shield loss. The third hit triggers a collapse/fade death animation and leaves the moonstone behind.
- **Treasure vault:** after collecting all three artifacts, Open treasure starts an approximately 17-second cutscene. The explorer walks to the vault, inserts the key, compass and moonstone in order, unlocks the chest, and reveals the treasure with light and particles. A glowing portal, orbiting artifacts, fireworks and a Heritage Hero celebration complete the finale. The reward screen follows. The booth helper supplies and verifies the physical reward; the game does not track redemption.

Keyboard: arrows / A / D move, Space jumps, E catches or throws, 1–3 select answers, Enter confirms. Chase mode also has press-and-hold movement/jump buttons and a Catch button for mouse or touch. Use the pause menu for help, sound, frame rate, restart and sources. The fullscreen icon requests native browser fullscreen; the game always fills its window.

## Sound and performance

Sound starts after pressing Play and can be muted in the pause menu. Effects include rail clicks, trap impact/bounce, pickups, catch chimes, orb throws, boss impacts/death, artifact insertion, vault unlocking and the treasure fanfare. Audio is synthesized locally, with no media downloads. Hidden tabs stop audio and rendering. Pausing freezes gameplay/cutscenes and stops pending sounds.

Eco mode defaults to 30 fps. Canvas width is 960 pixels; height follows the window, capped at 1440 pixels regardless of display density. Particles are capped at 100 and shockwave rings at 12. There are no frameworks, external fonts, network requests, telemetry, 3D rendering or stored student data. Reduced-motion preference suppresses particles, shake and major rotations while preserving all progress and reward steps. Actual ThinkPad T490 performance and speaker playback still need a check on the booth machine.

## Historical content

Questions are based on the historical-places slides of the supplied MPU's PBL1 – Visit Malaysia presentation by Firas, Hazeeq, Afiq and Adeeb. Other sections are excluded. “Sultan Ahmad Samad” is corrected to **Sultan Abdul Samad**. Scenery is illustrative, not an architectural reconstruction. Characters, traps, relics and guardian are fictional.

Supporting references:
- https://www.malaysia.travel/explore/famous-architectural-landmarks-in-malaysia
- https://www.tourism.gov.my/pdf/uploads/media/mi%20kl%20heritage%20walk.pdf
- https://www.malaysia.travel/explore/kellie-s-castle

Edit the levels array at the top of game.js for questions, choices, correct answer indexes (0–2), hints and explanations.

## Verification — 27 October 2026, shared-lives revision

- JavaScript syntax check passed.
- Browser playthrough at 1366 × 768 completed all nine questions, two wrong tracks, three manual NPC catches, the boss sequence and the expanded finale. Three remaining hearts carried through every level. A distant catch was rejected without losing a heart.
- Inspected brighter scenery and selected-only NPC highlighting, including selecting an incorrect NPC without disclosing the correct answer.
- `node game.test.cjs` verifies all six answer permutations, correct-answer remapping, fifth-miss failure in every mechanic, shared-life carryover, no solution disclosure, selected-only glow, all nine questions, traps, manual catches, boss animations, ordered artifact insertion, extended finale, pause, reset and reduced motion with simulated DOM/canvas.
- Mocked audio output verified 442 synthesized notes. Playback was not independently listened to; speaker quality remains a manual check.
- Final polish to offscreen labels and reopening the reward panel passed automated checks after the browser playthrough.
- Actual touch hardware, screen readers and T490 performance are not independently tested. The in-app browser's direct local-file URL restriction was not bypassed; browser testing used the local HTTP source preview. The delivered offline HTML embeds that same source.

This game is separate from Progression. No deployment or remote service is configured.

## Golden Bunga Raya secret
During an active question, enter Up Up Down Down Left Right Left Right B A. Allow no more than three seconds between presses. Held-key repeats do not count. The secret is unavailable on the title screen, in menus, during other cinematics or after a failed run.

An 8.5-second reveal freezes the current question and lives, summons a golden hibiscus with a three-part synthesized sound sequence, and returns to the same question. Escape pauses the reveal. The HUD flower stays for the current run. Complete all nine questions to see the flower awaken in the treasure portal and receive the distinct Heritage Legend SPECIAL PRIZE badge. Booth helpers handle the physical prize; redemption is not recorded. Restart or Next explorer clears the secret.

Artwork uses fixed-count canvas rays, motes and vector petals. Reduced motion disables drifting, rotation and the falling flight. No assets, downloads or dependencies were added.

Secret verification: real browser keyboard entry, cinematic layout and return to gameplay inspected. Automated tests cover sequence mismatch/timeouts/repeats, one-time activation, freeze/resume, pause, special ending and badge, reduced motion and next-player reset. Audio scheduling is tested with mocked output; speaker playback has not been independently listened to.
