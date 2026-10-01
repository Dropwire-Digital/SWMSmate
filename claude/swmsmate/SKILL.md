---
name: swmsmate
description: Draft an Australian Safe Work Method Statement (SWMS) for review from a few quick questions. Use when the user asks to make, write, draft or generate a SWMS or safe work method statement for a job.
---

# SWMSmate — SWMS drafting skill

Produce a **draft** SWMS for high risk construction work (HRCW) in Australia, from as few questions as possible, as a styled A4 HTML document (plus PDF if a headless browser is available). The output is always a draft for the user to review — never present it as final or compliant.

Layout: **landscape A4 by default** (easier to read on site); portrait if the user asks for it. Risk ratings (initial and residual, 5×5 matrix) are **optional** — decided at the confirm step.

## Principles

- **Ask little, infer a lot, confirm once.** The user describes the job in their own words; you propose the HRCW limbs, step sequence, hazards and controls, and they confirm or correct.
- **Never invent facts about the business, people or site.** Anything you had to assume goes in the document marked `CHECK` and is listed in the "Review before use" panel at the top.
- Plain English a worker can read on site. Short sentences. No filler.
- Controls follow the hierarchy of controls. Tag every control: `ELIM`, `SUB`, `ISO`, `ENG`, `ADMIN`, `PPE`. Lead each step with the highest-order control that applies. Tag honestly: scheduling, procedures, breaks and housekeeping are ADMIN, not ELIM — ELIM only when the hazard is actually removed.

## Step 1 — Intake (one message)

Skip any item the user already gave in their request. Ask the rest in a single plain-text message, formatted as a short fill-in list, e.g.:

> To draft your SWMS I need six things (rough answers are fine):
> 1. **Business** — name, ABN, and which state you work in
> 2. **The job** — what you're doing, in your own words (tools/plant you'll use, if it's easy)
> 3. **Site** — either a specific address (and is it occupied — residents, kids, pets — or empty?), **or** "generic" if you'll use this SWMS at lots of residential properties
> 4. **Who's the work for** — your own customer, or are you subcontracting to another company? (if so, which company)
> 5. **When** — start date and roughly how long (skip if generic)
> 6. **Who's in charge on site** — name and mobile (and anyone else on the crew, if you know)

Do not ask about: HRCW categories, hazards, controls, PPE, legislation, principal contractor, review dates, hospital, layout, risk ratings. You work those out (ratings are asked at Step 3).

If the answers are thin, make reasonable assumptions and mark them `CHECK` rather than asking again. Only ask a follow-up if the job description is too vague to name even one task step.

## Step 2 — Work it out

From the answers, determine:

1. **Jurisdiction** (from the state):
   - SA, NSW, QLD, TAS, ACT, NT → Work Health and Safety Regulations (harmonised), r. 299. Duty holder = "PCBU". Falls trigger 2 m.
   - WA → Work Health and Safety (General) Regulations 2022. Falls trigger **3 m for residential construction**, 2 m otherwise. Duty holder = "PCBU".
   - VIC → Occupational Health and Safety Regulations 2017, Part 5.1. Duty holder = "employer / self-employed person". Falls trigger 2 m. Note HSR consultation where one exists.
   - Regulator: SafeWork SA · SafeWork NSW · WorkSafe QLD · WorkSafe Tasmania · WorkSafe ACT · NT WorkSafe · WorkSafe WA · WorkSafe Victoria.
2. **HRCW limbs triggered** — from the 19-item list below. Only tick what the job actually involves. If none apply, tell the user a SWMS isn't legally required for this work (a SWMS is still fine as good practice) and ask whether to continue.
   - For each ticked limb, note **which job steps** it arises in and **one line on how** (e.g. "Mounting bracket at ~2.4 m from a ladder"). Every ticked limb must appear in at least one step, and every step's HRCW chips must match a ticked limb — the identification page and the steps table must agree.
   - Read the limbs literally. "Artificial extremes of temperature" means man-made heat or cold (cool rooms, freezers, furnaces, kilns, hot process areas) — **not** weather, sun or a hot roof space; treat those as ordinary hazards in the step. "Falling more than 2 m" is the distance a person could fall, not the working height. If a limb is borderline, tick it and mark `CHECK`.
3. **Job steps** — 4–10 ordered steps from arrival/set-up to clean-up/handover. For each: hazards and risks (specific to this job and site), controls (tagged), and who's responsible.
4. **Plant, tools and materials**; **licences/tickets** required (e.g. electrical licence, White Card, EWP, working at heights) — mark as `CHECK: confirm held`.
5. **PPE** summary.
6. **Emergency** — 000; nearest hospital with an emergency department to the site address (use web search if available; otherwise leave `CHECK`); first aider = the supervisor unless told otherwise (`CHECK`); muster point = sensible default (e.g. "front footpath / vehicle") marked `CHECK`; isolation points relevant to the job.
7. **Principal contractor** — for domestic/residential or small jobs where the user works for their own customer, assume there is none (construction projects under $250,000 have no principal contractor) and omit the field entirely. When subcontracting, see below.
8. **Site mode** — see "Generic (multi-site) SWMS" below. Specific address → normal. "Generic", "any house", "various sites", "all my residential jobs" → generic mode.
9. **Engagement** — see "Subcontracting to another company" below. Own customer → normal.
10. **Judgement check** — if any HRCW hazard is controlled only by ADMIN and/or PPE, add a one-line note in that step on why a higher-order control isn't reasonably practicable, marked `CHECK`.

## Generic (multi-site) SWMS

A generic SWMS for work done regularly is permitted, but the Construction Work Code of Practice says it must be reviewed and revised before each new activity so it fits the actual workplace. So a generic SWMS is only usable with a completed **Site check** at every property. In generic mode:

- **Section 1:** Work site = "Various residential properties — complete the Site check (last page) at each property before work starts". Site status = "Varies — recorded on Site check". Start / duration = "Ongoing". Sub-heading adds "(Generic — residential)".
- **Steps and hazards:** write for the typical case, and cover the common variations across houses (occupied vs vacant, children/pets, pre-1990 construction → possible asbestos, roof pitch/condition, access, overhead power lines). Where a hazard depends on the property, say so ("where the house is pre-1990…").
- **Emergency:** hospital, first aider, assembly point and isolation points are left as "Recorded on Site check" (no hospital lookup).
- **Review date:** 12 months from prepared, or sooner if a trigger occurs.
- **Site check page:** include the `site-check` block from the template (starts on a new page). Generate 6–8 yes/no checks **from this SWMS's own hazards** (e.g. a SWMS covering asbestos, overhead lines and ladder footing gets exactly those checks), phrased so "Yes" = safe to proceed. Keep the template's fixed last check ("No high risk work beyond what is ticked in section 3"). Then the "Anything different from this SWMS?" rows (hazard + extra control as a pair), emergency details for the address, and the supervisor's sign-off.
- **Review panel:** first item is always "Complete the Site check at each property before work starts (print or copy the last page per job)."
- **Filename:** `SWMS-DRAFT-generic-<short-activity>-<YYYY-MM-DD>.html`.
- In the Step 3 summary, say it's a generic SWMS and list the site checks it will include.

## Subcontracting to another company

When the user is working for another company (a builder, head contractor, retailer or installer network):

- **Section 1 (Business & job):** add the "Engaged by" row with the company's name (and contact if given).
- **Principal contractor:** if the company is a builder/head contractor on a project likely to be ≥ $250,000 (new build, major renovation, commercial), treat them as principal contractor: add the "Principal contractor" row with "provided: ____" and mark `CHECK: confirm they are the principal contractor`. If it's small domestic work (e.g. a retailer sending installers to homes) there's usually no PC — show only "Engaged by".
- **Section 2 (People & equipment):** add the "Head contractor rules" row: follow {{company}}'s site rules, induction, permits and any SWMS approval process — marked `CHECK`.
- **Sign-on:** add the "Reviewed by {{company}}" block under the sign-on table so the head contractor can review/accept the SWMS.
- **Review panel:** add "Send to {{company}} for review before work starts, and check whether they require their own SWMS template."
- Duty holder in Section 1 stays the user's business — the SWMS is theirs even when the other company reviews it.

Both options can apply at once (e.g. a generic SWMS for installs done for a retailer at many homes).

## Risk ratings (optional)

When ratings are on:
- Rate each step on its **highest-risk hazard**, before controls ("Risk") and after controls ("Residual"), as Likelihood × Consequence on the 5×5 matrix in the template. Show the level letter and the score pair, e.g. `H` with `4×4`.
- Levels: Low 1–4 · Medium 5–9 · High 10–16 · Extreme 20–25.
- Controls usually reduce **likelihood**; don't lower consequence unless a control actually changes the outcome (e.g. a harness limits fall severity, a lower platform removes the fall).
- Residual must not be Extreme. If residual is still High, flag it `CHECK: residual High — add controls or justify`.
- Always add "Risk ratings — confirm they reflect your experience of this work" to the Review panel.
- Include the RATINGS ONLY columns and the risk matrix. When ratings are off, delete those columns, their cells and the matrix.

## Step 3 — Confirm (one short message)

Before rendering, show a compact summary and get one confirmation. Use AskUserQuestion if available, with two questions in one call:
1. "Ready to generate?" — "Looks right — generate it" / "I'll make changes".
2. "Include risk ratings?" — "Yes" / "No". Put the likely choice first and mark it (Recommended): **Yes** when subcontracting to a builder/head contractor or when a principal contractor is involved; **No** for the user's own domestic customers.

Skip question 2 if the user already said whether they want ratings. Without AskUserQuestion, ask both in one plain-text line.

Summary format:

> **High risk work:** 1 Falls over 2 m (step 6) · 12 Energised electrical (steps 3, 4, 7)
> **Steps:** 1 Arrive & assess · 2 Isolate & test · 3 Set up ladder · 4 Run cable in roof space · 5 Terminate & test · 6 Clean up
> **Assumed (you'll see these flagged):** no principal contractor · Jane is first aider · house built pre-1990 so asbestos possible

If they make changes, apply them and go straight to rendering — don't reconfirm.

## Step 4 — Render

Write the HTML using the template below. Save to `SWMS-DRAFT-<short-site>-<YYYY-MM-DD>.html` — in Cowork use `/mnt/user-data/outputs/`; in Claude Code use the current working directory; in Claude.ai use the outputs folder the environment provides.

- **Landscape (default):** use the template as-is.
- **Portrait (only if asked):** change the `@page` line to `size: A4;` and use `<body class="portrait">`. Nothing else changes.
- Page order: **1** header, scope, Review panel, Business & job (with revision history) and People & equipment · **2** High risk construction work identification (all 19 categories on one page) · **3+** job steps · then emergency / monitoring, sign-on, and the site check (generic only). Keep Review panel items short (one line each) so page 1 fits.
- **HRCW identification page:** list all 19 in order. Ticked rows get `class="yes"`, `☒ Yes ☐ No`, the step numbers and the one-line reason; unticked rows get `☐ Yes ☒ No` and "—".
- **Steps table:** the "High risk work" column holds one chip per limb in that step, as number + short label from the list below (e.g. `<span class="hw">12 Electrical</span>`); "—" when none.

Then, if Chromium/Playwright is available, print it to PDF alongside (see below; orientation comes from the `@page` rule). If it isn't, skip the PDF silently — the HTML prints cleanly from a browser.

Required content (the 4 legal elements of r. 299 + admin fields):
1. Identifies the HRCW (identification page with all 19 categories, cross-referenced to the steps).
2. States hazards and risks per step.
3. Describes controls per step via the hierarchy.
4. Describes how controls are **implemented, monitored and reviewed** — named supervisor, check frequency, the mandatory review triggers, review date. This is the most commonly missed element; never leave it generic.
Plus: business name, ABN, address/state · site address · date prepared · person responsible for implementing and monitoring · workers consulted · sign-on table (8 blank rows) · revision history (Rev 0 — draft, on page 1).

Standards references (AS/NZS numbers) are optional; if you include any, add them to the Review panel as "verify current edition".

## Step 5 — Hand over

One or two sentences: the file, how many `CHECK` items need attention, and the reminder that the crew must read and sign it before starting. Offer to change anything (including portrait layout or adding/removing risk ratings). Don't recap the document.

## The 19 HRCW limbs

Full wording (identification page) → short chip label (steps table):

1. Risk of a person falling more than 2 m (WA residential: 3 m) → `Falls >2 m` (WA residential: `Falls >3 m`)
2. Work on a telecommunication tower → `Telco tower`
3. Demolition of an element of a structure that is load-bearing → `Load-bearing demolition`
4. Demolition of an element related to the physical integrity of a structure → `Structural demolition`
5. Likely to involve disturbing asbestos → `Asbestos`
6. Temporary load-bearing support for structural alterations or repairs → `Temporary support`
7. Work in or near a confined space → `Confined space`
8. Work in or near a shaft or trench deeper than 1.5 m, or a tunnel → `Trench / shaft`
9. Use of explosives → `Explosives`
10. Work on or near pressurised gas distribution mains or piping → `Gas mains`
11. Work on or near chemical, fuel or refrigerant lines → `Chem / fuel / refrigerant`
12. Work on or near energised electrical installations or services → `Electrical`
13. Work in an area that may have a contaminated or flammable atmosphere → `Flammable atmosphere`
14. Tilt-up or precast concrete elements → `Tilt-up / precast`
15. Work on, in or adjacent to a road, railway, shipping lane or other traffic corridor in use → `Traffic corridor`
16. Work in an area with movement of powered mobile plant → `Mobile plant`
17. Work in areas with artificial extremes of temperature → `Temperature extremes`
18. Work in or near water or other liquid with a risk of drowning → `Drowning risk`
19. Diving work → `Diving`

## Mandatory review triggers (print all)

- The work, system of work or location changes
- A new hazard or new information about a risk is identified
- A control is found not to be effective, or is changed
- A notifiable incident occurs during the work
- The SWMS is not being followed
- Before the work starts at each new site (if reused)

## HTML template

Fill every `{{…}}` (where a placeholder shows `a | b`, use whichever fits the mode). Repeat marked blocks as needed. Include blocks marked "ONLY when…", "RATINGS ONLY" or "GENERIC MODE ONLY" only in that case, and delete the rest. Wrap anything assumed in `<span class="check">CHECK: …</span>` and list every one in the Review panel. Remove all HTML comments from the output. Keep the CSS as-is.

```html
<!doctype html>
<html lang="en-AU">
<head>
<meta charset="utf-8">
<title>SWMS (DRAFT) — {{short job title}} — {{site address | "Generic residential"}}</title>
<style>
  /* LAYOUT SWITCH: landscape (default) = "A4 landscape"; portrait = "A4" and add class="portrait" to <body> */
  @page { size: A4 landscape; margin: 10mm 10mm 12mm; }
  :root { --ink:#18212b; --muted:#5b6672; --accent:#0b4f6c; --accent-soft:#e7f0f4; --line:#c7d0d8; --soft:#f4f6f8; --warn:#b54708; --warn-soft:#fff6e5; }
  * { box-sizing: border-box; }
  body { font: 9pt/1.4 "Helvetica Neue", Arial, sans-serif; color: var(--ink); margin: 0; background: #fff; }
  .page { max-width: 277mm; margin: 0 auto; padding: 6mm 0; }
  body.portrait .page { max-width: 190mm; }

  /* header */
  .masthead { display: grid; grid-template-columns: 1fr auto auto; gap: 14px; align-items: stretch; border-top: 5px solid var(--accent); padding-top: 8px; margin-bottom: 10px; }
  .masthead h1 { font-size: 18pt; margin: 0; letter-spacing: -0.3px; }
  .masthead .sub { color: var(--muted); font-size: 9.5pt; margin-top: 2px; }
  .masthead .biz { font-weight: 700; font-size: 10.5pt; margin-top: 6px; }
  .meta { border-collapse: collapse; font-size: 8.5pt; align-self: start; }
  .meta td { padding: 2px 8px; border: 0; border-left: 1px solid var(--line); }
  .meta td:first-child { color: var(--muted); }
  .stamp { align-self: start; border: 2px solid #b42318; color: #b42318; font-weight: 800; letter-spacing: 2px; padding: 4px 12px; font-size: 11pt; transform: rotate(-3deg); }
  body.portrait .masthead { grid-template-columns: 1fr auto; }
  body.portrait .meta { grid-column: 1 / -1; }
  body.portrait .stamp { grid-column: 2; grid-row: 1; }
  body.portrait .newpage { break-before: auto; }

  /* sections */
  h2 { font-size: 9.5pt; text-transform: uppercase; letter-spacing: 0.8px; color: var(--accent); border-bottom: 2px solid var(--accent); padding: 0 0 3px; margin: 12px 0 6px; break-after: avoid; }
  h2 .n { display: inline-block; background: var(--accent); color: #fff; width: 17px; height: 17px; line-height: 17px; text-align: center; border-radius: 50%; font-size: 8pt; margin-right: 6px; letter-spacing: 0; }
  .cols3 { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .cols2 { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  body.portrait .cols3, body.portrait .cols2 { grid-template-columns: 1fr; gap: 0; }
  .cols3 > div, .cols2 > div { break-inside: avoid; }
  .cols3 table { font-size: 8.1pt; } .cols3 th, .cols3 td { padding: 2.5px 5px; }
  .cols3 h2 { margin-top: 8px; }
  .newpage { break-before: page; }
  h2.mini { font-size: 8.5pt; margin-top: 10px; }
  .rev td, .rev th { padding: 2px 5px; font-size: 7.8pt; }

  /* tables */
  table { width: 100%; border-collapse: collapse; font-size: 8.6pt; }
  th, td { border: 1px solid var(--line); padding: 4px 6px; vertical-align: top; text-align: left; }
  thead th { background: var(--accent); color: #fff; font-weight: 600; border-color: var(--accent); }
  .kv th { background: var(--soft); width: 36%; font-weight: 600; color: #2c3742; }
  .kv tr, .sign tr, .steps tr { break-inside: avoid; }
  .small { font-size: 8.3pt; color: #3b4652; }
  .scope { background: var(--soft); border-left: 3px solid var(--accent); padding: 6px 8px; margin: 8px 0 0; font-size: 8.6pt; }

  /* review panel */
  .review { border: 1.5px solid var(--warn); background: var(--warn-soft); border-radius: 4px; padding: 7px 10px; margin-bottom: 4px; font-size: 8.5pt; }
  .review strong { color: var(--warn); }
  .review ol { margin: 4px 0 0; padding-left: 18px; columns: 2; column-gap: 24px; }
  body.portrait .review ol { columns: 1; }
  .check { background: #fde9bf; border-bottom: 1px dashed var(--warn); padding: 0 3px; font-size: 7.8pt; color: #7a2e0e; white-space: normal; }

  /* HRCW identification page */
  .hrtab { font-size: 8.4pt; }
  .hrtab td, .hrtab th { padding: 3.2px 6px; vertical-align: middle; }
  .hrtab td.no { width: 4%; text-align: center; font-weight: 800; color: var(--muted); }
  .hrtab td.box { width: 11%; white-space: nowrap; font-size: 9pt; }
  .hrtab td.box b { color: var(--accent); }
  .hrtab td.st { width: 9%; text-align: center; font-weight: 700; }
  .hrtab td.how { width: 34%; font-size: 8pt; }
  .hrtab tr { color: #7d8792; break-inside: avoid; }
  .hrtab tr.yes { color: var(--ink); }
  .hrtab tr.yes td { background: var(--accent-soft); }
  .hrtab tr.yes td.desc { font-weight: 700; }
  .hrtab tr.yes td.no { color: var(--accent); }
  .hr-intro { background: var(--soft); border-left: 3px solid var(--accent); padding: 6px 8px; font-size: 8.5pt; margin: 0 0 6px; }
  .hr-sign { margin-top: 8px; font-size: 8.5pt; }
  /* HRCW chips in the steps table */
  .hw { display: inline-block; background: var(--accent); color: #fff; font-size: 7pt; font-weight: 700; padding: 1px 5px; border-radius: 9px; margin: 0 3px 3px 0; white-space: nowrap; }
  .steps td.hr { width: 10%; }
  .steps td.hr .none { color: #9aa3ad; }

  /* steps table */
  .steps tbody tr:nth-child(even) td { background: #fafbfc; }
  .steps td.num { width: 3.5%; text-align: center; font-weight: 800; color: var(--accent); font-size: 10pt; }
  .steps td.step { width: 13%; font-weight: 600; }
  .steps td.haz { width: 22%; }
  .steps td.who { width: 9%; font-size: 8pt; }
  .steps td.rr { width: 6%; text-align: center; }
  .steps ul { margin: 0; padding-left: 13px; }
  .steps li { margin-bottom: 2px; }
  .tag { display: inline-block; min-width: 34px; text-align: center; font-size: 6.6pt; font-weight: 800; padding: 0 3px; border-radius: 2px; margin-right: 4px; color: #fff; vertical-align: 1px; }
  .ELIM { background: #067647; } .SUB { background: #3b7d23; } .ISO { background: #1570ef; }
  .ENG { background: #3538cd; } .ADMIN { background: #b54708; } .PPE { background: #667085; }
  .legend { font-size: 7.8pt; color: var(--muted); margin: 5px 0 0; }

  /* risk ratings (only when ratings are on) */
  .r { display: inline-block; min-width: 30px; font-weight: 800; font-size: 8pt; padding: 2px 4px; border-radius: 3px; }
  .r small { display: block; font-weight: 500; font-size: 6.8pt; }
  .r.L { background: #d1fadf; color: #05603a; } .r.M { background: #fef0c7; color: #93370d; }
  .r.H { background: #fdd6b5; color: #9c2a05; } .r.E { background: #b42318; color: #fff; }
  .matrix { width: auto; font-size: 7.4pt; }
  .matrix th, .matrix td { padding: 2px 5px; text-align: center; }
  .matrix th { background: var(--soft); color: var(--ink); border-color: var(--line); font-weight: 600; }
  .matrix td.L { background: #d1fadf; } .matrix td.M { background: #fef0c7; } .matrix td.H { background: #fdd6b5; } .matrix td.E { background: #b42318; color: #fff; }

  .sign td { height: 22px; }
  .site-check { break-before: page; }
  .checks td:nth-child(n+2) { text-align: center; font-size: 11pt; width: 7%; }
  footer { margin-top: 12px; font-size: 7.6pt; color: var(--muted); border-top: 1px solid var(--line); padding-top: 4px; display: flex; justify-content: space-between; }
  @media print { .page { padding: 0; } }
</style>
</head>
<body>
<div class="page">

<header class="masthead">
  <div>
    <h1>Safe Work Method Statement</h1>
    <div class="sub">{{short job title}}{{ " (Generic — residential)" if generic }}</div>
    <div class="biz">{{business name}} · ABN {{ABN}}</div>
  </div>
  <table class="meta">
    <tr><td>Site</td><td>{{site address | "Various residential properties"}}</td></tr>
    <tr><td>Prepared</td><td>{{today}} · Rev 0</td></tr>
    <tr><td>Review by</td><td>{{review date}}</td></tr>
    <tr><td>Legislation</td><td>{{jurisdiction short name}}</td></tr>
  </table>
  <div class="stamp">DRAFT</div>
</header>

<div class="scope" style="margin:0 0 8px"><strong>Scope of work:</strong> {{2–3 sentence plain description of the job}}</div>

<div class="review">
  <strong>Review before use.</strong> Drafted from a short description — the person responsible must check it before work starts. Confirm or fix:
  <ol>
    <!-- one <li> per CHECK item, in document order -->
    <li>{{check item}}</li>
  </ol>
</div>

<div class="cols3">
  <div>
    <h2><span class="n">1</span>Business &amp; job</h2>
    <table class="kv">
      <tr><th>{{PCBU | Employer / self-employed}}</th><td>{{business name}}</td></tr>
      <tr><th>ABN</th><td>{{ABN}}</td></tr>
      <tr><th>Address</th><td>{{business address or CHECK}}</td></tr>
      <tr><th>Contact</th><td>{{supervisor name, mobile}}</td></tr>
      <!-- ONLY when subcontracting -->
      <tr><th>Engaged by</th><td>{{company name, contact}}</td></tr>
      <!-- ONLY if the engaging company is (or may be) the principal contractor -->
      <tr><th>Principal contractor</th><td>{{PC name}} · provided: ______</td></tr>
      <tr><th>Work site</th><td>{{site address | generic wording}}</td></tr>
      <tr><th>Site status</th><td>{{occupied / vacant; residents, children, pets | "Varies — recorded on Site check"}}</td></tr>
      <tr><th>Start / duration</th><td>{{start date}} · {{duration | "Ongoing"}}</td></tr>
    </table>
    <h2 class="mini">Revision history</h2>
    <table class="rev">
      <thead><tr><th style="width:12%">Rev</th><th style="width:22%">Date</th><th>Change</th><th style="width:26%">By</th></tr></thead>
      <tbody>
        <tr><td>0</td><td>{{today}}</td><td>Draft prepared for review</td><td>{{supervisor}}</td></tr>
        <tr><td>&nbsp;</td><td></td><td></td><td></td></tr>
      </tbody>
    </table>
  </div>
  <div>
    <h2><span class="n">2</span>People &amp; equipment</h2>
    <table class="kv">
      <tr><th>Implements &amp; monitors</th><td>{{supervisor}}</td></tr>
      <tr><th>Reviews this SWMS</th><td>{{supervisor or business owner}}</td></tr>
      <tr><th>Workers consulted</th><td>{{crew names or CHECK}}</td></tr>
      <tr><th>Licences / tickets</th><td>{{list}} <span class="check">CHECK: confirm held</span></td></tr>
      <!-- ONLY when subcontracting -->
      <tr><th>Head contractor rules</th><td>Follow {{company}}'s site rules, induction, permits and SWMS approval process <span class="check">CHECK: confirm</span></td></tr>
      <tr><th>Plant &amp; tools</th><td>{{list}}</td></tr>
      <tr><th>Hazardous substances</th><td>{{list or "None expected"}}</td></tr>
      <tr><th>PPE (minimum)</th><td>{{list}}</td></tr>
    </table>
  </div>
</div>

<section class="newpage">
  <h2><span class="n">3</span>High risk construction work — identification</h2>
  <p class="hr-intro">Tick every category this work involves. <strong>A SWMS is required if any box is ticked.</strong> Each ticked item is cross-referenced to the job steps where it arises (section 4).</p>
  <table class="hrtab">
    <thead><tr><th>No.</th><th>High risk construction work</th><th>Involved?</th><th>Job steps</th><th>How it arises on this job</th></tr></thead>
    <tbody>
      <!-- all 19 limbs in order. Involved: class="yes", ☒ Yes ☐ No, step numbers, one-line reason. Not involved: ☐ Yes ☒ No, "—", blank -->
      <tr class="yes"><td class="no">{{n}}</td><td class="desc">{{limb}}</td><td class="box"><b>☒</b> Yes &nbsp; ☐ No</td><td class="st">{{2, 3}}</td><td class="how">{{one line: where/why on this job}}</td></tr>
      <tr><td class="no">{{n}}</td><td class="desc">{{limb}}</td><td class="box">☐ Yes &nbsp; ☒ No</td><td class="st">—</td><td class="how"></td></tr>
    </tbody>
  </table>
  <p class="hr-sign">Identified by: <strong>{{supervisor}}</strong> &nbsp; Date: {{today}} &nbsp; Signature: ______________________ &nbsp;&nbsp; <span class="small">If other high risk work comes up during the job, stop and review this SWMS.</span></p>
</section>

<h2 class="newpage"><span class="n">4</span>Job steps, hazards and controls</h2>
<table class="steps">
  <thead><tr>
    <th>#</th><th>Job step</th><th>High risk work</th><th>Hazards and risks</th>
    <!-- RATINGS ONLY --><th>Risk</th>
    <th>Control measures</th>
    <!-- RATINGS ONLY --><th>Residual</th>
    <th>Responsible</th>
  </tr></thead>
  <tbody>
    <!-- one <tr> per step -->
    <tr>
      <td class="num">1</td>
      <td class="step">{{step}}</td>
      <!-- chip per HRCW limb in this step (number + short label); "—" if none -->
      <td class="hr"><span class="hw">1 Falls &gt;2 m</span> <span class="hw">12 Electrical</span></td>
      <td class="haz"><ul><li>{{hazard → what could happen}}</li></ul></td>
      <!-- RATINGS ONLY: highest-rated hazard in the step; letter + L×C -->
      <td class="rr"><span class="r H">H<small>4×4</small></span></td>
      <td><ul>
        <li><span class="tag ENG">ENG</span>{{control}}</li>
        <li><span class="tag ADMIN">ADMIN</span>{{control}}</li>
      </ul></td>
      <!-- RATINGS ONLY -->
      <td class="rr"><span class="r L">L<small>1×4</small></span></td>
      <td class="who">{{name}}</td>
    </tr>
  </tbody>
</table>
<p class="legend">Controls, most to least effective: <span class="tag ELIM">ELIM</span>Eliminate <span class="tag SUB">SUB</span>Substitute <span class="tag ISO">ISO</span>Isolate <span class="tag ENG">ENG</span>Engineering <span class="tag ADMIN">ADMIN</span>Administrative <span class="tag PPE">PPE</span>Protective equipment</p>

<!-- RATINGS ONLY: risk matrix -->
<table class="matrix" style="margin-top:6px">
  <tr><th rowspan="2">Likelihood ↓ / Consequence →</th><th>1 Insignificant</th><th>2 Minor</th><th>3 Moderate</th><th>4 Major</th><th>5 Catastrophic</th></tr>
  <tr><th colspan="5" style="font-weight:400">Score = L × C · Low 1–4 · Medium 5–9 · High 10–16 · Extreme 20–25</th></tr>
  <tr><th>5 Almost certain</th><td class="M">5</td><td class="H">10</td><td class="H">15</td><td class="E">20</td><td class="E">25</td></tr>
  <tr><th>4 Likely</th><td class="L">4</td><td class="M">8</td><td class="H">12</td><td class="H">16</td><td class="E">20</td></tr>
  <tr><th>3 Possible</th><td class="L">3</td><td class="M">6</td><td class="M">9</td><td class="H">12</td><td class="H">15</td></tr>
  <tr><th>2 Unlikely</th><td class="L">2</td><td class="L">4</td><td class="M">6</td><td class="M">8</td><td class="H">10</td></tr>
  <tr><th>1 Rare</th><td class="L">1</td><td class="L">2</td><td class="L">3</td><td class="L">4</td><td class="M">5</td></tr>
</table>

<div class="cols2 newpage">
  <div>
    <h2><span class="n">5</span>Emergency</h2>
    <table class="kv">
      <tr><th>Emergency services</th><td><strong>000</strong> (112 from a mobile with no coverage)</td></tr>
      <tr><th>Nearest hospital (ED)</th><td>{{name, address, drive time | "Recorded on Site check"}}</td></tr>
      <tr><th>First aider / kit</th><td>{{name · kit location}}</td></tr>
      <tr><th>Assembly point</th><td>{{location}}</td></tr>
      <tr><th>Isolation points</th><td>{{switchboard, gas, water, solar/battery}}</td></tr>
      <tr><th>Stop work if</th><td>{{2–4 job-specific stop-work triggers}}</td></tr>
    </table>
  </div>
  <div>
    <h2><span class="n">6</span>Implementing, monitoring &amp; review</h2>
    <table class="kv">
      <tr><th>How controls are put in place</th><td>{{supervisor}} briefs all workers on this SWMS before work starts; everyone signs on. {{job-specific set-up check}}.</td></tr>
      <tr><th>How controls are checked</th><td>{{supervisor}} checks controls {{frequency}}; {{job-specific checks}}. Workers stop work and report if a control is missing or not working.</td></tr>
      <tr><th>Review date</th><td>{{review date}} — or sooner if a trigger occurs</td></tr>
      <tr><th>Must be reviewed when</th><td>
        <ul style="margin:0;padding-left:13px">
          <li>The work, system of work or location changes</li>
          <li>A new hazard or new information about a risk is identified</li>
          <li>A control is found not to be effective, or is changed</li>
          <li>A notifiable incident occurs during the work</li>
          <li>The SWMS is not being followed</li>
          <li>Before the work starts at each new site (if reused)</li>
        </ul></td></tr>
      <tr><th>Legislation</th><td>{{Act and Regulations}} · Code of Practice: Construction Work · Regulator: {{regulator}}</td></tr>
    </table>
  </div>
</div>

<h2><span class="n">7</span>Worker sign-on</h2>
<p class="small" style="margin:0 0 4px">By signing I confirm this SWMS has been explained to me, I understand it, and I will follow it. I will stop work and tell my supervisor if I can't.</p>
<table class="sign">
  <thead><tr><th style="width:26%">Name</th><th style="width:22%">Company</th><th style="width:16%">Licence / ticket no.</th><th style="width:22%">Signature</th><th>Date</th></tr></thead>
  <tbody>
    <!-- 8 blank rows -->
    <tr><td></td><td></td><td></td><td></td><td></td></tr>
  </tbody>
</table>
<!-- ONLY when subcontracting -->
<table class="kv" style="margin-top:8px">
  <tr><th style="width:20%">Reviewed by {{company}}</th><td>Name: ____________________ &nbsp; Signature: ____________________ &nbsp; Date: __________ &nbsp; ☐ Accepted &nbsp; ☐ Changes needed</td></tr>
</table>

<!-- GENERIC MODE ONLY: site-check block -->
<section class="site-check">
  <h2>Site check — complete at each property before work starts</h2>
  <p class="small" style="margin:0 0 6px">This generic SWMS only applies once this page is completed for the property. Copy or print one per job. If any answer is "No", fix it or record the extra control before starting.</p>
  <div class="cols2">
    <div>
      <table class="kv">
        <tr><th>Property address</th><td></td></tr>
        <tr><th>Date / job ref</th><td></td></tr>
        <tr><th>Occupied?</th><td>☐ Vacant &nbsp; ☐ Occupied — adults ___ children ___ pets ___</td></tr>
      </table>
      <table class="checks" style="margin-top:6px">
        <thead><tr><th>Check (from this SWMS)</th><th>Yes</th><th>No</th></tr></thead>
        <tbody>
          <!-- 6–8 rows, phrased so Yes = OK to proceed -->
          <tr><td>{{check}}</td><td>☐</td><td>☐</td></tr>
          <tr><td>No high risk work at this property beyond what is ticked in section 3 (if there is: stop and review this SWMS)</td><td>☐</td><td>☐</td></tr>
        </tbody>
      </table>
    </div>
    <div>
      <p class="small" style="margin:0 0 4px"><strong>Anything here different from this SWMS?</strong> ☐ No &nbsp; ☐ Yes — record each one:</p>
      <table class="sign">
        <thead><tr><th style="width:45%">Site-specific hazard</th><th>Extra control</th></tr></thead>
        <tbody><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr></tbody>
      </table>
      <table class="kv" style="margin-top:6px">
        <tr><th>Nearest hospital (ED)</th><td></td></tr>
        <tr><th>First aider / kit location</th><td></td></tr>
        <tr><th>Assembly point</th><td></td></tr>
        <tr><th>Isolation points</th><td></td></tr>
        <tr><th>Checked by (supervisor)</th><td>Name / signature / time:</td></tr>
      </table>
      <p class="small">Crew at this property must also sign on (section 7).</p>
    </div>
  </div>
</section>

<footer><span>{{business name}} · SWMS — {{short job title}} · Rev 0 DRAFT</span><span>Keep at the workplace for the duration of the work</span></footer>

</div>
</body>
</html>
```

## PDF render (if available)

```bash
chromium --headless --no-sandbox --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="<same name>.pdf" "file://<path>.html"
```
(Try `chromium`, `chromium-browser`, `google-chrome`, or `/opt/pw-browsers/chromium*/chrome-linux/chrome`.)