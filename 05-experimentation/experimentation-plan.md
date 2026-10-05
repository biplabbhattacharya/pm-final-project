# Experimentation Plan

> **Module 5 · ★ Deliverable 5.** Repo file `05-experimentation/experimentation-plan.md` — part of your submission.
> Do the lab in the **Module 5 · Exercise Guide** (linked from the Module 5 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Experimentation Plan** slide of your Module 6 final deck.

# Experimentation Plan (Module 5)

## Get your documents ready
- **From M3, your hypothesis sentence:** Based on users leaving the platform after browsing and not converting to power users, I believe that curating the catalog of titles for users that struggle with navigating a massive library will result in increased engagement and user retention, as measured by a 15% change in retention for users using spotlight. I will protect power user levels and will make a go/no-go decision after working on the spotlight program.
- **From M3, your primary success metric & guardrail metric:** Increased Search to play conversion rate and increased visitors with 30+ minute sessions
- **From M4, the feature you scoped in your PRD this is what you're testing:** A1 Spotlight Curated Rail

## Define your experiment parameters
- **Feature under test pull from your M4 PRD:** A1 Spotlight Curated Rail, This rail is the Spotlight treatment that drives the 12–15 point Month 1 lift. It shrinks the catalog right at the Moment of Misery, and it can reuse existing rail components.
- **Persona pull your M2 persona:** Priya, a 34-year-old subscriber with 14 years of tenure, one of StreamLine's most loyal, long-standing viewers. She wants to sit down and quickly land on something she actually wants to watch, without the session turning into a chore. She opens the app, scrolls for roughly twenty minutes through a catalog of 15,000 titles, finds nothing she wants, and closes the app without watching anything — in her words, she "ended up going back to a DVD."
- **Expected outcome the behaviour change you expect, from your M3 hypothesis:** More engaged users with more content played. Fewer wanderers or casual browsers.
- **Primary success metric the one number that defines success, from M3:** Increased Search to play conversion rate and increased visitors with 30+ minute sessions
- **Baseline rate today's rate of your primary metric, from your M3 data:** 11%
- **Guardrail metric & boundary what must not break, and how far it can move before you investigate:** Power Users should be greater than 22%
- **Minimum Detectable Effect (MDE) the smallest improvement worth shipping, your floor:** 4
- **Sample size per arm use the calculator in the builder, baseline + MDE:** 1109
- **Traffic split & test duration 50/50 standard · cover ≥ 2 weekly cycles:** 50/50
- **Significance threshold p < 0.05 is standard, explain any deviation:** p < 0.05

## Define your control and variant
- **Control (A) the current experience, reference your M2 moment of misery and M3 funnel/workflow data:** Product as-is. No changes
- **Variant (B) your single change, copy the relevant screens & functional requirements from your M4 PRD:** Screens to build:
Homepage with Spotlight Rail - Spotlight rail in the first position, above the fold, followed by standard catalog rows. A prototype control bar switches between mobile and desktop views, cohort (Spotlight or Full-Library), and user region.
Title Detail (from Spotlight) - Title artwork placeholder, name, a short synopsis, runtime, a "From Spotlight" tag, a Play button, and Back to Home.
Now Playing - A mock player with the title name, a "Now playing" confirmation, and a Back to Home button. An on-screen event log shows the events that fired.

Functional Requirements: 
FR1 - The Spotlight rail renders as the first row on the homepage and is fully visible without scrolling at 375×667 (mobile) and 1366×768 (desktop).
FR2 - The rail shows no more than 12 titles. The prototype dataset contains 10.
FR3 - Titles appear in exactly the config array order. The code does zero sorting or reordering.
FR4 - Mobile and desktop views show the same title IDs in the same order, a 100% match.
FR5 - Playback starts in no more than 2 taps from the homepage (tile tap, then Play).
FR6 - Titles marked unavailable, or not licensed for the selected region, are never shown (0 unplayable tiles).
FR7 - If the Spotlight config is empty or invalid, the rail is hidden and every other homepage row still renders, with no error shown to the user.
FR8 - Every rail impression, tile click, and play start logs exactly one event with cohort, title ID, and rail position.
- **Isolation check, what has NOT changed? list everything identical between arms (app version, recommendation engine, notifications, onboarding). If something changed inadvertently, your test is compromised.:** Everything else is the same, library, login screens, recommendation engine, notifications.

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** I believe that Spotlight Curated Rail for the Wanderer will result in Increased engagement and retention,
as measured by a 4% change in Increased Search to play conversion rate and increased visitors with 30+ minute sessions within 2 months.
We will protect Power User proportion at 22% throughout the test.
- **Your shipping criteria (filled in):** We will SHIP if Visitors with 30+ minute sessions improves by ≥ 4% at 0.05 threshold
and Power User proportion does not reach 21% after 2 months.

We will ITERATE if direction is positive but lift is below the MDE.

We will KILL if the primary metric shows no improvement or moves negatively.

The read date is fixed at the end of 2 months, no results reviewed before this date.

- **Hardest parameter to define, and did it change your hypothesis? quick debrief:** The MDE was the hardest parameter to define. I defined it such that we hit at least 15% in overall 30+ min sessions and protect our power users.
