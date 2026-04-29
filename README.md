<div align="center">

# Yash Jagdale — Backend & AI Platform Engineer

</div>

**2 years of hands-on experience** building production Python/FastAPI systems for AI-powered intelligence platforms at **C-DAC (Government of India R&D)**.

I specialize in the **infrastructure layer of AI systems** — not model research. My work is about making AI models reliable, fast, and scalable in production under real constraints.

---

## What I've Actually Built

At C-DAC, I've built components of a large-scale AI intelligence platform running in an **air-gapped government environment**. Here's what that looks like in practice:

**Face Re-identification at Scale**
Built a pipeline that processes images at billion-record scale. Integrated InsightFace for detection, ran a 3-model forensics ensemble (anti-spoofing + deepfake detection + style classification) in priority-based decision logic, stored 512-dim ArcFace embeddings in Qdrant, and applied DBSCAN clustering (cosine similarity, eps=0.45) to group identities across the corpus. Output: a Streamlit forensics dashboard showing liveness scores, fake probabilities, and cluster-level identity browsing.

**Leaked Intelligence System**
Ingested 110+ databases across 85+ threat actor groups. Built LLM-driven PII extraction, S0–S3 sensitivity tagging with reasoning, and a Neo4j graph where LLM-generated Cypher queries construct entity relationships dynamically. Built a Kundali-style search that returns all cross-database associations (addresses, IDs, cards, transactions) for any target identity with source proof.

**Async Video Intelligence Pipeline**
Celery + Dragonfly broker, Playwright scraping, yt-dlp download to MinIO, WhisperX transcription with speaker diarization, translation, entity extraction, and top-100 comment sentiment analysis with relevance scoring. Smart re-analysis detects previously processed videos and updates only changed metrics — reducing re-processing from minutes to under 1 second.

**Dark Web Intelligence Pipeline**
Async Tor/I2P/clearnet URL checker with 3-tier timeout retry logic — reduced 10,000+ manual URL validations from months to under a week. FastAPI proxies Tor-rendered onion pages inline. Multi-user collaborative metadata tagging with history auto-fill.

**Architecture Migration**
Diagnosed file parsing errors, variable mismatches, and timeout failures in a legacy Tor network relay analysis tool. Refactored full architecture: Spark + MariaDB → ClickHouse + PostgreSQL, Django → React, cut hourly pipeline update failures to zero.

**Internal Productivity Platform**
FastAPI + PocketBase + React + locally-hosted Granite 3.0 4b LLM. AI summarization, RAG chatbot (Qdrant) answering HR policy queries, calendar task tracker, WhatsApp-style group chat, leave planning calendar, manager dashboard with real-time notifications.

---

## Tech Stack

**Backend:** Python · FastAPI · SQLAlchemy · REST APIs · Asyncio · Celery · Pytest

**AI & LLM Infrastructure:** LLM Serving & Inference Optimization · RAG Pipelines (Qdrant, chunking, embedding APIs) · Model Orchestration · Speech-to-Text Integration · Computer Vision · Vector Clustering · LangChain

**Data & Search:** PostgreSQL · Elasticsearch · MinIO · Qdrant · Redis · ClickHouse · Neo4j

**Systems & DevOps:** Docker · Docker Compose · Linux · GitHub Actions · Nginx · Dragonfly · Tor Proxy · JMeter

**Architecture:** System Design (HLD/LLD) · Async Architectures · Clean Architecture · SOLID · Graph Database Design

---

## Public Projects

The repos pinned below are public reconstructions of patterns I've built in production — NDA prevents sharing the original platform code, but the architecture and engineering decisions are the same.

**[video-intelligence-backend](https://github.com/YashJagdale2122/video-intelligence-backend)**
FastAPI backend with state-machine job lifecycle and async worker pool. Key architectural decision: AI model stages isolated behind a common interface enabling hot-swap of inference backends without pipeline changes.

**[backend-job-processing](https://github.com/YashJagdale2122/backend-job-processing)**
State-machine-driven job lifecycle engine (PENDING → RUNNING → COMPLETED / FAILED / RETRYING) with clean API/Service/Repository/Domain separation and queue-agnostic worker architecture.

---

## How I Think

- **Systems over scripts** — I design for failure, retries, and observability from the start
- **Constraints are features** — Air-gapped deployment, shared GPU, limited VRAM forced better architecture decisions than unlimited cloud would have
- **Infrastructure owns the pipeline** — AI models are components, not the system
- **Depth over breadth** — I'd rather understand one system completely than touch ten shallowly

---

## Currently

- Serving notice period at C-DAC — **available from June 3, 2026**
- Completing LangChain & Vector Databases in Production (Activeloop / DeepLearning.AI)
- Seeking Backend / AI Platform Engineer roles in **Pune or Remote**

---

## Contact

- LinkedIn: [linkedin.com/in/yash-jagadale](https://linkedin.com/in/yash-jagadale)
- Email: yashjagadale21@gmail.com
- Location: Pune, India
