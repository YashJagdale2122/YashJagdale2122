<div align="center">

# Yash Jagdale — Backend & AI Platform Engineer

</div>

**2 years of hands-on experience** building production Python/FastAPI systems for AI-powered intelligence platforms at **C-DAC (Government of India R&D)**.

I specialize in the **infrastructure layer of AI systems** — not model research. My work is about making AI models reliable, fast, and scalable in production under real constraints.

---
## Technical Projects & Architecture Showcase

The repositories below are public reconstructions of patterns I've built in production — NDA prevents sharing original platform code, but the underlying system design and engineering metrics are identical.

**[leakdb-platform-engine](https://github.com/YashJagdale2122/leakdb-platform-engine)**
Distributed cyber threat intelligence pipeline architecture engineered to ingest, parse, and index massive unstructured data leaks out-of-band.
* **Architecture**: Engineered an asynchronous FastAPI edge gateway utilizing connection pooling (`asyncpg`) to return instant HTTP `202 Accepted` handshake acknowledgments, offloading heavy processing workloads off the client loop.
* **Broker & Queue**: Replaced single-threaded Redis topologies with **DragonflyDB** to handle distributed Celery state via its multi-threaded, shared-nothing architecture using Linux `io_uring` primitives.
* **Memory Safety**: Hardened worker execution blocks against fatal Out-of-Memory (OOM) container crashes by deploying memory-safe, multi-part chunked byte streaming generators restricted to a strict 32 KB allocation window.
* **AI Pipelines**: Implemented a three-tier high-availability OCR fallback cascade (Florence-2, preprocessed Tesseract with CLAHE contrast filtering, and EasyOCR) alongside binary EXIF metadata extraction and parameterized Neo4j Cypher graph mapping.

**[video-intelligence-backend](https://github.com/YashJagdale2122/video-intelligence-backend)**
FastAPI backend with state-machine job lifecycle and async worker pool. Key architectural decision: AI model stages isolated behind a common interface enabling hot-swap of inference backends without pipeline changes.

**[backend-job-processing](https://github.com/YashJagdale2122/backend-job-processing)**
State-machine-driven job lifecycle engine (PENDING → RUNNING → COMPLETED / FAILED / RETRYING) with clean API/Service/Repository/Domain separation and queue-agnostic worker architecture.

---

## What I've Actually Built (Production Experience)

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

**Backend & Systems:** Python · FastAPI · Asyncio · Celery · Dragonfly · Redis (RESP) · PostgreSQL · SQLAlchemy · Docker · Docker Compose · Nginx · Tor Proxy · Linux

**Data & Analytics Fabrics:** Elasticsearch Cluster v8.x · Qdrant Vector DB · ClickHouse · Neo4j Graph DB · MinIO Object Storage

**AI & Inference Infrastructure:** LLM Serving & Optimization · RAG Pipelines (Parent-Child Chunking, Embedding APIs) · Model Orchestration (vLLM/Ollama) · Computer Vision · Vector Clustering · Speech-to-Text

**Architecture:** Asynchronous Architectures · System Design (HLD/LLD) · Multi-Tenant SaaS Isolation · Clean Architecture · SOLID · Graph Database Design

---

## How I Think

- **Systems over scripts** — I design for failure, retries, and observability from the start
- **Constraints are features** — Air-gapped deployment, shared GPU, limited VRAM forced better architecture decisions than unlimited cloud would have
- **Infrastructure owns the pipeline** — AI models are components, not the system
- **Depth over breadth** — I'd rather understand one system completely than touch ten shallowly

---

## Currently

- **Available Immediately**
- Completing LangChain & Vector Databases in Production (Activeloop / DeepLearning.AI)
- Seeking Backend / AI Platform Engineer roles in **Pune or Remote**

---

## Contact

- LinkedIn: [linkedin.com/in/yash-jagadale](https://linkedin.com/in/yash-jagadale)
- Email: yashjagadale21@gmail.com
- Location: Pune, India
