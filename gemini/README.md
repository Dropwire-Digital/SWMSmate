Readme · MD
# SWMSmate for Gemini
 
Two ways to set it up, depending on your Google account:
 
| Your account | Use | Why |
|---|---|---|
| **Personal Google account** (gmail.com) | **Option 1 — Gemini skill** (recommended) | Google is replacing Gems with skills on personal accounts from **November 2026**. |
| **Google Workspace** (work or school) | **Option 2 — Gem** | Skills aren't available on Workspace accounts yet. Workspace Gems keep running until March 2027 (June 2027 for education accounts). |
 
```
gemini/
├── swmsmate/
│   └── SKILL.md          ← the skill (instructions + HTML template in one file)
└── gem-instructions.md   ← paste-in instructions for Option 2
```
 
---
 
## Option 1 — Gemini skill (personal accounts)
 
Requirements (Google's): a personal Google account, aged 18+, with **Keep Activity** turned on. Skills work in the Gemini web app, the Mac app and the mobile app.
 
1. Download [`swmsmate/SKILL.md`](swmsmate/SKILL.md) (click it, then **Download raw file**).
2. Go to [gemini.google.com](https://gemini.google.com) → **Settings → Skills**.
3. Choose **Upload** and select `SKILL.md`.
4. Start a new chat and ask: *"Make me a SWMS"*, or call it directly with `/swmsmate`.
> **Canvas:** Google says Canvas doesn't work with skills yet, so the skill gives you the SWMS as a code block to save. If you want the Canvas preview, use a Gem (Option 2) for now. Personal-account Gems are converted to skills from November 2026.
 
---
 
## Option 2 — Gem (Google Workspace accounts)
 
1. Go to [gemini.google.com](https://gemini.google.com) → **Gems → New Gem**.
2. **Name:** SWMSmate.
3. **Instructions:** paste the contents of [`gem-instructions.md`](gem-instructions.md).
4. **Knowledge:** upload [`swmsmate/SKILL.md`](swmsmate/SKILL.md).
5. **Default tool:** set it to **Canvas**, so every chat with the Gem starts with Canvas switched on.
6. **Save**, then open the Gem and ask: *"Make me a SWMS."* The finished SWMS opens in Canvas, where you can preview it and download it.
---
 
## Use it
 
> Make me a SWMS
 
> Draft a SWMS for replacing a switchboard at 14 Example Ave, Marion SA
 
> I need a generic SWMS for gutter cleaning I can use at any house. I'm subcontracting to Acme Roofing.
 
Gemini asks up to six quick questions, shows a one-screen summary to confirm, asks whether to include risk ratings, then writes the SWMS.
 
## Getting the PDF
 
**Gem with Canvas:** the SWMS opens in Canvas. Use Canvas's download or export option, or copy the code, then follow steps 2–4.
 
**Skill (no Canvas yet):** Gemini gives you the finished SWMS as a block of HTML code.
 
1. Copy the whole code block (use its copy or download button).
2. Paste it into a plain text file and save it as `SWMS-DRAFT-<site>.html`. On Windows use Notepad; on Mac use TextEdit in plain-text mode (**Format → Make Plain Text**).
3. Open the file in Chrome, Edge or Safari.
4. **Print → Save as PDF.** It's already set to A4 landscape. Turn on **Background graphics** if the colours don't show.
## Tips
 
- Ask for **portrait** if you prefer it, or ask it to add or remove risk ratings or change any step.
- Long SWMS can hit Gemini's response length. If the code stops before `</html>`, say *"continue the HTML exactly where you stopped"*, then join the two parts together.
- Results vary between models. Always review the **Review before use** box and every highlighted **CHECK** item.
 
