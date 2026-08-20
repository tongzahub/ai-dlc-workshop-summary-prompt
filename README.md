# AI-DLC Workshop — Prompt Pack

Three prompts, one file. Copy the one you need and paste it into your terminal.

| | Prompt | Who runs it | Where |
|---|---|---|---|
| 1 | **Two days, in your own record** | every team, any group | the team's own group folder |
| 2 | **Score one team** | facilitator only | the facilitator repository |
| 3 | **Reconstruct the two days** | facilitator only | the facilitator repository |
| 4 | **Workshop timeline map** | facilitator only | the facilitator repository |

Prompts 2, 3 and 4 read internal files — the rubric, the answer sheet — that are **not published
here**. Pasting them anywhere else produces nothing useful. Nothing on this page reveals what
those files contain, which is why this page can be handed out.

---

# 1 · Two days, in your own record

**Any group.** It reads what your team left behind — the AI-DLC audit trail, your git history,
your decision log — and writes `TEAM-SUMMARY.md` in your folder.

**When:** Day 2, after your demo, before the retro. Not earlier.
**Where:** a session opened at your group folder — the one holding `aidlc-docs/`,
`team-log.md` and your `.git`. Same place you have been working all along.

You do not need to say which group you are. It works that out from your folder.

```text
Read what my team left behind over the last two days and write a factual record of it.

WORK OUT WHERE YOU ARE FIRST
Read README.md and vision-document.md in this folder to identify which system we built.
Then confirm aidlc-docs/, team-log.md and .git exist here. If any is missing, say so and
carry on with what is here.

READ THESE
- aidlc-docs/aidlc-state.md and aidlc-docs/audit.md — the workflow's own record
- our execution plan under aidlc-docs/ — which stages it marked EXECUTE and which SKIP
- every file under aidlc-docs/ containing an [Answer]: tag — the questions and our answers
- team-log.md — roles, decisions, contradictions, gate approvals, hand edits, retro
- git log --format='%h|%ad|%s' --date=iso and git log --numstat --date=iso

RULES
- Facts only. Every statement cites the file or the commit it came from.
- If something is not recorded anywhere, write "not recorded". Do not reconstruct it from
  what probably happened, and do not fill a gap with a plausible guess.
- Quote our own words when the wording matters — a recorded rationale, a retro friction.
- Do not score us, grade us, or judge the quality of anything. This is a record.
- Do not open traceability-worksheet.md and do not write anything into it. That is our work.
- Do not compare us to any other team.

WRITE TEAM-SUMMARY.md IN THIS FOLDER, WITH THESE SECTIONS

1. What we built — three sentences. The system, who it is for, what it does now that works.

2. Our execution plan — a table of all nine AI-DLC stages with EXECUTE or SKIP for each, and
   the reason recorded for each SKIP. Where no reason was recorded, write "no reason
   recorded". Then: how many stages we executed, and how many Units of Work we produced.

3. Our extension decision — Security, Resiliency, Property-Based Testing: which we took,
   which we declined, and the rationale we recorded, quoted. A decline with no recorded
   reason counts as no reason.

4. The two days, hour by hour — one merged timeline from audit.md entries and git commit
   timestamps. Columns: time, what happened, source. Include every gate. Mark any gate where
   we requested changes rather than continuing.

5. The questions the workflow asked us, and how we answered — one row per [Answer]: tag.
   Columns: the question in short, our answer in short, and where our answer came from if we
   recorded a source (a stakeholder, a document, a quoted sentence).

6. Decisions we made, and why — from team-log.md and our answer files. Columns: the decision,
   the reason we recorded, when. Put the contradictions we resolved in their own sub-table:
   what disagreed with what, and how we settled it.

7. Where we changed our minds — every mid-workflow change in the audit trail, every gate we
   sent back for changes, every decision we revisited. What changed and why.

8. What our software produces — run whatever check our group folder provides against the
   answer key that ships with it, and paste the real output. If our numbers do not match,
   report the mismatch as it is. Do not adjust anything to make it match.

9. The honest notes — hand edits we declared, anything we skipped and knew we were skipping,
   anything unfinished, and the frictions from our retro in our own words, verbatim.

Keep it under three pages. Where the record is thin, let it read thin — a short honest
section is the finding, and padding it hides the one thing worth knowing.
```

### What you get

`TEAM-SUMMARY.md` — a factual record of your two days, sourced from your own artifacts. It
goes back with your folder, and it is the fastest way to brief someone who was not in the room.

It is also the honest test of whether you worked the way the workflow asked. A team that
answered in files, recorded the why, and committed as it went gets a summary with substance in
every section. A team that did not gets a lot of "not recorded" — which is worth knowing
before you try this on a real project, not after.

### What it deliberately does not do

- **It does not fill in `traceability-worksheet.md`.** Walking a number backwards to the
  sentence that caused it is the exercise. An AI reconstructing the chain for you produces a
  chain nobody in the team can defend at 15:00.
- **It does not score you.** The rubric is the facilitator's, and you can ask to see it at any
  time.
- **It does not compare you to the other teams.** The briefs are different on purpose.

---

# 2 · Score one team · facilitator

Run from the facilitator repository, after the team has handed its folder back. Never from
inside the team's folder.

**78 of the 100 points leave a trace in the repository.** The other 22 — the live demo, the
backwards walk performed out loud, and the parts about what you saw someone do — do not. This
prompt scores the 78 and leaves the 22 blank. It must never invent them.

```text
Score one AI-DLC workshop team from the artifacts they handed back.
Group: <g1|g2|g3|g4>   Team folder: <path>   Team name: <name>

READ FIRST, FROM THIS REPOSITORY
- Scoring-Sheet.md — the rubric, the acceptance check per group (2.2), the seeded content
  each group should have surfaced (3.2)
- Traceability-Map.md — the 18 loops, INCLUDING the caution section. Two loops can be passed
  by a wrong implementation. Read what it says to ask instead, and apply it in Pass 3.

RULES THAT OVERRIDE EVERYTHING
1. Evidence or zero. Every point cites a file:line you read or the output of a command you
   ran. No evidence found -> score 0 and write "no evidence found". Never award points on the
   assumption that a team probably did it.
2. The team's folder is read-only. Do not commit, create files, or run their formatter there.
   Their history is part of what you are scoring.
3. Never fill a [FACILITATOR] line. Those points are observed in the room.
4. One team per run. Never rank. If asked to compare teams, refuse and say why: the briefs
   are deliberately different and the totals are not comparable.
5. Quote, do not paraphrase, when the wording is the finding.
6. Report the awkward result. A flattering number makes section 6 of the outcome report
   useless.

PASS 0 — SNAPSHOT
git -C <folder> log --format='%h %ad %s' --date=iso | cat
git -C <folder> log --numstat --format='COMMIT %h %ad' --date=iso | cat
ls -R <folder>/aidlc-docs/
Record commit count, first-to-last span, whether aidlc-docs/ is committed. Keep the commit
list; Pass 2 needs the timestamps. If aidlc-docs/ is missing entirely, stop and report it —
section 1 is 0 and the team did not run the workflow.

PASS 1 — HOW QUESTIONS WERE ANSWERED (rubric 1.2, max 8, auditable ceiling 6)
Find every file under aidlc-docs/ containing [Answer]: tags. Classify each answer:
  EMPTY    — tag present, nothing after it
  BARE     — a letter or one word, no reason
  REASONED — a choice plus why, in the team's own words
  SOURCED  — a choice, a why, and a pointer to where it came from: a stakeholder, a
             document, a quoted sentence
Cross-check every SOURCED one: open the group's stakeholder notes / change request / bug
reports and confirm the cited sentence is actually there. An answer citing a source that does
not exist is a worse finding than a bare one — report it explicitly.
Output a table: file, question, class, note. Then the counts. Award:
  6   no EMPTY, majority SOURCED
  4-5 no EMPTY, majority REASONED
  2-3 some BARE but every question answered
  0-1 any EMPTY at a gate that was then approved
Append: "[FACILITATOR] +0-2 — answers given in chat? deduct on the second warning: ___"

PASS 2 — PROCESS AND AUDIT TRAIL
1.3 aidlc-docs complete (max 8, fully auditable). Score against THEIR OWN execution plan, not
    against the fullest possible shape. Read the plan first, then check the artifacts it
    promised. A missing artifact the plan said EXECUTE is a deduction.
1.1 every stage ended at a human-approved gate (max 8, ceiling 6). For each stage in audit.md
    and aidlc-state.md: is there a gate record with explicit approval, and does the next stage
    start after it? A stage that advanced with no gate entry is the finding.
    "[FACILITATOR] +0-2 — did the Reviewer actually read before approving?"
1.4 audit trail verbatim, not retro-fitted (max 6, fully auditable). A timestamp job. Compare
    the order of events in audit.md against git log. The retro-fit signature: aidlc-docs/
    arriving in one large commit at the end, or audit entries all within minutes of each other
    describing code committed over hours. Check the reverse too: code with no audit entry near
    it. Report the actual timestamps you compared. 6 = docs grew alongside the code.
1.5 extension decision recorded with rationale (max 5). Grep aidlc-docs/ and team-log.md for
    Security / Resiliency / PBT. The expected choice per group is in Scoring-Sheet.md. Score
    the RATIONALE, not the choice — an unrecorded "no" scores the same as never having been
    asked. Quote it. A correct choice with no why is 1, not 5.
1.6 no vibe coding (max 5, ceiling 3). Find code commits no unit doc or audit entry accounts
    for, and declared hand edits in team-log.md. A declared hand edit costs nothing; an
    undeclared one is the finding. List suspect commits by hash and what they touched.
    "[FACILITATOR] +0-2 — hand edits you saw in the room: ___"

PASS 3 — WORKING SOFTWARE — RUN THE COMMANDS
Do not read the code and conclude it looks right. Start their service and run the group's
acceptance check from Scoring-Sheet.md section 2.2. Paste the real output.
2.2 answer key reproduced (max 10). Exact match = 10. Partial = the proportion of rows that
    match, and name the rows that did not.
    THEN run the anti-false-pass check for this group. Traceability-Map.md's caution section
    names the loops that a wrong implementation can pass and the question to ask instead —
    apply it exactly. If the headline check passes while the anti-false-pass check fails, that
    sentence goes at the TOP of the sheet. It is the most valuable thing this pass produces.
2.3 tests assert what was at risk, and the screen is thin (max 5). Run their suite. Then read
    the screen's code: does it call the API, or recompute the number itself? A screen that
    recomputes scores 0 here regardless of how it looks — the number on it is no longer
    evidence about the service.
2.4 brownfield only (max 3). git log the pre-existing test files. Modified? Run them. For a
    greenfield group mark N/A and remove 3 from both the max and the total — do not award the
    points by default.

PASS 4 — DECISION QUALITY AT GATES
3.1 contradictions found and resolved with the why (max 6). Search team-log.md and the answer
    files for each seeded disagreement handled, and quote the resolution. Score on whether the
    why is recorded, not on which way they went.
3.2 seeded content surfaced (max 6). Take this group's row from Scoring-Sheet.md section 3.2 —
    one point per item, capped at 6. For each, find evidence the team NOTICED it: an answer
    file, a log entry, a test, a line of code that only makes sense if they knew. Distinguish
    "the code happens to be correct" from "they found it": a correct implementation with no
    trace of the discovery is worth half, and say which one you are looking at.
3.3 scope pushed back (max 4). Find the Phase 2 items in the group's documents and check what
    happened to each: recorded as deferred (full marks), silently built (deduct, and say what
    they built), silently dropped (deduct).
3.4 EXECUTE/SKIP justified (max 4). For every SKIP in the execution plan, is a reason
    attached? Unreasoned SKIPs that happen to be correct still score low — the exercise is
    defending the plan, not receiving it.

PASS 5 — DEMO AND RETRO
4.2 traceability-worksheet.md filled in, break real and specific (max 3). Check each chain
    against Traceability-Map.md. A chain that stops at "the AI decided that" IS the finding —
    score on whether they noticed and said so, not on whether the chain was complete. One
    honest break beats five easy chains. Say which loops they picked and whether they are the
    easy ones.
4.3 retro frictions specific and actionable (max 3). "It was slow" = 0. "Gate approval took 20
    minutes because only one person had read the design" = full marks.
"[FACILITATOR] 4.1 (max 4) — walked one number backwards, live, without reconstructing it: ___"

WRITE scores/<group>-<team-name>.md
  # <Team> — artifact-based score
  Scored by: AI pass over handed-back artifacts, <date>
  Repository: <path>, <N> commits, <first> -> <last>
  ## Headline — one sentence. A failed anti-false-pass check goes here.
  ## Auditable score — <X> / 78   (table: item, max, score, evidence file:line)
  ## Needs the facilitator — 22 points not in the repository
     2.1 acceptance scenario demoed live, on the screen  12  ___
     4.1 walked one number backwards, live                4  ___
     1.1 Reviewer read before approving                   2  ___
     1.2 answers given in chat                            2  ___
     1.6 hand edits seen in the room                      2  ___
  ## Commands run — verbatim, with output
  ## Three things this team did that a real project would want
  ## Three things that would bite them on a real project
  ## One sentence for the team
  ## One thing they should take back

Do not compute a /100 total. The facilitator adds the 22 and does that per team, against that
team's own brief — and does not publish it.
```

---

# 3 · Reconstruct the two days · facilitator

Run from the facilitator repository, after **every** team has handed back and after prompt 2
has run for each of them — section 6 of the report draft reads what prompt 2 wrote.

```text
Reconstruct what happened over the two workshop days from what the teams left behind.
Team folders: g1=<path> g2=<path> g3=<path> [g4=<path>]

READ FIRST, FROM THIS REPOSITORY
- Workshop-Outcome-Report.md — the template you are drafting against. DO NOT OVERWRITE IT.
- Traceability-Map.md — to check whether each team's demoed chain is real
- ../AIDLC-Workshop-Kit/Workshop-Agenda.md — for the planned-versus-actual table
- scores/*.md — the per-team scores, if they have been produced

WHAT THE ARTIFACTS CAN AND CANNOT TELL YOU
  audit.md            proves the stage sequence, every gate, every mid-workflow change
                      cannot show whether a human read the artifact before approving
  aidlc-state.md      proves where the workflow ended up
                      cannot show how much argument happened on the way
  the execution plan  proves EXECUTE/SKIP per stage — the central evidence of this workshop
                      cannot show whether the team defended the plan or accepted it
  [Answer]: files     prove what was asked and answered, in whose words
                      cannot show answers typed into chat instead
  git log timestamps  prove real elapsed time, order, whether docs grew with the code
                      cannot show time spent reading, discussing, or stuck
  team-log.md         proves decisions with the why, contradictions, hand edits, the retro
                      cannot show anything the Scribe did not write down
Anything in the second line of each pair is [FACILITATOR] — leave it blank.

RULES
1. Never rank the teams. The one cross-team comparison this report exists to make is SHAPE:
   which stages each plan executed and skipped. That is the thesis, not a league table. Do not
   order teams by stage count, commit count, or score.
2. Derived or blank. Every filled cell cites the artifact it came from. Missing artifact ->
   "not recorded", and that absence is itself a finding worth reporting.
3. Retro quotes are verbatim. Do not smooth them, translate them, or merge two into one.
4. Only the groups that actually ran get a column. Three teams means three columns — never
   leave a column of blanks that reads as a team who failed to deliver.
5. Team folders are read-only.

PASS 0 — INVENTORY
Per team: commit count, first and last commit time, whether aidlc-docs/ is committed, which
assistant they used. Flag anything missing at the top — a team with no aidlc-docs/ in git
changes what the rest of the report can say about them.

PASS 1 — THE TWO-DAY TIMELINE
Merge every team's audit.md entries and git commits into ONE chronological table, labelled by
team: time, team, event, source. Include every gate.
Then the agenda-versus-actual table, which is the part a sponsor reads: workflow started,
requirements/RE closed, execution plan approved, first unit complete, answer key reproduced,
screen up — planned time against each team's actual.
Where a team ran late, say by how long and what the audit trail shows they were doing. A team
that spent two extra hours in Requirements because stakeholders contradicted each other is a
success story, not a delay — but only if the audit trail shows that is what happened. Check
before you frame it that way.

PASS 2 — THE ADAPTIVE WORKFLOW (fills report section 2)
For each team, from the execution plan and audit.md, mark every stage EXECUTE or SKIP:
Workspace Detection, Reverse Engineering, Requirements Analysis, User Stories, Workflow
Planning, Application Design, Units Generation, Construction, Build and Test.
Fill the section 2 matrix. Count stages executed out of 9, count Units of Work, record the
extension decision with the rationale QUOTED. Compare each plan against the expected shape for
that group and give every deviation a row: what they did differently, their recorded
rationale, whether it was defensible.
Then fill the sponsor sentence with real numbers:
  "N teams, one methodology, ___ to ___ stages executed. Nobody configured that difference —
   the workflow proposed it from the shape of the work, and each team defended or changed it
   at a gate."
If the numbers are the same across all teams, SAY SO PLAINLY. That would mean the workflow did
not adapt, and it is the most important sentence in the report. Do not spin it.

PASS 3 — TRACEABILITY (fills report section 3)
From each traceability-worksheet.md, take the loop the team demoed. Check it against
Traceability-Map.md: is it one of the 18, is the chain real, is it one of the easy ones?
Fill both tables — the chains that closed, and the ones that BROKE. The second is worth more
to the client. Then find the cross-team pattern; if it shows up in most teams, say it in one
sentence. For the closing session, pull one loop per team for the screen: the sentence a human
said, and the number it lands on.

PASS 4 — WHAT THE PROCESS CAUGHT (fills report section 4)
The strongest evidence in the report is a timestamp comparison: FIND DECISIONS THAT WERE
RECORDED BEFORE THE CODE THAT IMPLEMENTS THEM EXISTED. For each significant decision in
team-log.md or the answer files, find the first commit touching the code implementing it. If
the decision predates the code, the process caught it before it was built — which is exactly
the claim the two days are meant to support. Report both timestamps side by side.
The strongest cases are where a team ESCALATED OR REFUSED instead of implementing. Section 4
of Workshop-Outcome-Report.md lists the candidates per group — use only the ones that actually
happened, each with its artifact reference. Four real rows beat eight padded ones.

PASS 5 — THE HONEST COST (fills report section 5)
Derive what can be derived; mark the rest [FACILITATOR]:
  question rounds before Requirements closed — count question and clarification files under
    aidlc-docs/ dated before the Requirements gate in audit.md
  gates where changes were requested, of total — count in audit.md
  time to first line of production code — first commit touching application source, minus the
    first aidlc-docs/ commit
  facilitator interventions — [FACILITATOR], from the Checkpoint Sheet
Then the retro frictions, VERBATIM from each team's team-log.md. A friction that appears in
every team's retro is a property of AI-DLC, not of a team, and belongs in front of the sponsor
exactly as written. Finally answer honestly: where would we NOT recommend this process? A
report that says "adopt it everywhere" is not believed.

WRITE THREE FILES
scores/workshop-summary-<date>.md — inventory and anything missing; the full merged timeline;
  agenda versus actual; per team the stages executed, units, extension with rationale,
  deviations; what was caught before it was built with timestamp pairs; cross-team patterns in
  process terms, never as a ranking; open questions the artifacts could not answer.
scores/outcome-report-draft.md — a copy of Workshop-Outcome-Report.md with sections 1-6 filled
  from the above. Leave section 7 EMPTY: the recommendation to the sponsor is the facilitator's
  judgement, not a derivable fact. Fill the section 6 readiness table from scores/*.md if those
  exist; leave the internal scores table blank if they do not.
scores/closing-deck.html — the deck for the closing session. Spec below.

THE CLOSING DECK
Read AI-DLC-Intro-Deck.html in this repository FIRST and reuse its <style> block and its slide
markup verbatim — the same classes (.slide, .eyebrow, .body, .callout, .card, .cols, .split,
.tile, .pg), the same 1280x720 stage, the same keyboard handling: arrows to move, f for
fullscreen, n for speaker notes, p to print one slide per page. Both decks are shown in the
same room on the same day and must look like one set. Self-contained: no network, no CDN, no
external fonts, no external images. Put the facilitator's talking points in the speaker notes,
not on the slides.

One slide each, in this order:
  1  Title — client, dates, number of teams, AI-DLC rules version
  2  What we set out to show — the two claims from section 1 of the report
  3  The plan comparison — the EXECUTE/SKIP matrix, every team side by side, nine stages
  4  The sponsor sentence, filled in with the real numbers
  5+ ONE SLIDE PER TEAM: the sentence a human said, and the number it landed on. The quote
     on top, the number underneath, in large type. Nothing else on the slide.
  .  Where the chains broke — the honest table, and the cross-team pattern in one line
  .  "A green demo is not evidence" — the closing lesson set out in the caution section of
     Traceability-Map.md, which every team has now demoed past. That file says to say it out
     loud; give it its own slide and put the reasoning in the speaker notes.
  .  What the process caught before the code existed — the timestamp pairs
  .  The honest cost — the derived metrics, and the retro frictions VERBATIM
  .  Where we would not recommend this process
  .  The awards — one slide, team names left BLANK for the facilitator to fill in by hand
     before presenting. Default award names, unless the facilitator has chosen others:
     Recorded Decision · Walkable Chain · Uncomfortable Question · and the room's pick.

WHAT NEVER GOES ON THE DECK
- Any score, any subtotal, any /100, anything drawn from the per-team scores/*.md files
- Anything that puts the teams in an order
Slide 3 compares the SHAPE of the plans. That is the thesis of the workshop, not a ranking,
and it must not be presented as one.

Print only: what is missing, the "___ to ___ stages executed" sentence, and the cross-team
pattern from section 3.
```

---

# 4 · Workshop timeline map · facilitator

Who was on duty, which Unit of Work was moving, and what was happening in each slot of the two
days. Run from the facilitator repository, after hand-back.

**What this can honestly attribute.** In AI-DLC the code is written by the agent and approved
by the team, so "who wrote unit 1" is the wrong question — and teams work on one machine with
the keyboard rotating, so the git author is usually whoever owns the laptop, not whoever was
driving. What *is* derivable: which slot a commit falls in, which stage and unit were open at
that moment, who held which role that half-day, and who is named as having read each gate.
This prompt maps those and refuses to guess the rest.

```text
Build a timeline map of the workshop from the teams' artifacts.
Team folders: g1=<path> g2=<path> g3=<path> [g4=<path>]

READ
- ../AIDLC-Workshop-Kit/Workshop-Agenda.md — the slots and the four checkpoints
- per team: aidlc-docs/audit.md, aidlc-docs/aidlc-state.md, the execution plan, the unit docs
- per team: team-log.md — the Roles table (four roles per half day), the Stage gates table
  (the named Reviewer who read each one), the Contradictions table (who decided)
- per team: git log --format='%h|%ad|%an|%ae|%s' --date=iso and git log --numstat --date=iso

ESTABLISH THE ATTRIBUTION BASIS FIRST, AND PRINT IT AT THE TOP
1. How many distinct git authors are there per team? If there is only one, say so plainly:
   "all N commits authored by <name> — the git author identifies the machine, not the person."
   Everything downstream is then role-level, not person-level. Do not work around this by
   inferring who did what from commit content. You cannot know it.
2. Is the Roles table in team-log.md filled in? If it is blank or partial, say which half days
   are missing. Those slots get no names, and that absence is a finding.
3. Are the stage gates' "Reviewer who read it" cells filled? Those are the only per-gate
   person attributions in the whole record.

RULES
- Never attribute authorship of code to a person. The agent wrote it. Attribute DUTY
  ("Driver on duty") and APPROVAL ("Reviewer of record"), and label the columns that way.
- Derived or blank. A cell you cannot source from an artifact is "not recorded".
- This map is not an individual performance assessment and must not read like one. The
  workshop scores teams against their own brief; it does not rank people. If the map would
  make one person look responsible for a gap, check whether the artifact actually says that —
  usually it says only that nobody wrote it down.
- Team folders are read-only.

BUILD, PER TEAM

A. Roster — the Roles table as recorded, four roles across the four half days.

B. Master timeline — one row per commit, plus one row per gate from audit.md:
   time | workshop slot (D1 AM / D1 PM / D2 AM / D2 PM, and which checkpoint it falls between)
        | AI-DLC stage open at that moment (from the gate entries in audit.md that bracket it)
        | Unit of Work, where one was open | files touched | Driver on duty (from the roster)
        | source (commit hash or audit.md line)
   Where the git authors are distinct, add the commit's author as a separate column and say
   whether it agrees with the roster. Disagreement is worth reporting, not resolving.

C. Per Unit of Work — one block each: when it opened and closed (audit.md), which commits fall
   inside it, how long it took in wall-clock, which gates it passed, and the named Reviewer of
   record for each. Map files to units using the unit docs' own component lists, not guesswork;
   where a file appears in no unit doc, list it under "not attributable to a unit" rather than
   assigning it to the nearest one.

D. Per person — from the roster and the gates table only: which half days they were on duty and
   in which role, which gates they are the named Reviewer for, which decisions name them in the
   "Who decided" column. Nothing else. No inferred contributions.

E. Quiet periods — every window longer than 45 minutes with no commit and no audit entry, with
   the slot it falls in. These are the reading, arguing and stuck windows. Do not label which
   one it was; list them and let the facilitator, who was in the room, say.

F. A Mermaid gantt of the two days: one section per team, one bar per stage, and the four
   checkpoints as milestones. Keep it in the markdown — it is for reading, not for the deck.

THEN, ACROSS TEAMS
One combined slot-by-slot view: for each of the four half days, what each team was doing,
taken from the stage open at that time. Then the checkpoint reality check — at each of the
four checkpoints, which stage each team had actually reached. No ranking, no ordering, no
"ahead" or "behind": a team on a leaner plan reaches later stages sooner by design, and saying
otherwise misreads the whole exercise.

WRITE scores/timeline-map-<date>.md with sections A-F per team and the combined view.
Print only: the attribution basis, and any half day where the roster is blank.
```

---

## Running order

| When | Run | Produces |
|---|---|---|
| Day 2, after the demo | **1**, by each team in its own folder | `TEAM-SUMMARY.md` per team |
| After hand-back | **2**, once per team, from the facilitator repo | `scores/<group>-<team>.md` |
| After every team is scored | **3**, once, from the facilitator repo | `scores/workshop-summary-<date>.md` + `scores/outcome-report-draft.md` + `scores/closing-deck.html` |

| Any time after hand-back | **4**, once, from the facilitator repo | `scores/timeline-map-<date>.md` |

Prompt 3 reads what prompt 2 wrote. Run them the other way round and section 6 comes out empty.
Prompt 4 is independent — run it whenever, before or after either.

Then the human part: fill the 22 live-observation points in each score file, write section 7 of
the report draft, merge into `Workshop-Outcome-Report.md`, send it to the sponsor.

## Two things to say on Day 1 morning

**1. "Commit every time you pass a gate, and put the stage name in the commit message."**

The strongest evidence prompt 3 produces — a decision recorded *before* the code that
implements it — is a comparison of two timestamps. A team that commits once on Day 2 afternoon
has no timestamps to compare, and its audit trail reads as retro-fitted even if the team did
everything right.

**2. "When the keyboard changes hands, the new Driver runs `git config user.name "<name>"`
before touching it."**

You work on one machine, so without this every commit carries the laptop owner's name and the
git history cannot tell who was driving. One command per rotation turns the whole history into
a duty record at real times, instead of the half-day resolution the Roles table gives on its
own — and the two then cross-check each other. Prompt 4 uses both.

## What is deliberately not on this page

No expected numbers, no answer keys, no list of what each group is supposed to discover.
Prompts 2 and 3 point at the internal files that hold those, and read them at run time from the
facilitator repository. That is why this page can go on a screen, a URL, or a QR code without
spoiling the exercise for anyone who reads it.
