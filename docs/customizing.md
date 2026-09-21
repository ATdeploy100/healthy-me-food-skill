# Customizing

Change what you like. The defaults are a place to start, and your doctor's numbers beat the table's. Disclaimer in the README.

## Change these

**`references/inputs.md`** is where your information goes: profile and activity, goals in order, reports, allergies and won't-eat foods, eating pattern, food lists, strictness, caffeine, alcohol, supplements, your normal week, places you eat, log file, tone. The skill reads it before the first verdict. The Computed targets block at the bottom is filled by the skill; if you type a different protein or calorie number there, the skill uses yours.

**`references/biomarkers.md`** if you have blood work, blood pressure readings or a body-composition scan. Upload the report in chat and the skill fills this for you.

**`references/markers.md`** is the lookup table the skill reads reports against: lab range, common target, food angle. If your doctor gave you different targets, put them in the optimal column.

**`references/food-lists.md`** and **`references/habits.md`** are the defaults. Edit them if you eat differently from the whole-food default. The tie-break order in `food-lists.md`, and the adjustments under it, decide which of two good options wins, so that is the section most worth a look.

## Leave these alone unless you know why

**`SKILL.md`** is the decision logic and the output formats. It is strict about short answers, one question at a time (Setup is the exception) and verdict first. If you loosen those, the answers get long.

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
