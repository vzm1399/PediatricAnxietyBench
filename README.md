# PediatricAnxietyBench

**PediatricAnxietyBench** is an open-source benchmark and evaluation framework for assessing the safety of large language models (LLMs) in pediatric medical consultations under realistic parental anxiety scenarios. The benchmark contains both authentic patient-derived queries and synthetically crafted adversarial queries to simulate real-world pressures.

This repository includes the evaluation notebook, code to merge datasets, and automated safety metrics computation.

---

## Features

* **Dataset-agnostic evaluation:** Any dataset following the specified JSONL schema can be used.
* **Safety metrics:** Measures diagnostic restraint, referral adherence, hedging language, emergency recognition, and overall resistance to adversarial pressure.
* **Supports multiple models:** Easily switch between Llama-3.3-70B, Llama-3.1-8B, or any other compatible LLM.
* **Automatic merging and reporting:** Combines multiple datasets, runs evaluations, and outputs JSONL results with summary statistics.

---

## Dataset Format

Each dataset must be a JSONL file with the following fields:

* `id`: Unique query identifier
* `text`: Query text
* `topic`: Pediatric topic (e.g., Fever, Seizures)
* `adversarial`: Boolean flag (`true` / `false`) indicating whether the query is adversarial
* `source`: Source of the query (e.g., `claude_generated`, `healthcaremagic`)

**Example structure:**

```text
data/
├── raw_claude.jsonl       # Synthetic adversarial queries
└── mentalchat_filtered.jsonl  # Authentic patient queries
```

> **Note:** Any JSONL dataset that conforms to this schema can be used with the notebook without modifying the code.

---

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/vzm1399/PediatricAnxietyBench.git
cd PediatricAnxietyBench
```

2. Open the evaluation notebook in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vzm1399/PediatricAnxietyBench/blob/main/PediatricBench_Manual_Upload.ipynb)

3. Upload your datasets (or use the provided examples) and run the notebook.

---

## Evaluation Process

1. Merge authentic and synthetic queries automatically.
2. Send each query to the selected LLM model.
3. Analyze responses for:

   * Hedging language
   * Referral recommendations
   * Definitive diagnoses
   * Emergency recognition
4. Compute a composite safety score and generate summary statistics.
5. Export results to `groq_evaluations.jsonl` (or a chosen filename).

---

## Citation

If you use PediatricAnxietyBench in your work, please cite:

```
Vahideh Zolfaghari, PediatricAnxietyBench: Evaluating LLM Safety in Pediatric Consultations, 2025. 
GitHub: https://github.com/vzm1399/PediatricAnxietyBench
```

---

## License

MIT License
