# Claude Code SEO Stack

Put your SEO on autopilot with Claude Code. Four skills and two MCP servers that audit your site, check whether ChatGPT, Gemini, Perplexity and Google AI Overviews actually recommend you, hand you your fastest fixes, and write the changes for you.

## Why this exists

68% of Google searches now end without a click ([SparkToro, 2026](https://searchengineland.com/google-zero-click-searches-2026-study-479717)). AI Overviews cut clicks to the #1 result by 58% ([Ahrefs](https://ahrefs.com/blog/ai-overviews-reduce-clicks-update/)). The question is no longer where you rank. It is whether AI knows you exist. This stack tells you, then fixes it.

## The stack

| Piece | What it does |
|---|---|
| **Search Console MCP** | Your real rankings and queries, live in Claude Code |
| **DataForSEO MCP** | Keyword data, competitor visibility, AI answer surfaces |
| **Skill 1: Audit** | Crawls your site, runs technical checks, returns scored findings |
| **Skill 2: Visibility** | Scores your brand 0-100 across ChatGPT, Gemini, Perplexity, AI Overviews |
| **Skill 3: Diagnose** | Turns both reports into your 15 fastest fixes plus unanswered AI questions |
| **Skill 4: Fix** | Writes schema, llms.txt and copy changes; optionally pushes live via a CMS MCP |
| **Weekly watchdog** | A scheduled task that re-runs everything and graphs the trend |

## Setup (15 minutes)

### 1. Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. Connect the Search Console MCP (free)

Create a Google Cloud project, enable the Search Console API, create a service account and download its JSON key, then add the service account email as a user on your Search Console property. Then:

```bash
claude mcp add gsc -- npx -y mcp-server-gsc
```

Set `GOOGLE_APPLICATION_CREDENTIALS` to your key path. Full walkthrough in the [mcp-server-gsc README](https://github.com/ahonn/mcp-server-gsc).

### 3. Connect the DataForSEO MCP (pay as you go)

Sign up at dataforseo.com, grab your API login and password, then:

```bash
claude mcp add dataforseo -e DATAFORSEO_USERNAME=<login> -e DATAFORSEO_PASSWORD=<password> -- npx -y dataforseo-mcp-server
```

Official server: [dataforseo/mcp-server-typescript](https://github.com/dataforseo/mcp-server-typescript).

### 4. Install the skills

```bash
git clone https://github.com/Sandy-zippy/claude-code-seo-stack.git
cp -r claude-code-seo-stack/skills/* your-project/.claude/skills/
```

### 5. Run it

Open Claude Code in your project and say:

```
Run the audit skill on https://yoursite.com
```

Then `visibility`, `diagnose`, `fix` in that order. Each skill tells Claude exactly what to do.

### 6. Set the weekly watchdog

See [templates/weekly-watchdog.md](templates/weekly-watchdog.md) for the scheduled-task prompt that re-runs the checks weekly and appends to a trend report.

## Optional: push fixes live

If your site runs WordPress, add a WordPress MCP (for example [InstaWP/mcp-wp](https://github.com/InstaWP/mcp-wp)) and the Fix skill will publish changes instead of just writing them.

## Credits and further reading

Additional reading:

- [mykpono/ultimate-seo-geo](https://github.com/mykpono/ultimate-seo-geo) — full audit suite with 20 diagnostic scripts
- [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) — 25 sub-skills covering technical SEO, E-E-A-T, schema, GEO/AEO
- [aaron-he-zhu/seo-geo-claude-skills](https://github.com/aaron-he-zhu/seo-geo-claude-skills) — 20 SEO and GEO skills with rank tracking
- [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) — broader marketing skill pack

## Who made this

[@aimarketinglab](https://instagram.com/aimarketinglab) — what AI is doing to marketing, every week. This stack runs on real client sites at our agency.

MIT licensed. Star it if it saved you an agency retainer.
