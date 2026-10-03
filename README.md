# Roadmap Quest

A free, game-style progress tracker that builds a **personal study roadmap** for students and helps them stick to it with daily quests, XP, streaks and rewards.

**Live app:** https://sadman-hamim-dev.github.io/-roadmap-quest/

## What it does
- **Personal roadmap:** a short questionnaire (stage, goal, field, English, coding level, marks, math, time, funding and more) builds a roadmap for each student, with a summary table explaining what each answer means for the plan.
- **Daily quests:** a few small tasks per day (coding, math, English reading and writing, working on a project) that fit the student's field and time.
- **XP, levels and streaks:** every quest, roadmap item, project and review earns XP. A "never skip two days" streak keeps the habit going.
- **Reward shop and badges:** students spend XP on rewards they choose themselves, and unlock badges.
- **Trackers:** projects, courses, English practice, competitions, tests (SAT, IELTS and others) and a university list with deadlines and aid notes.
- **Weekly review:** three short questions to reflect and plan the next week.
- **One-time AI roadmap (optional):** after confirming their answers, each account can get one AI-adapted roadmap. If the AI is unavailable, a standard rule-based roadmap is used and the chance is kept.
- **Works on any screen:** a bottom menu on phones, a side menu on laptops, and an optional two-panel layout (Rewards > Settings).

## How it works
| Part | Technology |
|---|---|
| App | One `index.html` file (plain HTML, CSS and JavaScript, no build step) |
| Hosting | GitHub Pages |
| Login and storage | Supabase (email login, a `progress` table protected by row-level security) |
| AI (optional) | A Supabase Edge Function that keeps the API key private and allows one roadmap per account |

Progress is also saved in the browser, so the app keeps working during short connection drops.

## Privacy and safety
- Each account can read and write only its own data.
- Students are asked to use a nickname and **not** to enter their name, school, phone number or address.
- Roadmaps are guidance, not guarantees. Admission rules, deadlines and aid policies change, so always check each university's official website.
- No secret keys belong in this repository. Only the public Supabase URL and public (anon/publishable) key go in `index.html`.

## Run your own copy
1. Create a free Supabase project and run the SQL in `SETUP.md`.
2. Put your project URL and public key at the top of `index.html`.
3. Publish the repository with GitHub Pages.
4. Optional: run `ai_setup.sql`, deploy `supabase/functions/roadmap/index.ts` as an Edge Function named `roadmap`, and add your AI key as a secret.

The full step-by-step guide, test checklist and troubleshooting table are in [`SETUP.md`](SETUP.md).

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `SETUP.md` | Complete setup guide |
| `ai_setup.sql` | Database table for the one-AI-roadmap rule |
| `supabase/functions/roadmap/index.ts` | Private AI function |
| `my_roadmap.sql` | Optional: loads a ready-made roadmap into one account |

## Ideas for later
- Roadmap templates for more goals and countries
- Charts for progress over time
- Install-to-home-screen support with offline mode

## Status
Built as a personal project. Feedback and bug reports are welcome through GitHub issues.
