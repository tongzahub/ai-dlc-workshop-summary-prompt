# AI-DLC Workshop — Prompt Pack

Three prompts, one file. Copy the one you need and paste it into your terminal.

| | Prompt | Who runs it | Where |
|---|---|---|---|
| 1 | **Two days, in your own record** | every team, any group | the team's own group folder |
| 2 | **Score one team** | facilitator only | the facilitator repository |
| 3 | **Reconstruct the two days** | facilitator only | the facilitator repository |
| 4 | **Workshop timeline map** | facilitator only | the facilitator repository |
| 5 | **Closing run** — the one you run on the day | facilitator only | the facilitator repository |

Prompts 2, 3, 4 and 5 read internal files — the rubric, the answer sheet — that are **not published
here**. Pasting them anywhere else produces nothing useful. Nothing on this page reveals what
those files contain, which is why this page can be handed out.

---

# 1 · Two days, in your own record

**Any group.** The recap you show at the close. It reads what your team left behind — the
AI-DLC audit trail, your git history, your decision log — and writes `TEAM-SUMMARY.html` in
your folder: a self-contained presentation **in Thai** that you open by double-clicking it,
with no internet. Two acts — **เราทำอะไรไปบ้าง**, then **เราได้อะไรบ้าง**.

**It runs nothing.** No services, no tests, no checks, no Docker. Shut everything down
whenever you like; this only reads files.

**When:** Day 2, after your demo, before the retro. Not earlier.
**Where:** a **fresh** session opened at your group folder — the one holding `aidlc-docs/`,
`team-log.md` and your `.git`. Same folder you have worked in all along, new session.

> **Why a fresh session matters.** Pasted into the session that ran your workflow, the
> assistant will answer from what it remembers of the conversation instead of reading what
> was actually written down — and a summary of the chat is not a record of the artifacts. A
> fresh session has to open the files, which is the whole point.

You do not need to say which group you are. It works that out from your folder.

> **Copying it:** use the copy button at the top right of the block below. One click takes
> exactly this prompt and nothing else.

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
- AI-DLC-Cheat-Sheet.md, if it is in this folder or the one above it — for the explainer
  slides. If it is not there, use the essentials written into the slide list below.

RULES
- Run nothing. Do not start our service, do not run our tests, do not run any check, do not
  touch Docker. This is a read of what is already written down.
- Facts only. Every statement cites the file or the commit it came from.
- If something is not recorded anywhere, write "not recorded". Do not reconstruct it from
  what probably happened, and do not fill a gap with a plausible guess.
- Quote our own words when the wording matters — a recorded rationale, a retro friction.
- Do not score us, grade us, or judge the quality of anything. This is a record.
- Do not open traceability-worksheet.md and do not write anything into it. That is our work.
- Do not compare us to any other team.

WRITE TEAM-SUMMARY.html IN THIS FOLDER — A SELF-CONTAINED RECAP PRESENTATION IN THAI.
This is what a team shows at the close of a two-day workshop. It answers two questions, in
this order: **เราทำอะไรไปบ้าง** and then **เราได้อะไรบ้าง**. Build the content first, then the
deck to the spec at the end.

ACT 1 — เราทำอะไรไปบ้าง

1. What we built — three sentences. The system, who it is for, what it does now that works.

2. How we worked — AI-DLC in one slide. Context for everything that follows, not a lecture:
   the agent proposes and the human approves; every stage ends at a gate and nothing advances
   until a person approves it; Workflow Planning decides EXECUTE or SKIP per stage, which is
   why teams under the same rules end up with different plans; the agent's questions go into
   files with an [Answer]: tag and are answered there, not in chat; three extensions
   (Security, Resiliency, Property-Based Testing) are decided at Requirements Analysis with
   the reason recorded either way. Use AI-DLC-Cheat-Sheet.md if you found it. Keep it to what
   the room needs to follow the next slide.

3. The path our team took — the nine stages (Workspace Detection, Reverse Engineering,
   Requirements Analysis, User Stories, Workflow Planning, Application Design, Units
   Generation, Construction, Build and Test) with EXECUTE or SKIP for each, and the reason
   recorded for each SKIP. Where no reason was recorded, write "ไม่ได้บันทึกเหตุผลไว้". Then how
   many stages we executed and how many Units of Work we produced.

4. Our extension decision — which we took, which we declined, and the rationale we recorded,
   quoted. A decline with no recorded reason counts as no reason.

5. The two days, hour by hour — one merged timeline from audit.md entries and git commit
   timestamps. Columns: time, what happened, source. Include every gate. Mark any gate where
   we requested changes rather than continuing.

6. The questions the workflow asked us, and how we answered — one row per [Answer]: tag.
   Columns: the question in short, our answer in short, and where our answer came from if we
   recorded a source (a stakeholder, a document, a quoted sentence).

7. Decisions we made, and why — from team-log.md and our answer files. Columns: the decision,
   the reason we recorded, when.

8. Where we changed our minds — every mid-workflow change in the audit trail, every gate we
   sent back for changes, every decision we revisited. What changed and why.

ACT 2 — เราได้อะไรบ้าง

This act is an INVENTORY, not a claim. Count and quote what exists. Do not assert value the
artifacts do not show, do not write anything that sounds like marketing, and do not congratulate
us. A section with nothing behind it gets one honest line and moves on — that is a result too.

9. What we have now that we did not have two days ago — count it. How many files under
   aidlc-docs/ and what they are; how many commits, over how many hours; the service and its
   endpoints; the tests and what they assert; the screen; how many decisions are in
   team-log.md; how many gates were passed.

10. What the process caught before it was built — decisions recorded BEFORE the code that
    implements them existed. For each, put both timestamps side by side: when the decision
    was written down, and the first commit touching the code that carries it out. Find as
    many as the record supports. This is the strongest thing in the deck; if there are none,
    say so plainly rather than reaching.

11. Contradictions that got settled on record — what disagreed with what, how we settled it,
    who decided, and where it is written down.

12. What we deliberately did not build — scope parked with a recorded reason rather than
    silently built or silently dropped, and where that decision lives.

13. The honest cost — first commit to last, how many rounds of questions before Requirements
    closed, how many gates we sent back for changes, any hand edit we declared, and anything
    left unfinished.

14. Frictions, in our own words — verbatim from our retro. Do not smooth them, do not
    translate them, do not merge two into one.

15. What we would take to a real project — only if we recorded it. If we did not, write
    "ยังไม่ได้บันทึกไว้" and let that be the last honest line of the deck.

Let the material decide the length. A section with a lot recorded gets more than one slide; a
section with nothing recorded gets one line saying so and moves on. Do not pad to a target,
and do not squeeze to one either — a thin slide is the finding, and padding hides it.

THE DECK — TEAM-SUMMARY.html

LANGUAGE — THAI
Write every heading, label, caption and sentence of your own in Thai.
Quoted material is never translated. A stakeholder's sentence, a rationale we recorded, a
retro friction, a file name, a command, a commit message — all stay exactly as they were
written, in whatever language that was. Translating a quote breaks the one rule this whole
record rests on. Where a Thai caption introduces an English quote, that is correct.

NOTHING MAY BE CUT OFF — THIS IS THE RULE THAT MATTERS MOST
A slide never clips its content and never hides it behind an invisible scroll.
- If a section does not fit on one slide, continue it on the next and title them
  "… (1/3)", "… (2/3)", "… (3/3)". Splitting is always the right answer.
- Split a long table by rows across several slides, repeating the header row on each.
- A long quote gets a slide of its own.
- Shrink type only down to a floor of about 18px on the 1280x720 stage. Below that, split
  instead of shrinking. Never shrink to make something fit.
- Only as a last resort may a content block scroll — and then it must have a visible
  scrollbar and a "เลื่อนดูต่อ ↓" hint underneath, so nobody can miss that there is more.
Before you finish, walk every slide and check: is any content outside the stage, or sitting
under a hidden overflow? If so, split it.

MECHANICS
- One file. No network, no CDN, no external fonts or images, no build step. It must open by
  double-clicking on a laptop with no internet.
- A fixed 1280x720 stage, centred and scaled to fit the window, one slide visible at a time.
- Arrow keys and click to move; f for fullscreen; p to print one slide per page. Show the
  slide number and the total in a corner.
- Fonts: "Leelawadee UI","Noto Sans Thai","Sarabun",Tahoma,sans-serif — system fonts only,
  nothing downloaded. Thai needs room: line-height 1.6 or more, and never letter-space Thai.
- Light background, dark text, one accent colour, generous type — readable from the back of a
  room on a projector.

SLIDES, IN ORDER
1  Title — our team name, the system we built, our group, the two dates. Under it, one line
   of real numbers taken from the sections: "สองวัน · รัน __ จาก 9 stage · __ unit of work ·
   __ commit · __ การตัดสินใจที่บันทึกไว้".
2  "สองวันนี้เราทำอะไร" — the recap in five lines. It works as the contents page for what
   follows, so someone who reads only this slide still knows what happened.
3+ Act 1, items 1 to 8, in order, across as many slides as each needs.
.  A divider slide: "เราได้อะไรบ้าง".
.  Act 2, items 9 to 15, in order.
.  Last slide: the single line from item 15, on its own.

Put nothing on a slide that does not come from the sections above.
```

### What you get

`TEAM-SUMMARY.html` — a Thai-language recap of your two days, built only from your own
artifacts, as long as the material warrants and no longer. Double-click to open it; no
internet, no PowerPoint. It goes back with your folder, and it is the fastest way to brief
someone who was not in the room.

Act 2 is the half worth reading twice. **เราได้อะไรบ้าง** is not a list of achievements — it is
an inventory: what exists now that did not exist on Monday, and which decisions were written
down *before* the code that carries them out, with both timestamps next to each other. That
pair of timestamps is the hardest thing to argue with, and it is the closest thing you have to
proof that the process did something a normal sprint would not.

It is also the honest test of whether you worked the way the workflow asked. A team that
answered in files, recorded the why, and committed as it went gets a recap with substance in
every section. A team that did not gets a lot of "ไม่ได้บันทึกไว้" — which is worth knowing
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

**It starts nothing and runs nothing** — no Docker, no test suite, no acceptance check.
Everything below is a read.

That splits the 100 points three ways. **68 can be verified by reading the repository.**
**10** — 2.2, the answer key — depend on whether the team committed any output of their own
check; usually they did not, and the point lands with the facilitator, who watched the number
on the screen. The last **22** are the live demo, the backwards walk performed out loud, and
the parts about what you saw someone do. This prompt never invents any of the three.

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

PASS 3 — WORKING SOFTWARE — FROM THE RECORD, NOT FROM A TEST RUN
Do not start any service. Do not run any test suite or acceptance check. Read what is in the
repository, and say plainly how strong that evidence is.
2.2 answer key reproduced (max 10, RARELY IN THE REPOSITORY). Nothing in this pack runs the
    check, so the only evidence is whatever the team happened to commit: a check output, a
    test log, a result recorded in team-log.md or on their own slides. Find it, score from it,
    and label the row "team-reported, not verified". If there is none — which is the usual
    case — score 0 with "no output recorded" and leave it to the facilitator, who saw the
    number on the screen at Checkpoint 4 and at the demo. That is their call, not yours.
    THEN the anti-false-pass READ. Traceability-Map.md's caution section names the loops a
    wrong implementation can pass and what to look for instead. Inspect the implementation
    statically for exactly that. If the team reports a pass while the code shows the pattern
    the caution describes, that goes at the TOP of the sheet — worded as SUSPECTED, pointing
    at the file and line. It is the most valuable thing this pass produces, and the
    facilitator settles it with one question rather than a test run.
2.3 tests assert what was at risk, and the screen is thin (max 5, verifiable by reading). Read
    the test files: do they assert the behaviour that was actually at risk, or only that the
    code runs? Then read the screen's code: does it call the API, or recompute the number
    itself? A screen that recomputes scores 0 here regardless of how it looks — the number on
    it is no longer evidence about the service. Neither check needs execution.
2.4 brownfield only (max 3, verifiable by reading). git log and git diff the pre-existing test
    files. Were they modified? Report the diff. For a greenfield group mark N/A and remove 3
    from both the max and the total — do not award the points by default.

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
  ## Headline — one sentence. A suspected anti-false-pass finding goes here.
  ## Verified by reading — <X> / 68   (table: item, max, score, evidence file:line)
  ## Team-reported, not verified — 2.2 answer key, <X> / 10, source <file:line>
     Quote the output the team recorded, verbatim. If there is none, say so.
  ## Needs the facilitator — 22 points not in the repository
     2.1 acceptance scenario demoed live, on the screen  12  ___
     4.1 walked one number backwards, live                4  ___
     1.1 Reviewer read before approving                   2  ___
     1.2 answers given in chat                            2  ___
     1.6 hand edits seen in the room                      2  ___
  ## Three things this team did that a real project would want
  ## Three things that would bite them on a real project
  ## One sentence for the team
  ## One thing they should take back

Do not compute a /100 total. The facilitator adds the 22, confirms the 10, and does that per
team, against that team's own brief — and does not publish it.
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

WRITE TWO FILES
scores/workshop-summary-<date>.md — inventory and anything missing; the full merged timeline;
  agenda versus actual; per team the stages executed, units, extension with rationale,
  deviations; what was caught before it was built with timestamp pairs; cross-team patterns in
  process terms, never as a ranking; open questions the artifacts could not answer.
scores/outcome-report-draft.md — a copy of Workshop-Outcome-Report.md with sections 1-6 filled
  from the above. Leave section 7 EMPTY: the recommendation to the sponsor is the facilitator's
  judgement, not a derivable fact. Fill the section 6 readiness table from scores/*.md if those
  exist; leave the internal scores table blank if they do not.

The closing deck is not built here — prompt 5 owns it, and by the time you run this it has
already been presented. If the deck needs regenerating with fuller data, re-run prompt 5.

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

# 5 · Closing run · facilitator · **this is the one you run on the day**

One paste, one machine, every team, before the workshop closes. It produces the closing deck
and the crib sheet you hold while presenting it.

**When:** while the demos are running. Teams finish their work at Checkpoint 4, so collect the
folders then and start this — the deck is ready for the comparison slot without you leaving
the room.

**What it deliberately does not do:** it does not score anyone — scoring needs live
observation you do not have before the close. Like every other prompt in this pack, it starts
no services and runs no tests; it reads artifacts. Prompts 2, 3 and 4 do the rest afterwards,
and nothing here has to be redone.

```text
Build the closing session material from every team's artifacts.
Team folders: g1=<path> g2=<path> g3=<path> [g4=<path>]

THIS IS THE FAST RUN — artifacts only. Do not start any service, do not run any test suite,
do not score anyone. Budget twenty minutes. If something is missing, note it and move on
rather than hunting for it.

READ, FROM THIS REPOSITORY
- Traceability-Map.md — to check each team's demoed chain is real, and its caution section
- AI-DLC-Intro-Deck.html — you will reuse its styles and slide markup
- ../AIDLC-Workshop-Kit/Workshop-Agenda.md
PER TEAM, READ-ONLY
- aidlc-docs/audit.md, aidlc-docs/aidlc-state.md, the execution plan, the unit docs
- team-log.md and traceability-worksheet.md
- git log --format='%h|%ad|%s' --date=iso

RULES
- Never rank the teams. The only cross-team comparison is the SHAPE of the execution plans.
  Do not order teams by stage count, commit count, or anything else.
- Derived or blank. A cell you cannot source is "not recorded", and say so on the crib sheet
  so you are not caught out on stage.
- Retro frictions go in VERBATIM. Do not smooth, translate, or merge them.
- Only the groups that actually ran get a column or a slide.

EXTRACT PER TEAM — this is the whole list
1. EXECUTE or SKIP for each of the nine stages; the count; the number of Units of Work
2. The extension decision, with the recorded rationale QUOTED
3. The loop they demoed: the sentence a human said, and the number it landed on. Check it
   against Traceability-Map.md — is it one of the 18, is it real, is it one of the easy ones
4. Where their chain broke, in their own words from traceability-worksheet.md
5. ONE decision recorded before the code that implements it existed, with both timestamps —
   the decision in team-log.md or an answer file, and the first commit touching that code
6. Their retro frictions, verbatim
7. How many gates they sent back for changes, out of the total

THEN, ACROSS TEAMS
- the sponsor sentence with real numbers: "N teams, one methodology, ___ to ___ stages
  executed. Nobody configured that difference." If the numbers are identical across teams,
  say that plainly instead — it would mean the workflow did not adapt, and it is the most
  important sentence of the day.
- the pattern in the broken chains, in one line
- whether the same friction appears in every team's retro

WRITE scores/closing-deck.html
Read AI-DLC-Intro-Deck.html FIRST and reuse its <style> block and slide markup verbatim — the
same classes (.slide, .eyebrow, .body, .callout, .card, .cols, .split, .tile, .pg), the same
1280x720 stage, the same keys: arrows to move, f fullscreen, n speaker notes, p print. Both
decks are shown in the same room on the same day and must look like one set. Self-contained:
no network, no CDN, no external fonts or images. Talking points go in the speaker notes, not
on the slides.
Slides, in order:
  1  Title — client, dates, number of teams, AI-DLC rules version
  2  What we set out to show — one methodology, N engagements, N execution plans; and every
     behaviour traceable to a sentence someone said
  3  The plan comparison — the EXECUTE/SKIP matrix, every team side by side, nine stages
  4  The sponsor sentence, filled in
  5+ ONE SLIDE PER TEAM: the quote on top, the number underneath, large. Nothing else.
  .  Where the chains broke — the honest table, and the pattern in one line
  .  "A green demo is not evidence" — the closing lesson set out in the caution section of
     Traceability-Map.md. That file says to say it out loud; give it a slide of its own and
     put the reasoning in the speaker notes.
  .  What the process caught before the code existed — the timestamp pairs
  .  The retro frictions, verbatim
  .  The awards — team names left BLANK to fill in by hand. Default names, unless the
     facilitator has chosen others: Recorded Decision, Walkable Chain, Uncomfortable
     Question, and the room's pick.
NEVER ON THE DECK: any score, any subtotal, any /100, anything that puts the teams in an
order. Slide 3 compares plan SHAPE — the thesis, not a ranking.

WRITE scores/closing-crib.md
One page to hold while presenting. Per slide: the number or quote that is on it, and the one
sentence to say. Then a short list of what was missing from the artifacts, so nothing on the
deck surprises you in front of the room.

Print the "___ to ___ stages" sentence and anything that was missing.
```

---

## Running order

**On the day**

| When | Run | Produces |
|---|---|---|
| Day 2, after the demo | **1**, by each team in its own folder | `TEAM-SUMMARY.html` per team |
| Day 2, during the demos | **5**, once, from the facilitator repo | `scores/closing-deck.html` + `scores/closing-crib.md` |

Prompt 5 is the only one that has to finish before the room empties. It reads artifacts only,
so collect the folders at Checkpoint 4 and start it as the first team begins demoing.

**Afterwards, at your desk**

| When | Run | Produces |
|---|---|---|
| After hand-back | **2**, once per team | `scores/<group>-<team>.md` |
| After every team is scored | **3**, once | `scores/workshop-summary-<date>.md` + `scores/outcome-report-draft.md` |
| Any time after hand-back | **4**, once | `scores/timeline-map-<date>.md` |

Prompt 3 reads what prompt 2 wrote. Run them the other way round and section 6 comes out empty.
Prompt 4 is independent — run it whenever.

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
