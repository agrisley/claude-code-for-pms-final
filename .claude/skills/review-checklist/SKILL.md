---
name: review-checklist
description: Run Annie's standard four-point review on a product brief before it goes any further. Use when Annie says "review this brief", "run the review checklist", "check this brief", or points at a brief file or wiki page and wants the usual check.
---

# Review checklist

Give any brief the same four checks, every time. Annie should not have to explain them again.

## Input

A brief: a file path, a wiki page, or pasted text. If none is given, ask which brief. Read all of it, start to end, before judging anything.

## The four checks

1. **Owner.** The brief names who owns it, by person or role. A team name alone, "TBD", or an owner who has left does not pass. Check names against the Team directory if the wiki is available.
2. **Success measure.** The brief says how we'll know it worked: a metric or observable outcome, ideally with a baseline and a target or timeframe. "Improve the experience" does not pass. A metric with no baseline is a partial pass.
3. **Scope matches.** Compare the scope stated at the start (problem, goals, summary) with the scope at the end (requirements, features, next steps, what's being built). Flag anything that appears at the end but not the start (scope creep) and anything promised at the start that never appears at the end (dropped). Quote both sides.
4. **Problem before fix.** The brief explains the problem before it proposes a solution. Check the order, and check that the problem is evidenced (data, tickets, interviews) rather than only asserted. A solution in the title or opening paragraph, with the problem arriving after, does not pass.

## Output

Use this shape:

```
Brief: <title / path>

1. Owner: PASS | PARTIAL | FAIL
   <one line, with a short quote or location>
2. Success measure: PASS | PARTIAL | FAIL
   <one line>
3. Scope matches: PASS | PARTIAL | FAIL
   Start: <what it says>
   End: <what it says>
   Differences: <added / dropped, or "none">
4. Problem before fix: PASS | PARTIAL | FAIL
   <one line: where the problem is, where the fix first appears>

Verdict: ready to go further | fix first
Fix list: <only the items that are not PASS, each as one concrete change>
```

## Rules

- Judge only against the four checks. Don't add extra criteria or rewrite the brief.
- Cite where in the brief each finding comes from (section heading or quote). Don't invent content the brief doesn't have.
- If something is ambiguous, say so and mark PARTIAL rather than guessing.
- Verdict is "ready to go further" only if all four are PASS.
- Report only. Don't edit the brief unless Annie asks.
