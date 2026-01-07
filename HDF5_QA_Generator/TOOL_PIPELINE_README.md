# HDF5 Tool-Use Training Pipeline

Generate tool-use training data for HDF5 agentic capabilities.

## 📁 Folder Structure

```
HDF5_QA_Generator/
├── tool_definitions/           # Tool definition files
│   └── hdf5_tools.json        # 25 HDF5 MCP tools
├── phase9_tool_generate/       # Generated tool-use examples
├── phase10_tool_curate/        # Quality-filtered examples
└── phase11_tool_export/        # Final training format
```

## 🔧 Tool Definitions

**hdf5_tools.json** - 25 tools based on iowarp/agent-toolkit MCP server:

| Category | Tools | Count |
|----------|-------|-------|
| File Operations | `open_file`, `close_file`, `get_filename`, `get_mode` | 4 |
| Navigation | `get_by_path`, `list_keys`, `visit` | 3 |
| Dataset Operations | `read_full_dataset`, `read_partial_dataset`, `get_shape`, `get_dtype`, `get_size`, `get_chunks` | 6 |
| Attribute Operations | `read_attribute`, `list_attributes` | 2 |
| Performance | `hdf5_parallel_scan`, `hdf5_batch_read`, `hdf5_stream_data`, `hdf5_aggregate_stats` | 4 |
| Discovery | `analyze_dataset_structure`, `find_similar_datasets`, `suggest_next_exploration`, `identify_io_bottlenecks`, `optimize_access_pattern` | 5 |

## 🚀 Pipeline Commands

### Phase 9: Generate Tool-Use Examples

```bash
# Navigate to Generator root
cd "/home/shazzadul/Illinois_Tech/Spring26/RA/Fine tuning/Generator"

# Option 1: Auto mode (balanced single + multi-step)
uv run generator tool-generate \
  HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase9_tool_generate/tool_examples.json \
  --target-pairs 500

# Option 2: Single-step only (simple tasks)
uv run generator tool-generate \
  HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase9_tool_generate/tool_examples_single.json \
  --single-step \
  --target-pairs 300

# Option 3: Multi-step only (complex workflows)
uv run generator tool-generate \
  HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase9_tool_generate/tool_examples_multi.json \
  --multi-step \
  --target-pairs 200
```

### Phase 10: Curate Tool-Use Examples

```bash
# Standard curation (threshold 7.0)
uv run generator tool-curate \
  HDF5_QA_Generator/phase9_tool_generate/tool_examples.json \
  -o HDF5_QA_Generator/phase10_tool_curate/tool_curated.json

# High quality only (threshold 8.0)
uv run generator tool-curate \
  HDF5_QA_Generator/phase9_tool_generate/tool_examples.json \
  -o HDF5_QA_Generator/phase10_tool_curate/tool_curated_high.json \
  --threshold 8.0
```

### Phase 11: Export to Training Format

```bash
# Export to JSONL (ChatML format)
uv run generator export \
  HDF5_QA_Generator/phase10_tool_curate/tool_curated.json \
  -o HDF5_QA_Generator/phase11_tool_export/tool_training.jsonl \
  -f chatml \
  --system-prompt "You are an HDF5 expert assistant that helps users work with HDF5 files using specialized tools."

# Export to Alpaca format
uv run generator export \
  HDF5_QA_Generator/phase10_tool_curate/tool_curated.json \
  -o HDF5_QA_Generator/phase11_tool_export/tool_training_alpaca.json \
  -f alpaca
```

## ⚡ Quick Pipeline (All-in-One)

```bash
cd "/home/shazzadul/Illinois_Tech/Spring26/RA/Fine tuning/Generator"

# Full pipeline with curation
uv run generator tool-pipeline \
  HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase11_tool_export/tool_training.json \
  --target-pairs 500 \
  --threshold 7.0

# Quick generation (skip curation for testing)
uv run generator tool-pipeline \
  HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase9_tool_generate/tool_draft.json \
  --target-pairs 50 \
  --skip-curation
```

## 📊 Expected Output

### Phase 9 Output (tool_examples.json)
```json
{
  "instruction": "Read the temperature dataset from my climate simulation file",
  "solution": {
    "reasoning_path": [
      {
        "step": 1,
        "thought": "First, I need to open the HDF5 file",
        "tool": "open_file",
        "args": {"path": "climate_sim.h5", "mode": "r"}
      },
      {
        "step": 2,
        "thought": "Now I can read the temperature dataset",
        "tool": "read_full_dataset",
        "args": {"path": "/results/temperature"}
      }
    ],
    "api_documentation": "open_file(path: string, mode: string = r)..."
  },
  "metadata": {
    "difficulty": "medium",
    "mode": "multi"
  }
}
```

### Phase 10 Output (tool_curated.json)
Same format with added `rating`, `clarity`, `accuracy` fields.

### Phase 11 Output (tool_training.jsonl)
```json
{"messages": [
  {"role": "system", "content": "You are an HDF5 expert assistant..."},
  {"role": "user", "content": "Read the temperature dataset from my climate simulation file"},
  {"role": "assistant", "content": "Step 1: First, I need to open the HDF5 file\nTool: open_file(path='climate_sim.h5', mode='r')\n\nStep 2: Now I can read the temperature dataset\nTool: read_full_dataset(path='/results/temperature')"}
]}
```

## 🔗 Complete HDF5 Training Pipeline

For a fully capable HDF5 model, combine both pipelines:

```bash
# 1. QA Pipeline (domain knowledge) - Phases 1-8
uv run generator pipeline /path/to/hdf5_lancedb -o HDF5_QA_Generator/phase8_export/qa_training.jsonl

# 2. Tool Pipeline (agentic capabilities) - Phases 9-11
uv run generator tool-pipeline HDF5_QA_Generator/tool_definitions/hdf5_tools.json \
  -o HDF5_QA_Generator/phase11_tool_export/tool_training.json

# 3. Merge for final training
cat HDF5_QA_Generator/phase8_export/qa_training.jsonl \
    HDF5_QA_Generator/phase11_tool_export/tool_training.jsonl \
    > HDF5_QA_Generator/final_hdf5_training.jsonl
```

This creates a model that both **understands HDF5 concepts** and **knows how to use HDF5 tools**.
