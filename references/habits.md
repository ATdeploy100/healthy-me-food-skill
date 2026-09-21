# Default habit rules

Version 1.0.0, September 2026.

Generic defaults. The user's own rules in `inputs.md` override these. Habit notes attach to food verdicts as one line, only when a trigger fires, once per topic per conversation. Habit questions get three lines or fewer, action first. Sources for the numbers are in `docs/sources.md`.

## Caffeine

- Coffee in the morning, with food. Default cutoff: eight to nine hours before the user's usual bedtime (about 2pm for an 11pm bedtime) unless the user sets a different time. A single small coffee (about 100 mg) up to four hours before bed has little measured effect on sleep; a large one (300 to 400 mg, a big cold brew or two double espressos) disrupts sleep even twelve hours out. The cutoff protects against the second kind.
- Cap around 400 mg a day, about four small cups. Pregnancy: 200 mg, and the skill says so once.
- No energy drinks or sweetened coffee drinks. Black, or with a splash of milk.
- Decaf and tea (green, black, herbal) are the swaps after cutoff.

Triggers: coffee on the menu after cutoff (suggest decaf or tea); energy drink, frappe or sweetened iced coffee on the menu (name the swap); user mentions poor sleep (coffee with breakfast only, none after).

## Alcohol

- Less is better for every goal on the list; there is no protective dose. The skill does not moralize about it. Default setting: allow one, pick the least bad.
- Least-bad ladder from what is listed: dry red or white wine, or a clear spirit neat or with soda water, ahead of beer, ahead of cocktails, sweet wines, cider, or anything with juice, syrup, cream or tonic. A standard drink is 5 oz wine, 12 oz beer, 1.5 oz spirits; a restaurant pour is often one and a half.
- Water alongside, food alongside, and finish two to three hours before bed. Alcohol close to bed fragments the second half of the night even when it helps falling asleep.
- Drinks most days: flag once per conversation against the goal it works against (sleep, immunity, weight, blood pressure, triglycerides, liver markers), then move on. Never repeat it in the same conversation.
- Triglycerides, ALT, GGT, uric acid or blood pressure off range in `biomarkers.md`: the Drink line moves to soda water with lime as the first pick and names wine as the compromise.

Triggers: drinks list visible (one pick, one line); user asks for a second (least-bad again, marked compromise); Profile says most days (the once-per-conversation flag); travel day or late dinner (water before wine, stop early).

## Stress and recovery

- Regular meals with protein, fiber and fat. Blood sugar swings read as anxiety and get treated as hunger, not the other way round.
- Do not skip breakfast on a heavy day, and eat lunch even if it is short.
- One coffee on a heavy day, not three. Caffeine on top of stress raises heart rate and the afternoon crash.
- A ten-minute walk after a meal counts, for glucose and for the head.
- Screens off 30 to 60 minutes before bed; finish eating two to three hours before bed.

Triggers: user mentions a stressful day, a big meeting, an exam or travel (eat breakfast, don't skip lunch, one coffee, finish dinner early); late-night menu or room service (light, protein and vegetables, no dessert).

## Immunity

- Sleep is the biggest lever: consistent bed and wake times, seven hours minimum.
- Protein at every meal; the immune system is built from it.
- Color and variety on the plate; a fermented food most days (yogurt, kefir, kimchi, sauerkraut, miso).
- Hydrate on flights, wash hands after, first meal on arrival protein first.
- Alcohol and a short night are the two things most likely to precede getting sick. The skill says so once when both show up.

Triggers: user mentions feeling run down or a cold coming on (add the fermented or vitamin C-rich option, protein first, skip the drink); travel day or airline menu (hydrate, protein first meal on arrival, bed on the destination clock).

## Strength and training

- Protein at every meal at the per-meal target in `inputs.md`. Spreading it across the day beats one large evening dose.
- Training days: the meal within two hours after the session gets the larger protein portion plus a whole grain or legume. Timing matters less than hitting the daily total.
- Older adults (65 and over) need more protein per meal to get the same muscle response, which is why the skill floors the target at 1.2 g/kg and uses 1.6.
- Resistance training two or more times a week is the other half of every strength, weight and blood-sugar goal. The skill mentions it once per conversation when the user's goals include one of those, never in a menu verdict.

Triggers: user mentions a workout (name the post-workout meal shape in one line); menu verdict where the best pick is light on protein (add the protein fix to the Order line).

## Supplements

The skill says what the evidence supports and what it does not, checks for overlap with the user's food and markers, and never gives a dose. Doses, interactions and anything prescription are the doctor's.

- **Creatine monohydrate**: the best-supported supplement for strength and lean mass, with growing evidence for cognition and older adults. Raises serum creatinine on a blood test without harming the kidney; tell the doctor before a draw. Fine for vegetarians and vegans, who tend to benefit more.
- **Omega-3 (EPA and DHA)**: supports triglycerides and the omega-3 index. Two servings of fatty fish a week does the same job; the skill prefers the fish and treats the capsule as the fallback. Not a substitute for the ApoB work.
- **Vitamin D**: worth it when the blood level is low or sun exposure is minimal (northern winters, indoor work). No benefit shown from pushing a normal level higher.
- **Magnesium**: reasonable when intake is low (few greens, nuts, legumes) or for sleep and cramps; glycinate or citrate are the usual forms. Food first.
- **Protein powder**: a food, not a supplement. Useful when the per-meal target is hard to hit from meals; whey or a pea and rice blend.
- **Fiber (psyllium)**: a real lever for LDL and ApoB when food fiber is short. Food first (oats, beans, lentils, chia).
- **Skip by default**: multivitamins for people who eat varied food, iron unless ferritin is low, fat burners, detox products, greens powders as a vegetable substitute, and anything sold on a single small study.
- **Overlap checks the skill runs**: iron in a multivitamin when ferritin is high; vitamin K supplements for anyone who mentions a blood thinner (doctor line, immediately); high-dose niacin or red yeast rice for people already discussing statins (doctor line); creatine before a kidney panel (mention the creatinine effect once).

Triggers: user names a supplement or asks whether to take one (three lines: what it does for their goals, what it does not, doctor line if clinical); Profile lists a supplement that overlaps a marker (say so once at setup, not in verdicts).

## Out of scope by default

Workout programming, supplement doses, medication, lab interpretation, diagnosis. Give the food or habit angle, then one line to take the rest to a doctor. Once per conversation.
