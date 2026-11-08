## Hi there 👋 I'm Kayla

AI application developer focused on turning LLMs, RAG and computer vision into reliable, measurable tools. I care about the parts that make AI usable in production: output guardrails, hallucination checks, evaluation sets, and cost and latency trade-offs.

### 🚀 Featured Projects

**[GenAI Agent Studio](https://github.com/kayla162/genai-agent-studio)** — Brand-compliant e-commerce posters from a one-line brief

- Multimodal agent: Plans copy and layout with Gemini structured output, grounded in a brand-guideline RAG (BGE-M3 + reranker, int8 ONNX), and generates backgrounds with SDXL inpainting on ComfyUI. The product photo stays untouched; only the background is regenerated.
- Automated compliance review: Runs 8 rule-based checks and 3 VLM checks, and caught 30/30 deliberately planted typos. Failed posters are regenerated after query rewriting; in a fluorescent-color test case, off-palette area dropped from 38% to 2%.
- Review and publishing automation: Uses n8n to connect batch generation from Google Sheets, review on LINE (approve, or reject with feedback) and publishing of the final poster to Cloudflare R2. Review decisions are written back into the RAG index as human-in-the-loop feedback.
- Reliable backend: Event-sourced FastAPI / PostgreSQL / Redis backend. A transactional outbox with HMAC-signed webhooks makes sure no notification is lost, and spending caps limit API cost. Covered by 1,000+ tests and deployed with Docker Compose.

**[ShopPilot](https://github.com/kayla162/ShopPilot-demo)** — Shopee seller analytics with a fine-tuned local LLM · [Live demo](https://shoppilot-demo-fqegbgf2rvzuah3tzjhqqt.streamlit.app/) · [Model](https://huggingface.co/kayla162/shoppilot-qwen2.5-1.5b-tools-lora)

- Tool calling with a 1.5B model: Sellers ask questions in Chinese, and a local Qwen 2.5 1.5B calls 7 query tools to find the answer. A numeric-grounding guard blocks any number not found in the tool output.
- QLoRA fine-tuning: Trained on program-generated trajectories on a 6 GB laptop GPU in 44 minutes. On the same 4-bit model, accuracy rose from 59% to 96% on 141 auto-graded questions (McNemar p < 1e-11), on par with a 5× larger Qwen3 8B. The release was chosen from three data versions by failure mode, and the adapter is published on Hugging Face as PEFT and GGUF weights.
- Fast local inference: llama.cpp 4-bit quantization cuts CPU latency from 50 s to 3.6 s per answer, with token-by-token streaming.
- Measurable after launch: A monitoring tab tracks p50/p95 latency, cache hits and guard blocks. Sellers rate answers 👍/👎, and their real questions can be exported and re-run as an evaluation set. Covered by 686 tests in CI.

**[Industrial Anomaly Detection](https://github.com/kayla162/aoi-patchcore)** — Few-shot AOI with PatchCore
- Trained on good samples only: mean **image AUROC 0.987** across all 15 MVTec AD categories
- Cost-optimal thresholds from escape vs. overkill costs; ONNX export runs **2.7× faster** on CPU

**[GridLens TW](https://github.com/kayla162/gridlens-tw)** — local-first Text2SQL over Taiwan Power Company open data (Extensions)

- Built the local-LLM evaluation and fixes: each round is scored on a question set written before the changes. Accuracy rose 14→21, 10→15 and 15→20 over three rounds, and McNemar tests confirm the gain is not noise (pooled p ≈ 0.00002).
- Chose the defaults from data: compared 3 local models and n-gram vs. embedding retrieval, question by question on the same 121 questions.
- Built an MCP server so AI agents such as Claude can query the data in Chinese. Agents can only send questions, never SQL, so every query passes the same guards.
- Built a realtime generation collector that runs every 10 minutes, with Chinese-language queries over the live data; ships with a one-command Docker demo.

**[Engineering Regulation Search & Compliance Checker](https://github.com/kayla162/Engineering-Quality)**
- Custom regulation index and multi-level parser that matches cited standards in engineering documents and exports audit reports

**[Brand Portal](https://github.com/kayla162/brand-portal)** — [Live site](https://brand-portal-hxu.vercel.app/)
- React + Vite site on Vercel; GitHub Actions schedules sync events (TDX API) and room availability (iCal)

### 🛠️ Tech Stack

**LLM & RAG** `Gemini` `OpenAI` `Hugging Face` `PEFT / QLoRA` `llama.cpp` `Ollama` `BGE-M3` `Reranker` `Chroma`

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

**[ShopPilot](https://github.com/kayla162/ShopPilot-demo)** — 微調本機 LLM 的蝦皮賣家分析工具 · [線上 demo](https://shoppilot-demo-fqegbgf2rvzuah3tzjhqqt.streamlit.app/) · [模型](https://huggingface.co/kayla162/shoppilot-qwen2.5-1.5b-tools-lora)

- 1.5B 模型的工具呼叫：賣家用中文提問，本機 Qwen 2.5 1.5B 自己呼叫 7 個查詢工具找答案；數字防捏造檢查攔下工具回傳裡沒有的數字
- QLoRA 微調：用程式產生的訓練資料，在 6 GB 筆電顯示卡上訓練 44 分鐘；同一個 4-bit 模型在 141 題自動評分的題目上，答對率從 59% 提升到 96%（McNemar p < 1e-11），和 5 倍大的 Qwen3 8B 相當；從三版訓練資料中依答錯的方式選出發布版本，以 PEFT 和 GGUF 格式公開在 Hugging Face
- 本機快速推論：llama.cpp 4-bit 量化讓 CPU 每題從 50 秒降到 3.6 秒，回答逐字串流顯示
- 上線後可量測：監控分頁追蹤延遲 p50／p95、快取命中與攔截比例；賣家可對回答按 👍／👎，真實提問能匯出成評測集重跑；686 個測試在 CI 自動執行

**[工業瑕疵檢測](https://github.com/kayla162/aoi-patchcore)** — PatchCore 少樣本 AOI 異常偵測
- 只用良品訓練，在 MVTec AD 全部 15 個品項達 **平均 image AUROC 0.987**
- 依漏檢與過殺成本推導最佳門檻；ONNX 匯出後 CPU 推論 **快 2.7 倍**

**[電力透視鏡 GridLens TW](https://github.com/kayla162/gridlens-tw)** — 台電開放資料的地端 Text2SQL 查詢系統（延伸開發）

- 負責本機 LLM 評測與改善：每輪先寫新題庫再修正，三輪答對 14→21、10→15、15→20，並以 McNemar 檢定確認不是運氣（三輪合計 p ≈ 0.00002）
- 用數據選型：三個本機模型、n-gram 與 embedding 兩種檢索，在 121 題上逐題配對比較後才定預設
- 開發 MCP server，讓 Claude 等 AI 代理用中文查詢；代理只能送問題、不能送 SQL，一律經過守門
- 開發每 10 分鐘的即時發電收集器，並支援用中文查詢即時資料；提供 Docker 一鍵展示

**[工程法規智慧檢索與符合性檢查平台](https://github.com/kayla162/Engineering-Quality)**
- 自建法規索引與多層次解析引擎，自動比對工程文件引用標準並匯出稽核報告

**[品牌總入口網站](https://github.com/kayla162/brand-portal)** — [線上網站](https://brand-portal-hxu.vercel.app/)
- 以 React + Vite 建置並部署至 Vercel，透過 GitHub Actions 排程同步活動（TDX API）與房況（iCal）

### 🛠️ 技術工具

**LLM 與 RAG** `Gemini` `OpenAI` `Hugging Face` `PEFT / QLoRA` `llama.cpp` `Ollama` `BGE-M3` `Reranker` `Chroma`

**視覺與部署** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**後端與資料** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**前端與 DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`
