# Nicolás Muñoz García

Physics undergraduate at the University of Salamanca. I build software for scientific discovery, and I work to make research and AI reachable for the people around me.

## About

I am in the second year of a four-year physics degree (expected graduation, 2029). My interests sit in astrophysics, astronomy and cosmology — the questions that made me choose the degree in the first place.

I write software because a research problem needed it, not the other way around. Everything below started as something I wanted to exist and could not find.

## PaperTok

**[papertok.app](https://papertok.app/#/)** · **[source](https://github.com/mugar123/papertok)**

An open-source web application for discovering scientific literature through a personalized, scrollable feed.

It started with a problem I ran into as a student: an enormous amount of interesting research is freely available, yet finding anything outside a narrow, well-formed search query remains difficult. PaperTok lets you browse instead of query — you interact with papers, follow topics, authors and institutions, and the feed gradually learns what you care about while deliberately leaving room for results you would not have looked for.

Beyond the feed, it includes a reader that rewrites papers at three levels of background, per-paper annotations, LaTeX export, an interactive citation map, and a periodical *Research* section that surveys what is worth attention over a chosen span of time. The recommendation engine is built inside the project rather than delegated to a third-party API, so its signals — explicit preferences, learned affinity, following, recency, citation impact, semantic relevance and exploration — remain inspectable and adjustable.

| Layer | Built with |
| --- | --- |
| Interface | React 19, Vite, Tailwind CSS 4, Radix UI, Framer Motion, KaTeX |
| API | Cloudflare Workers, Workers KV for caching and rate-limit accounting |
| Data and identity | Firebase Authentication, Cloud Firestore, security rules covered by an emulator-run test suite |
| Sources | arXiv, OpenAlex, PubMed, Semantic Scholar, OpenReview, NIH iCite, Hugging Face Hub and others, normalized into a single record shape |
| Language models | Gemini, with a DeepSeek and Kimi fallback chain, streamed to the client |
| Delivery | Vercel for the front end, Cloudflare for the API, Node's test runner and ESLint on every change |

The interface ships in English and Spanish, installs as a standalone app, and labels every paper honestly — whether it passed peer review, and whether you can actually read it — showing nothing rather than guessing when the record does not say.

Around a hundred people have used it so far. I have never promoted it: I sent the link to a few classmates, and it travelled from there.

## Working with AI

I have followed this field closely since GPT-3.5, and I have moved from reading about it to depending on it in production.

**Running models in the open.** PaperTok's AI features are not a single API call behind a spinner. Requests fall through a chain of providers so one outage does not take the feature down, responses stream so the reader is never left staring at silence, and anything that costs money states its price before you spend it and refunds the charge when the request fails. Most of the engineering in that feature is about failure and cost, not about prompts.

**Evaluating what ships.** I read the technical reports that accompany each model release, follow the research, and watch how benchmarks move — but I decide with my own tests, running new models against problems I actually have. A benchmark tells you what a model can do; only your own workload tells you whether it does what you need.

**Building with agentic tools.** PaperTok is written with heavy use of AI-assisted development. I have worked with Codex and Antigravity as well, and settled on Claude Code because its workflow is the one I adapt to best — chosen the same way I choose models, by running the real job through each of them. I have firm opinions about doing this well. I delegate work I can specify precisely and verify cheaply. I do not delegate architecture, security boundaries, or the decision about what is worth building. Every change arrives as a diff I read before it lands, and the practices below exist because AI-assisted code needs harder verification, not softer.

## On campus

I am part of **Supernova**, a student astronomy organization at the University of Salamanca. We run outreach workshops — open to anyone, not only to students — and observation outings for our members. Most of it is logistics and explanation: standing in front of people who are curious and have no background yet, which is the part that decides whether a first look through a telescope becomes a second one.

That is also where PaperTok's first users came from. I like building things for people I can actually talk to afterwards.

## How I work

A few practices this project has made non-negotiable:

- **A test earns its place by failing.** I verify coverage by mutation: break the code on purpose, and if the suite stays green the test was decorative.
- **Measure before optimizing.** Performance work starts with a profile of the real deployment, not with a guess about which line is slow.
- **Close the gap by default.** When a limit protects something that matters, the safe value is the default, and the number that justifies it goes in the commit.

## What I am working toward

I want to keep building tools that make research easier to reach, and to help other science students get genuine use out of AI. Most of the people around me are curious about these tools and have no idea where to start — the distance between the two is smaller than it looks, and closing it is work I enjoy. I am open to collaboration, internships and community work in that direction.

## Contact

- [papertok.app](https://papertok.app/#/)
- [LinkedIn](https://www.linkedin.com/in/nicol%C3%A1s-mu%C3%B1oz-garc%C3%ADa-619489309/)
- [X / Twitter](https://x.com/therealmugar)
- nicomg60@gmail.com
