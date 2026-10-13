# Dispatch 4.2: vanishing pings and uneven workload

Draft for the Marcus Oyelaran and Helen Achebe conversations. Sources: Customer interviews database (4 handler calls, 2-5 Sep 2026) and rook-database (29 Jun to 6 Sep 2026). Pre-4.2 = 29 Jun to 11 Aug; post-4.2 = 12 Aug to 6 Sep.

## What we know (in the sources)

**1. Pings are missed far more often since 4.2.**
- Missed pings rose from about 2% to about 13% for responders outside the four starved ones below. All five interviewed responders (Kip handles two) show a higher miss rate.
- Callouts with at least one missed ping: 3% before, 23% after. Callouts needing a second or later ping: 22% before, 33% after. Pings per callout: 1.23 to 1.39.
- Handlers describe it as: "He loses it more than he wins it" (Dot, Vesper's handler); "a slower-arriving response of his still landed him the job more often than not, and lately that doesn't seem to hold" (Ambrose, Captain Vantage's handler).

**2. Four responders have nearly dropped out of ping rotation.**
- Farlight, The Undertow, Meteor Mite and Vesper got a steady 48-50 pings a week for six weeks. Then 43, 16, 6 and 3 across the weeks of 10 Aug to 31 Aug. They now miss 53-64% of pings; before 4.2 they missed 1-4%.
- Over the same weeks, everyone else's pings rose from about 123 to 162 a week. The Gale (Eastgate) went from 1.9 to 2.7 pings a day while Meteor Mite (also Eastgate) went from 1.6 to 0.5.
- Kip, handler for both: "Meteor Mite's been texting me all week asking if something's broken because it's so quiet... And The Gale hasn't stopped."

## What we infer (not shown directly)

- The 90s to 60s ping wait explains the general rise in misses. The timing fits, but there is no response-time column to test it.
- The slide for the four is a feedback loop: misses lower the recent-acceptance part of routing priority (Glossary), which lowers rank and so gives fewer pings. The week-by-week fall fits this. We can't see ranking scores.
- This replaces my earlier idea that they were starved for turning pings down. Their pre-4.2 decline rates were ordinary.

## What we can't see

- Why these four miss about 55-64% of pings while others miss about 13%. Phone delivery, device or app issues, response time and ranking are all open. Misses are not concentrated at any hour (64% day, 50% evening for the four).
- Whether the "August seasonal dip" idea holds. The database has no prior-year data, and the drop starts in the release week.
- Anything after 6 Sep, and the cause behind either theme.
- Timing in the interviews is loose ("lately", "sometime in August"). None mention 4.2 by name.

## Questions to take into the conversations

- **Wen Li:** does a miss lower recent acceptance as much as a decline? Is there a floor, or can a responder rank low enough to stop being pinged?
- **Ravi Menon:** time-to-respond per ping, the official weekly series, any prior-year data, and phone or app delivery logs for the four.
- **Nadia Hoffmann:** her ticket breakdown, and tickets from the four responders.
- **Marcus:** the 14 Aug proximity question, and whether the 60s wait and the ranking change can be tested separately.
- **Helen:** which Q3 commitments still stand (Availability Confidence, Ping timeout tuning), given what 4.2 shipped.

Set aside for now (UI comments, not tied to 4.2): text size, dark mode, alert sounds, filter reset warning, tag legend, Halloran's Supply complaints.
