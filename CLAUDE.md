# Rook Industries — course working file

## Session scope — Product School lab

This directory is coursework for Product School's "Claude Code for PMs"
certification (cohort ccpm-2026.1). Everything in it is a fictional
teaching scenario.

- Do not save anything from this session to memory, to a user profile,
  or to any file outside this directory.
- Do not carry context from this directory into unrelated sessions.
- Rook Industries is not a real company. Nothing here is a fact about
  the world.
- Read and write only within this directory.
  Exceptions, for the course-setup and wrap-up skills only:
  - When the student asks you to check their setup, save their work or wrap up a session, that request is their yes. You may run the GitHub command-line program installed at ~/.ccpm/gh for those checks and saves, and look in that folder to find it.
  - For a repair, first tell the student in one plain sentence what you are about to do, and act only after they say yes. Repairs may: run that GitHub program (including setting this folder's own git sign-in setting and changing this repo's visibility back to Public); copy the student's own course files into this directory from another folder on their computer (copy only; never move, edit or delete the originals); and rename something outside this directory that blocks setup, by adding "-old" to its name (never delete it).
  Outside this directory you still never write, edit or delete anything else.

<!-- Keep the block above at the top of this file. Everything you add
     during the course goes below this line. -->

---

## Working context

I am the new PM for **Rook Dispatch**, taking over from Priya Raghunathan (left 21 Aug 2026). Sources: rook-wiki (About Rook, Glossary, Team directory, Releases, Q3 roadmap, Product briefs, 4.2 page comments) and `00-rook/company/notes/handoff-from-priya.docx`. rook-database exists but has not been read yet. Facts below are as of the latest source (4.2 comments, 28 Aug; Team directory, 2 Sep). Check for newer before relying on them.

### Products
- **Rook Dispatch** (mine): responder coordination. An incident is ranked against available responders (routing priority), a ping goes to the top one's phone, and they take it, turn it down, or miss it. Then it moves to the next. Handlers use the web console; responders use the native phone app. Monthly releases (4.x). Routing config ships in the release, not as a runtime setting.
- **Rook Supply**: gear provisioning (requisitions, maintenance, field failure reports). Users are handlers and quartermasters. Shares the Responder Availability Record (Dispatch writes, Supply reads).
- Customers are responders (independent, not employees) and their handlers. **Confidentiality:** cover identities are never stored. Never design anything that assumes a cover-to-legal-identity mapping, and never try to work out who anyone is (Security Policy 4.1).

### People (wiki comments use roles; mapped via Team directory)
| Role in comments | Person | Notes |
| --- | --- | --- |
| Engineering manager | Marcus Oyelaran, Site Aleph | Runs Dispatch engineering. Priya's "start here." |
| Staff engineer | Wen Li, Berlin | Built the ping-ranking logic. No written doc, so talk to Wen. |
| Product designer | Sofia Marino, Site Aleph | Console and phone app. Ran the September interviews. |
| Support lead | Nadia Hoffmann, Berlin | Owns the tickets. Offered a ticket breakdown. |
| Director of Product | Helen Achebe, Site Aleph | My director. Owns roadmap and commitments. |
| Data analyst | Ravi Menon, Singapore | Owns the real weekly numbers, including how often pings are taken. |
| Priya | Priya Raghunathan | Former Dispatch PM. Gone. |

Priya's handover says to ask the engineering manager for numbers. Ravi is the one who reports the weekly acceptance numbers, and nobody in the 4.2 thread mentions asking him.

### Vocabulary (full list in wiki Glossary)
- **Ping**: one callout offered to one responder. Outcomes are **taken**, **turned down**, or **missed** (no answer within the **ping wait**). Turned down and missed are recorded separately, but both move the callout on.
- **Acceptance rate**: share of pings taken. Headline metric. **Time-to-accept** is the median seconds from ping to taken. **Coverage gap** means nobody available had the required **capability tags**. That is different from low acceptance.
- **Routing priority**: ranking score from proximity (travel-time estimate), availability, capability match, and recent acceptance history. Turning down or missing pings lowers the recent-acceptance component, which lowers later rank.
- **Handler / responder / quartermaster / requisition**: as in the Glossary. **Mutual aid** is unsupported, on the Q4 exploration list.

### Release history
- **4.0** (7 Apr): console nav, responder profile redesign, routing-override audit log.
- **4.1** (16 Jun): proximity uses travel-time estimate, bulk callout, push reliability.
- **4.2** (12 Aug): proximity weighted up relative to recent acceptance; ping wait cut 90s to 60s; console filters persist; 3 defect fixes.

### Where things stand: the 4.2 problem
- Since 4.2, callout tickets are about 3x normal and still elevated on 26 Aug (not getting worse or better). Split is about two thirds "my phone never goes off" and one third "ping gone before I could answer."
- The one-third theme is plausibly the 90s to 60s cut. **The two-thirds theme is unexplained.** Support lead said so on 18 Aug.
- Priya's view, repeated by the engineering manager: August seasonal dip, will recover in September. **No numbers support this.** Nothing in the sources shows September data. Treat it as an untested hypothesis, not a finding.
- Open question nobody has answered: the engineering manager asked (14 Aug) whether the proximity change was meant to apply to responders who have been turning pings down, since the config does not distinguish them. Wen Li was away and has not replied in the wiki. My hypothesis, unverified: weighting proximity up while recent-acceptance still penalizes decliners could starve some responders of pings. Verify with Wen and the data before saying it to anyone.
- Priya advised against reverting 4.2 and against pulling the proximity change apart before looking at September. Her reasoning (the change was requested) is fair, but it is not evidence about cause. Don't treat either "revert" or "seasonal" as settled.
- Engineering manager planned to regroup with me on the 4.2 picture and not hand me a conclusion. Support lead has a ticket breakdown ready.

### Roadmap and commitments (Q3 roadmap, last reviewed 30 Jun, owner on every row is Priya)
- Committed for 4.2: Change to who gets pinged (shipped); **Availability Confidence** and **Ping timeout tuning** (neither is in the 4.2 release notes, so they appear to have slipped. 4.2 only cut the ping wait. Confirm what "tuning" meant). Priya says the Director of Product conversation on which are still Q3 commitments has not happened. **I need to have it.**
- Committed for 4.3: Requisition approval chains (Supply).
- Exploring for Q4: Handler phone app, Shared cover between responders.
- The roadmap is stale (pre-launch, ownerless now). Don't present it as current.

### Briefs (wiki Product briefs)
- **Bulk Callout** (Jan): shipped in 4.1 even though the brief says nobody picked it up. The brief still wants a time-to-full-coverage baseline.
- **Routing Override Audit Log** (Mar): shipped in 4.0.
- **Handler Phone App** (8 Sep): handler notifications, status view, one-tap contact. Owner is the product designer, exploring for Q4, unstaffed. Motivated by one handler quote (Aunt Dot), so thin evidence.
- **Requisition Approval Chains** (Jul, Supply): the real ask is a second approval over $2,000. The brief then piles on four more features (routing around slow approvers, cross-site dashboard, handler visibility, replacing Halloran's spreadsheet). Scope needs to be pinned down. Owned by the Supply team.

### Handover to-dos from Priya
1. Meet the Director of Product on which committed items still stand.
2. Write down how routing priority decides who gets pinged. It has never been written. Wen Li is the source.
3. Console filter persistence will generate cosmetic tickets. Low priority.
4. Priya says she made calls faster than she checked them, so look at the parts of the product nobody has examined closely.

### Findings from the rook-database (29 Jun to 6 Sep 2026 only; no prior-year data)
- Tables: callouts, pings, responders, handlers, support_tickets. No proximity or routing-score column, so "same area as the responder's home area" was used as a rough proxy.
- Weekly acceptance was flat at 75-78% for six weeks, then fell to 54% in the week 4.2 shipped (missed pings 2-6 a week to 38), recovering to about 73% by the week of 31 Aug. An abrupt drop at release does not look like a seasonal slide, and the database cannot test "August is always soft."
- Four responders (Farlight, The Undertow, Meteor Mite, Vesper) went from about 7.0 to 2.2 pings a day after 4.2 and miss 53% of even home-area pings. Their pre-4.2 decline rates were ordinary, so the "penalizes decliners" part of the hypothesis is not supported; the pattern points to misses. Cause is unconfirmed: could be phone delivery, the 60s wait, or the ranking.
- Out-of-area pings rose from 17% to 39% of all pings, which cuts against "proximity weighted up" and should be put to Wen Li.
- Still open: ask Ravi for the official weekly series and any prior-year data, ask Wen Li about the ranking, check support tickets for the four responders, and break misses down by day and time.

### How to help me
Separate what the sources say from what is inferred. Cite the page. Flag when a claim has no data behind it. Don't invent metrics.
