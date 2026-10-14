# 03 · Rewind — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly.

Last session you read four conversations and every support ticket
since 4.2 — and found the two piles did not agree.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.

Let's break this down by responder and by time of day. Show me visually over tables. The graphics can be simple. It'd also like to include a rate of turned down

### 2.

What columns/data points are available in the data set that we havent yet looked at?

### 3.

Yes dive into whether misses and out of area pings. Also i want to know about the happened at, to dig into the 90 to 60s  change. ask me 1-3 clarifying questions before moving forward

### 4.

open question on missed-last-ping callouts

### 5.

So based on this data exlcusively is it accurate to say to this question "what release 4.2 actually did to responders, what's the one number you'd put in front of her?" the 4.2 release increased missed pings from 3 to 23 (help me turn this into a relative proportion across either the same time frame or a proportion that is comparable). These misses focused on three responsders (Stomwrack, Ironvale and The Undertow) potentially due to shorter response time of 60s, the unintended consequence making these rank lower.

### 6.

Compare the support_tickets table on rook-database against the pings table. Where do they agree or disagree with each other? When did people start writing in, and when do the numbers actually move?

### 7.

Yes lets dig into that open text to see what we might be missing. Theme ticket text and replies where possible and align it to repsonder/handler dispatch data.

### 8.

Can you make a visual for each responder on number of tickets, pings, missed pings, tickets on their behalf . i want to see about this claim There may be two mechanisms: the phone buzzes but the ping expires (the 60s wait, or expiring mid-swipe), and the phone doesn’t ring at all. Different fixes would apply. ask clarifying questions if needed before building.

### 9.

find info on this Phone delivery logs for the group 1 four. If pings were sent but never delivered, that is the “never rings” mechanism. This is the check I’d prioritise.

### 10.

I want to look now only at Farlight. Show me every week for them, how many times we pinged them, how many they took. Then tell me what happened to that person, week by week, in plain English.

### 11.

Do we have any insight on Farlight's ranking throughout this time period? Also are the pings they got post-release in, out or mixed of their home area?

### 12.

In plain english, summarize the above in 1-2 sentances

### 13.

If I'd only asked for the number, not the rows, what would I have missed?
