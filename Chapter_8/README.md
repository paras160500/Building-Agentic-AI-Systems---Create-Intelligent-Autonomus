# 🔍 Explainable AI (XAI) Techniques


![Diagram](diagram.png)

---

## 📌 Overview

This project is a hands-on exploration of **Explainable AI (XAI)** techniques applied to a transformer-based NLP model. It demonstrates how to peek inside a "black box" model and understand *why* it makes the predictions it does, using three complementary approaches:

- 🧠 **Attention Visualization** — see which tokens the model focuses on
- 🎯 **Saliency Maps** — measure the contribution of each input token to the output
- 💬 **Natural Language Explanations** — generate human-readable reasoning using an LLM

All of this is built around a `bert-base-uncased` model fine-tuned for sequence classification, using a simple travel-related query as the running example.

---

## 🗂️ What's Inside

| File | Description |
|------|-------------|
| `chapter_8_main.ipynb` | The main notebook containing all the code, explanations, and visual outputs |
| `diagram.png` | Visual overview/diagram referenced above |

---

## ⚙️ How It Works

### 1️⃣ Model & Tokenizer Setup
Loads `bert-base-uncased` along with its tokenizer and prepares it for sequence classification (2 labels).

### 2️⃣ Attention Visualization 🧠
- Extracts attention weights from all transformer layers
- Plots a heatmap (using Seaborn) showing how strongly each token attends to every other token in the input

### 3️⃣ Saliency Maps 🎯
- Uses [Captum](https://captum.ai/) to compute gradient-based saliency scores
- Visualizes which tokens most strongly influence the model's prediction via a bar chart

### 4️⃣ Natural Language Explanations 💬
- Sends the input query to an OpenAI chat model
- Generates a clear, natural-language explanation of *why* the input is meaningful — bridging the gap between raw model internals and human understanding

---

## 🚀 Getting Started

> ℹ️ **Note:** The `requirements.txt` file lives in the **parent folder** — install dependencies from there before running this notebook.

```bash
pip install -r ../requirements.txt
```

You'll also need an **OpenAI API key** for the natural language explanation section. The notebook will prompt you to enter it securely at runtime.

Then simply open and run:

```bash
jupyter notebook xai_techniques.ipynb
```

---

## 🧪 Example Query

```text
"What are the best family-friendly travel destinations in Europe?"
```

This single example is used consistently across all three techniques, making it easy to compare and contrast how each method explains the model's behavior.

---

## 🛠️ Tech Stack

- 🤗 `transformers` (BERT)
- 🔥 `torch`
- 📈 `matplotlib` + `seaborn`
- 🧮 `captum`
- 🤖 `openai`

---

## ✨ Why This Matters

As models grow more complex, understanding *how* and *why* they reach their conclusions becomes critical — especially for trust, debugging, and fairness. This notebook is a compact, practical playground for experimenting with multiple XAI methods side by side.

---

⭐ Feel free to fork, tweak the input query, or swap in your own fine-tuned model to explore further!