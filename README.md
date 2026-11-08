## Hi there 👋 I'm Kayla

AI application developer focused on turning LLMs, RAG and computer vision into reliable, measurable tools. I care about the parts that make AI usable in production: output guardrails, hallucination checks, evaluation sets, and cost and latency trade-offs.

### 🚀 Featured Projects

**[GenAI Agent Studio](https://github.com/kayla162/genai-agent-studio)** — Brand-compliant e-commerce posters from a one-line brief· [demo](https://genai-agent-studio.kayla-swag-19.workers.dev/studio) 

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
- Trained on good samples only: mean **image AUROC 0.986** across all 15 MVTec AD categories
- Cost-optimal thresholds from escape vs. overkill costs; ONNX export speeds up CPU feature extraction **2.7×**

**[GridLens TW](https://github.com/kayla162/gridlens-tw)** — Ask Taiwan Power open data in Chinese: local-first Text2SQL with guardrails (Extensions) · [Live demo](https://gridlens-tw.onrender.com)

- Guarded by design: rules first, a local LLM (Ollama qwen3:8b) for the long tail; an AST SQL guard and a semantic guard block 16/16 SQL attacks and refuse questions the data cannot answer.
- Measured, not guessed: each fix round is scored on a fresh question set (14→21, 10→15, 15→20; pooled McNemar p ≈ 0.00002), and defaults were chosen by comparing 3 local models and 3 retrievers on 121 questions.
- Agent-ready: an MCP server lets Claude query the data in Chinese. Agents send questions, never SQL, so every query passes the same guards.

**[Engineering Regulation Compliance Platform](https://github.com/kayla162/Engineering-Quality)** — Verify cited regulations and ask legal questions with verifiable citations · [Summary](https://github.com/kayla162/Engineering-Quality/blob/master/docs/portfolio-en.md)

- RAG Q&A with verified citations: Claude answers only from retrieved articles and must quote them verbatim; a program checks every quote against the source text. On the held-out set: **0 wrong answers**, **9/9 trap questions refused**, accuracy 50% → **75%** from better retrieval alone.
- Hybrid search on pgvector: exact matching for article numbers and standard codes plus BGE-M3 vectors, stored in the existing PostgreSQL. Held-out **Recall@5 0.54 → 0.91**; the architecture was chosen by comparing four designs on a dev set, not by default.
- Model choice by error type: compared Opus, Sonnet and Haiku at several effort levels on the same questions; kept Opus because Sonnet turned a mandatory "shall" into "may" — a legal error quote-checking cannot catch.
- Reads real engineering documents: OCR on scanned contract drawings raised drawing-number accuracy from **35% to 92%**, cutting items to check by hand from 312 to 30. Covered by 1,000+ tests in CI.

**[Brand Portal](https://github.com/kayla162/brand-portal)** — [Live site](https://brand-portal-hxu.vercel.app/)
- One NFC tap links all three brands, with a guest hub for the vacation cabin: food, sights, itineraries, and room availability
- Built with React + Vite and deployed on Vercel; GitHub Actions schedules sync events (TDX API) and room availability (iCal)

### 🛠️ Tech Stack

**LLM & RAG** `Claude` `Gemini` `OpenAI` `Hugging Face` `PEFT / QLoRA` `llama.cpp` `Ollama` `BGE-M3` `pgvector` `Reranker` `Chroma`

**Vision & Deployment** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**Backend & Data** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**Frontend & DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`

---

## 嗨！我是 Kayla 👋

專注於 AI 應用開發，把 LLM、RAG 與電腦視覺做成可靠、可量測的實用工具。我重視讓 AI 能真正上線的環節：輸出護欄、防幻覺檢查、評測集設計，以及成本與延遲的取捨。

### 🚀 代表專案

**[虛實整合 GenAI Agent](https://github.com/kayla162/genai-agent-studio)** — 一句話需求生成品牌合規的電商海報· [線上 demo](https://genai-agent-studio.kayla-swag-19.workers.dev/studio) 

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
- 只用良品訓練，MVTec AD 全 15 品項平均 **image AUROC 0.986**
- 依漏檢與過殺成本推導最佳門檻；ONNX 匯出後 CPU 特徵提取 **快 2.7 倍**

**[電力透視鏡 GridLens TW](https://github.com/kayla162/gridlens-tw)** — 用中文查台電開放資料的地端 Text2SQL（延伸開發）· [線上 demo](https://gridlens-tw.onrender.com)

- 守門優先：規則先接、本機 LLM（Ollama qwen3:8b）補長尾；語法樹與語意雙層守門，SQL 攻擊 16/16 攔截，資料答不出的問題直接拒答並建議問法
- 用數據說話：每輪先寫新題庫再修正，三輪答對 14→21、10→15、15→20（McNemar 合計 p ≈ 0.00002）；三個本機模型、三種檢索方式在 121 題上逐題比較後才定預設
- 給 AI 代理用：MCP server 讓 Claude 用中文查詢；代理只能送問題、不能送 SQL，一律經過同樣的守門

**[工程法規符合性檢查平台](https://github.com/kayla162/Engineering-Quality)** — 查證文件引用的法規是否有效，並用口語問法規、得到可驗證出處的回答

- 引用可驗證的 RAG 問答：Claude 只能根據檢索到的條文回答並逐字引用，程式逐條比對原文；保留測試集**錯誤答案 0**、陷阱題 **9/9 正確拒答**，只靠改善檢索就讓答對率由 50% 提升到 **75%**
- pgvector 混合搜尋：條號、標準編號精確比對＋BGE-M3 向量，直接存在既有的 PostgreSQL；保留測試集 **Recall@5 0.54 → 0.91**，架構是在開發集上比較四種設計後才決定
- 依錯誤性質選模型：同題比較 Opus、Sonnet、Haiku 與不同 effort，Sonnet 會把條文的「應」改寫成「得」，引文驗證擋不到這種錯誤，因此維持 Opus
- 讀得懂真實工程文件：掃描契約圖 OCR 的圖號辨識率由 **35% 提升到 92%**，待人工確認的工項由 312 筆降到 30 筆；1,000 多個測試在 CI 上自動執行

**[品牌總入口網站](https://github.com/kayla162/brand-portal)** — [線上網站](https://brand-portal-hxu.vercel.app/)
- 一張 NFC 卡串起三個品牌，並為度假小屋住客提供美食、景點、行程與空房查詢
- 以 React + Vite 建置並部署至 Vercel，透過 GitHub Actions 排程同步活動（TDX API）與房況（iCal）

### 🛠️ 技術工具

**LLM 與 RAG** `Claude` `Gemini` `OpenAI` `Hugging Face` `PEFT / QLoRA` `llama.cpp` `Ollama` `BGE-M3` `pgvector` `Reranker` `Chroma`

**視覺與部署** `PyTorch` `SDXL` `ComfyUI` `ONNX Runtime` `PatchCore`

**後端與資料** `Python` `FastAPI` `PostgreSQL` `Redis` `SQL` `pandas`

**前端與 DevOps** `Next.js` `TypeScript` `React` `Docker` `GitHub Actions`
