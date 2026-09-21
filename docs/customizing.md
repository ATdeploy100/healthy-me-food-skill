# Customizing

This whole folder is a sandbox. Configure it to your own needs, and treat every default as a starting point to check with your doctor. The skill is not one.

## Change these

**`references/inputs.md`** is the whole personalization surface. Your profile and activity, goals ranked, reports, allergies and won't-eat foods, eating pattern, food lists, strictness, caffeine, alcohol, supplements, your normal week, places you eat, log file, tone. Every verdict reads this first. The Computed targets block at the bottom is filled by the skill; edit it if you want a different protein or calorie number and the skill will use yours.

**`references/biomarkers.md`** if you have blood work, blood pressure readings or a body-composition scan. Upload the report in chat and the skill fills this for you.

**`references/markers.md`** is the lookup table the skill reads reports against: lab range, common optimal target, food angle. Edit the optimal column if your doctor gave you different targets; the skill uses yours.

**`references/food-lists.md`** and **`references/habits.md`** hold the defaults. Edit them if your dietary pattern is different from the whole-food default. The tie-break ladder in `food-lists.md` and its adjustments by goal are the sections most worth tuning: they decide which of two good options wins.

## Leave these alone unless you know why

**`SKILL.md`** is the decision logic and the output formats. It is deliberately strict about brevity, the one-question rule (Setup is the only exception) and verdict-first formatting. Loosening those is how the skill turns into a lecture.

## Common tweaks

| You want | Change |
|---|---|
| Scores on every plate photo | Add "always give a 1 to 10 on plates" to Formatting in `inputs.md` |
| Stricter, no compromise flags | Set Strictness to "strict" |
| Vegan or vegetarian | Set Eating pattern; the skill filters and re-ranks the ladder on its own |
| Weight loss as a goal | Rank it in Goals; the skill recommends a calorie range once, you pick the number, then it uses portion levers, never protein cuts |
| A different calorie number | Overwrite "Daily target, your choice" in Computed targets |
| Calorie estimate without a weight goal | Set Show calories to "yes" |
| No calorie numbers anywhere | Set Show calories to "no" and leave weight out of Goals |
| Higher protein than the computed number | Overwrite Protein per day in Computed targets |
| No habit notes at all | Set Habit areas to "none" |
| No Drink line | Set Alcohol to "leave drinks out" |
| A different caffeine cutoff | Write it in Caffeine |
| Your doctor's targets instead of the table's | Edit the optimal column in `markers.md` |
| Exact lookbacks | Name a Log file in `inputs.md` |
| Blood-sugar first rather than cholesterol first | Rank it as goal 1; the ladder adjustment in `food-lists.md` applies automatically |

## Adding a marker

Add a row to the right table in `markers.md`: lab range, common optimal target, direction, one-line food angle. If it has no food lever, say so in the food angle column so the skill lists it under Fine and moves on.

## Adding a mode

Copy the shape of an existing mode in `SKILL.md`: a trigger row in the Modes table, a decision rule if it needs one, a verdict format with bold labels and a line cap. If your new format needs more than one phone screen, it is two modes.
