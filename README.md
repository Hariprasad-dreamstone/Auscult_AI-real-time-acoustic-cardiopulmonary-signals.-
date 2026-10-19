# AUSCULT AI — Real-time Acoustic Cardiopulmonary Signals

AUSCULT AI is an experimental training and export pipeline for a small 1D-CNN classifier that detects simple cardiopulmonary acoustic classes from MFCC features — designed to be small enough for on-device inference (ESP32 / TensorFlow Lite Micro). The working notebook and training scripts are available in `final_AUSCULT_AI_Project.ipynb`.

Live Colab notebook:
https://colab.research.google.com/github/Hariprasad-dreamstone/Auscult_AI-real-time-acoustic-cardiopulmonary-signals.-/blob/main/final_AUSCULT_AI_Project.ipynb

## Project overview

- Input: MFCC feature arrays (shape used in notebook: 63 frames × 13 coefficients).
- Model: compact 1D-CNN / small dense networks used in the notebook for rapid iteration.
- Output classes (labels used in the notebook):
  - Normal
  - Aortic Stenosis
  - Mitral Regurg.
  - Asthma / Wheeze
  - Pulmonary Crackles
- Exports: Keras .keras model and TensorFlow Lite `.tflite` file suitable for mobile or microcontroller deployment.
- Target hardware: prototyped for ESP32 + MAX9814 microphone preamp, with TFLite Micro for on-device inference.

> Note: The notebook uses synthetic data for demonstration and model export workflows. Replace with real, labeled auscultation recordings and proper preprocessing for any real clinical use.

## What’s inside the notebook

- Data generation (synthetic) and seeding for reproducibility.
- Model definitions (multiple small architectures explored — Conv1D and dense-only variants).
- Training runs and evaluation (classification report and confusion matrix printed).
- Keras model saving and conversion to TFLite.
- Inline code to generate a base64 download link for the produced TFLite file.
- Example model sizes seen in the notebook (~277 KB and variations depending on model).

## Quickstart (Colab)

1. Open the notebook in Colab:
   - Use the link above.
2. Run cells in order. The notebook creates `/content/models/auscult_model.tflite` and provides a download link when conversion completes.

## Reproducing locally

1. Clone the repository:
   ```bash
   git clone https://github.com/Hariprasad-dreamstone/Auscult_AI-real-time-acoustic-cardiopulmonary-signals.-.git
   cd Auscult_AI-real-time-acoustic-cardiopulmonary-signals.-
