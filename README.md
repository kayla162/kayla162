## Hi there 👋 I'm Kayla

AI application developer focused on turning LLMs, RAG and computer vision into reliable, measurable tools. I care about the parts that make AI usable in production: output guardrails, hallucination checks, evaluation sets, and cost and latency trade-offs.

### 🚀 Featured Projects

**[GenAI Agent Studio](https://github.com/kayla162/genai-agent-studio)** — Brand-compliant e-commerce posters from a one-line brief

- Multimodal agent: Plans copy and layout with Gemini structured output, grounded in a brand-guideline RAG (BGE-M3 + reranker, int8 ONNX), and generates backgrounds with SDXL inpainting on ComfyUI. The product photo stays untouched; only the background is regenerated.
- Automated compliance review: Runs 8 rule-based checks and 3 VLM checks, and caught 30/30 deliberately planted typos. Failed posters are regenerated after query rewriting; in a fluorescent-color test case, off-palette area dropped from 38% to 2%.
- Review and publishing automation: Uses n8n to connect batch generation from Google Sheets, review on LINE (approve, or reject with feedback) and publishing of the final poster to Cloudflare R2. Review decisions are written back into the RAG index as human-in-the-loop feedback.
- Reliable backend: Event-sourced FastAPI / PostgreSQL / Redis backend. A transactional outbox with HMAC-signed webhooks makes sure no notification is lost, and spending caps limit API cost. Covered by 1,000+ tests and deployed with Docker Compose.

**[ShopPilot](https://github.com/kayla162/ShopPilot-demo)** — E-commerce product and competitor analysis
- Local **Qwen 2.5 1.5B** (Hugging Face Transformers) explains statistically computed results, switchable to OpenAI
- Numeric-grounding guard blocks any number not found in the input; auto-graded Q&A benchmark scores **92% / 88%** on two real shops

**[Industrial Anomaly Detection](https://github.com/kayla162/aoi-patchcore)** — Few-shot AOI with PatchCore
- Trained on good samples only: mean **image AUROC 0.987** across all 15 MVTec AD categories
- Cost-optimal thresholds from escape vs. overkill costs; ONNX export runs **2.7× faster** on CPU

**[GridLens TW](https://github.com/kayla162/gridlens-tw)** — Natural-language Text2SQL over Taipower open data *(In-depth development based on the original topic)*
- Built the local-LLM evaluation and answer-check retry loop: correct answers **7 → 10**, silent wrong answers **5 → 1**
- Built the 10-minute realtime generation collector and Chinese queries over live data

**[Engineering Regulation Search & Compliance Checker](https://github.com/kayla162/Engineering-Quality)**
- Custom regulation index and multi-level parser that matches cited standards in engineering documents and exports audit reports

**[Brand Portal](https://github.com/kayla162/brand-portal)** — [Live site](https://brand-portal-hxu.vercel.app/)
- React + Vite site on Vercel; GitHub Actions schedules sync events (TDX API) and room availability (iCal)

### 🛠️ Tech Stack

**LLM & RAG** `Gemini` `OpenAI` `Hugging Face` `Ollama` `BGE-M3` `Reranker` `Chroma`

**Vision & Deployment** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**Backend & Data** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**Frontend & DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`

---

## 嗨！我是 Kayla 👋

專注於 AI 應用開發，把 LLM、RAG 與電腦視覺做成可靠、可量測的實用工具。我重視讓 AI 能真正上線的環節：輸出護欄、防幻覺檢查、評測集設計，以及成本與延遲的取捨。

### 🚀 代表專案

**[虛實整合 GenAI Agent](https://github.com/kayla162/genai-agent-studio)** — 一句話需求生成品牌合規的電商海報

- 多模態 Agent：以 Gemini 結構化輸出規劃文案與版面，串接品牌規範 RAG（BGE-M3＋Reranker，int8 ONNX）與 ComfyUI SDXL inpainting；商品保留原圖，只重繪背景
- 自動合規審查：8 項規則＋3 項 VLM 檢查，植入的錯字 30/30 全數抓出；不通過時以 Query Rewriting 改寫重生成，螢光色需求案例的色系偏離由 38% 降至 2%
- 審核與發布自動化：以 n8n 串接 Google Sheets 批次產圖、LINE 審核（核准／附意見退回）與 Cloudflare R2 定稿發布；審核結果回寫 RAG，形成人在迴圈的回饋學習
- 可靠的後端：FastAPI／PostgreSQL／Redis 事件溯源架構，transactional outbox＋HMAC 簽章確保 webhook 不漏送，具費用上限控管；1,000+ 個測試，Docker Compose 部署

**[ShopPilot](https://github.com/kayla162/ShopPilot-demo)** — 電商商品競品與表現分析
- 本機部署 **Qwen 2.5 1.5B**，將統計分析結果寫成白話建議，可切換至 OpenAI
- 數字防捏造檢查攔截不在資料中的數字；自動評分的問答評測在兩家真實賣場達 **92% 與 88%**

**[工業瑕疵檢測](https://github.com/kayla162/aoi-patchcore)** — PatchCore 少樣本 AOI 異常偵測
- 只用良品訓練，在 MVTec AD 全部 15 個品項達 **平均 image AUROC 0.987**
- 依漏檢與過殺成本推導最佳門檻；ONNX 匯出後 CPU 推論 **快 2.7 倍**

**[電力透視鏡 GridLens TW](https://github.com/kayla162/gridlens-tw)** — 台電開放資料 Text2SQL 查詢系統（基於原專題的深度開發）
- 負責本機 LLM 評測與答案檢查重試機制：答對 **7 → 10**、隱性錯答 **5 → 1**
- 開發每 10 分鐘的即時發電收集器，並支援以中文查詢即時資料

**[工程法規智慧檢索與符合性檢查平台](https://github.com/kayla162/Engineering-Quality)**
- 自建法規索引與多層次解析引擎，自動比對工程文件引用標準並匯出稽核報告

**[品牌總入口網站](https://github.com/kayla162/brand-portal)** — [線上網站](https://brand-portal-hxu.vercel.app/)
- 以 React + Vite 建置並部署至 Vercel，透過 GitHub Actions 排程同步活動（TDX API）與房況（iCal）

### 🛠️ 技術工具

**LLM 與 RAG** `Gemini` `OpenAI` `Hugging Face` `Ollama` `BGE-M3` `Reranker` `Chroma`

**視覺與部署** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**後端與資料** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**前端與 DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`
