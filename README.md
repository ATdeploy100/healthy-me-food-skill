# Healthy Me

A personal food and daily-habit decision skill for any AI assistant. Send it a photo of a menu, a fridge, a plate or a package, or name a restaurant before you go, and it tells you what to order, what to make, or whether to eat it, in a few lines, judged against your own goals, lab results and food lists.

It is a decision tool, not a nutrition course. Verdict first, reasons after, one habit note when it earns its place, and it stops.

## What it does

| You send | You get |
|---|---|
| "Set me up" | Eight questions in one message, then your protein target (and a recommended calorie range if weight is a goal), a proposed goal ranking, and your filled-in profile file |
| A lab report, a photo of results, pasted values, a blood-pressure log or a DEXA | What to work on, what's fine, the food angle per marker, and your filled-in biomarkers file |
| Menu photo | The composed order (with the swaps you'd ask the server for), why, a backup, the two to four items to skip, the one drink if there's a list |
| Fridge or pantry photo | Two or three meals to make, what to use first, what to leave |
| A plate, a package, a label | Enjoy, Limit or Avoid, one line why, a swap if needed, a 1 to 10 if you ask |
| A restaurant name | It finds the menu online and gives you the order before you sit down |
| "How did I eat this week?" | Counts and one or two adjustments, only when you ask |
| "What does my day look like?" | Reads your calendar and plans meals and coffee around the load |
| A question about coffee, alcohol, sleep, stress, workouts, supplements, travel | Three lines, action first, never a dose |

Works with any assistant that takes custom instructions and a few reference files. Nothing in the folder is tied to one product.

## Quick start

1. Clone or download this repo.
2. Install it one of three ways (see `docs/setup.md`): paste `SKILL.md` into your assistant's custom instructions with the `references/` files as its knowledge, upload it as a packaged skill, or drop the folder into your agent's skills directory.
3. Say "set me up". Answer what you want, skip the rest, upload a lab report if you have one.
4. Save the files it hands back over `references/inputs.md` and `references/biomarkers.md`.
5. Send a menu.

If you'd rather type than chat, fill in `references/inputs.md` by hand. Blank fields fall back to sensible defaults.

## What it knows

Everything about you lives in `references/`. `SKILL.md` is the logic and should not need editing.

- `inputs.md`: your profile and ranked goals, eating pattern, food lists, strictness, caffeine, alcohol, supplements, places you eat, and the targets the skill computed
- `biomarkers.md`: your results, one row per marker with the food angle
- `markers.md`: the lookup table for about 25 common markers (lipids, glucose and insulin, blood pressure, inflammation, liver, kidney, iron and vitamins, thyroid, body composition) with lab ranges, common optimal targets and food angles
- `food-lists.md`: default Enjoy, Limit and Avoid lists, the tie-break ladder and how it shifts by goal, default orders by cuisine
- `habits.md`: caffeine, alcohol, stress, immunity, training and supplement defaults with the triggers that fire a habit note

Sources for the numbers are in `docs/sources.md`. See `docs/customizing.md` for what to change and what to leave alone.

## Privacy

Your health data lives only in your copy of `references/`. Nothing in this repo contains anyone's results. If you fork it, keep `references/inputs.md` and `references/biomarkers.md` out of any public branch (uncomment the two lines in `.gitignore` once you fill them in; see `docs/setup.md`).

## Not medical advice

This is a sandbox. You configure it to your own needs, and every number in it (protein target, calorie range, the "optimal" column in `markers.md`, the food angles) is a starting point, not a prescription. The skill is not a doctor and does not replace one: take your reports, your targets and anything about medication, supplement doses or a diagnosis to yours, and change the files when they tell you something different.

In use, the skill gives the food and habit angle and sends anything clinical to your doctor in one line per conversation, then gets on with the verdict. When weight is a goal it recommends a calorie range and you pick the number; it does not set one for you. It does not compute calorie targets for anyone under 18, pregnant or breastfeeding, or with a history of disordered eating, and it caps protein for anyone who mentions kidney disease.

## Changelog

### 1.0.0 (2026-09-21)

First public release.

- New **Setup** mode: eight questions in one chat message, computed protein target from body weight and goal, a recommended calorie range (Mifflin-St Jeor) when weight is a ranked goal with the user picking the number, filled-in `inputs.md` handed back.
- New **Report intake** mode: reads lab PDFs, result photos, pasted values, blood-pressure logs and DEXA reports against `references/markers.md`, proposes a goal ranking, hands back `biomarkers.md`.
- New `references/markers.md` lookup table, about 25 markers with lab range, common optimal target and food angle.
- Profile block in `inputs.md`: personal stats, activity, eating pattern, meals a day, alcohol, supplements, log file, show-calories switch, plus a Computed targets block.
- Alcohol rule and **Drink** line: one drink, best choice from the list, once-per-conversation flag for daily drinking, moved to soda water first when triglyceride, liver, uric acid or blood pressure markers are off.
- Supplement basics in `habits.md`: what the evidence supports, what to skip, the overlap checks, never a dose.
- Caffeine defaults updated to the 2025 dose-and-timing trial (cutoff eight to nine hours before bed).
- Ladder adjustments by goal or marker and default orders by cuisine in `food-lists.md`.
- Logging record format for exact lookbacks.
- Scope guards: no calorie math for under-18, pregnancy, breastfeeding or disordered-eating history; protein capped at 1.2 g/kg for kidney disease.
- `docs/sources.md` with the sources behind the defaults.

## License

MIT. Fork it, change it, share it.
