# Eval-STT

## Overview
This repository provides a comprehensive evaluation of open-source Speech-to-Text (STT) models. The evaluation covers multiple aspects, including:
- Word Error Rate (WER)
- Real-Time Factor (RTF)
- Latency
- CPU Utilization
- GPU Utilization
- Speed

## Models Evaluated
The evaluation includes various STT models, such as:
- whisper-tiny
- whisper-base
- whisper-small
- whisper-medium
- whisper-large-v2
- wav2vec2-base
- wav2vec2-large
- wav2vec2-english
- wav2vec2-xlsr-en
- hubert-large

## How to Use
A Jupyter Notebook (`.ipynb`) script is included in this repository to automate the evaluation process. To run the script, follow these steps:

1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Open and run the Jupyter Notebook:
   ```sh
   jupyter notebook evaluate_stt.ipynb
   ```

3. To evaluate models, add them to the `STTEvaluator` class inside the notebook. Example:
   ```python
   class STTEvaluator:
       def __init__(self, device='cuda' if torch.cuda.is_available() else 'cpu'):
           self.device = device
           self.models = {
               'whisper-large-v2': ('openai/whisper-large-v2', self._load_whisper, self._transcribe_whisper),
               'wav2vec2-base': ('facebook/wav2vec2-base-960h', self._load_wav2vec2, self._transcribe_wav2vec2)
           }
           self.results = {}
   ```

