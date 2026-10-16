# 05 · Super Speed — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. You've spent three sessions finding out what went
wrong: the two piles of feedback that didn't agree, the numbers that
hid four people inside an average, and the code that settled it —
the shorter timeout is what did it.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.

Use rook-wiki for the Glossary, the Team directory, and the comments on the 4.2 release (people are named by role; the Team directory maps roles to names). Also read the Word doc 00-rook/company/notes/handoff-from-priya.docx. Then read 05-super-speed/director-request.txt. That's the note our Director of Product sent me this morning, and it's what I need to answer. We already know the problem: once somebody's gone quiet, the only thing that brings them back is being asked, and being quiet is exactly what stops them being asked. Draft me a one-page brief for what we'd build instead. Tell me who it's for (most impact is for the responders but will be a nice to have fix for the handlers), what changes for that person (i believe we want misses and turn downs to be treated differently, misses shouldnt be penalized, also maybe extent the wait time again maybe like 75 s), and what it deliberately doesn't do. Do not build a prototype. If you have questions regarding what we'd like in the brief ask them here before drafting the brief.

### 2.

Can we give everyone a one-tank rank restore? I think that makes the most sense. Remind me what the current weights are?

### 3.

lets also change the routing weights proximity to .6 and recent acceptance to .35

### 4.

write now each possible root cause, one or two words on what our data shows on if its the reason for quiet and then a column for if this update will help?

### 5.

do i have any blind spots in this brief youd recommend i consider

### 6.

no lets address them what would you prpose in stead

### 7.

in line hear, give me the brie as your one-line pitch for the feature, the sentence you'd say to the person it happens to, not the sentence you'd say in a planning meeting.

### 8.

Take the brief you just wrote and build me a working prototype, an actual screen I can click through, not a description of one. Save it as 05-super-speed/prototype.html, a single file I can just open in my browser. Show me where this would actually happen, and make at least one thing on it respond when I click it.

### 9.

can you add a screen for the live alert on a lock screen and put that in the flow like a push notification to their phone then they open it up. i also want a side by side to ahve the handler console also an app experience. im now second guessing the cant go right now it seems like itd be a turn down? perhaps it shoudl like skip them for now but they stay in the queue as needed. ask clarifying questions before building again

### 10.

can you add little avatar circles on the responder cards for the handler app

### 11.

i want them superhero avatars like cartoon-y

### 12.

yes add them to web console
