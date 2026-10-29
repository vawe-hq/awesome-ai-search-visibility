# Awesome AI Search Visibility [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> What the evidence says about getting a site or a developer tool named and cited by AI answer engines and coding agents.

Each entry gives one finding with its number, a link to the source, and the kind of source. The list covers answer engine optimization (AEO), generative engine optimization (GEO), how AI crawlers read a site, how to measure visibility, and programmatic SEO. The [vawe-hq](https://github.com/vawe-hq) team keeps it. Links were last checked on 2026-10-30.

## How to read this

- Findings conflict. Two entries in this list disagree on whether coding agents send `Accept: text/markdown`. Read both.
- Engines change fast. A number from last month can be wrong now. Check the date on the source.
- Most numbers come from one study on one set of engines. Treat each as one data point.
- Source kinds: paper (arXiv, not all peer reviewed), vendor (a company that sells in this field or runs the platform it measures), official docs, research report (an independent firm), practitioner (a person reporting their own site or logs), and forum (a thread or comment).
- Entries marked *[not re-checked]* come from pages the maintainers could not open in the last check. The number is as reported by the research notes.

## Contents

- [What decides whether an AI names you](#what-decides-whether-an-ai-names-you)
- [How AI crawlers read a site](#how-ai-crawlers-read-a-site)
- [Measuring visibility](#measuring-visibility)
- [Programmatic SEO](#programmatic-seo)
- [Contributing](#contributing)

## What decides whether an AI names you

- [A Fitted Stage Model of Brand Visibility](https://arxiv.org/abs/2609.23162) (paper) - A brand was mentioned 2.8% (GPT) and 3.8% (Gemini) of the time with no own-domain citation, 49.0% and 58.4% with one, and 91.4% and 100% with a branded search query too.
- [Data-Void Exploits in Web-Searching LLMs](https://arxiv.org/abs/2610.30365) (paper) - On thin topics, one page filled the gap in 31% of answers.
- [LLM preferences for libraries and languages](https://arxiv.org/abs/2503.17181) (paper) - Eight LLMs overused popular libraries, for example NumPy where it was not needed in up to 45% of cases, which is a handicap for a new tool.
- [Navigating the Shift: Web Search vs Generative AI Response Generation](https://arxiv.org/abs/2601.16858) (paper) - Claude 4.5 drew 65% of its cited sources from earned media, and the domain overlap with Google's top 10 ranged from 4.0% (GPT-4o) to 15.2% (Perplexity).
- [Scoring Without the Engine](https://arxiv.org/abs/2609.07559) (paper) - The levers from the 2023 GEO paper moved citation on none of ten modern engine families.
- [What Drives Citations in Production LLMs](https://arxiv.org/abs/2609.35077) (paper) - Domain authority was about six times stronger than any other non-alignment page feature, and FAQ blocks, structured data and Core Web Vitals fell to zero once the domain was held fixed.
- [What Drives Citations in Production LLMs, page wording](https://arxiv.org/abs/2609.35077) (paper) - Page wording that matches the prompts buyers use was the top page-level predictor (beta +0.37), and the page type "pricing" scored +0.42 in the paper's coefficient figure.
- [Which tools do Claude, Codex and Cursor choose? 17k runs](https://armature.tech/blog/which-tools-coding-agents-install) (vendor, Armature sells developer-tool growth) - Claude Code searched the web in about 30% of sessions and Codex in 94%, the three agents picked the same tool in only 42% of cells, and a "1-day retention" free-tier limit on a pricing page made one product lose picks.

## How AI crawlers read a site

- [A made-up cats.txt got fetched and cited](https://markwilliamscook.substack.com/p/how-catstxt-showed-llmstxt-evidence) (practitioner) - A fake standard file was fetched by four crawlers, indexed by Google and quoted by an AI Overview, so a fetch of `llms.txt` proves nothing.
- [A third of Perplexity's citations don't contain the number they're cited for](https://hausresearch.com/reports/perplexity-citation-audit) (research report, Haus Research) - 34.7% of 1,826 numeric citations pointed to a page that was unreadable or lacked the cited figure.
- [AI features and your website](https://developers.google.com/search/docs/appearance/ai-features) (official docs, Google) - Google says AI features have no extra technical requirements, and their clicks are counted inside the "Web" search type in Search Console.
- [Developer Experience with AI Coding Agents](https://arxiv.org/abs/2604.02544) (paper) - Coding agents collapse navigation into one or two requests, so bounce rate and time on page stop meaning anything.
- [Do AI bots read llms.txt?](https://www.ezy.ai/research/do-ai-bots-read-llms-txt) (vendor, EZY) - Over 12 weeks on 83 sites, OpenAI fetched `llms.txt` 7 times and Anthropic 9 times, against 3,990 and 3,120 `robots.txt` fetches.
- [Does Anthropic crawl data from the web](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) (official docs, Anthropic) - Anthropic lists ClaudeBot (training), Claude-User (user fetch) and Claude-SearchBot (search index), and a robots.txt rule must be repeated per subdomain.
- [Googlebot](https://developers.google.com/search/docs/crawling-indexing/googlebot) (official docs, Google) - Googlebot indexes only the first 2 MB of uncompressed HTML.
- [Hacker News: Bear Blog operator on llms.txt](https://news.ycombinator.com/item?id=48410589) (forum) - The operator of a platform with about 80,000 blogs reports that no AI player requests `llms.txt`.
- [Hacker News: GPTBot on a workers.dev hostname](https://news.ycombinator.com/item?id=47153800) (forum) - One poster saw 160,000 GPTBot requests in 24 hours on an unlisted alias hostname that bypassed the zone's firewall rules.
- [Markdown for Agents](https://blog.cloudflare.com/markdown-for-agents) (vendor, Cloudflare) - Serving markdown on `Accept: text/markdown` cut one post from 16,180 to 3,150 tokens, and the post says Claude Code and OpenCode send the header.
- [Nginx logs: AI traffic vs referral traffic](https://surfacedby.com/blog/nginx-logs-ai-traffic-vs-referral-traffic) (vendor, SurfacedBy) - In a log probe of eight assistants, none sent `Accept: text/markdown`, though coding agents were not the subject. This conflicts with the Cloudflare entry above.
- [OpenAI crawlers](https://developers.openai.com/api/docs/bots) (official docs, OpenAI) - OpenAI lists four bots (OAI-SearchBot, GPTBot, ChatGPT-User, OAI-AdsBot), and says robots.txt "may not apply" to the user-initiated ChatGPT-User.
- [Perplexity bots](https://docs.perplexity.ai/guides/bots) (official docs, Perplexity) - Perplexity lists PerplexityBot (search index) and Perplexity-User, which "generally ignores robots.txt".
- [The rise of the AI crawler](https://vercel.com/blog/the-rise-of-the-ai-crawler) (vendor, Vercel) - GPTBot, ClaudeBot, PerplexityBot and OAI-SearchBot do not run JavaScript, and 404 rates were 34.82% (ChatGPT) and 34.16% (Claude) against 8.22% for Googlebot.

## Measuring visibility

- [AEO natural experiment on ChatGPT referral traffic](https://arxiv.org/abs/2606.04362) (paper) - On one site, treated pages gained 1.82x more ChatGPT referrals than untreated pages (CI 1.31 to 2.54), but a placebo test did not clear (p=0.16), so the result is suggestive only.
- [Cloudflare Radar 2025 Year in Review](https://blog.cloudflare.com/radar-2025-year-in-review) (vendor, Cloudflare) - Crawl-to-refer ratios were 25,000 to 100,000 to 1 for Anthropic, up to 3,700 to 1 for OpenAI, under 200 to 1 for Perplexity and about 3 to 1 for Google.
- [Paraphrase Brittleness in RAG Commercial Recommendation](https://arxiv.org/abs/2605.27440) (paper) - Paraphrases of one intent named overlapping brands only 0.135 to 0.288 of the time (Jaccard), so a fixed prompt set measures your wording.
- [r/juststart: 0 to 43 AI citations, week 3](https://www.reddit.com/r/juststart/comments/1syovm1/) (practitioner, *[not re-checked]*) - Several hundred ChatGPT-User fetches in 8 hours of firewall logs showed up as 1 click in GA4 (poster's count: 398 hits), so server logs see what analytics misses.
- [r/juststart: GEO experiment on static GitHub Pages](https://www.reddit.com/r/juststart/comments/1sb46r8/) (practitioner, *[not re-checked]*) - Two GEO checker tools scored the same page 95 and 18.
- [Reddit citations are dropping in ChatGPT](https://promptwatch.com/data/reddit-citations-are-dropping-in-chatgpt) (vendor, Promptwatch) - Reddit's share of ChatGPT citations fell 86% between early August and 17 August 2026, so a single-source tactic can expire in days.
- [Scoring With the Engine](https://arxiv.org/abs/2609.22655) (paper) - Four engines shared almost no cited URLs (mean Jaccard 0.0079), and one engine's URL set turned over 67% in one to two days.

## Programmatic SEO

- [I built 225 programmatic SEO pages, Google indexed 18%](https://arnjen.com/blog/programmatic-seo-225-pages-google-indexed-18-percent) (practitioner) - 41 of 225 pages were indexed, hubs with real text got in 13 of 15, and card-grid hubs got in 0 of 15.
- [r/bigseo: 60% of the pages got deindexed](https://www.reddit.com/r/bigseo/comments/1t0xwsy/) (practitioner, *[not re-checked]*) - Of about 800 template pages, 60% were deindexed by month 4, and the survivors had a data point found nowhere else and links from two or more hand-written pages.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md). One entry per pull request, with a source.

## Maintained by vawe-hq

Kept by the team behind [vawe](https://vawe.dev), an open-source HTML-to-video framework for coding agents. License: [CC0 1.0](LICENSE).
