# Marker lookup table

Version 1.2.0, September 2026.

What the skill uses to read a lab report. Each row gives the typical lab range, the target many preventive clinicians use, the direction that matters, and the one-line food angle the skill applies. Ranges vary by lab, unit and country; the skill uses the range printed on the user's own report first and this table only for the "optimal" column and the food angle. None of this is a diagnosis. Interpretation, medication and doses go to the user's doctor.

The optimal column is one school of preventive medicine and is more aggressive than most lab reference ranges; it is a starting point, and the user's own doctor's targets replace it.

Units: US labs report lipids and glucose in mg/dL. Many other countries use mmol/L. Convert if needed: cholesterol mg/dL ÷ 38.67 = mmol/L; triglycerides mg/dL ÷ 88.57 = mmol/L; glucose mg/dL ÷ 18 = mmol/L.

## Priority order

When a report has several markers off, the skill ranks the work in this order and makes the top cluster goal 1 unless the user's own ranking says otherwise:

1. Atherogenic lipids: ApoB, LDL-C, non-HDL, triglycerides
2. Glycemic: HbA1c, fasting glucose, fasting insulin
3. Blood pressure
4. Inflammation: hs-CRP
5. Liver: ALT, AST, GGT
6. Kidney: eGFR, creatinine, uric acid (the protein rule changes here)
7. Micronutrients and iron: vitamin D, B12, folate, ferritin, iron saturation
8. Thyroid: TSH
9. No food lever: Lp(a), most genetic markers

## Lipids

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| ApoB | < 90 mg/dL | < 80 mg/dL; < 60 to 70 for people at high cardiovascular risk | High | Saturated fat down (fatty red meat, butter, cream, cheese-heavy dishes, coconut oil), soluble fiber up (oats, beans, lentils, barley), fatty fish twice a week, nuts daily. The strongest single food lever on this table. |
| LDL-C | < 100 to 130 mg/dL | < 100 mg/dL; < 70 or < 55 for people with existing heart disease or high risk | High | Same as ApoB. Swap butter for olive oil, red meat for fish, poultry or legumes. Refined carbs matter less here than for triglycerides. |
| Non-HDL cholesterol | < 130 mg/dL | < 100 mg/dL | High | Same as ApoB. |
| Triglycerides | < 150 mg/dL | < 100 mg/dL | High | Sugar, refined starch and alcohol down first; fatty fish and fiber up. Fruit juice and sweet drinks are the fastest cut. |
| HDL-C | > 40 (men) / > 50 (women) mg/dL | 60 to 90 mg/dL | Low | Weak food lever. Olive oil, nuts, fatty fish, exercise. Do not chase it with food at the expense of ApoB. Above about 90 mg/dL it stops being protective, so the skill treats very high HDL as neutral. |
| Lp(a) | Lab specific; reported in either mg/dL or nmol/L | High is 50 mg/dL or 125 nmol/L and above | High | No food lever. Genetic, measured once. The two units do not convert by a fixed factor; read the user's report in the unit it uses. Listed for the doctor conversation; it makes the ApoB work more important, nothing else. |

## Glucose and insulin

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| HbA1c | < 5.7 % | < 5.5 % | High | Refined starch and added sugar down, protein and fiber at every meal, vegetables and protein before the starch on the plate, a walk after the biggest meal. Whole grains move below legumes on the ladder. |
| Fasting glucose | 70 to 99 mg/dL | 70 to 85 mg/dL | High | Same as HbA1c. Late-night eating and alcohol raise the morning number. |
| Fasting insulin | < 25 µIU/mL | 2 to 8 µIU/mL (noisy test; one reading means little) | High | Same as HbA1c, with more weight on cutting snacking between meals and liquid calories. |
| Post-meal glucose (CGM or 2-hour test) | < 140 mg/dL | < 110 to 115 mg/dL | High | Eating order (vegetables, protein, then starch), vinegar or a salad first, a ten-minute walk after. |

## Blood pressure

| Marker | Typical range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| Blood pressure | < 130/80 | < 120/80 | High | Sodium down (restaurant food, deli meat, sauces, bread), potassium up (beans, leafy greens, potatoes, yogurt, bananas), alcohol down, less caffeine on a high-reading day. Ask for sauces on the side and skip the soy and salt-crusted dishes. |

## Inflammation

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| hs-CRP | < 3.0 mg/L | < 1.0 mg/L | High | Fried food, processed meat and sugar down; fatty fish, olive oil, nuts, colorful vegetables and fermented foods up. A single high reading during or after an illness means nothing; retest. |
| Homocysteine | < 15 µmol/L | < 10 µmol/L | High | Folate (leafy greens, legumes), B12 (fish, eggs, dairy), B6 (poultry, chickpeas). Weak food lever if B12 or folate are already fine. |

## Liver

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| ALT | < 40 to 55 U/L | < 30 U/L (men), < 25 U/L (women) | High | Alcohol and sugar (fructose in sweet drinks and juice) are the two levers. Coffee is fine here. Weight loss if weight is high. |
| AST | < 40 U/L | < 30 U/L | High | Same as ALT. A hard workout the day before the draw raises it; retest before acting. |
| GGT | < 50 to 60 U/L | < 25 U/L | High | Alcohol first, then everything under ALT. |

## Kidney and uric acid

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| eGFR | > 60 mL/min | > 90 mL/min | Low | Below 60: the skill drops the protein factor to 1.2 g/kg and stops recommending protein supplements. Hydrate, sodium down. Doctor conversation. |
| Creatinine | 0.7 to 1.3 mg/dL | Within range | High | Rises with muscle mass and creatine supplements; alone it means little. Read eGFR instead. |
| Uric acid | < 7.0 (men) / < 6.0 (women) mg/dL | < 6.0 mg/dL | High | Beer, spirits, sugary drinks and organ meats down; shellfish and red meat in smaller portions; water, coffee and low-fat dairy up. |

## Iron, vitamins, minerals

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| Ferritin | 30 to 300 ng/mL (men), 15 to 150 (women) | 50 to 150 ng/mL | Both | Low: red meat in moderation, shellfish, legumes with a vitamin C food, skip tea and coffee with iron-rich meals. High: no iron-fortified cereals or supplements, red meat is not an "energy plus", coffee or tea with meals is fine. High ferritin also tracks inflammation and alcohol; the doctor sorts out which. |
| Iron saturation | 20 to 50 % | 25 to 45 % | Both | Same as ferritin. |
| Vitamin D (25-OH) | 30 to 100 ng/mL | 40 to 60 ng/mL | Low | Fatty fish, egg yolks, fortified dairy, sunlight. Food alone rarely fixes a low reading; supplement is a doctor conversation. |
| Vitamin B12 | 200 to 900 pg/mL | > 400 pg/mL | Low | Fish, shellfish, eggs, dairy. Vegans and people on acid reducers or metformin: supplement is a doctor conversation. |
| Folate | > 3 to 4 ng/mL | > 10 ng/mL | Low | Leafy greens, legumes, asparagus, avocado. |
| Magnesium (serum) | 1.7 to 2.2 mg/dL | Upper half of range | Low | Pumpkin seeds, almonds, spinach, black beans, dark chocolate (small). Serum magnesium is a blunt marker; low-normal still gets the food angle. |
| Omega-3 index | > 4 % | > 8 % | Low | Fatty fish twice a week (salmon, sardines, mackerel, herring, trout). Low-mercury choices for anyone eating fish daily. |

## Thyroid

| Marker | Typical lab range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| TSH | 0.4 to 4.0 mIU/L | 0.5 to 2.5 mIU/L | Both | Weak food lever. Adequate iodine (fish, dairy, iodized salt) and selenium (two Brazil nuts a day). Anything off range is a doctor conversation; the skill does not change food picks on TSH alone. |

## Body composition

| Marker | Typical range | Common optimal target | Matters when | Food angle |
|---|---|---|---|---|
| Body fat % (DEXA or scale) | Men 10 to 22 %, women 20 to 32 % | Men 12 to 20 %, women 22 to 30 % | High | Protein target up to 2.0 g/kg, deficit from starch and drinks, never protein. Resistance training is the other half; the skill mentions it once. |
| Waist circumference | Men < 40 in / 102 cm, women < 35 in / 88 cm | Men < 37 in / 94 cm, women < 31.5 in / 80 cm | High | Same as body fat. Alcohol and liquid sugar are the fastest cuts. |
| Visceral fat (DEXA) | Lab specific | Lower quartile | High | Same as body fat, with extra weight on alcohol and fructose. |

## How the skill writes a marker into biomarkers.md

One row per marker: name, value with unit, date, direction (above range, below range, off optimal, fine), and the food angle from this table shortened to the part that applies to this user. Example: `ApoB | 96 mg/dL | Sep 2026 | above optimal | saturated fat down, soluble fiber up, fatty fish twice a week`. The skill then sets the goal 1 marker cluster in `inputs.md` and stops.
