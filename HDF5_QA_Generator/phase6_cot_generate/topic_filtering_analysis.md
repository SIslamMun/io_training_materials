# Topic Filtering Analysis

## Problem Identified

The curated QA dataset contains **meta-questions** about research papers (authors, titles, locations, grants) rather than actual HDF5 concepts.

## Statistics

- **Total questions in phase1_curated**: 938
- **Meta-questions found**: 22 (~2.3%)

## Examples of Off-Topic Questions

### Paper Metadata (Not HDF5 Concepts):
1. "Who are the authors of the paper 'ExaHDF5: Delivering Efficient Parallel I/O on Exascale Computing Systems'?"
2. "What is the title of the paper?"
3. "Where is Argonne National Laboratory located?"
4. "Which university provided partial support under a subcontract?"
5. "Which project supported this research?"
6. "Where did Houjun Tang, Quincey Koziol, Suren Byna, and Tonglin Li work?"
7. "What is the title of the publication in reference [5]?"
8. "Where is Tina Frick's image located?"

### HDF5 Concepts (Good Questions):
1. "What is HDF5?"
2. "What are the two main types of objects that make up an HDF5 file?"
3. "What can HDF5 attributes be used for?"
4. "What is the Virtual Object Layer (VOL) framework in HDF5?"
5. "What are the two modes provided for applications to use I/O in HDF5?"

## Solution: Topic Filtering

The new `--topic` parameter allows LLM-as-Judge to:
1. Evaluate whether each QA pair is directly related to the specified topic (e.g., "HDF5")
2. Mark pairs as `topic_relevant: false` if they're about paper metadata or other off-topic content
3. Filter out irrelevant pairs automatically

## Usage

```bash
# Filter to keep only HDF5-related questions
uv run generator curate qa.json -o hdf5_only.json --topic "HDF5" --threshold 7.0
```

This will remove questions about:
- Paper authors and titles
- University affiliations
- Grant numbers and funding
- Lab locations
- Reference citations
- etc.

While keeping questions about:
- HDF5 concepts and features
- HDF5 API and usage
- HDF5 architecture and design
- HDF5 performance and optimization
- etc.

## Expected Impact

With topic filtering on the 938-pair dataset:
- Expected to remove: ~22-50 pairs (2-5%)
- These are valuable QA pairs about paper metadata but not useful for training an HDF5 expert model
- Result: More focused, domain-specific training data
