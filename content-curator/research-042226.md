# AI Intel Research — 04/22/26

> Daily file. 3 sweeps max. Each sweep appended below.

---

## Sweep 1 — 04/22/26

> Run time: ~08:00 PT (automated)

---

### Table of Contents

- [What's Hot Right Now](#s1-whats-hot)
- [Deep Dives](#s1-deep-dives)
  - [DD0: Gemini Enterprise Agent Platform](#s1-dd0)
  - [DD1: Google 8th-Gen TPUs for Agentic Era](#s1-dd1)
  - [DD2: MCP v2.1 + A2A v1.0 — The Agent Protocol Stack Solidifies](#s1-dd2)
  - [DD3: Qwen3.6-27B — Flagship Coding in a Dense 27B Model](#s1-dd3)
  - [DD4: AutomationBench — Cross-App Workflow Orchestration Benchmark](#s1-dd4)
  - [DD5: "All Your Agents Are Going Async" (HN signal)](#s1-dd5)
- [Raw Signals](#s1-raw-signals)

---

### <a name="s1-whats-hot"></a>What's Hot Right Now

- 🔥 **Google launches Gemini Enterprise Agent Platform** — full-stack BUILD/SCALE/GOVERN/OPTIMIZE platform replacing Vertex AI; 200+ models, Agent Memory Bank, cryptographic agent identity, A2A orchestration, Agent Gateway with prompt injection protection. → [Deep Dive](#s1-dd0)
- 🔥 **Google Cloud Next '26 drops 8th-gen TPUs purpose-built for agent inference** — TPU 8i delivers 11.6 exaflops FP8 at 80% better perf/dollar than Ironwood; first time Google explicitly brands hardware around "agentic era." → [Deep Dive](#s1-dd1)
- ⚡ **MCP v2.1 + A2A v1.0 are now the production stack** — Claude Desktop, Cursor, and Microsoft Agent Framework 1.0 all shipped full MCP support this week; A2A v1.0 adds Signed Agent Cards for cryptographic inter-agent identity. → [Deep Dive](#s1-dd2)
- 🧠 **Qwen3.6-27B hits HN top 5** — flagship-level coding in a dense 27B (no MoE tax), tops SWE-bench Pro and Terminal-Bench 2.0; China's open-weight push continues to compress the capability gap. → [Deep Dive](#s1-dd3)
- 📐 **AutomationBench drops** — first benchmark for cross-application workflow orchestration; agents must discover APIs autonomously and comply with business policies across domains. → [Deep Dive](#s1-dd4)
- 🔄 **"All Your Agents Are Going Async"** — HN thread (102 pts, 65 comments) around post arguing synchronous agent loops are the bottleneck and async-first design is the unlock for production scale. → [Deep Dive](#s1-dd5)

---

### <a name="s1-deep-dives"></a>Deep Dives

#### <a name="s1-dd0"></a>DD0: Gemini Enterprise Agent Platform ⚠️ *Added post-sweep — flagged by user*

**Why it's hot**
Google renamed and overhauled Vertex AI into the **Gemini Enterprise Agent Platform** at Cloud Next '26 today. This is no longer an incremental update — all future Vertex AI services will be delivered *exclusively* through this platform. It's the most complete enterprise agent stack any hyperscaler has shipped: four layers (Build / Scale / Govern / Optimize) each with production-grade features. Particularly notable: Agent Memory Bank with long-term persistence, cryptographic agent identity, Agent Gateway (prompt injection protection via Model Armor), anomaly detection, and native A2A + AP2 (agent payment protocol) support.

**Signals**
- Agent Studio (low-code) + ADK (code-first, graph-based sub-agent networks) — covers both citizen developers and engineers
- Agent Runtime: sub-second cold starts, supports multi-day autonomous workflows
- Agent Memory Bank: Memory Profiles for high-accuracy recall + personalized sessions — Gurunavi case: 30%+ user satisfaction lift
- Payhawk: 50%+ reduction in expense submission time using Memory Bank
- PayPal: multi-agent workflows with AP2 (agent payment protocol) for secure commerce
- Agent Anomaly Detection: statistical models + LLM-as-a-judge — first enterprise-grade behavioral security layer
- 200+ models via Model Garden including Claude Opus/Sonnet/Haiku — not just Gemini-locked
- Agent Garden: pre-built templates (code modernization, financial analysis, invoice processing) — directly relevant for Intuit-adjacent workflows

**Angle for a post**
*"Google's Gemini Enterprise Agent Platform: the full breakdown"* — walk the BUILD/SCALE/GOVERN/OPTIMIZE framework layer by layer, highlight what's genuinely new vs. Vertex AI rebrand, and compare governance features (Agent Identity, Gateway, Anomaly Detection) against what AWS Bedrock and Azure AI Foundry currently offer. Strong post for the finance/enterprise-AI audience.

**Links**
- Announcement: https://cloud.google.com/blog/products/ai-machine-learning/introducing-gemini-enterprise-agent-platform
- Console: https://console.cloud.google.com/agent-platform/overview

---

#### <a name="s1-dd1"></a>DD1: Google 8th-Gen TPUs for Agentic Era

**Why it's hot**
Google announced two new chips at Cloud Next '26: TPU 8t (training) and TPU 8i (inference). The inference chip is explicitly optimized for "intricate, collaborative, iterative work of many specialized agents." This is the first time a major hyperscaler has publicly scoped silicon design around multi-agent patterns — not just transformer inference generally.

**Signals**
- TPU 8i: 11.6 exaflops FP8, 331.8TB HBM per pod, 19.2 Tbps scale-up BW per chip
- TPU 8t: reduces frontier model training cycle "from months to weeks," 400Gbps scale-out
- Virgo Network: new interconnect with 4x datacenter BW increase
- GA "later this year" via Google AI Hypercomputer
- HN story score: 209, 110 comments

**Angle for a post**
_"Why Google built a chip for agents, not models"_ — the split into 8t/8i mirrors how the industry thinks about agent infra: long-horizon training jobs vs. high-throughput, low-latency inference bursts from coordinating agents. First principles explainer on why agent workloads need different silicon than batch inference.

**Links**
- Blog: https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/eighth-generation-tpu-agentic-era/
- HN: https://news.ycombinator.com/item?id=47862497
- SemiAnalysis deep-dive: https://newsletter.semianalysis.com/p/tpuv7-google-takes-a-swing-at-the

---

#### <a name="s1-dd2"></a>DD2: MCP v2.1 + A2A v1.0 — The Agent Protocol Stack Solidifies

**Why it's hot**
This week every major IDE and agent framework shipped MCP v2.1 support (Claude Desktop, Cursor, Microsoft Agent Framework 1.0). A2A v1.0 launched Signed Agent Cards (cryptographic identity for inter-agent delegation) and AP2 extension (commerce/payment workflows). The layered model is now canonical: MCP = vertical (agent↔tools/data), A2A = horizontal (agent↔agent).

**Signals**
- Microsoft Agent Framework 1.0 ships with stable APIs + full MCP — enterprise adoption signal
- A2A now integrated across Microsoft, AWS, Salesforce, SAP, ServiceNow
- Claude Mythos Preview (Apr 7) available to 50 partner orgs via Project Glasswing
- The Register published "Deciphering the alphabet soup of agentic AI protocols" (Jan 2026) — topic has sustained 90-day mindshare
- A year ago A2A launched with 50 partners; today it's the horizontal coordination bus for production

**Angle for a post**
_"MCP + A2A: the TCP/IP moment for agents"_ — analogy to how TCP/IP separated concerns (transport vs. addressing) maps cleanly to MCP/A2A separation. Practical guide: when to use each, how they compose, what breaks if you conflate them.

**Links**
- DEV Community guide: https://dev.to/pockit_tools/mcp-vs-a2a-the-complete-guide-to-ai-agent-protocols-in-2026-30li
- Elasticsearch labs: https://www.elastic.co/search-labs/blog/a2a-protocol-mcp-llm-agent-newsroom-elasticsearch
- InfoQ architecture: https://www.infoq.com/articles/architecting-agentic-mlops-a2a-mcp/
- The Register: https://www.theregister.com/2026/01/30/agnetic_ai_protocols_mcp_utcp_a2a_etc/

---

#### <a name="s1-dd3"></a>DD3: Qwen3.6-27B — Flagship Coding in a Dense 27B Model

**Why it's hot**
Alibaba's Qwen3.6-27B is a dense (non-MoE) model that tops coding benchmarks against much larger models. It hit HN top 5 today (score 139, 70 comments). Alongside the 35B-A3B MoE and Max-Preview, the Qwen3.6 family now spans open-source and API tiers. The dense 27B variant matters most for local/edge deployment — no MoE routing overhead.

**Signals**
- Tops SWE-bench Pro, Terminal-Bench 2.0, SkillsBench, QwenClawBench, QwenWebBench, SciCode
- AMD Day 0 support on Instinct GPUs — supply chain coordination signal
- Qwen3.6-Plus: 1M context, 65K output tokens, always-on CoT, native function calling
- HN score: 139, 70 comments
- GitHub: https://github.com/QwenLM/Qwen3.6

**Angle for a post**
_"27B is the new 70B"_ — data-driven take on how coding benchmark scores shifted in 2025-26 such that a well-trained 27B dense model now matches 2024-era 70B models on agentic coding tasks. What this means for teams running local coding agents.

**Links**
- Qwen blog: https://qwen.ai/blog?id=qwen3.6-27b
- HN: https://news.ycombinator.com/item?id=47863217
- HuggingFace MoE variant: https://huggingface.co/Qwen/Qwen3.6-35B-A3B

---

#### <a name="s1-dd4"></a>DD4: AutomationBench — Cross-App Workflow Orchestration Benchmark

**Why it's hot**
New ArXiv paper (Apr 20) introducing the first benchmark for agents doing cross-application workflow orchestration — requiring autonomous API discovery and policy compliance across business domains. This fills a key gap: existing benchmarks test single-tool use; AutomationBench tests agents coordinating across heterogeneous enterprise APIs.

**Signals**
- ArXiv: https://arxiv.org/abs/2604.18934 (Daniel Shepard, Apr 20 2026)
- Complements SWE-bench (coding) by focusing on workflow integration rather than code synthesis
- Relevant to Intuit/enterprise context: agents routing across QB, payroll, tax APIs is exactly this pattern
- Google Cloud + Wiz shipping "Threat Hunting and Detection Engineering agents" this week — real enterprise demand for cross-app orchestration

**Angle for a post**
_"Why we need AutomationBench (and what it reveals about current agents)"_ — explainer on the benchmark design + early results showing where agents fail on multi-app workflows. Concrete implications for teams building finance/tax agent pipelines.

**Links**
- ArXiv: https://arxiv.org/abs/2604.18934
- Related: BONSAI human-AI co-dev workspace: https://arxiv.org/abs/2604.19247
- Context: ClawNet cross-user agent network: https://arxiv.org/abs/2604.19211

---

#### <a name="s1-dd5"></a>DD5: "All Your Agents Are Going Async"

**Why it's hot**
HN thread (102 pts, 65 comments) around https://zknill.io/posts/all-your-agents-are-going-async/ — arguing that synchronous request/response agent loops are the production bottleneck and the field is converging on async-first architectures. Strong practitioner signal given comment volume.

**Signals**
- HN score: 102, 65 comments — sustained engagement, not just upvote farming
- Connects to broader infra shift: langfuse (25K stars, trending today on GitHub) adding async trace support
- Prefill-as-a-Service paper (ArXiv 2604.15039) on cross-datacenter KV cache prefilling = infrastructure needed for async agent patterns
- Multi-agent systems Gartner stat: 1,445% surge in inquiries Q1'24→Q2'25

**Angle for a post**
_"Async agents: the architecture shift nobody's talking about"_ — why sync loops feel natural but break at scale, what async-first agent design looks like in practice, what infra primitives (queues, async evals, async trace) you need. Frame against the Prefill-as-a-Service paper for the infra angle.

**Links**
- Post: https://zknill.io/posts/all-your-agents-are-going-async/
- HN: https://news.ycombinator.com/item?id=47821853
- Prefill-as-a-Service ArXiv: https://arxiv.org/abs/2604.15039

---

### <a name="s1-raw-signals"></a>Raw Signals

#### HackerNews — Top AI/LLM Stories (Top 30 filtered, top 5 by score)

| Score | Comments | Title | URL |
|------:|--------:|-------|-----|
| 960 | 841 | ChatGPT Images 2.0 | https://openai.com/index/introducing-chatgpt-images-2-0/ |
| 749 | 901 | SpaceX says it has agreement to acquire Cursor for $60B | https://twitter.com/spacex/status/2046713419978453374 |
| 209 | 110 | Our eighth generation TPUs: two chips for the agentic era | https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/eighth-generation-tpu-agentic-era/ |
| 145 | 122 | Show HN submissions tripled and now mostly have the same vibe-coded look | https://www.adriankrebs.ch/blog/design-slop/ |
| 139 | 70 | Qwen3.6-27B: Flagship-Level Coding in a 27B Dense Model | https://qwen.ai/blog?id=qwen3.6-27b |

*Note: Also notable — "All your agents are going async" (102 pts, 65 cmts), "Kernel code removals driven by LLM-created security reports" (78 pts), "MuJoCo Advanced Physics Simulation" (81 pts)*

#### GitHub Trending — Daily (top 5 AI-related)

| Repo | Stars Total | Daily Δ | Lang | Description |
|------|------------|---------|------|-------------|
| zilliztech/claude-context | 7,256 | +873 | TypeScript | Code search MCP for Claude Code — entire codebase as agent context |
| HKUDS/RAG-Anything | 17,385 | +770 | Python | All-in-One RAG Framework |
| langfuse/langfuse | 25,463 | +160 | TypeScript | Open source LLM observability: metrics, evals, prompt management |
| koala73/worldmonitor | 51,278 | +449 | TypeScript | Real-time global intelligence dashboard, AI-powered news aggregation |
| sansan0/TrendRadar | 54,306 | +932 | Python | AI-driven public opinion & trend monitor, multi-platform aggregation |

#### Google AI Blog — 8 Most Recent

| Date | Title | URL |
|------|-------|-----|
| Apr 22 2026 | We're launching two specialized TPUs for the agentic era | https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/tpus-8t-8i-cloud-next/ |
| Apr 21 2026 | 3 new ways Ads Advisor is making Google Ads safer and faster | https://blog.google/products/ads-commerce/ads-advisor-google-ads/ |
| Apr 17 2026 | 7 ways to travel smarter this summer, with help from Google | https://blog.google/products-and-platforms/products/search/summer-travel-tips-google-search-ai/ |
| Apr 16 2026 | A new way to explore the web with AI Mode in Chrome | https://blog.google/products-and-platforms/products/search/ai-mode-chrome/ |
| Apr 16 2026 | New ways to create personalized images in the Gemini app | https://blog.google/innovation-and-ai/products/gemini-app/personal-intelligence-nano-banana/ |
| Apr 15 2026 | Gemini 3.1 Flash TTS: the next generation of expressive AI speech | https://blog.google/innovation-and-ai/models/gemini-models/gemini-3-1-flash-tts/ |
| Apr 14 2026 | Turn your best AI prompts into one-click tools in Chrome | https://blog.google/products-and-platforms/products/chrome/skills-in-chrome/ |
| Apr 14 2026 | Bringing people together at AI for the Economy Forum | https://blog.google/company-news/outreach-and-initiatives/creating-opportunity/ai-economy-forum/ |

#### ArXiv — LLM Agents + AI Orchestration (top 5 by recency, deduped)

| Date | Title | First Author | URL |
|------|-------|-------------|-----|
| Apr 21 2026 | PlayCoder: Making LLM-Generated GUI Code Playable | Zhiyuan Peng | https://arxiv.org/abs/2604.19742 |
| Apr 21 2026 | Time Series Augmented Generation for Financial Applications | Anton Kolonin | https://arxiv.org/abs/2604.19633 |
| Apr 21 2026 | Integrating Anomaly Detection into Agentic AI for Proactive Risk Management | Farbod Zorriassatine | https://arxiv.org/abs/2604.19538 |
| Apr 21 2026 | ClawNet: Human-Symbiotic Agent Network for Cross-User Autonomous Cooperation | Zhiqin Yang | https://arxiv.org/abs/2604.19211 |
| Apr 20 2026 | AutomationBench: Cross-Application Workflow Orchestration Benchmark | Daniel Shepard | https://arxiv.org/abs/2604.18934 |

#### X / Twitter — Signal Posts

| Handle | Signal | URL |
|--------|--------|-----|
| @mirra | Introducing Agentic Solution Systems — new architecture for autonomous agent coordination in personal computing | https://x.com/mirra/status/2039426094672281645 |
| @aixbt_agent | Agent narrative has the velocity right now: NARA agent-native L1, Ghast AI decentralized assistant | https://x.com/aixbt_agent/status/2043365900326404335 |
| @omarsar0 | LLM agents follow "detailed balance" macroscopic physical law — discovery applies across models | https://x.com/omarsar0/status/2000626975296405525 |
| @AndrewYNg | New course: LLMs as Operating Systems — Agent Memory (Letta AI) | https://x.com/AndrewYNg/status/1854587401018261962 |
| @Python_Dv | AI Engineering vs Agentic AI — career breakdown 2026, hiring expectations shifting toward orchestration skills | https://x.com/Python_Dv/status/2027979897822740792 |
| @Marktechpost | A-MEM: Agentic memory system for LLM agents enabling dynamic memory structuring (Rutgers/Ant/Salesforce) | https://x.com/Marktechpost/status/1896045837362602036 |

#### Star History / Velocity Observations

- **Top weekly gainer (Apr 15–21):** `forrestchang/andrej-karpathy-skills` +5,739 stars — Karpathy-adjacent content drives massive velocity
- **NousResearch/hermes-agent** +3,830 — agent framework momentum continues
- **VoltAgent/awesome-design-md** +1,761; **JuliusBrussee/caveman** +1,698 — creative/coding agents trending
- From trending today: `sansan0/TrendRadar` (54K stars, +932 daily) and `zilliztech/claude-context` (+873) are the standout velocity stories
- langfuse at 25K total with +160/day — sustained LLM observability demand, not a spike

#### TLDR AI Newsletter — 04/22/26 *(added post-sweep; source added to spec)*

| Section | Title | URL |
|---------|-------|-----|
| Headlines | ChatGPT Images 2.0 | https://openai.com/index/introducing-chatgpt-images-2-0/ |
| Headlines | OpenAI "Hermes" — always-on agent platform for ChatGPT | https://www.testingcatalog.com/openai-develops-platform-for-always-on-agents-on-chatgpt/ |
| Headlines | Qwen3.5-Omni Technical Report — text/audio/image/video, 256k ctx | https://www.alphaxiv.org/abs/2604.15804 |
| Analysis | Coding agents ignore their own budgets (Ramp Labs) | https://x.com/RampLabs/status/2046624992956146158 |
| Analysis | When Can LLMs Learn to Reason with Weak Supervision? | https://salmanrahman.net/rlvr-weak-supervision |
| Engineering | CrabTrap — LLM-as-a-judge HTTP proxy for agent security | https://x.com/pedroh96/status/2046604993982009825 |
| Engineering | Google Stitch DESIGN.md format open-sourced | https://blog.google/innovation-and-ai/models-and-research/google-labs/stitch-design-md/ |
| Misc | Anthropic "Conway" — always-on agent with UI extensions (web + mobile) | https://www.testingcatalog.com/anthropics-works-on-its-always-on-agent-with-new-ui-extensions/ |
| Misc | Deep Research Max — Gemini 3.1 Pro autonomous research agents | https://blog.google/innovation-and-ai/models-and-research/gemini-models/next-generation-gemini-deep-research |
| Misc | Agent World Training Arena — self-evolving task environment | https://agent-tars-world.github.io/ |
| Misc | OpenAI Codex at 4M weekly active users; enterprise sales push | https://www.wsj.com/cio-journal/openai-is-working-with-consultants-to-sell-codex-f355b1b9 |
| Misc | Sam Altman criticizes Anthropic Mythos as "fear-based marketing" | https://techcrunch.com/2026/04/21/sam-altman-throws-shade-at-anthropics-cyber-model-mythos-fear-based-marketing/ |

*Notable TLDR-only scoops: OpenAI "Hermes" always-on agent platform (not in HN top 30); Anthropic "Conway" always-on agent; CrabTrap LLM-judge proxy; Ramp Labs finding that coding agents ignore token budgets.*

---

*Sweep 1/3 complete — 04/22/26*

---

## Sweep 2 — 04/22/26

> Run time: ~12:00 PT (manual — scheduled run missed; session was closed at dispatch time)

---

### Table of Contents

- [What's Hot Right Now](#s2-whats-hot)
- [Deep Dives](#s2-deep-dives)
  - [DD1: OpenAI Responses API — Built-in Agent Execution Loop + Shell Tool](#s2-dd1)
  - [DD2: Databricks Unity AI Gateway — MCP Governance for Agents](#s2-dd2)
  - [DD3: Over-editing in Coding Agents](#s2-dd3)
  - [DD4: Parallel Agents in Zed](#s2-dd4)
- [Raw Signals](#s2-raw-signals)

---

### <a name="s2-whats-hot"></a>What's Hot Right Now

- ⚙️ **OpenAI ships agent execution loop + shell tool in Responses API** — built-in container runtime, context compaction, reusable agent skills; no more DIY execution environments for agentic workflows. → [Deep Dive](#s2-dd1)
- 🔐 **Databricks Unity AI Gateway adds MCP governance** — fine-grained per-agent permissions for MCP server access, OBO auth, full MLflow tracing; Unity Catalog governance model now extends to agents. → [Deep Dive](#s2-dd2)
- ✂️ **"Over-editing" in coding agents surfaces as a real problem** — HN thread (143 pts, 71 cmts) on paper showing models modify code beyond what's necessary; direct implication for agent reliability. → [Deep Dive](#s2-dd3)
- ⚡ **Zed ships Parallel Agents** — multiple agents running concurrently inside the editor; first IDE to make parallelism a first-class feature, not a workaround. → [Deep Dive](#s2-dd4)

---

### <a name="s2-deep-dives"></a>Deep Dives

#### <a name="s2-dd1"></a>DD1: OpenAI Responses API — Built-in Agent Execution Loop + Shell Tool

**Why it's hot**
OpenAI extended the Responses API with a complete agent execution loop: the model proposes shell commands → API forwards to container runtime → output fed back into context → loop repeats until completion. Also adds reusable agent skills, context compaction, and hosted sandboxed workspace. Key implication: developers no longer need to hand-roll execution environments. This competes directly with Google's Agent Runtime (announced this morning in Gemini Enterprise Agent Platform).

**Signals**
- Shell tool: model proposes commands, API handles execution, streaming, retries, timeouts
- Hosted container: manages intermediate files, safe network access out of the box
- Context compaction: built-in — critical for long-horizon agent tasks
- Reusable agent skills: define once, invoke across agents
- InfoQ: "extending the Responses API to serve as a foundation for autonomous agents"
- VentureBeat: "support agent skills and a complete terminal shell"

**Angle for a post**
*"OpenAI just commoditized the agent execution layer"* — what it means that both Google (Agent Runtime) and OpenAI (Responses API loop) shipped managed execution environments the same day. The DIY agent scaffolding era is ending; the platform era is starting. What this means for teams using LangChain, CrewAI, or custom loops.

**Links**
- OpenAI announcement: https://openai.com/index/equip-responses-api-computer-environment/
- InfoQ: https://www.infoq.com/news/2026/03/openai-responses-api-agents/
- Shell tool docs: https://developers.openai.com/api/docs/guides/tools-shell

---

#### <a name="s2-dd2"></a>DD2: Databricks Unity AI Gateway — MCP Governance for Agents

**Why it's hot**
Databricks rebranded AI Gateway as Unity AI Gateway, folding it into Unity Catalog. The headline feature: MCP governance — fine-grained control over which agents can access which external MCP servers, with OBO (on-behalf-of) auth, audit logs, rate limits, and guardrails. MLflow Tracing gives end-to-end observability of every request and tool call. This is the enterprise data platform answer to the agent governance problem — distinct from Google's Agent Gateway in that it's data-platform-native, not cloud-infra-native.

**Signals**
- Supported OAuth providers: Glean, GitHub, Atlassian (Jira/Confluence), Google Drive, SharePoint — enterprise-ready connector set
- Unity Catalog audit logs: who accessed what, when, through which agent — compliance-ready
- Agent sprawl governance post on Databricks blog signals real customer pain
- Competes with: Google Agent Gateway, Azure AI Foundry governance, AWS Bedrock guardrails

**Angle for a post**
*"The MCP governance gap just got filled — by a data platform"* — why Databricks moving on MCP governance before the cloud hyperscalers is interesting; Unity Catalog already has the identity/permission graph for data; agents are just another consumer. Practical guide to what teams on Databricks should configure now.

**Links**
- Main announcement: https://www.databricks.com/blog/ai-gateway-governance-layer-agentic-ai
- MCP connection guide: https://www.databricks.com/blog/ai-gateway-how-connect-agents-external-mcps-securely
- Agent sprawl post: https://www.databricks.com/blog/governing-coding-agent-sprawl-unity-ai-gateway

---

#### <a name="s2-dd3"></a>DD3: Over-editing in Coding Agents

**Why it's hot**
HN story (143 pts, 71 comments): paper at https://nrehiew.github.io/blog/minimal_editing/ shows coding agents routinely modify code beyond what the task requires — "over-editing." This is a reliability/trust issue: agents that touch more than necessary introduce unintended regressions, make diffs harder to review, and erode developer trust. Directly relevant to the Ramp Labs finding from TLDR (sweep 1) that agents ignore token budgets — both point to agents lacking self-constraint.

**Signals**
- Strong HN engagement (71 comments) — practitioners validating this from experience
- Connects to sweep 1's TLDR signal: "coding agents ignore their own budgets" (Ramp Labs)
- Implication for agent evaluation: minimal edit rate should be a benchmark dimension alongside correctness
- AutomationBench (sweep 1 ArXiv) specifically evaluates policy compliance — same theme

**Angle for a post**
*"Your coding agent is doing too much — and that's the problem"* — frame over-editing as the flip side of under-capability; why minimal edit rate matters for production trust; what evaluation criteria teams should add to their agent evals today.

**Links**
- Paper: https://nrehiew.github.io/blog/minimal_editing/
- HN: https://news.ycombinator.com/item?id=47866913

---

#### <a name="s2-dd4"></a>DD4: Parallel Agents in Zed

**Why it's hot**
Zed shipped Parallel Agents — multiple agents running concurrently inside the editor. HN score: 79, 36 comments. While other IDEs (Cursor, VS Code) support agents sequentially, Zed is first to make parallel agent execution a first-class UI primitive. Pairs with the "all agents going async" theme from sweep 1 — async/parallel is emerging as the production-scale pattern across both tooling and architecture.

**Signals**
- HN score: 79, 36 comments
- Connects directly to sweep 1 DD5 ("All your agents are going async")
- Zed is Rust-based, performance-focused — parallel agents fits the brand
- No equivalent in Cursor or VS Code Copilot yet

**Angle for a post**
*"Zed just showed us what async-first agent UX looks like"* — short take on why parallelism in the editor matters, what workflows it unlocks (concurrent test + fix + refactor streams), and why this is a leading indicator of where all IDEs are heading.

**Links**
- Zed blog: https://zed.dev/blog/parallel-agents
- HN: https://news.ycombinator.com/item?id=47866750

---

### <a name="s2-raw-signals"></a>Raw Signals

#### HackerNews — New AI/LLM Stories Since Sweep 1 (top 5 by score)

| Score | Comments | Title | URL |
|------:|--------:|-------|-----|
| 143 | 71 | Over-editing refers to a model modifying code beyond what is necessary | https://nrehiew.github.io/blog/minimal_editing/ |
| 96 | 19 | Martin Fowler: Technical, Cognitive, and Intent Debt | https://martinfowler.com/fragments/2026-04-14.html |
| 79 | 36 | Parallel Agents in Zed | https://zed.dev/blog/parallel-agents |
| 31 | 7 | Workspace Agents in ChatGPT | https://openai.com/index/introducing-workspace-agents-in-chatgpt/ |
| 25 | 17 | Show HN: Broccoli — one-shot coding agent on the cloud (Linear → PR) | https://github.com/besimple-oss/broccoli |

#### GitHub Trending — Delta Since Sweep 1

| Repo | Stars Now | Δ Since Sweep 1 | Notes |
|------|----------|-----------------|-------|
| zilliztech/claude-context | 7,369 | +113 | Still accelerating |
| KeygraphHQ/shannon | 39,423 | +346 | **New entry** — AI security testing tool |
| HKUDS/RAG-Anything | 17,455 | +70 | Steady |
| langfuse/langfuse | 25,529 | +66 | Steady |
| Fincept-Corporation/FinceptTerminal | 12,924 | +116 | Steady |

*New entry: `KeygraphHQ/shannon` — autonomous white-box AI security testing (source code → exploit). Relevant given agent security theme running through today's sweeps.*

#### ArXiv — No new papers since sweep 1 (same top 5, all Apr 21)

#### TLDR AI — Same issue as sweep 1 (single daily edition). No new items.

#### X / Twitter — New Signals

| Handle/Source | Signal | URL |
|--------------|--------|-----|
| OpenAI | Workspace Agents in ChatGPT — Codex-powered, automate complex team workflows autonomously | https://openai.com/index/introducing-workspace-agents-in-chatgpt/ |
| Databricks Blog | Unity AI Gateway: governing coding agent sprawl with MCP fine-grained permissions | https://www.databricks.com/blog/governing-coding-agent-sprawl-unity-ai-gateway |
| InfoQ | OpenAI Responses API extended as foundation for autonomous agents | https://www.infoq.com/news/2026/03/openai-responses-api-agents/ |

#### Star History — No new data since sweep 1.

---

*Sweep 2/3 complete — 04/22/26*
