# Setup

If you only want to try it, use `QUICKSTART.md` (copy the file, paste it into your assistant's instructions, type "set me up"). This page covers the full folder, which gives you editable food lists, a marker lookup table and a log file. Pick the route that matches your tool.

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
3. Make a folder called `healthy-me-food-skill` containing only `SKILL.md` and the `references/` folder. Leave out the README, docs, examples and `QUICKSTART.md`; they are for people, and a second copy of the instructions in the package can confuse the assistant.
4. Zip that folder so `SKILL.md` sits at the root of the zip. Rename the extension if your tool wants one (`.skill`, for example).
5. Upload it where your assistant manages skills or tools.

The `healthy-me-food-skill.skill` in the repo is exactly this, with blank reference files.

The skill triggers automatically on menu and food photos. To update your data, edit the reference file and re-upload.

## C. A coding or desktop agent

Copy `SKILL.md` and `references/` (in a folder called `healthy-me-food-skill`) into wherever your agent looks for skills or instruction folders. Leave the docs, examples and `QUICKSTART.md` out. It loads on the next session. Say "set me up" and the agent can write the filled-in reference files straight back into the folder.

## What setup asks

One message, eight numbered questions, all optional:

1. Height, weight, age
2. Activity level
3. Goals, ranked
4. Health reports (upload, paste, or "none")
5. Allergies, foods you won't eat, then how you eat
6. Strictness
7. Coffee and alcohol habits
8. Places you eat, workout days, meal times, tone

It then works out your protein target, suggests a goal order from your report, and hands back the filled files. Give height and weight in whatever units you use; the skill converts.

The targets are a place to start. Change them when your doctor gives you different ones. See the disclaimer in the README.

## Keeping your data private

Once `references/inputs.md` and `references/biomarkers.md` contain your real information, uncomment the two lines in `.gitignore` so they stay out of a public fork. Keep a private copy somewhere else. Your reports and body stats go only into your copy of the files and the assistant you paste them into.

## Optional: log file and live data folder

Name a log file in `inputs.md` and the skill appends one line per verdict, so a lookback counts real meals. If your assistant can read a cloud folder, name the path in `inputs.md` and the skill will read the newest lab export from it. Without either, it uses the reference files in the folder.
