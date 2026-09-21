# Healthy Me

Send your AI assistant a photo of a menu, a fridge, a plate or a package, or name a restaurant before you go. It tells you what to order, what to make, or whether to eat it, in a few lines, based on your goals, your lab results and the foods you eat. Works with any assistant that takes custom instructions.

## Not medical advice

This is not medical advice. This is not a doctor, and it does not substitute for seeing one. It is for people who want to play around with food decisions using their own information. We hold no responsibility for how you use it or for anything you do with what it tells you. Take your reports, your targets and any question about medication, supplements or a diagnosis to a doctor.

## Install

### Option 1: paste and go (one minute)

1. Open [`QUICKSTART.md`](QUICKSTART.md) and copy the whole file.
2. Paste it where your assistant keeps standing instructions (a project, a custom assistant, a "gem", a system prompt). No files to upload.
3. Type "set me up", answer the questions, and send a menu.

Your answers stay in that chat or project. To keep them for good, paste the profile block it hands you at the bottom of the same instructions.

### Option 2: upload it as a skill (two minutes)

For assistants that accept skill files.

1. Download [`healthy-me.skill`](healthy-me.skill) (click it, then the download button).
2. Upload it where your assistant manages skills.
3. Open a chat, type "set me up", answer the questions, and send a menu.

The skill triggers on its own when you send a menu, fridge or plate photo. To keep your profile, paste the block it hands you into a note you can drop into a new chat, or use Option 3.

### Option 3: full customization (ten minutes)

1. Download this folder (green Code button, Download ZIP) or clone it.
2. Fill in `references/inputs.md`, or leave it blank and let "set me up" fill it for you.
3. Install: paste `SKILL.md` into your assistant's instructions and upload the `references/` folder as its knowledge files, or zip `SKILL.md` and `references/` together and upload that as a skill, or drop those two into your agent's skills directory. The README, docs, examples and `QUICKSTART.md` are for reading; leave them out of the install. Details in [`docs/setup.md`](docs/setup.md).

Option 3 gives you editable food lists, a lab-marker lookup table, sources for the numbers, and a log file for exact lookbacks. Options 1 and 2 carry the same decision logic with the defaults built in.

## What it does

| You send | You get |
|---|---|
| "Set me up" | Eight questions in one message, then your protein target, a calorie range if weight is a goal, a suggested goal order, and your profile |
| A lab report, a results photo, pasted values, a blood-pressure log or a DEXA | What to work on, what's fine, the food angle for each marker |
| Menu photo | The order (with the swaps to ask the server for), why, a backup, two to four items to skip, one drink if there's a list |
| Fridge or pantry photo | Two or three meals to make, what to use first, what to leave |
| A plate, a package, a label | Enjoy, Limit or Avoid, one line why, a swap if needed, a 1 to 10 if you ask |
| A restaurant name | It finds the menu online and gives you the order before you sit down |
| "How did I eat this week?" | Counts and one or two adjustments, only when you ask |
| "What does my day look like?" | Reads your calendar and plans meals and coffee around it |
| A question about coffee, alcohol, sleep, stress, workouts, supplements, travel | Three lines, action first, no doses |

## The files (Option 3)

- `SKILL.md`: the decision logic and answer formats. You should not need to edit it.
- `QUICKSTART.md`: the single-file version for Option 1.
- `healthy-me.skill`: the packaged version for Option 2 (a zip of `SKILL.md` and `references/`, nothing else).
- `references/inputs.md`: your profile, goals, food lists, strictness, caffeine, alcohol, supplements, places you eat, and the targets the skill worked out
- `references/biomarkers.md`: your results, one row per marker with the food angle
- `references/markers.md`: a lookup table of about 25 common markers with lab ranges, common targets and food angles
- `references/food-lists.md`: default Enjoy, Limit and Avoid lists, the tie-break order and how it shifts by goal, default orders by cuisine
- `references/habits.md`: caffeine, alcohol, stress, immunity, training and supplement defaults
- `docs/sources.md`: where the numbers come from
- `docs/customizing.md`: what to change and what to leave alone

## Privacy

Your health data stays in your copy of `references/` and in whatever assistant you paste it into. This repo contains no one's results. If you fork it, uncomment the two lines in `.gitignore` once you fill in `inputs.md` and `biomarkers.md`, so they stay out of any public branch.

## How it handles limits

When weight is a goal it recommends a calorie range and you pick the number. It gives no calorie targets to anyone under 18, pregnant or breastfeeding, or with a history of disordered eating, and it caps protein for anyone who mentions kidney disease. On medication, supplement doses, lab interpretation or diagnosis, it gives the food angle and tells you once per conversation to ask your doctor.

## Changelog

### 1.1.1 (2026-09-21)

- README: install as three options; `healthy-me.skill` added to the repo for direct download.

### 1.1.0 (2026-09-21)

- `QUICKSTART.md`: single-file paste-and-go version with the defaults built in.
- README rewritten around two install paths and a plain disclaimer.
- Setup questions reworded: options listed as Option 1, 2, 3; allergies and won't-eat foods first in question 5; drinks question in plain words; fixed two-sentence close.
- Instructions written for any assistant; product names removed.

### 1.0.0 (2026-09-21)

First public release.

- **Setup** mode: eight questions in one chat message, protein target from body weight and goal, recommended calorie range (Mifflin-St Jeor) when weight is a ranked goal with the user picking the number, filled-in `inputs.md` handed back.
- **Report intake** mode: reads lab PDFs, result photos, pasted values, blood-pressure logs and DEXA reports against `references/markers.md`, proposes a goal order, hands back `biomarkers.md`.
- `references/markers.md` lookup table, about 25 markers.
- Profile block and Computed targets block in `inputs.md`.
- Alcohol rule and **Drink** line. Supplement basics in `habits.md`, no doses.
- Caffeine defaults updated to the 2025 dose-and-timing trial.
- Tie-break adjustments by goal and default orders by cuisine in `food-lists.md`.
- Logging record format for lookbacks.
- Age, pregnancy, disordered-eating and kidney guards on the calorie and protein math.
- `docs/sources.md`.

## License

MIT.
