# IO Training Materials

> Training datasets for LLM fine-tuning generated from Phagocyte and QA Generator pipelines.

---

## � Research Modes

The Phagocyte pipeline supports three research modes:

| Mode | Description | Example |
|------|-------------|---------|
| **Directed Research** | Focused research with specific goals and queries | HDF5_Phagocyte |
| **Undirected Research** | Exploratory research without predefined direction | (ADIOS_Phagocyte) |
| **No Research** | Artifact collection without research synthesis | JARVIS_Phagocyte |

---

## 📁 Datasets

| Dataset | Source | Research Mode | Description |
|---------|--------|---------------|-------------|
| **ADIOS_Phagocyte/** | Phagocyte | Directed | Research, documents, markdowns, vector store |
| **HDF5_Phagocyte/** | Phagocyte | Directed | Research, documents, markdowns, vector store |
| **HDF5_QA_Generator/** | QA Generator | N/A | QA pairs, CoT data, training exports |
| **JARVIS_Phagocyte/** | Phagocyte | No Research | Artifacts for research report creation |

---

## Dataset Details

### ADIOS_Phagocyte
Source data collected via Phagocyte pipeline for ADIOS domain using **directed research** mode.

### HDF5_Phagocyte
Source data collected via Phagocyte pipeline for HDF5 domain using **directed research** mode.

### HDF5_QA_Generator  
Training datasets generated via QA Generator pipeline.

| Dataset | Pairs |
|---------|-------|
| Regular QA | 938 |
| CoT QA | 649 |

**Export Formats:** ChatML, Alpaca, ShareGPT, JSONL

### JARVIS_Phagocyte
Source data collected via Phagocyte pipeline for JARVIS domain using **no research** mode.

Artifacts provided for creating custom research reports:

| Component | Contents |
|-----------|----------|
| Documents | PDFs and research papers |
| markdowns | Converted markdown files |
| artifacts | Research metadata, thinking steps |
| Research | References, batch queries |
| RAG | LanceDB vector store |
| github | Source code from repositories |
