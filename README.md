# seo-skills — Marketing Skills for AI Agents

> **Attribution notice**: This repository was compiled by **Tony Blaise** and is based on content extracted and adapted from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills). Full credit goes to **[Corey Haines](https://corey.co?ref=marketingskills)** for the original work. This copy is used for personal learning and experimentation under the MIT License.



A collection of AI agent skills focused on marketing tasks. Built for technical marketers and founders who want AI coding agents to help with conversion optimization, copywriting, SEO, analytics, and growth engineering. Works with Claude Code, OpenAI Codex, Cursor, Windsurf, and any agent that supports the [Agent Skills spec](https://agentskills.io).

Originally built by [Corey Haines](https://corey.co?ref=marketingskills). Need hands-on help? Check out [Conversion Factory](https://conversionfactory.co?ref=marketingskills) — Corey's agency for conversion optimization, landing pages, and growth strategy. Want to learn more about marketing? Subscribe to [Swipe Files](https://swipefiles.com?ref=marketingskills). Want an autonomous AI agent that uses these skills to be your CMO? Try [Magister](https://magistermarketing.com?ref=marketingskills).

New to the terminal and coding agents? Check out the companion guide [Coding for Marketers](https://codingformarketers.com?ref=marketingskills).

**Contributions welcome!** Found a way to improve a skill or have a new one to add? [Open a PR](#contributing).

Run into a problem or have a question? [Open an issue](https://github.com/coreyhaines31/marketingskills/issues) — we're happy to help.

## What are Skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks. When you add these to your project, your agent can recognize when you're working on a marketing task and apply the right frameworks and best practices.

## How Skills Work Together

Skills reference each other and build on shared context. `content-strategy` acts as the planning foundation — other skills pull from it to align on topics, audience, and goals.

```
                    ┌──────────────────────────────────────┐
                    │          content-strategy            │
                    │    (foundation for content work)     │
                    └──────────────────┬───────────────────┘
                                       │
    ┌──────────────┬────────────────────┼──────────────┬──────────────┐
    ▼              ▼                    ▼              ▼              ▼
┌──────────┐ ┌──────────┐        ┌──────────┐  ┌────────────┐ ┌───────────┐
│  SEO &   │ │   CRO    │        │Content & │  │Competitor  │ │ Strategy  │
│Discovery │ │          │        │   Copy   │  │Intelligence│ │           │
├──────────┤ ├──────────┤        ├──────────┤  ├────────────┤ ├───────────┤
│seo-audit │ │cro       │        │copywritng│  │competitor- │ │launch     │
│ai-seo    │ │          │        │copy-edit │  │ analysis   │ │           │
│site-arch │ │          │        │image     │  │competitor- │ │           │
│programm  │ │          │        │          │  │ profiling  │ │           │
│schema    │ │          │        │          │  │            │ │           │
└────┬─────┘ └────┬─────┘        └────┬─────┘  └─────┬──────┘ └─────┬─────┘
     │            │                   │               │              │
     └────────────┴──────────┬────────┴───────────────┴──────────────┘
                             │
         Skills cross-reference each other:
           copywriting ↔ cro
           seo-audit ↔ schema ↔ ai-seo
           competitor-analysis ↔ competitor-profiling
           content-strategy → copywriting, seo-audit
```

See each skill's **Related Skills** section for the full dependency map.

## Available Skills

<!-- SKILLS:START -->
| Skill | Description |
|-------|-------------|
| [ai-seo](skills/ai-seo/) | When the user wants to optimize content for AI search engines, get cited by LLMs, or appear in AI-generated answers.... |
| [competitor-analysis](skills/competitor-analysis/) | When the user wants to create competitor comparison or alternative pages for SEO and sales enablement. Also use when... |
| [competitor-profiling](skills/competitor-profiling/) | When the user wants to research, profile, or analyze competitors from their URLs. Also use when the user mentions... |
| [content-strategy](skills/content-strategy/) | When the user wants to plan a content strategy, decide what content to create, or figure out what topics to cover. Also... |
| [copy-editing](skills/copy-editing/) | When the user wants to edit, review, or improve existing marketing copy, or refresh outdated content. Also use when the... |
| [copywriting](skills/copywriting/) | When the user wants to write, rewrite, or improve marketing copy for any page — including homepage, landing pages,... |
| [cro](skills/cro/) | When the user wants to optimize, improve, or increase conversions on any marketing page or form — including homepage,... |
| [image](skills/image/) | When the user wants to create, generate, edit, or optimize images for marketing — blog heroes, social graphics, product... |
| [launch](skills/launch/) | When the user wants to plan a product launch, feature announcement, or release strategy. Also use when the user... |
| [programmatic-seo](skills/programmatic-seo/) | When the user wants to create SEO-driven pages at scale using templates and data. Also use when the user mentions... |
| [schema](skills/schema/) | When the user wants to add, fix, or optimize schema markup and structured data on their site. Also use when the user... |
| [seo-audit](skills/seo-audit/) | When the user wants to audit, review, or diagnose SEO issues on their site. Also use when the user mentions "SEO... |
| [site-architecture](skills/site-architecture/) | When the user wants to plan, map, or restructure their website's page hierarchy, navigation, URL structure, or internal... |
<!-- SKILLS:END -->

## Installation

### Option 1: CLI Install (Recommended)

Use [npx skills](https://github.com/vercel-labs/skills) to install skills directly:

```bash
# Install all skills
npx skills add coreyhaines31/marketingskills

# Install specific skills
npx skills add coreyhaines31/marketingskills --skill cro copywriting

# List available skills
npx skills add coreyhaines31/marketingskills --list
```

This automatically installs to your `.agents/skills/` directory (and symlinks into `.claude/skills/` for Claude Code compatibility).

### Option 2: Claude Code Plugin

Install via Claude Code's built-in plugin system:

```bash
# Add the marketplace
/plugin marketplace add coreyhaines31/marketingskills

# Install all marketing skills
/plugin install marketing-skills
```

### Option 3: Clone and Copy

Clone the entire repo and copy the skills folder:

```bash
git clone https://github.com/coreyhaines31/marketingskills.git
cp -r marketingskills/skills/* .agents/skills/
```

### Option 4: Git Submodule

Add as a submodule for easy updates:

```bash
git submodule add https://github.com/coreyhaines31/marketingskills.git .agents/marketingskills
```

Then reference skills from `.agents/marketingskills/skills/`.

### Option 5: Fork and Customize

1. Fork this repository
2. Customize skills for your specific needs
3. Clone your fork into your projects

### Option 6: SkillKit (Multi-Agent)

Use [SkillKit](https://github.com/rohitg00/skillkit) to install skills across multiple AI agents (Claude Code, Cursor, Copilot, etc.):

```bash
# Install all skills
npx skillkit install coreyhaines31/marketingskills

# Install specific skills
npx skillkit install coreyhaines31/marketingskills --skill cro copywriting

# List available skills
npx skillkit install coreyhaines31/marketingskills --list
```

## Upgrading from v1.x to v2.0

v2.0 renames 17 skills and consolidates `page-cro` + `form-cro` into a single `cro` skill. If you installed the v1.x skills, you'll have **stale old-name folders** in your install directory after upgrading — the new skills install alongside the old ones, so you'll see both `skills/page-cro/` and `skills/cro/`, etc. Clean them up:

```bash
# From the directory where you installed the skills (e.g., .agents/skills/ or .claude/skills/)
rm -rf page-cro form-cro \
       ab-test-setup analytics-tracking aso-audit competitor-alternatives \
       email-sequence free-tool-strategy launch-strategy onboarding-cro \
       paid-ads paywall-upgrade-cro popup-cro pricing-strategy \
       product-marketing-context referral-program schema-markup \
       signup-flow-cro social-content
```

Then reinstall the v2.0 skills via your usual method (e.g., `npx skills add coreyhaines31/marketingskills`).

### Migrate the product marketing context file

In v2.0 the context file moved from `.claude/` to `.agents/` and was renamed from `product-marketing-context.md` to `product-marketing.md`. Move your existing context file:

```bash
mkdir -p .agents
# v2.0 file (or pre-v2.0 file with new name)
mv .claude/product-marketing.md .agents/product-marketing.md 2>/dev/null
# pre-v2.0 file with legacy name
mv .claude/product-marketing-context.md .agents/product-marketing.md 2>/dev/null
```

Skills will still check `.claude/` and the legacy `product-marketing-context.md` filename as fallbacks, so nothing breaks if you don't migrate.

### Full rename map

| Old | New |
|-----|-----|
| `ab-test-setup` | `ab-testing` |
| `analytics-tracking` | `analytics` |
| `aso-audit` | `aso` |
| `competitor-alternatives` | `competitors` |
| `email-sequence` | `emails` |
| `form-cro` | merged into `cro` |
| `free-tool-strategy` | `free-tools` |
| `launch-strategy` | `launch` |
| `onboarding-cro` | `onboarding` |
| `page-cro` | `cro` |
| `paid-ads` | `ads` |
| `paywall-upgrade-cro` | `paywalls` |
| `popup-cro` | `popups` |
| `pricing-strategy` | `pricing` |
| `product-marketing-context` | `product-marketing` |
| `referral-program` | `referrals` |
| `schema-markup` | `schema` |
| `signup-flow-cro` | `signup` |
| `social-content` | `social` |

## Usage

Once installed, just ask your agent to help with marketing tasks:

```
"Help me optimize this landing page for conversions"
→ Uses cro skill

"Write homepage copy for my SaaS"
→ Uses copywriting skill

"Audit the SEO on my site"
→ Uses seo-audit skill

"Plan what content to create this quarter"
→ Uses content-strategy skill

"Research my top competitor"
→ Uses competitor-profiling skill
```

You can also invoke skills directly:

```
/cro
/seo-audit
/copywriting
/content-strategy
/ai-seo
```

## Skill Categories

### SEO & Discovery
- `seo-audit` - Technical and on-page SEO
- `ai-seo` - AI search optimization (AEO, GEO, LLMO)
- `programmatic-seo` - Scaled page generation
- `site-architecture` - Page hierarchy, navigation, URL structure
- `schema` - Structured data

### Content & Copy
- `content-strategy` - Content planning and topic selection
- `copywriting` - Marketing page copy
- `copy-editing` - Edit and polish existing copy
- `image` - AI image generation, design tools, and optimization

### Conversion Optimization
- `cro` - Pages and forms

### Competitor Intelligence
- `competitor-analysis` - Comparison and alternative pages for SEO and sales
- `competitor-profiling` - Research and profile competitors from their URLs

### Strategy
- `launch` - Product launches and announcements

## Contributing

Found a way to improve a skill? Have a new skill to suggest? PRs and issues welcome!

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding or improving skills.

## License

[MIT](LICENSE) - Use these however you want.
