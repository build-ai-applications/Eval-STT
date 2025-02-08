# 🚀 Eval-STT: Open-Source Speech-to-Text Evaluation Framework

## 🌟 Overview
**Eval-STT** is an open-source evaluation framework for benchmarking **Speech-to-Text (STT) models**. It provides a structured approach to compare transcription models based on key performance metrics, ensuring **fair and transparent** evaluations.

### 📊 Key Metrics Evaluated:
- **🎯 Word Error Rate (WER)** – Measures transcription accuracy.
- **⚡ Real-Time Factor (RTF)** – Evaluates processing speed.
- **⏳ Latency** – Assesses transcription delay.
- **💻 CPU Utilization** – Tracks computational efficiency on CPU.
- **🎮 GPU Utilization** – Measures GPU resource usage.
- **🚀 Speed** – Compares performance across different hardware configurations.

## 🤖 Models Evaluated
Eval-STT supports a range of **open-source** STT models across different architectures:

### 🌀 Whisper Models (OpenAI)
- `whisper-tiny`
- `whisper-base`
- `whisper-small`
- `whisper-medium`
- `whisper-large-v2`

### 🎙️ Wav2Vec2 Models (Facebook AI)
- `wav2vec2-base`
- `wav2vec2-large`
- `wav2vec2-english`
- `wav2vec2-xlsr-en`

### 🏗️ HuBERT Model (Facebook AI)
- `hubert-large`

## 🚀 Getting Started

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/build-ai-applications/Eval-STT
cd Eval-STT
```

### 2️⃣ Install Dependencies
Ensure you have the required dependencies installed:
```sh
pip install -r requirements.txt
```

### 3️⃣ Run the Evaluation Notebook
The evaluation is automated via a **Jupyter Notebook**:
```sh
jupyter notebook evaluate_stt.ipynb
```

### 4️⃣ Add More Models for Evaluation 🚀
Modify the `STTEvaluator` class inside the notebook to include additional models. Example:

```python
import torch

class STTEvaluator:
    def __init__(self, device='cuda' if torch.cuda.is_available() else 'cpu'):
        self.device = device
        self.models = {
            'whisper-large-v2': ('openai/whisper-large-v2', self._load_whisper, self._transcribe_whisper),
            'wav2vec2-base': ('facebook/wav2vec2-base-960h', self._load_wav2vec2, self._transcribe_wav2vec2)
        }
        self.results = {}
```

Extend the dictionary with **more models** as needed! 🚀

## 📈 Evaluation Metrics
Our framework provides detailed performance insights:
- **✅ Accuracy (WER)** – Lower is better.
- **⚡ Speed (RTF, Latency)** – Lower is better.
- **💡 Resource Efficiency (CPU/GPU Utilization)** – Lower means more cost-effective deployment.

Results are logged and visualized **automatically** in the notebook! 📊🚀

## 🤝 Contribute to Eval-STT!
Eval-STT is **open-source**, and we welcome contributions from the community! 🎉

### How to Contribute:
1. **Fork** the repository.
2. Implement model loading and transcription functions.
3. Update the evaluation notebook.
4. Submit a **pull request (PR)** with a description of changes.

Your contributions help make **Eval-STT** the best open-source **Speech-to-Text evaluation framework!** 🚀💡

## 📚 References
1. [Artificial Analysis: Speech-to-Text](https://artificialanalysis.ai/speech-to-text)
2. [NVIDIA NeMo ASR Metrics](https://docs.nvidia.com/nemo-framework/user-guide/latest/nemotoolkit/asr/scores.html)
3. [IEEE STT Evaluation Paper](https://ieeexplore.ieee.org/document/9688073)
4. [German STT Evaluation GitHub](https://github.com/domcross/german-stt-evaluation)
5. [Coqui-AI STT Models](https://github.com/coqui-ai/STT-models/releases)
6. [ESPnet STT Recipe](https://espnet.github.io/espnet/recipe/st1.html)

## 📜 License
Eval-STT is **open-source** under the **Apache 2.0**. Use it freely and contribute to make it better! 🚀

## 📬 Contact Us
For any questions, suggestions, or feature requests, **open an issue** or reach out to the maintainers! 💡
