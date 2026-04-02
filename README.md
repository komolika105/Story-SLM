# Story-SLM
# Tiny Story SLM

A **Small Language Model (SLM)** fine-tuned for **tiny story generation, continuation, and instruction-based storytelling**. This project focuses on building a lightweight language model that can generate short, coherent, and creative stories using a custom instruction-response dataset.

---

## 📌 Project Overview

The goal of **Tiny Story SLM** is to train a compact and efficient language model capable of:

* Generating short children-friendly stories
* Completing partial story prompts
* Producing instruction-following narrative responses
* Learning storytelling structure from tabular + template-based datasets
* Running efficiently on low-resource hardware

This project is ideal for:

* Story generation research
* Educational AI tools
* Low-latency local inference
* Fine-tuning experiments on custom datasets
* SLM benchmarking and optimization

---

## 🎯 Objectives

* Build a **small, efficient language model** for storytelling
* Convert raw tabular datasets into **instruction-tuning format**
* Generate **50K+ synthetic story samples** using diverse templates
* Fine-tune using **LoRA / QLoRA / full fine-tuning**
* Evaluate coherence, creativity, and response quality
* Deploy for local inference or web integration

---

## 🏗️ Project Architecture

```text
Dataset → Template Engine → Tokenization → SLM Fine-Tuning → Evaluation → Inference API
```

### Pipeline

1. **Raw Dataset Collection**
2. **Prompt Template Conversion**
3. **Instruction-Response Pair Creation**
4. **Tokenization**
5. **Fine-Tuning**
6. **Validation**
7. **Story Generation**

---

## 📂 Project Structure

```bash
tiny-story-slm/
│
├── data/
│   ├── raw/                    # Original story datasets
│   ├── processed/              # Cleaned instruction datasets
│   └── synthetic/              # Generated 50K+ samples
│
├── notebooks/
│   ├── dataset_preparation.ipynb
│   ├── template_generation.ipynb
│   └── training_analysis.ipynb
│
├── src/
│   ├── data_preprocessing.py
│   ├── template_engine.py
│   ├── train.py
│   ├── evaluate.py
│   └── inference.py
│
├── models/
│   └── checkpoints/
│
├── configs/
│   └── training_config.yaml
│
├── requirements.txt
└── README.md
```

---

## 📊 Dataset Format

The dataset follows **instruction-response format**.

### Example

```json
{
  "instruction": "Write a short bedtime story about a brave rabbit.",
  "input": "The rabbit is afraid of the dark forest.",
  "output": "Once upon a time, a brave little rabbit named Luna entered the dark forest..."
}
```

### Supported Templates

* Story generation
* Story continuation
* Moral story generation
* Character-based story creation
* Dialogue story writing
* Emotion-driven storytelling
* Genre-specific prompts

---

## ⚙️ Installation

```bash
git clone https://github.com/your-username/tiny-story-slm.git
cd tiny-story-slm
pip install -r requirements.txt
```

---

## 🚀 Training

### Run Fine-Tuning

```bash
python src/train.py
```

### Using Config File

```bash
python src/train.py --config configs/training_config.yaml
```

### Recommended Hyperparameters

```yaml
model_name: tinyllama
batch_size: 8
learning_rate: 2e-5
epochs: 3
max_length: 512
lora_r: 16
lora_alpha: 32
```

---

## 🧠 Model Choices

Recommended base SLMs:

* entity["company","Microsoft"] Phi-2 / Phi-3 Mini
* entity["company","Meta"] Llama 3.2 1B
* entity["company","Google"] Gemma 2B
* entity["company","Alibaba Group"] Qwen 1.5 0.5B
* TinyLlama 1.1B

Best for your project:

* **TinyLlama / Phi Mini** for fast experimentation
* **Gemma 2B** for stronger language quality

---

## 📈 Evaluation Metrics

We evaluate the model on:

* **Perplexity**
* **BLEU / ROUGE**
* **Story coherence**
* **Instruction following score**
* **Creativity score**
* **Repetition rate**
* **Human readability**

### Run Evaluation

```bash
python src/evaluate.py
```

---

## 💡 Inference Example

```python
from transformers import pipeline

pipe = pipeline("text-generation", model="./models/checkpoints")

prompt = "Write a short story about a lonely robot who finds a friend."
result = pipe(prompt, max_new_tokens=120)
print(result[0]["generated_text"])
```

---

## 🌟 Sample Output

**Prompt:**

> Write a tiny story about a lost star.

**Generated Story:**

> A tiny star slipped from the night sky and landed in a quiet lake. A little girl found its glow, lifted it gently, and placed it back into the heavens, where it shined brighter than ever.

---

## 🔬 Research Extensions

Future improvements:

* Reinforcement learning for creativity optimization
* Story memory consistency module
* Character persistence across stories
* Multilingual tiny story generation
* Image-to-story generation
* Story + voice narration pipeline
* Educational moral scoring

---

## 🛠️ Tech Stack

* Python
* PyTorch
* Hugging Face Transformers
* PEFT / LoRA
* Datasets
* Pandas
* NumPy
* Weights & Biases

---

## 📌 Use Cases

* Kids learning apps
* Bedtime story generators
* AI storytelling games
* Creative writing assistants
* Educational chatbot modules
* Character dialogue generation

---

## 🤝 Contribution

Contributions are welcome.

```bash
fork → clone → create branch → commit → push → PR
```

---

## 📜 License

MIT License

---

## 👩‍💻 Author

**Komolika Raut**
AI Engineer | SLM Research | Deep Learning | NLP

---

## ⭐ Acknowledgment

Special thanks to:

* entity["company","Hugging Face"] for transformers ecosystem
* Open-source SLM communities
* TinyStories dataset researchers
* PEFT contributors

---

## 📬 Contact

If you want collaboration on **SLM, storytelling AI, or compact model research**, feel free to connect.
