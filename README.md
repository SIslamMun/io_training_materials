# IO Training Materials

> Training datasets for LLM fine-tuning generated from Phagocyte and QA Generator pipelines.

---

## 📁 Datasets

| Dataset | Source | Description |
|---------|--------|-------------|
| **HDF5_Phagocyte/** | Phagocyte | Research, documents, markdowns, vector store |
| **HDF5_QA_Generator/** | QA Generator | QA pairs, CoT data, training exports |
| **JARVIS_Phagocyte/** | Phagocyte | Research, documents, markdowns, source code |

---

## Dataset Details

### HDF5_Phagocyte
Source data collected via Phagocyte pipeline for HDF5 domain.

### HDF5_QA_Generator  
Training datasets generated via QA Generator pipeline.

| Dataset | Pairs |
|---------|-------|
| Regular QA | 938 |
| CoT QA | 649 |

**Export Formats:** ChatML, Alpaca, ShareGPT, JSONL

### JARVIS_Phagocyte
Source data collected via Phagocyte pipeline for JARVIS domain.

| Component | Contents |
|-----------|----------|
| Documents | PDFs and research papers |
| markdowns | Converted markdown files, research reports |
| Research | References, metadata, research reports |
| RAG | LanceDB vector store |
| source_code | Source code artifacts |
