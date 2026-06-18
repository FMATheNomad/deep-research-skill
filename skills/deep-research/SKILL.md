---
name: deep-research
description: "Massive autonomous web research via AI-powered browsing. Use this skill when the user needs to research a topic deeply, compare information across multiple sources, gather data from many websites, or conduct comprehensive web research. Automatically searches, fetches dozens of pages in parallel, and synthesizes findings. Triggers: 'research this topic', 'search for complete info about', 'deep research', 'compare X and Y', 'gather data from multiple sources', 'research about'. Far more efficient than browser automation for research — uses direct content fetching in parallel."
compatibility: opencode
metadata:
  author: FMA Software Labs
  stack: web, research, ai
  source: fmasoftwarelabs
---

# Deep Research — Autonomous Massive Web Research

A pipeline for conducting deep, multi-source web research. Uses OpenCode's built-in `websearch` and `webfetch` tools to search, fetch dozens of pages in parallel, and synthesize comprehensive findings.

**No API keys needed. No accounts. Completely free.**

## How It Works

```
User: "Search for complete info about antimatter"

Agent:
  Step 1: websearch("antimatter physics")          → 10+ source URLs
  Step 2: wefetch(source1) + webfetch(source2) + ... (parallel, 10+ at once)
  Step 3: Read & synthesize all content
  Step 4: Present structured summary with sources
```

## Research Workflow

### Step 1: Understand the Scope

Determine:
- **Topic** — what to research
- **Depth** — overview vs deep dive vs comparison
- **Sources needed** — general web, academic, news, documentation
- **Output format** — summary, comparison table, structured report

### Step 2: Search for Sources

Use `websearch` to find relevant pages. Always search multiple queries for comprehensive coverage:

```bash
# Primary search — cast a wide net
websearch("topic")
websearch("topic research paper")
websearch("topic latest 2025 2026")
websearch("topic comparison alternatives")
websearch("topic tutorial guide")

# Collect ALL returned URLs across searches
```

**Pro tip:** Use `OPENCODE_ENABLE_EXA=1` environment variable before starting OpenCode to enable `websearch` tool.

### Step 3: Fetch Pages in Parallel

Use `webfetch` to fetch all collected URLs. **Fetch at least 10-20 pages in parallel** for proper deep research:

```bash
# Launch all fetches in parallel — do NOT wait for each one
webfetch(url1)
webfetch(url2)
webfetch(url3)
...
webfetch(urlN)
```

**Rules:**
- Fetch ALL URLs, not just a few
- Prioritize: Wikipedia, academic sources, official docs, reputable blogs
- Skip obvious low-value pages (forums, spam)
- If some fail, note it and continue

### Step 4: Analyze & Synthesize

After receiving all content:

1. **Identify key themes** across sources
2. **Note contradictions** — different sources may disagree
3. **Find unique insights** — each source adds value
4. **Structure the answer**:
   - Executive summary (2-3 sentences)
   - Detailed findings with source citations
   - Key statistics / data points
   - Different perspectives
   - Conclusion

### Step 5: Present Results

Format the response with:

```
## 📋 Research: [Topic]

**Summary:** [2-3 sentence overview]

### Key Findings
1. **[Finding 1]** — [detail] ([source](url))
2. **[Finding 2]** — [detail] ([source](url))
...

### Detailed Analysis
[Comprehensive synthesis of all sources]

### Sources
- [Title](url) — [what this source contributed]
- [Title](url) — [what this source contributed]
...

### Further Questions
- [Aspect not fully covered]
- [Related topic worth exploring]
```

## Research Templates

### Template: Comparison Research

```bash
# User: "Compare X and Y"
websearch("X vs Y comparison")
websearch("X features pricing")
websearch("Y features pricing")
websearch("X review")
websearch("Y review")

# Fetch all results in parallel
webfetch(url1) ... webfetch(urlN)

# Present as comparison table:
# | Feature | X | Y |
# | Pricing | $ | $ |
# | Pros | ... | ... |
# | Cons | ... | ... |
```

### Template: Deep Technical Research

```bash
# User: "How does technology X work?"
websearch("X explained")
websearch("X architecture")
websearch("X tutorial")
websearch("X whitepaper")
websearch("X vs alternatives")
```

### Template: Market / Competitive Research

```bash
# User: "Analyze the market for X"
websearch("X market size 2025")
websearch("X competitors")
websearch("X trends")
websearch("X funding")
websearch("X review")
```

## Tips for Maximum Results

1. **Search multiple queries** — different angles yield different sources
2. **Fetch everything in parallel** — bash `&` style or sequential tool calls
3. **Prioritize quality sources** — Wikipedia, official docs, .edu, .gov, reputable tech sites
4. **Note failed fetches** — try alternative URLs if available
5. **Cite sources** — always link back to original content
6. **10+ pages minimum** — for truly deep research, aim for 20-30+ pages

## How This Beats Firecrawl

| Feature | Firecrawl | This Skill |
|---------|-----------|------------|
| API Key Required | ✅ Yes | ❌ **No** |
| Cost | Free tier (500K credits) | **Free unlimited** |
| Search | ✅ Built-in | ✅ via `websearch` (Exa) |
| Markdown output | ✅ | ✅ via `webfetch` |
| Parallel fetching | ✅ | ✅ (agent can batch) |
| AI synthesis | Separate API | ✅ **Built into agent** |
| Customizable | Limited | ✅ **Full control** |
| Open source | AGPL | ✅ **MIT** |

## Limitations

- `websearch` requires Exa (enabled via `OPENCODE_ENABLE_EXA=1` or OpenCode provider)
- `webfetch` fetches one URL at a time per tool call (but agent can parallelize)
- Rate limits depend on your OpenCode provider
- Some sites block automated fetching (JavaScript-heavy SPAs)
