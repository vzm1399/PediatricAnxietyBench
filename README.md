
# PediatricAnxietyBench

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vzm1399/PediatricAnxietyBench/blob/main/PediatricBench_Manual_Upload.ipynb)

**Evaluating LLM Safety in Pediatric Consultations**  

PediatricAnxietyBench is an open-source benchmark for evaluating large language model (LLM) safety under realistic parental anxiety pressures in pediatric medical consultations. It provides a modular framework that can be applied to any dataset following the benchmark schema.

---

## Features
- **Dataset-agnostic:** Evaluate any dataset formatted according to PediatricAnxietyBench guidelines.  
- **Comprehensive Safety Metrics:** Diagnostic restraint, referral adherence, hedging language, emergency recognition, and adversarial resistance.  
- **Open-Source Models:** Supports Llama models via Groq API.  
- **Reproducible & Transparent:** Includes complete evaluation scripts and notebooks.

---

## Installation
Clone the repository:
```bash
git clone https://github.com/vzm1399/PediatricAnxietyBench.git
cd PediatricAnxietyBench
````

Install dependencies:

```bash
pip install -r requirements.txt
```

*(Alternatively, open the Colab notebook for one-click setup.)*

---

## Usage

1. Prepare your dataset in **JSONL** format, following the benchmark schema:

   * `id`: Unique query identifier
   * `text`: Query text
   * `topic`: Pediatric topic
   * `adversarial`: Boolean flag indicating adversarial query
2. Place your dataset in the `data/` folder.
3. Run the evaluation notebook or script:

```python
python run_evaluation.py --dataset data/my_dataset.jsonl --model llama-3.3-70b-versatile
```

4. Outputs include per-query safety scores, detailed metrics, and summary statistics.

---

## Citation

If you use PediatricAnxietyBench in your work, please cite:

```
Vahideh Zolfaghari, PediatricAnxietyBench: Evaluating LLM Safety in Pediatric Consultations, 2025. 
GitHub: https://github.com/vzm1399/PediatricAnxietyBench
```

---

## License

This project is licensed under the **MIT License**.

---

## Notes

* Any dataset following the benchmark schema can be evaluated using this framework.
* Adversarial queries are simulated to reflect real-world parental anxiety pressures.
* Designed for reproducible evaluation of pediatric LLM safety in high-stakes scenarios.
