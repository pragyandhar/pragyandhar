<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=210&section=header&color=0:0B0F19,45:4C1D95,100:06B6D4&text=Pragyan%20Chandra%20Dhar&fontColor=EDE9FE&fontSize=42&fontAlignY=34&desc=Backend%20%2B%20AI%20Systems%20%C2%B7%20RAG%20%C2%B7%20Multi-Agent%20Orchestration&descSize=16&descAlignY=54&animation=fadeIn" />

<a href="https://linkedin.com/in/pragyan-dhar">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&pause=1200&color=22D3EE&center=true&vCenter=true&width=720&height=45&lines=Backend+%2B+AI+systems+engineer;RAG+pipelines+that+survive+real+traffic;3%2C100%2B+MAU+%C2%B7+~3s+latency+%C2%B7+%2420%2Fmo+inference;Measured%2C+not+vibes" alt="Typing SVG" />
</a>

<br/>

<a href="https://linkedin.com/in/pragyan-dhar"><img src="https://img.shields.io/badge/LinkedIn-pragyan--dhar-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0B0F19" /></a>
<a href="https://github.com/pragyandhar"><img src="https://img.shields.io/badge/GitHub-pragyandhar-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0B0F19" /></a>
<a href="mailto:pragyandhar@gmail.com"><img src="https://img.shields.io/badge/Email-pragyandhar%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0B0F19" /></a>
<img src="https://img.shields.io/badge/Location-Delhi%2C%20IN-A78BFA?style=for-the-badge&logo=googlemaps&logoColor=white&labelColor=0B0F19" />

<img src="https://komarev.com/ghpvc/?username=pragyandhar&label=PROFILE+VIEWS&color=6D28D9&style=for-the-badge" alt="profile views" />

</div>

---

```yaml
# ~/pragyandhar/manifest.yaml
identity:
  name:      Pragyan Chandra Dhar
  role:      B.Tech CSE — AI/ML Specialization @ GLA University, Mathura
  graduates: 2027
  based_in:  Delhi, India

what_i_do:
  - Design retrieval systems that answer correctly and cheaply, at the same time
  - Orchestrate LLM agents with checkpointing, retries and human-in-the-loop gates
  - Instrument everything — if it isn't measured, it isn't shipped

operating_principles:
  - Latency and cost are product features, not afterthoughts
  - A cache hit is the cheapest inference you will ever run
  - Every LLM output is untrusted input until something validates it

currently:
  building:  reliability + evaluation tooling for LLM-generated code
  learning:  distributed systems, retrieval evaluation, low-level design
  open_to:   AI/ML engineering and backend internships & full-time roles
```

---

## Live in production

Not a side project. Real users, real invoices, real on-call.

### **AskGLA** — AI Admissions Assistant · *deployed on GLA University's official website*

| Signal | Value |
| :--- | :--- |
| Queries served | **~8,000** across 4,000+ sessions in 30 days |
| Monthly active users | **3,100+** |
| Average latency | **~3s** end-to-end |
| Cache hit rate | **~35%** resolved with zero LLM calls |
| Inference cost | **~$20/month** — about **₹0.21 per conversation** |
| Conversion impact | **270+** high-intent leads · **300+** admission-conversion clicks |
| Surfaces | Web widget · Chrome extension · Admin console |
| Languages | English · Hindi · Hinglish |

**Stack:** FastAPI · React · Azure · Supabase/Postgres (pgvector) · Redis · Docker · GitHub Actions
**Retrieval:** hybrid — pgvector dense + BM25 sparse + cross-encoder reranking
**Guided by:** Prof. Dr. Ram Manohar Nisarg · Prof. Gaurav Bathla · Prof. Dr. Ashok Bhansali

---

## How I think about a request

The same shape shows up in everything I build — spend nothing until you have to, and never trust the model's output blindly.

```mermaid
flowchart LR
    U(["Incoming query"]) --> C{"Cache layer<br/>Redis · memory · file"}
    C -- "~35% hit" --> OUT(["Response · zero LLM cost"])
    C -- "miss" --> R["Hybrid retrieval<br/>pgvector + BM25"]
    R --> RR["Cross-encoder<br/>reranking"]
    RR --> L["LLM synthesis"]
    L --> V{"Validation gate<br/>citations · severity scoring"}
    V -- "fails" --> L
    V -- "passes" --> OUT
    OUT --> A["Telemetry<br/>latency · cost · funnel"]
    A -.->|"tunes"| C

    classDef entry fill:#4C1D95,stroke:#A78BFA,stroke-width:2px,color:#EDE9FE
    classDef work  fill:#0F172A,stroke:#22D3EE,stroke-width:1.5px,color:#E2E8F0
    classDef gate  fill:#1E1B4B,stroke:#F472B6,stroke-width:2px,color:#FBCFE8
    classDef obs   fill:#052E2B,stroke:#34D399,stroke-width:1.5px,color:#D1FAE5

    class U,OUT entry
    class R,RR,L work
    class C,V gate
    class A obs
```

---

## Things I've built

<table>
<tr>
<td width="50%" valign="top">

### 🧭 Khoj
**Multi-Agent Research Orchestration**

LangGraph orchestration across **5 specialised agents**, with PostgreSQL checkpointing and time-travel debugging.

- Exponential-backoff retry logic → **−70% agent failure rate**
- Redis caching with MD5 fingerprinting → **−40% redundant LLM spend**
- SSE token streaming, human-in-the-loop interrupt gates, citation-verification subgraph
- Repository Pattern architecture — non-LLM endpoints hold **sub-50ms** under concurrent load

`Python` `FastAPI` `LangGraph` `LangChain` `PostgreSQL` `Redis` `ChromaDB` `React` `Docker` `Tavily`

</td>
<td width="50%" valign="top">

### 🛡️ Shinrai
**AI Code Reliability Layer**

An async validation pipeline that treats LLM-generated code as guilty until proven safe.

- **12 reliability and security checks** → ~70% lower faulty-deployment risk
- Tiered severity scoring (Critical/Major/Minor) with weakest-link aggregation — 3-dimension confidence in **<200ms**
- Auto-repair loop re-prompts the model with structured issue context → **~80%** of low-confidence code fixed within 3 retries

`FastAPI` `Celery` `Redis` `SQLite` `Azure AI Foundry` `Bandit` `Ruff` `Mypy` `pip-audit` `Docker`

</td>
</tr>
</table>

---

## Stack

<div align="center">

**Languages**

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white&labelColor=0B0F19" />

**AI / Orchestration**

<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/LangGraph-4C1D95?style=for-the-badge&logo=graphql&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/CrewAI-6D28D9?style=for-the-badge&logo=openai&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/RAG_Pipelines-22D3EE?style=for-the-badge&logo=elasticsearch&logoColor=black&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Multi--Agent_Systems-A78BFA?style=for-the-badge&logo=probot&logoColor=black&labelColor=0B0F19" />

**Backend**

<img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/SQLAlchemy-C63C1E?style=for-the-badge&logo=sqlalchemy&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black&labelColor=0B0F19" />

**Data & Vectors**

<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Pinecone-000000?style=for-the-badge&logo=pinecone&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logo=qdrant&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/ChromaDB-FF6B35?style=for-the-badge&logo=databricks&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white&labelColor=0B0F19" />

**Infrastructure**

<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white&labelColor=0B0F19" />
<img src="https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=black&labelColor=0B0F19" />

</div>

<details>
<summary><b>System design patterns I actually use →</b></summary>

<br/>

| Pattern | Where it earned its keep |
| :--- | :--- |
| Hybrid retrieval (dense + sparse + rerank) | AskGLA — recall from BM25, precision from the reranker |
| Multi-layer caching (Redis → memory → file) | Cut ~35% of traffic before it ever reaches a model |
| Async pipelines with Celery workers | Shinrai — 12 parallel checks without blocking the API |
| Fault-tolerant checkpointing | Khoj — resume a 5-agent graph from any prior state |
| Repository Pattern | Keeps non-LLM endpoints under 50ms regardless of agent load |
| Human-in-the-loop interrupt gates | Never let an agent commit an irreversible step unreviewed |
| Multi-tenant architecture | One deployment, isolated data boundaries |

</details>

---

## GitHub

<div align="center">

<img height="165" src="https://github-stats-extended.vercel.app/api?username=pragyandhar&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&title_color=A78BFA&icon_color=22D3EE&text_color=C9D1D9&bg_color=0D1117" />
<img height="165" src="https://github-stats-extended.vercel.app/api/top-langs/?username=pragyandhar&layout=compact&langs_count=8&hide_border=true&title_color=A78BFA&text_color=C9D1D9&bg_color=0D1117" />

<br/><br/>

<img src="https://streak-stats.demolab.com?user=pragyandhar&hide_border=true&background=0D1117&stroke=4C1D95&ring=22D3EE&fire=F472B6&currStreakLabel=A78BFA&sideLabels=C9D1D9&currStreakNum=EDE9FE&sideNums=C9D1D9&dates=8B949E" />

</div>

---

## Beyond the terminal

- 🎤 Delivered a **7-hour Power BI workshop** at TechNavya'24, GLA University's official tech fest
- 📚 Taught for a year in **Ajhai village** with the Udaan Asma Tak NGO — the best debugging practice I've had is explaining something to someone who has no reason to pretend they understood
- 🎓 CGPA **8.23/10** · Class 12 **85%** · Class 10 **95%**

---

## Talk to me about

<div align="center">

`retrieval evaluation` · `cutting inference cost without cutting quality` · `agent failure modes` · `caching strategy` · `Postgres over a vector DB, and when it stops being true` · `shipping student projects to real users`

</div>

<br/>

<div align="center">

**Open to AI/ML engineering and backend roles.**
If you're hiring for systems that have to stay up — let's talk.

<a href="https://linkedin.com/in/pragyan-dhar"><img src="https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0B0F19" /></a>
<a href="mailto:pragyandhar@gmail.com"><img src="https://img.shields.io/badge/Send_a_mail-EA4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0B0F19" /></a>

<img src="https://capsule-render.vercel.app/api?type=waving&height=120&section=footer&color=0:06B6D4,55:4C1D95,100:0B0F19" />

</div>
