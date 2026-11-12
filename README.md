# Sangrish Saigiridhar

I build AI systems that people actually use at work: LLM agents, document extraction and data pipelines, shipped to production for manufacturing clients.
MSc Business Analytics & AI at Warwick Business School · Coventry, UK

[sangrish.com](https://www.sangrish.com)  WIP so dont judge xD
[LinkedIn](https://linkedin.com/in/sangrish)

---

### How I use LLMs

- **They read messy input. They are never the source of truth for a number.** Extraction models in my pipelines may only quote text that exists in the source document. Anything they can't ground goes to a human.
- **Not everything should be an LLM.** When planners need numbers that match their spreadsheet to the decimal, I write a deterministic engine and prove parity against the old process.
- **Measure before you claim.** My KV-cache research started out "beating" H2O. Then I found the win was a bug in my own baseline, and I published the correction ([kvs-cache](https://github.com/Sangrish-braincade/kvs-cache)).

### Production work

The client code is private. I'm happy to walk through any of it.

| Built | How it works | Outcome |
|---|---|---|
| **Purchase-order → SAP pipeline** | AWS Textract OCR + Claude. The model may only quote text the OCR actually found, and any ungrounded field blocks posting until a person reviews it. | Its parity audit exposed a **$373,287** accounts-receivable overstatement in the legacy process |
| **AI CRM lead tool** | Next.js + AWS Bedrock. Deduplicates lead spreadsheets, classifies each company against the live Dynamics 365 schema, and uploads only after human approval. Per-user Microsoft sign-in attributes each record to the right salesperson. | Replaced a manual IT-upload and qualification workflow |
| **Natural-language business assistant** | A planner-driven agent that searches CRM, SharePoint, email and Power BI, including a natural-language-to-DAX tool over six dashboards | Replaced four separate systems for routine data questions |
| **Supply-planning engine** | Deterministic on purpose, with no LLM in the loop | Matched the planners' workbook at **100.000%** on days of supply; three planning cycles accepted into production |
| **Dust-detection vision model** | Trained from hand-annotated data and deployed on an automotive supplier's inspection line | Inspects **~100,000 parts a day** |

### Open source

| Repo | What it is |
|---|---|
| [**cov-leam-crime-map**](https://github.com/Sangrish-braincade/cov-leam-crime-map) | [Live](https://covcrimeinfo.warwickly.com). 36 months of police.uk crime for Coventry and Leamington as a hex map for students, plus local crime news matched to police records. Git is the database: daily GitHub Actions commit new data and Amplify rebuilds. Article text is never stored or sent to an AI model. |
| [**kvs-cache**](https://github.com/Sangrish-braincade/kvs-cache) | An ablation study of KV-cache eviction for GQA LLMs (Qwen2.5-3B, Llama-3.2-3B) on one 8 GB GPU, including a documented correction of my own earlier result |
| [**vortex**](https://github.com/Sangrish-braincade/vortex) | A video editor built for AI agents, in Rust. An agent writes edit scripts that the engine runs, exposed as an MCP server. |
| [**cursor-coach**](https://github.com/Sangrish-braincade/cursor-coach) | A voice-driven desktop guide. Whisper runs locally, a vision model reads the screen, and a mascot points to what to click. It teaches; it never clicks for you. |
| [**sang-town**](https://github.com/Sangrish-braincade/sang-town) | [My portfolio](https://www.sangrish.com) as a small 3D town you walk around (Three.js) |

### Before this

- **Co-founder & Head of AI, Aicade** (2023–2026). Led a seven-person team building a text-to-game platform that produces playable 2D games in under 60 seconds.
- **Founder, Pulstra** (solo, part-time). Built and sold a RAG-based research-discovery product to ~300 paying customers.
- **Samsung R&D PRISM** (AI research assistant, RAG) · **Satoshi Terminal** (multi-region AWS infrastructure)
- **Published:** ship-hull defect detection and segmentation, *Results in Engineering* vol. 30 (3rd of 9 authors)

### Stack

`Python` `TypeScript` `SQL` · `FastAPI` `Next.js` `React` · `PostgreSQL` `Supabase` `MongoDB` · `AWS (Bedrock, Textract, ECS, Lambda)` `GCP Cloud Run` · `Dynamics 365` `Power BI / DAX` `SharePoint` · LLM agents, tool calling, structured outputs, RAG
