# SWMSmate reference

Detailed rules for drafting an Australian SWMS. Read alongside `SKILL.md` and fill in `assets/swms-template.html`.

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
- Rate each step on its **highest-risk hazard**, before controls ("Risk") and after controls ("Residual"), as Likelihood × Consequence on the 5×5 matrix in `assets/swms-template.html`. Show the level letter and the score pair, e.g. `H` with `4×4`.
- Levels: Low 1–4 · Medium 5–9 · High 10–16 · Extreme 20–25.
- Controls usually reduce **likelihood**; don't lower consequence unless a control actually changes the outcome (e.g. a harness limits fall severity, a lower platform removes the fall).
- Residual must not be Extreme. If residual is still High, flag it `CHECK: residual High — add controls or justify`.
- Always add "Risk ratings — confirm they reflect your experience of this work" to the Review panel.
- Include the RATINGS ONLY columns and the risk matrix. When ratings are off, delete those columns, their cells and the matrix.

## Rendering rules

Fill in `assets/swms-template.html`. File name: `SWMS-DRAFT-<short-site>-<YYYY-MM-DD>.html`.

- **Landscape (default):** use the template as-is.
- **Portrait (only if asked):** change the `@page` line to `size: A4;` and use `<body class="portrait">`. Nothing else changes.
- Page order: **1** header, scope, Review panel, Business & job (with revision history) and People & equipment · **2** High risk construction work identification (all 19 categories on one page) · **3+** job steps · then emergency / monitoring, sign-on, and the site check (generic only). Keep Review panel items short (one line each) so page 1 fits.
- **HRCW identification page:** list all 19 in order. Ticked rows get `class="yes"`, `☒ Yes ☐ No`, the step numbers and the one-line reason; unticked rows get `☐ Yes ☒ No` and "—".
- **Steps table:** the "High risk work" column holds one chip per limb in that step, as number + short label from the list below (e.g. `<span class="hw">12 Electrical</span>`); "—" when none.


Required content (the 4 legal elements of r. 299 + admin fields):
1. Identifies the HRCW (identification page with all 19 categories, cross-referenced to the steps).
2. States hazards and risks per step.
3. Describes controls per step via the hierarchy.
4. Describes how controls are **implemented, monitored and reviewed** — named supervisor, check frequency, the mandatory review triggers, review date. This is the most commonly missed element; never leave it generic.
Plus: business name, ABN, address/state · site address · date prepared · person responsible for implementing and monitoring · workers consulted · sign-on table (8 blank rows) · revision history (Rev 0 — draft, on page 1).

Standards references (AS/NZS numbers) are optional; if you include any, add them to the Review panel as "verify current edition".

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

## Filling the template

Fill every `{{…}}` (where a placeholder shows `a | b`, use whichever fits the mode). Repeat marked blocks as needed. Include blocks marked "ONLY when…", "RATINGS ONLY" or "GENERIC MODE ONLY" only in that case, and delete the rest. Wrap anything assumed in `<span class="check">CHECK: …</span>` and list every one in the Review panel. Remove all HTML comments from the output. Keep the CSS as-is.

