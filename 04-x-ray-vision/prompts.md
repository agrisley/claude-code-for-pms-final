# 04 · X-Ray Vision — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. Last session the numbers showed you what happened: a
ping used to wait ninety seconds and now it waits sixty, people
missed pings they used to catch, and missing one counts the same as
turning one down — so four responders stopped hearing from us
altogether.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.

How are we estimating travel time?

### 2.

Is anything else different about the code besides this "Proximity went from 0.45 to 0.60, and recent acceptance went from 0.40 to 0.25."?

### 3.

would you say this is accurate based on the code "Based on what I found, the reason some responders are getting no pings at all is declining and misses are penalized the same.

### 4.

Prior to 4.2 could responders get 'points' back on their ranking?

### 5.

Are there any engineering comments in the codebase worth evaluating further

### 6.

The pings table on rook-database has last session's numbers. Read that alongside this code. Does it back up what I found in Lab A (hypothesis pasted below)? And does that answer the engineering manager's question above?

The code treats a miss like a decline, with no fade and no recovery except by taking a callout. With the 4.2 timeout cut producing more misses, that could drag some responders’ scores down. But the weights suggest rank alone shouldn’t remove them, so something else is probably involved, such as phone delivery, availability, or a part of the ranking we haven’t seen.

### 7.

oh sorry this was the question if that wasnt clear "Engineering managerAug 14, 2:47 PM
Quick one, did the change to who gets asked first apply to responders who'd already been turning jobs down, or just new ones? Can't tell from the code and don't want to guess on this. Anyone know?"

### 8.

who is the egineering manager? marcus?

### 9.

in plain english, explain to me why haveier decliner didnt lost pings the most after the 4.2 release? wouldnt that have driven them down more with the ranking strategy?

### 10.

draft a reply to the eng mgr

### 11.

One sentence

### 12.

Find me the part of this code that takes points off somebody when they miss a ping or turn one down. Show it to me and explain it in plain English. Then find me every single thing in this code that puts points back on.

### 13.

Somebody has been quiet for a month. Walk me through, step by step, exactly what would have to happen for them to start getting work again.

### 14.

Given proximity is highest chunk, is there a way for a user trying to build up their ranking to know where the best place to be is?

### 15.

According to my findings in the code, for someone who's gone quiet, they would need to not miss any callouts and accept every call out they get their rank back up

### 16.

rewrite with your recc
