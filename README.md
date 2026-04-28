# Machine Translation in Sovereign Language Models: A Case Study of Amália for European Portuguese

### Overview:

This repository contains the datasets and code used in the paper "Machine Translation in Sovereign Language Models:
A Case Study of Amália for European Portuguese".
The study evaluates the emergent English-to-European-Portuguese (EU-PT) machine translation
capabilities of Amália, a 9B-parameter sovereign LLM developed for European Portuguese,
benchmarking it against state-of-the-art commercial systems (DeepL, Google Translate) and
multilingual open-source models (EuroLLM family, LLaMA-3 FFT).
Translation performance is assessed on the FRMT and NTrex-128 benchmarks using a
multi-metric framework covering translation quality (SacreBLEU, ROUGE-L, COMET-22)
and regional variety fidelity (VID).

### Datasets:

FRMT — Style-targeted translation benchmark with EU-PT and BR-PT references, covering lexical, entity, and random
content categories. [[Paper](https://aclanthology.org/2023.tacl-1.39/)]

NTrex-128 — News-domain translation benchmark with 1,997 professionally translated sentences across 128 languages,
including EU-PT and BR-PT. [[Paper](https://aclanthology.org/2022.sumeval-1.4/)]

The "datasets" folder contains all the datasets from this project: FRMT and NTrex english text with EU-PT references
translation, plus all models EU-PT translations of two these datasets.

### Evaluation Metrics:

SacreBLEU — Precision-based n-gram overlap metric. [[Paper](https://aclanthology.org/W18-6319/)]

ROUGE-L — Longest common subsequence metric. [[Paper](https://aclanthology.org/W04-1013/)]

COMET-22 — Neural MT evaluation metric based on cross-lingual encoders (
XLM-RoBERTa). [[Paper](https://aclanthology.org/2020.emnlp-main.213/)]

VID (Variety Identification) — Ratio of model outputs classified as EU-PT vs. BR-PT, using a dedicated language variety
identifier. [[Paper](https://ojs.aaai.org/index.php/AAAI/article/view/34705)]

### Reproducing the Results:

1. Capture model translations -
   Open and run model_responses.ipynb. This notebook handles prompting each model with the benchmark source sentences
   and saving the outputs to the datasets/ folder.
   Two prompting strategies are used, one for Instruct models (Amália, EuroLLM Instruct),
   and another for Base models (EuroLLM Base).

2. Evaluate translations -
   Open and run evaluate_model.ipynb. This notebook loads the translation outputs from datasets/ and computes all four
   metrics (SacreBLEU, ROUGE-L, COMET-22, VID) against the reference translations. This was used to evaluate the models
   translations outputs.
