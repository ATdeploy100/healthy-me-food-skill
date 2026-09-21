# Setup

Healthy Me is a folder of plain-text instructions. Any AI assistant that can take custom instructions and read a few files can run it. Pick the route that matches your tool, then say "set me up" in chat.

## A. A chat assistant with custom instructions and file uploads (easiest, works on phone)

Most assistants have a way to save standing instructions plus a few reference files: a project, a custom assistant, a "gem", a workspace. Whatever yours calls it:

1. Create one and name it whatever you like.
2. Open `SKILL.md`, copy everything below the front matter (the block between the `---` lines), and paste it into the instructions field.
3. Upload the five files in `references/` as its knowledge or reference files.
4. Start a chat and say "set me up". Answer the eight questions in one message (skip any you like), upload a lab report if you have one.
5. The skill hands back a filled-in `inputs.md` (and `biomarkers.md` if you uploaded a report). Save those over the files you uploaded.
6. Send a menu.

To update your data later, upload a new report in chat or say what changed; the skill hands back the updated file to replace.

## B. A skill or tool file

Some assistants accept a packaged skill: a zip with `SKILL.md` at the root and the `references/` folder alongside it.

1. Say "set me up" in any chat with the skill loaded, or fill in `references/inputs.md` by hand.
2. Paste the filled-in files over `references/inputs.md` and `references/biomarkers.md`.
3. Zip the `healthy-me` folder so `SKILL.md` sits at the root of the zip. Rename the extension if your tool wants one (`.skill`, for example).
4. Upload it where your assistant manages skills or tools.

The skill triggers automatically on menu and food photos. To update your data, edit the reference file and re-upload.

## C. A coding or desktop agent

Copy the `healthy-me` folder into wherever your agent looks for skills or instruction folders. It loads on the next session. Say "set me up" and the agent can write the filled-in reference files straight back into the folder.

## What setup asks

One message, eight numbered questions, all optional:

1. Height, weight, sex, age
2. Activity level
3. Goals, ranked
4. Health reports (upload, paste, or "none")
5. Allergies, foods you won't eat, then how you eat
6. Strictness
7. Coffee and alcohol habits
8. Places you eat, workout days, meal times, tone

It then computes your protein target, recommends a calorie range if weight is a goal and asks which number you want to work to, proposes a goal ranking from your report, and hands back the filled files. Units: give height and weight in whatever you use; the skill converts.

Everything it computes is a starting point. This is a sandbox you tune to your own needs, and the skill is not a doctor: take the targets and your reports to yours, and change the files when they say something different.

## Keeping your data private

Once `references/inputs.md` and `references/biomarkers.md` contain your real information, uncomment the two lines in `.gitignore` so they never get committed to a public fork. Keep a private copy elsewhere. Your reports and body stats never leave your copy of the files and whatever assistant you paste them into.

## Optional: log file and live data folder

Name a log file in `inputs.md` and the skill appends one line per verdict, which makes the lookback mode exact instead of reconstructing from past conversations. If your assistant can read a cloud folder, name the path in `inputs.md` and the skill will read the newest lab export from it. Without either, it uses the bundled reference files, which is fine for most people.
