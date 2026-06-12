# The Weekly Watchdog

A Claude Code scheduled task that re-runs the visibility check and rank pull every week, appends to a trend report, and tells you if anything moved. Rankings are a trend line, not a launch day.

## Set it up

In Claude Code, create a scheduled task (weekly, pick a quiet hour) with this prompt:

```
Run the weekly SEO watchdog for <domain>:

1. Pull top-50 queries/pages from the Search Console MCP (last 7 days vs prior 7).
2. Re-run the visibility skill's question set (stored in seo-reports/visibility-questions.md)
   and recompute the /100 score.
3. Append one row to seo-reports/trend.md:
   | date | visibility score | avg position (top 50) | clicks (7d) | AI citations | notes |
4. Compare with last week's row. If the visibility score moved 5+ points or any money
   query moved 3+ positions either way, write a short WHAT CHANGED section naming the
   likely cause (check seo-reports/changes-*.md for recent fixes).
5. Keep it honest: no movement is a valid result. Say "no movement" rather than
   narrating noise.
```

## Reading the trend

- Expect nothing for 1-2 weeks after fixes. Schema and llms.txt changes need recrawls.
- The visibility score usually moves before rankings do — AI surfaces refresh faster than the index.
- If clicks fall while positions hold, check whether an AI Overview appeared on your money queries (the audit skill's step 1 catches this).
