# Biomarkers (optional)

Version 1.0.0, September 2026.

Your results live here. Two ways to fill it in: upload or paste a report in chat and the skill hands back this file completed (see Report intake in `SKILL.md`), or type the rows yourself. The lookup the skill uses for the optimal column and the food angle is `markers.md`. Leave this file empty and the skill runs on the plain-language goals in `inputs.md`.

**Data date:** 

**Source** (lab name, panel name, home cuff, DEXA): 

## Work on

Markers out of the lab range or off the common optimal target, most important first.

| Marker | Result | Date | Direction | Food angle |
|---|---|---|---|---|
| | | | | |

## Fine

Markers that came back clearly good, so the skill does not over-correct. One line is enough: "Blood sugar, inflammation and liver markers all in range."



## Goal 1 marker cluster

The group at the top of Work on. The skill copies this into `inputs.md` under Computed targets and uses it to break ties.



## History (optional)

One line per past draw so the skill can say "down from X in March" when you ask. Keep it short.

| Date | What moved |
|---|---|
| | |

## How the skill uses this file

- The top cluster under Work on sets goal 1 unless `inputs.md` ranks goals differently.
- Each row's food angle adjusts the tie-break ladder in `food-lists.md`: blood sugar rows move whole grains below legumes; high ferritin removes fortified foods and the "red meat for energy" idea; blood pressure rows push sodium-heavy dishes down; liver or triglyceride rows move the Drink line to soda water first.
- Markers with no food lever (Lp(a), genetics) are listed once and never drive a verdict.
- Update the data date every time you paste new results. After six months the skill says so once per conversation and keeps working.
- Nothing here is a diagnosis. Direction words are "above range", "below range", "off optimal", "fine".
