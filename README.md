## Hi there 👋 I'm Kayla

AI application developer focused on turning LLMs, RAG and computer vision into reliable, measurable tools. I care about the parts that make AI usable in production: output guardrails, hallucination checks, evaluation sets, and cost and latency trade-offs.

### 🚀 Featured Projects

**[GenAI Agent Studio](https://github.com/kayla162/genai-agent-studio)** — One-line brief to brand-compliant e-commerce posters
- Gemini structured-output agent + brand-guideline RAG (BGE-M3 + reranker, int8 ONNX on CPU) + SDXL inpainting via ComfyUI + VLM compliance review
- Failed reviews trigger query rewriting and regeneration: off-palette area dropped from **38% to 2%**
- Event-sourced FastAPI / PostgreSQL / Redis backend with cost caps, **1,000+ tests**, Docker Compose

**[ShopPilot](https://github.com/kayla162/shoppilot)** — E-commerce product and competitor analysis
- Local **Qwen 2.5 1.5B** (Hugging Face Transformers) explains statistically computed results, switchable to OpenAI
- Numeric-grounding guard blocks any number not found in the input; auto-graded Q&A benchmark scores **92% / 88%** on two real shops

**[Industrial Anomaly Detection](https://github.com/kayla162/aoi-patchcore)** — Few-shot AOI with PatchCore
- Trained on good samples only: mean **image AUROC 0.987** across all 15 MVTec AD categories
- Cost-optimal thresholds from escape vs. overkill costs; ONNX export runs **2.7× faster** on CPU

**[GridLens TW](https://github.com/kayla162/gridlens-tw)** — Natural-language Text2SQL over Taipower open data *(team project)*
- Built the local-LLM evaluation and answer-check retry loop: correct answers **7 → 10**, silent wrong answers **5 → 1**
- Built the 10-minute realtime generation collector and Chinese queries over live data

**[Engineering Regulation Search & Compliance Checker](https://github.com/kayla162/aoi-patchcore.git)**
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

**[虛實整合 GenAI Agent](https://github.com/kayla162/genai-agent-studio)** — 一句話生成品牌合規電商海報
- Gemini 結構化輸出 Agent，串接品牌規範 RAG（BGE-M3 + Reranker，int8 ONNX）、ComfyUI 上的 SDXL inpainting 與 VLM 合規審查
- 審查不通過時自動改寫重生成，色系偏離從 **38% 降至 2%**
- 事件溯源架構的 FastAPI / PostgreSQL / Redis 後端，具費用上限控管，共 **1,000+ 個測試**，以 Docker Compose 部署

**[ShopPilot](https://github.com/kayla162/shoppilot)** — 電商商品競品與表現分析
- 本機部署 **Qwen 2.5 1.5B**，將統計分析結果寫成白話建議，可切換至 OpenAI
- 數字防捏造檢查攔截不在資料中的數字；自動評分的問答評測在兩家真實賣場達 **92% 與 88%**

**[工業瑕疵檢測](https://github.com/kayla162/aoi-patchcore)** — PatchCore 少樣本 AOI 異常偵測
- 只用良品訓練，在 MVTec AD 全部 15 個品項達 **平均 image AUROC 0.987**
- 依漏檢與過殺成本推導最佳門檻；ONNX 匯出後 CPU 推論 **快 2.7 倍**

**[電力透視鏡 GridLens TW](https://github.com/kayla162/gridlens-tw)** — 台電開放資料 Text2SQL 查詢系統（團隊專案）
- 負責本機 LLM 評測與答案檢查重試機制：答對 **7 → 10**、隱性錯答 **5 → 1**
- 開發每 10 分鐘的即時發電收集器，並支援以中文查詢即時資料

**[工程法規智慧檢索與符合性檢查平台](https://github.com/kayla162/aoi-patchcore.git)**
— 基於 PatchCore 的少樣本異常檢測，結合 CNN 特徵提取、Coreset 抽樣與 ONNX 推論最佳化，探索 AOI 產線應用。
- 自建法規索引與多層次解析引擎，自動比對工程文件引用標準並匯出稽核報告

**[品牌總入口網站](https://github.com/kayla162/brand-portal)** — [線上網站](https://brand-portal-hxu.vercel.app/)
- 以 React + Vite 建置並部署至 Vercel，透過 GitHub Actions 排程同步活動（TDX API）與房況（iCal）

### 🛠️ 技術工具

**LLM 與 RAG** `Gemini` `OpenAI` `Hugging Face` `Ollama` `BGE-M3` `Reranker` `Chroma`

**視覺與部署** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**後端與資料** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**前端與 DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`
