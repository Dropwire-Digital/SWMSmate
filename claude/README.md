# SWMSmate for Claude

A Claude **skill**: a folder with a `SKILL.md` that teaches Claude how to draft a SWMS. Claude loads it automatically whenever you ask for a SWMS.

```
claude/
├── swmsmate/
│   └── SKILL.md      ← the skill (instructions + HTML template)
└── swmsmate.zip      ← same folder, zipped for uploading to Claude apps
```

## Install

### Option 1 — Claude Code (terminal)

Install for every project (personal skills folder):

```bash
git clone https://github.com/Dropwire-Digital/SWMSmate.git
mkdir -p ~/.claude/skills
cp -r SWMSmate/claude/swmsmate ~/.claude/skills/
```

Or install for one project only, so everyone working in that repo gets it:

```bash
mkdir -p .claude/skills
cp -r /path/to/SWMSmate/claude/swmsmate .claude/skills/
```

Start a new Claude Code session. Check it's there by asking: *"What skills do you have?"*

### Option 2 — Claude desktop / web app (Claude.ai, Cowork)

1. Download [`swmsmate.zip`](swmsmate.zip) (click the file, then **Download raw file**).
2. In Claude, open **Settings → Capabilities** and make sure **Code execution and file creation** is turned on (skills need it).
3. Under **Skills**, choose **Upload skill** and select `swmsmate.zip`.
4. Make sure the skill is toggled **on**.

> Skills availability depends on your Claude plan and, on Team/Enterprise plans, on your admin enabling them. If you don't see a Skills section, check with your admin or Anthropic's help centre.

## Use it

Just ask:

> Make me a SWMS

> Draft a SWMS for replacing a switchboard at 14 Example Ave, Marion SA

> I need a generic SWMS for gutter cleaning I can use at any house — I'm subcontracting to Acme Roofing

Claude asks up to six quick questions (business, the job, site, who it's for, when, who's in charge), shows you a one-screen summary to confirm, asks if you want risk ratings, and then writes the SWMS.

## What you get

- `SWMS-DRAFT-<site>-<date>.html` — landscape A4, prints cleanly from any browser.
- `SWMS-DRAFT-<site>-<date>.pdf` — when Claude's environment has a headless browser available (Cowork and most Claude Code setups). If not, open the HTML and **Print → Save as PDF** (the page is already set to A4 landscape).

Ask for **portrait** if you prefer it, or ask Claude to change any step, control or rating after it's drafted.

## Update

Claude Code: pull the repo and copy the folder again (overwrite). Claude apps: delete the old skill and upload the new `swmsmate.zip`.

## Customise

Everything is in `swmsmate/SKILL.md`:

- **Intake questions** — *Step 1*.
- **Branding / colours** — the `:root { --accent: … }` line in the HTML template.
- **Your standard controls or PPE** — add a short section, e.g. "Always include: hi-vis on commercial sites; our ladder inspection tag system".

If you change it for Claude.ai, re-zip the `swmsmate` folder (the zip must contain the folder, not just the file).
