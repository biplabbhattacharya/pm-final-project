# Competitive Analysis & Journey Map (Module 2)

## Responses
- **Role, who are you solving for? (the specific user segment or profile):** Priya, a 34-year-old subscriber with 14 years of tenure, one of StreamLine's most loyal, long-standing viewers
- **Goal, what is this user ultimately trying to achieve?:** She wants to sit down and quickly land on something she actually wants to watch, without the session turning into a chore.
- **Friction, the main barrier (moment of misery) stopping them from succeeding:** She opens the app, scrolls for roughly twenty minutes through a catalog of 15,000 titles, finds nothing she wants, and closes the app without watching anything — in her words, she "ended up going back to a DVD." This is the hook's core paradox made literal: maximum volume, zero perceived value, for one of the platform's most engaged users
- **External tools, the outside platforms or tools the user is forced to use:** Strictly speaking, Priya doesn't adopt a new external app or service, her workaround is a regression to legacy physical media (her existing DVD collection and player). This is worth flagging as notable in itself. That makes her workaround harder to detect in product analytics (no competitor sign-up, no support ticket, just silent disengagement) and arguably more dangerous because it's invisible to the business until it hardens into cancellation.
- **The process, the 3 to 5 manual steps the user takes to get the job done:** Open the app with clear intent to watch something.
Manually scroll the home screen for approximately 20 minutes, since descriptive search fails (BUG-1080) and the recommendation rail offers no reliable shortcut (BUG-1091).
Evaluate and reject titles repeatedly with no system assist — pure visual scanning against 15,000 titles.
Give up and close the app without starting anything.
Walk away from the device entirely and retrieve a physical DVD to watch instead.
- **Core frustration, the exact moment the process feels most “broken”:** The exact break point is the instant the 20-minute scroll session ends with zero watch-starts — not a bad recommendation, not a slow load, but total decision paralysis converting into total disengagement. Her own words capture it precisely:"I open the app, scroll for like twenty minutes, and close it without watching anything... I ended up going back to a DVD." The moment the product feels most "broken" isn't a bug or an error state — it's the absence of any resolution after sustained effort. For a subscriber with 14 years of tenure, that's the moment trust in the platform's core value proposition (help me find something to watch) silently fails
- **The evidence, a specific quote or behavior from the research that proves this:** The proof is a direct, verbatim quote from the research, not an inference, but Priya's own account of both the behavior and the workaround in a single statement:

"I open the app, scroll for like twenty minutes, and close it without watching anything. There's 15,000 titles but nothing I actually want. I ended up going back to a DVD." Priya, 34, heavy viewer
- **Your journey map, a shareable link, or the map file you committed (e.g. journey-map.html):** Attached PPTX file
