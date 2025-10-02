# Build an LLM - My Codebase (inspired by Sebastian Raschka)

> TL;DR: This repository contains my personal implementations, experiments, and extended notes while working through 'Build a Large Language Model (From Scratch)' by Sebastian Raschka. The code is written from-scratch (PyTorch-first), adapted for my use case and learning objectives.
> Disclaimer: This repo is inspired by and credits Sebastian Raschka's work -- I do not claim ownership of the original book content or official repository. See the "Credits & Attribution" section for details.

---

## Project purpose & scope

- Re-implement and deeply understand the core components of a GPT-style LLM:
  - Tokenization & BPE
  - Embeddings & positional encodings
  - Causal self-attention and multi-head attention
  - Transformer blocks and layer norms
  - Training loop, optimizer, and learning-rate scheduling
  - Generation and sampling strategies
  - Basic fine-tuning and instruction-following (small-scale)
- Add extensions specific to my use case (replace the placeholders below with your actual use case):
  - Use case example A: fine-tune for domain-specific classification (e.g., biomedical Q&A)
  - Use case example B: build a small LLM for on-device inference with quantization
  - Use case example C: experiment with instruction finetuning and RLHF surfacing pipelines

---

## Repository structure (suggested)

```
.
├── chapters/                 # Notebook-by-chapter (ch01, ch02, ...)
│   ├── ch01/
│   ├── ch02/
│   └── ...
├── notebooks/                # Supplemental and experiments
├── src/                      # Reusable python modules (tokenizers, model, trainer)
│   ├── llm/
│   │   ├── tokenizer.py
│   │   ├── model.py
│   │   ├── train.py
│   │   └── utils.py
├── data/                     # small sample datasets (gitignored in real usage)
├── weights/                  # pre-trained checkpoints (gitignored -- use downloads)
├── tests/                    # unit tests
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

---

## How to use this repo (quickstart)

1. Clone your repo (or skip if you already have it locally):
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

2. Create a virtual environment and install deps
```bash
python -m venv .venv
source .venv/bin/activate    # macOS / Linux
.venv\Scripts\activate     # Windows (PowerShell)
pip install -r requirements.txt
```

3. Open notebooks
```bash
jupyter lab
```
Open chapters/ch04/ch04.ipynb (or equivalent) to explore the GPT implementation.

---

## Data, weights and large files

- Never add large datasets or model checkpoints directly to the repo. Use one of:
  - Git LFS for moderately sized files.
  - External hosting (S3, Google Drive, huggingface.co) and a small download script (scripts/download_weights.sh).
- Add data/ and weights/ to .gitignore (sample provided).

---

## Notebook header (add to each notebook)
```python
'''
Notebook inspired by: Sebastian Raschka - Build a Large Language Model (From Scratch)
Official repo: https://github.com/rasbt/LLMs-from-scratch

This notebook contains my own re-implementation, experiments and notes.
'''
```

---

## Credits & Attribution

This project is inspired by Sebastian Raschka's book 'Build A Large Language Model (From Scratch)' and the official companion repository 'rasbt/LLMs-from-scratch'. Please consult the original book and repository for the canonical implementations and licensing terms.

Canonical resources:
- Sebastian Raschka - Build A Large Language Model (From Scratch). Official GitHub: https://github.com/rasbt/LLMs-from-scratch
- Companion video/course and workshop materials available from Sebastian Raschka (see his site and YouTube playlist)

(When hosting or publishing your derived code, always respect the original license in the upstream repository and include attribution.)
