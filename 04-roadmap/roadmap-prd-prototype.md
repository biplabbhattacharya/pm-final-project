# Roadmap, PRD & Prototype

> **Module 4 · ★ Deliverable 4.** Repo file `04-roadmap/roadmap-prd-prototype.md` — part of your submission.
> Do the lab in the **Module 4 · Exercise 1 Guide** (linked from the Module 4 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Roadmap, PRD & Prototype** slide of your Module 6 final deck. (Your Module 4 · Exercise 2 PRD sprint lands in `prd-and-prototype.md`.)

# Feature Roadmap, Module 4 · StreamLine Spotlight

**Team:** 2 engineers + 1 designer

## Strategic anchors
- **Persona:** The wanderer: The persona we are solving for is the user that has way to many options to choose from and for whom the software does not sync clearly between mobile and desktop. This creates a lot of friction with not able to select new titles or resume progress between platforms.
- **Primary metric:** Retention. Spotlight cohorts retain 12 to 15 points higher at Month 1 than Full-Library cohorts.
- **Moment of misery:** Users leave the platform after browsing a very large catalog. Spotlight cohorts retain 12 to 15 points higher at Month 1 than Full-Library cohorts
- **Guardrail:** potlight cohorts retain 12 to 15 points higher at Month 1 than Full-Library cohorts. But the Month 0 → Month 1 drop remains the single largest leak regardless of cohort type.

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| A1 Spotlight Curated Rail | 5 | 2 | Quick Win | Now | This rail is the Spotlight treatment that drives the 12–15 point Month 1 lift. It shrinks the catalog right at the Moment of Misery, and it can reuse existing rail components. |
| A2 'Why You'll Love This' Label | 4 | 3 | Major Project | Next | It targets decision paralysis directly. But hover doesn't exist on mobile, so as written it misses half the Wanderer's sessions. AI-generated reasons also add effort. |
| A3 Hidden Gem Badge | 2 | 1 | Fill-In | Later | It's cheap, since it's just a metadata rule. But it adds a signal without reducing choices, so it does little for the Month 0 to Month 1 leak. |
| A4 Mood-Based Entry Point | 3 | 3 | Time Sinker | Cut | It narrows choice, but it puts a gate in front of content at login, which adds friction in exactly the Month 0 window. It also needs mood tags across the catalog. |
| A5 Personalized Spotlight Queue | 4 | 5 | Major Project | Next | It fits the persona well and could carry progress across devices. But new users in Month 0 have thin taste profiles, so the AI is weakest where the leak is. Too heavy for 3 weeks. |
| A6 Spotlight Digest Email | 2 | 2 | Fill-In | Later | It could win back users after they leave. It happens outside the app, though, so it doesn't fix the browsing friction that drives them away. |
| A7 Curator Profiles | 2 | 4 | Time Sinker | Cut | It adds a social layer and more things to follow and browse. That's the opposite of fewer, clearer choices. |
| A8 Watch Party (Spotlight) | 1 | 5 | Time Sinker | Cut | It doesn't touch choice overload or resuming across devices, and synchronized playback plus chat is heavy engineering. |
| A9 Advanced Filter Engine | 1 | 3 | Time Sinker | Cut | This is a power-user tool for searching the full library. It works against the Spotlight idea by giving the Wanderer more controls and more options. |
| A10 Offline Download (Spotlight) | 2 | 5 | Time Sinker | Cut | It's a mobile convenience, but it doesn't solve choice or sync. Licensing and DRM rights make it expensive. |

## Roadmap
### NOW, 3-week sprint
- **A1 Spotlight Curated Rail**, This rail is the Spotlight treatment that drives the 12–15 point Month 1 lift. It shrinks the catalog right at the Moment of Misery, and it can reuse existing rail components.

### NEXT, following 1-2 sprints
- **A2 'Why You'll Love This' Label**, It targets decision paralysis directly. But hover doesn't exist on mobile, so as written it misses half the Wanderer's sessions. AI-generated reasons also add effort.
- **A5 Personalized Spotlight Queue**, It fits the persona well and could carry progress across devices. But new users in Month 0 have thin taste profiles, so the AI is weakest where the leak is. Too heavy for 3 weeks.

### LATER, backlog
- **A3 Hidden Gem Badge**, It's cheap, since it's just a metadata rule. But it adds a signal without reducing choices, so it does little for the Month 0 to Month 1 leak.
- **A6 Spotlight Digest Email**, It could win back users after they leave. It happens outside the app, though, so it doesn't fix the browsing friction that drives them away.

### ✂ Cut List
- **A4 Mood-Based Entry Point**, It narrows choice, but it puts a gate in front of content at login, which adds friction in exactly the Month 0 window. It also needs mood tags across the catalog.
- **A7 Curator Profiles**, It adds a social layer and more things to follow and browse. That's the opposite of fewer, clearer choices.
- **A8 Watch Party (Spotlight)**, It doesn't touch choice overload or resuming across devices, and synchronized playback plus chat is heavy engineering.
- **A9 Advanced Filter Engine**, This is a power-user tool for searching the full library. It works against the Spotlight idea by giving the Wanderer more controls and more options.
- **A10 Offline Download (Spotlight)**, It's a mobile convenience, but it doesn't solve choice or sync. Licensing and DRM rights make it expensive.

