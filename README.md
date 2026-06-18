<div align="center">

# 🔬 Deep Research Skill

### *Massive autonomous web research for AI coding agents — no API keys, no limits, completely free*

[![GitHub Release](https://img.shields.io/github/v/release/FMATheNomad/deep-research-skill?style=for-the-badge&logo=github&color=blue)](https://github.com/FMATheNomad/deep-research-skill/releases)
[![GitHub Stars](https://img.shields.io/github/stars/FMATheNomad/deep-research-skill?style=for-the-badge&logo=github&color=yellow)](https://github.com/FMATheNomad/deep-research-skill/stargazers)
[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-%E2%9D%A4%EF%B8%8F-30363D?style=for-the-badge&logo=githubsponsors)](https://github.com/sponsors/FMATheNomad)
[![GitHub License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![OpenCode](https://img.shields.io/badge/OpenCode-Skill-6C47FF?style=for-the-badge&logo=opencode)](https://opencode.ai)

---

# ⭐️ Support This Project ⭐️

**This is a free, open-source skill built by a solo founder. If it saves you time or money, please:**

[![Star](https://img.shields.io/badge/⭐️_Star_this_repo-Support_the_project-yellow?style=for-the-badge)](https://github.com/FMATheNomad/deep-research-skill/stargazers)
[![Sponsor](https://img.shields.io/badge/%E2%9D%A4%EF%B8%8F_Sponsor_on_GitHub-Support_the_creator-30363D?style=for-the-badge&logo=githubsponsors)](https://github.com/sponsors/FMATheNomad)

**Every star & sponsor helps a solo founder keep building free tools for everyone.** 🙏

---

> **Firecrawl who?** This skill gives your AI agent the power to search, fetch, and synthesize information from **dozens of web pages in parallel** — completely free, no API keys, no accounts, no limits.

</div>

## 🔥 Why This Exists

Firecrawl is great, but:
- ❌ Needs API key + account
- ❌ Free tier limited (500K credits)
- ❌ Self-host requires Docker + infrastructure
- ❌ AGPL license

**Deep Research Skill** uses what OpenCode already has built-in — `websearch` (powered by Exa, **free no API key**) and `webfetch` (built-in, **free**) — and orchestrates them into a massive parallel research pipeline.

## ✨ Features

| Feature | Description |
|---------|-------------|
| **🔍 Multi-Query Search** | Searches from multiple angles for comprehensive coverage |
| **⚡ Parallel Fetching** | Fetches 10-30+ pages simultaneously |
| **🧠 AI-Powered Synthesis** | Agent reads & synthesizes all content intelligently |
| **📊 Structured Output** | Comparison tables, deep dives, summaries with citations |
| **🔓 Completely Free** | No API keys, no accounts, no credit limits |
| **📚 Research Templates** | Comparison, technical, market research — ready to use |

## 🚀 Installation

### One-Click

```bash
npx skills add FMATheNomad/deep-research-skill@deep-research -g -y
```

### Manual — OpenCode

```bash
mkdir -p ~/.config/opencode/skills/deep-research
curl -o ~/.config/opencode/skills/deep-research/SKILL.md \
  https://raw.githubusercontent.com/FMATheNomad/deep-research-skill/main/skills/deep-research/SKILL.md
```

### Prerequisites

- [OpenCode](https://opencode.ai) installed
- Start with `OPENCODE_ENABLE_EXA=1 opencode` to enable `websearch`

## 🔬 How It Works

```mermaid
graph TD
    A[User: Research Topic X] --> B[websearch: multiple queries]
    B --> C[Collect 10-30+ URLs]
    C --> D[webfetch: ALL URLs in parallel]
    D --> E[Agent reads & synthesizes]
    E --> F[Structured Report with Sources]
    
    style A fill:#6C47FF,color:#fff
    style B fill:#4CAF50,color:#fff
    style D fill:#FF9800,color:#fff
    style F fill:#f44336,color:#fff
```

### Example Session

```
You: "Cari informasi lengkap tentang quantum computing"

Agent (deep research activated):
  → websearch("quantum computing explained")
  → websearch("quantum computing 2025 2026 breakthroughs")
  → websearch("quantum computing companies")
  → websearch("quantum computing vs classical")
  → Collected 28 URLs from Wikipedia, IBM, Nature, MIT, etc.
  
  → Fetching 28 pages in parallel...
  
  → Synthesizing findings from all sources...
  
  → 📋 Research: Quantum Computing
  
    Summary: Quantum computing leverages quantum mechanics...
    
    Key Findings:
    1. Current state: ...
    2. Major players: ...
    3. Breakthroughs in 2025-2026: ...
    
    Sources:
    - Wikipedia — overview & history
    - IBM Quantum — current technology
    - Nature — latest research papers
```

## 📋 Research Templates

### Comparison Research

```
"Compare PostgreSQL and Supabase for production use"
→ Searches: "PostgreSQL vs Supabase", "Supabase review", "PostgreSQL production tips"
→ Fetches 15+ comparison articles, reviews, docs
→ Returns comparison table: features, pricing, pros/cons, use cases
```

### Technical Deep Dive

```
"How does WebRTC work under the hood?"
→ Searches: "WebRTC explained", "WebRTC architecture", "WebRTC STUN TURN"
→ Fetches 20+ technical articles, RFCs, implementation guides
→ Returns comprehensive technical explanation with diagrams
```

### Market Research

```
"Analyze the AI code generation market in 2026"
→ Searches: "AI code generation market size", "AI coding tools comparison", "GitHub Copilot vs alternatives"
→ Fetches 25+ market reports, reviews, funding news
→ Returns market analysis with trends, competitors, opportunities
```

## ⚡ Pro Tips

1. **Enable websearch** — start OpenCode with `OPENCODE_ENABLE_EXA=1 opencode`
2. **Ask for depth** — "deep research about X, minimal 20 sources"
3. **Specify format** — "compare X and Y in a table", "give me a structured report"
4. **Iterate** — ask follow-up questions to go deeper
5. **Combine with agent-browser** — for pages that need JS/clicking, use agent-browser then webfetch

## 🆚 vs Firecrawl

| Feature | Firecrawl | **Deep Research Skill** |
|---------|-----------|------------------------|
| 💰 **Cost** | Free tier (500K credits) | **Unlimited free** |
| 🔑 **API Key** | Required | **Not needed** |
| 🏗 **Self-host** | Docker required | **Nothing to host** |
| 🔍 **Search** | Built-in | via `websearch` (Exa) |
| 📄 **Scrape** | Built-in | via `webfetch` |
| ⚡ **Parallel** | ✅ Yes | ✅ **Agent batches** |
| 🧠 **Synthesis** | Separate API | **Built into agent** |
| 📜 **License** | AGPL-3.0 | **MIT** |
| 🔌 **Setup** | CLI + API key | **Skill only** |

**Bottom line:** Firecrawl is better for automated crawling at scale (thousands of pages). Deep Research Skill is better for **intelligent research** — searching, reading, and synthesizing from dozens of pages with zero cost.

## 🗺 Roadmap

- [ ] **Bulk mode** — research 10+ topics in one session
- [ ] **PDF support** — fetch and parse academic PDFs
- [ ] **Citation export** — BibTeX, APA, MLA format
- [ ] **Research report generation** — export to markdown/PDF
- [ ] **Scheduled research** — monitor topics over time
- [ ] **Multi-language** — research in Indonesian, Japanese, etc.

## 📁 Project Structure

```
deep-research-skill/
├── .github/
│   ├── workflows/validate.yml
│   └── FUNDING.yml
├── skills/
│   └── deep-research/
│       └── SKILL.md
├── README.md
├── LICENSE
└── .gitignore
```

## 🤝 Contributing

Add new research templates, improve the pipeline, or suggest features. See [CONTRIBUTING.md](CONTRIBUTING.md).

<div align="center">

---

## ⭐️ Support the Project ⭐️

**Built by a solo founder who got tired of API keys and credit limits.**  
If this skill helps you, please support it — every bit counts:

[![Star](https://img.shields.io/badge/⭐️_Star_this_Repo-1_click-yellow?style=for-the-badge)](https://github.com/FMATheNomad/deep-research-skill/stargazers)
[![Sponsor](https://img.shields.io/badge/%E2%9D%A4%EF%B8%8F_Sponsor_on_GitHub-Support_a_solo_founder-30363D?style=for-the-badge&logo=githubsponsors)](https://github.com/sponsors/FMATheNomad)
[![Share](https://img.shields.io/badge/🐦_Share_on_X-Tell_the_world-000000?style=for-the-badge&logo=x)](https://x.com/intent/tweet?text=🔥%20Firecrawl%20alternative%20-%20completely%20free%2C%20no%20API%20keys.%20Deep%20research%20skill%20for%20AI%20coding%20agents.%20Search%20%26%20read%20dozens%20of%20pages%20in%20parallel.%20%F0%9F%94%AC&url=https://github.com/FMATheNomad/deep-research-skill)

---

*Free research for everyone. Open source. MIT licensed.*

[![FMA Software Labs](https://img.shields.io/badge/FMA%20Software%20Labs-000000?style=for-the-badge)](https://fmasoftwarelabs.up.railway.app)
[![X / Twitter](https://img.shields.io/badge/Follow-%40fmathenomad-000000?style=for-the-badge&logo=x)](https://x.com/fmathenomad)

</div>
