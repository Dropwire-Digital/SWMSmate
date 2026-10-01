# SWMSmate for ChatGPT

Two ways to set it up, depending on your ChatGPT plan:

| Your plan | Use | Why |
|---|---|---|
| **Business, Enterprise, Edu** | **Option 1 — ChatGPT skill** (recommended) | Skills load automatically whenever you ask for a SWMS. |
| **Free, Go, Plus, Pro** | **Option 2 — ChatGPT Project** | Skills aren't available on personal plans yet. A Project gives the same result inside one project. |

> **Why not a Custom GPT?** OpenAI has stopped new GPT creation on personal accounts and is retiring Custom GPTs on **11 December 2026** in favour of skills and plugins. SWMSmate ships as a skill so it keeps working after that date.

```
chatgpt/
├── swmsmate/                     ← the skill
│   ├── SKILL.md                  ← workflow and rules
│   ├── references/swms-reference.md   ← detailed SWMS rules (HRCW list, jurisdictions…)
│   └── assets/swms-template.html      ← the landscape A4 template
├── swmsmate.zip                  ← same folder, zipped for upload
└── project-instructions.md       ← paste-in instructions for Option 2
```

---

## Option 1 — ChatGPT skill (Business / Enterprise / Edu)

1. Download [`swmsmate.zip`](swmsmate.zip) (click it, then **Download raw file**).
2. In ChatGPT, open **Plugins → Skills**.
3. Choose **Create → Upload from your computer** and select `swmsmate.zip`.
4. Wait for the upload check to finish. Skills are scanned on upload, and your admin may need to approve it if it shows **Needs review**.
5. Start a new chat and ask: *"Make me a SWMS."*

If your workspace doesn't show **Skills**, your admin may have turned them off. Use Option 2 in the meantime.

To share it with your team, open the skill's **•••** menu and share it with people or groups in your workspace.

---

## Option 2 — ChatGPT Project (any plan, including Free)

1. In the ChatGPT sidebar choose **New project** and name it **SWMSmate**.
2. Open the project's **•••** menu → **Project settings**. Paste the full contents of [`project-instructions.md`](project-instructions.md) into the instructions box, then save.
3. Add these two files to the project (drag them in, or use **Add files**):
   - [`swmsmate/references/swms-reference.md`](swmsmate/references/swms-reference.md)
   - [`swmsmate/assets/swms-template.html`](swmsmate/assets/swms-template.html)
4. Start a new chat **inside the project** and ask: *"Make me a SWMS."*

Free accounts allow 5 files per project, so you're well within the limit.

---

## Use it

> Make me a SWMS

> Draft a SWMS for replacing a switchboard at 14 Example Ave, Marion SA

> I need a generic SWMS for gutter cleaning I can use at any house. I'm subcontracting to Acme Roofing.

ChatGPT asks up to six quick questions, shows a one-screen summary to confirm, asks whether to include risk ratings, then produces the SWMS.

## Getting the PDF

ChatGPT gives you `SWMS-DRAFT-<site>-<date>.html` as a download. If it can't create files in your chat, it pastes the HTML in a code block instead; copy that into a text file ending in `.html`.

1. Open the file in Chrome, Edge or Safari.
2. **Print → Save as PDF.** It's already set to A4 landscape. Turn on **Background graphics** if the colours don't show.

## Tips

- Ask for **portrait** if you prefer it, or ask it to add or remove risk ratings or change any step.
- If ChatGPT skips the template or changes the layout, remind it: *"Use the swms-template.html file exactly as provided."*
- Results vary between models. Always review the **Review before use** box and every highlighted **CHECK** item.
