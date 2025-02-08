# Eval-STT

## Overview
Eval-STT is a comprehensive evaluation framework for open-source Speech-to-Text (STT) models. It benchmarks various models based on key performance metrics, including:

- **Word Error Rate (WER)** – Measures transcription accuracy.
- **Real-Time Factor (RTF)** – Evaluates processing speed relative to audio length.
- **Latency** – Assesses the delay in generating transcriptions.
- **CPU Utilization** – Tracks computational efficiency on CPU.
- **GPU Utilization** – Measures resource usage on GPU.
- **Speed** – Compares performance across different hardware configurations.

This repository provides a structured approach to evaluate multiple STT models, ensuring a fair and consistent comparison.

## Models Evaluated
The following STT models are included in the evaluation:

### Whisper Models (OpenAI)
- `whisper-tiny`
- `whisper-base`
- `whisper-small`
- `whisper-medium`
- `whisper-large-v2`

### Wav2Vec2 Models (Facebook AI)
- `wav2vec2-base`
- `wav2vec2-large`
- `wav2vec2-english`
- `wav2vec2-xlsr-en`

### HuBERT Model (Facebook AI)
- `hubert-large`

These models cover a diverse range of architectures optimized for accuracy and efficiency.

## How to Use
### 1. Clone the Repository
```sh
git clone https://github.com/build-ai-applications/Eval-STT/edit/feat-initial-release/README.md
cd Eval-STT
```

### 2. Install Dependencies
Ensure you have the required dependencies installed:
```sh
pip install -r requirements.txt
```

### 3. Run the Evaluation Notebook
The evaluation is automated via a Jupyter Notebook.
```sh
jupyter notebook evaluate_stt.ipynb
```

### 4. Add Models for Evaluation
Modify the `STTEvaluator` class inside the notebook to include additional models. Example implementation:

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

Extend the dictionary with more models as needed.

## Evaluation Metrics
The evaluation framework provides quantitative comparisons based on:
- **Accuracy (WER)** – Lower is better.
- **Speed (RTF, Latency)** – Lower is better.
- **Resource Efficiency (CPU/GPU Utilization)** – Lower is better for cost-effective deployment.

Results are logged and visualized within the notebook.

## Contribution Guidelines
We welcome contributions! To add support for additional models:
1. Fork the repository.
2. Implement model loading and transcription functions.
3. Update the evaluation notebook.
4. Submit a pull request with a description of changes.

## License
This repository is licensed under the MIT License.

## Contact
For any queries or suggestions, please open an issue or contact the maintainers.

