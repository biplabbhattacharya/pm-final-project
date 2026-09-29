# PRD & Prototype Sprint

> **Module 4 · Lab 2.** Repo file `04-roadmap/prd-and-prototype.md` — part of your submission.
> Do the lab in the **Module 4 · Exercise 2 Guide** (linked from the Module 4 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It deepens the top feature from your `roadmap-prd-prototype.md` and feeds the **Roadmap, PRD & Prototype** slide of your Module 6 deck.

## Responses

- **The "Now" feature I'm scoping (name + one-line core description):** Spotlight Curated Rail. The wanderer: The persona we are solving for is the user that has way to many options to choose from and for whom the software does not sync clearly between mobile and desktop. This creates a lot of friction with not able to select new titles or resume progress between platforms.
- **My finalized Must-Haves (after overriding the AI):** Rail sits in the first homepage position, above the fold.
Built with the existing rail component and existing title tiles.
Events for rail impression, tile click, and play start from the rail, all tagged by cohort.
Titles come from a manually maintained list (a config file or an existing CMS field), with no algorithmic reordering
- **What I demoted from Must → Should/Won't, and why:**  Keep the existing Continue Watching row next to the rail for users with titles in progress.
Titles unavailable in the user's region or license window are filtered out.
A retention dashboard by cohort (Day 7, Day 30, Month 1).
- **One thing my PRD makes explicit that a vague brief would have missed:** Functional requirements, smart behaviors, technical constraints.
- **Where the prototype revealed a gap in my PRD logic (what I updated):** _(not filled in)_
- **My shareable prototype URL:** _(not filled in)_



# Spotlight Curated Rail, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** The wanderer: The persona we are solving for is the user that has way to many options to choose from and for whom the software does not sync clearly between mobile and desktop. This creates a lot of friction with not able to select new titles or resume progress between platforms.

## 1. The Big Picture
- **Vision:** Help every new StreamLine member find something worth watching in seconds, not scrolls.
- **Press release:** StreamLine members no longer have to scroll through thousands of titles to find something to watch. Spotlight is a hand-picked rail of 8 to 12 titles that sits first on the homepage, chosen by StreamLine's editors rather than an algorithm. New members see a short, trusted list on their first visit and can start watching right away, without getting lost in the catalog.

Spotlight shows the same picks in the same order on mobile and desktop, so a title spotted on the train is still there that night on the laptop. The full library is still one scroll away for anyone who wants it. Early cohort data shows members who start with a curated experience are 12 to 15 points more likely to still be with StreamLine a month later.
- **Success metric:** Retention and attention
- **Guardrail:** Power users > 22%

## 2. The Details
### User stories
- As a new member overwhelmed by the catalog, I want a short list of hand-picked titles at the top of my homepage so that I can choose something in seconds without scrolling.
- As a member who switches between phone and laptop, I want the same Spotlight picks in the same order on both devices so that a title I noticed on my phone is easy to find later on desktop.
- As a member who has picked a Spotlight title, I want one tap to take me to the title and start playing so that choosing quickly turns into watching.
### Screens to build
- 1. Homepage with Spotlight Rail - Spotlight rail in the first position, above the fold, followed by standard catalog rows. A prototype control bar switches between mobile and desktop views, cohort (Spotlight or Full-Library), and user region.
- 2. Title Detail (from Spotlight) - Title artwork placeholder, name, a short synopsis, runtime, a "From Spotlight" tag, a Play button, and Back to Home.
- 3. Now Playing - A mock player with the title name, a "Now playing" confirmation, and a Back to Home button. An on-screen event log shows the events that fired.
### Functional requirements
- FR1 - The Spotlight rail renders as the first row on the homepage and is fully visible without scrolling at 375×667 (mobile) and 1366×768 (desktop).
- FR2 - The rail shows no more than 12 titles. The prototype dataset contains 10.
- FR3 - Titles appear in exactly the config array order. The code does zero sorting or reordering.
- FR4 - Mobile and desktop views show the same title IDs in the same order, a 100% match.
- FR5 - Playback starts in no more than 2 taps from the homepage (tile tap, then Play).
- FR6 - Titles marked unavailable, or not licensed for the selected region, are never shown (0 unplayable tiles).
- FR7 - If the Spotlight config is empty or invalid, the rail is hidden and every other homepage row still renders, with no error shown to the user.
- FR8 - Every rail impression, tile click, and play start logs exactly one event with cohort, title ID, and rail position.
### Smart behaviors (Situation → Outcome)
- If cohort = Spotlight → the Spotlight rail renders in position 1.
- If cohort = Full-Library → no Spotlight rail renders and the standard rows start at position 1.
- If a title is unavailable or not licensed for the user's region → that tile is skipped and the next title moves up.
- If more than 12 titles remain after filtering → only the first 12 in config order are shown.
- If 0 titles remain after filtering → the rail is hidden and the homepage loads normally.
- If the config is empty or malformed → the rail is hidden and nothing appears in its place.
- If the viewport switches between mobile and desktop → the layout changes, but title order and IDs stay the same.
- If a user taps a Spotlight tile → Title Detail opens with the "From Spotlight" tag, and a spotlight_tile_click event logs.
- If a user taps Play on a title opened from Spotlight → Now Playing opens and a spotlight_play_start event logs.
- If a user opens a title from a standard row → no Spotlight events log and the "From Spotlight" tag is hidden.
- If the Spotlight rail renders → one spotlight_impression event logs per page load, not per re-render.
### Technical constraints
- No backend: no APIs or network calls. All titles, config, and user settings come from hardcoded JavaScript arrays in the file.
- No database or persistence: no localStorage, sessionStorage, or cookies. Refreshing resets everything.
- State: useState only. No Redux, Context, useReducer, or other state libraries.
- No routing library: a single screen state value switches between the three screens.
- One shared Rail component for both Spotlight and standard rows. No custom Spotlight-only component, which mirrors M5.
- No recommendation, personalization, or sorting logic: the config order is final.
- No real video: the player is a static mock.
- No authentication: the control bar sets cohort and region.
- No analytics SDK: events go to console.log and an on-screen event log.
- No licensed artwork: use solid-color placeholder tiles with the title text.
- No editor or CMS UI (that's S3), no Continue Watching logic (S1, S2), and no labels, badges, or filters (A2, A3, A9).
- Only two viewports, mobile and desktop. No TV, console, or casting layouts.
- No UI component libraries: use plain CSS in one style block.

## 3. The Logistics
### Features out
- Removing or hiding the full library
- Rebuilding cross-device resume or sync
### Edge cases & safety guard
- 1. Region filtering leaves 0 titles - The rail is hidden, standard rows move up to position 1, and no empty rail or placeholder appears.
- 2. Config is malformed (missing IDs, duplicate titles, bad fields) - Invalid entries are skipped and duplicates show only once. If nothing valid is left, the rail is hidden and the homepage loads normally.
- 3. A title becomes unavailable between the tile tap and Play	- Title Detail shows a short "no longer available" message with Back to Home. Play is disabled and no spotlight_play_start event logs.
### Decision log
- Curate from a config file, not an editor UI.
- Run the test on new sign-ups only
### Evals
- Accuracy - 100% match to filtered config order across all scenarios.
- Time-on-task  - Median of 30 seconds or less with at least 80* of participants finishing without help.
- Safety - The rail never breaks the homepage, surfaces unplayable titles, or crosses cohorts.

## MoSCoW scope
- **Must:** Rail sits in the first homepage position, above the fold.; Built with the existing rail component and existing title tiles.; Events for rail impression, tile click, and play start from the rail, all tagged by cohort.; Titles come from a manually maintained list (a config file or an existing CMS field), with no algorithmic reordering
- **Should:** Keep the existing Continue Watching row next to the rail for users with titles in progress.; Titles unavailable in the user's region or license window are filtered out.; A retention dashboard by cohort (Day 7, Day 30, Month 1).
- **Could:** A one-line, human-written note per tile explaining the pick/; Light personalized ordering within the fixed curated set
- **Won't (now):** Algorithmic or taste-based selection; Rebuilding cross-device resume or sync

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
