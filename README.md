# VirusID: Rapid Pathogen Identification via Native Fluorescence & Deep Learning

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)](https://www.tensorflow.org/)
[![Status](https://img.shields.io/badge/Status-Research-green)]()

> A revolutionary approach to virus identification combining **Native Fluorescence Spectroscopy** with state-of-the-art **Hybrid Deep Learning**.

## 🧬 Biotechnological Innovation

**Problem**: Traditional pathogen detection (PCR, Culture) is slow, expensive, and requires specialized reagents (kits).
**Solution**: **Native Fluorescence Spectroscopy**.

This project utilizes the unique "fingerprint" of pathogens. When irradiated with electromagnetic energy, molecules within viruses (proteins, amino acids) absorb and re-emit light at specific spectra. This **native fluorescence** is unique to the molecular composition of the virus.

-   **Label-Free**: No need for dyes, tags, or expensive reagents.
-   **Rapid**: Instantaneous spectral reading.
-   **Cost-Effective**: Minimal consumable costs.

## 🧠 AI & Engineering: The CBAM-STA CRNN Architecture

To decode the complex, noisy spectral data, we engineered a custom Deep Learning model: **FAN-ConBiLSTM**, integrating **Convolutional Block Attention Modules (CBAM)** and **Spatio-Temporal Attention (STA)**.

### Scientific Model Architecture

The model treats the spectral data as a spatio-temporal sequence (Dimensions: `6 timestamps x 588 spectral features`) and processes it through a sophisticated pipeline designed to capture both local feature patterns and long-term temporal dependencies.

#### 1. Feature Extraction with Residual Conv1D
The initial stage uses **TimeDistributed Conv1D** layers to extract local spectral features from each timeframe independently.
-   **Residual Connections**: Crucial for deep networks, we employ `Add()` layers to skip connections between Convolutional blocks. This mitigates the vanishing gradient problem and allows the model to learn identity functions, preserving essential spectral information from earlier layers while refining features in deeper layers.

#### 2. CBAM: Convolutional Block Attention Module
We integrate CBAM to adaptively refine features. CBAM sequentially infers attention maps along two separate dimensions:
-   **Channel Attention (What)**: Exploits the inter-channel relationship of features. It focuses on *which* spectral frequencies are most meaningful for pathogen identification, suppressing noise.
-   **Spatial Attention (Where)**: Focuses on *where* the informative parts of the signal are located within the feature map.
-   **Integration**: These attention maps are multiplied with the input feature map for adaptive feature refinement.

#### 3. STA: Spatio-Temporal Attention
To analyze the evolution of the viral signal over time (the 6 timestamps), we employ a Spatio-Temporal Attention mechanism:
-   **Bidirectional LSTM (BiLSTM)**: We use BiLSTM layers to process availability in both forward and backward directions. This allows the model to understand the *context* of the spectral evolution—how the fluorescence signal changes over the observation period.
-   **Multi-Head Self Attention**: Placed after the LSTM layers, this mechanism allows the model to weigh the importance of different time steps relative to each other. It identifies critical moments in the temporal sequence that are most indicative of the specific virus type.

#### 4. FAN Layer (Feature Adaptation Network)
A specialized layer implementing sinusoidal (`cos`, `sin`) and gated activations. This component captures periodic and complex non-linear patterns in the bio-signal, drawing inspiration from Fourier Analysis Networks to handle high-frequency variations in the spectral data.

### 💡 Key Design Decisions

#### Why TimeDistributed?
The model deals with **Spatio-Temporal** data. We use the `TimeDistributed` wrapper to apply the *same* Feature Extraction (CNN) layer to *each* of the 6 time steps independently.
-   **Reasoning**: This ensures that the feature extraction process is **time-invariant**. The model learns to recognize the spectral "fingerprint" of the virus regardless of *when* it occurs in the sequence, preserving the temporal structure for the subsequent LSTM layers to analyze. This prevents the flattening of time dimensions early in the network, which would destroy critical evolutionary data (CRNN approach).

#### Why Keras (TensorFlow)?
We opted for the **Keras Functional API** over PyTorch for this specific implementation.
-   **Abstraction**: Keras provides native support for complex layer wrappers like `TimeDistributed` and `Bidirectional` with a cleaner syntax.
-   **Production**: The `Functional API` allows for easy definition of complex, multi-input/multi-output directed acyclic graphs (DAGs), which is essential for our elaborate Residual + Attention architecture.
-   **Ecosystem**: Seamless integration with TensorFlow Serving (TFX) allows for rapid deployment of the trained model as a diagnostic tool.

### Performance

The model achieves exceptional sensitivity and specificity in distinguishing viral pathogens (e.g., COVID-19 VS Negative/Others).

-   **F1 Score**: > 0.95
-   **Accuracy**: > 95%

## 📂 Project Structure

-   `FANFAN_3.ipynb`: The core research notebook containing the full pipeline.
-   `WORKFLOW.md`: Step-by-step guide to run the analysis (Locally or on Colab).
-   `README_OLD.md`: **IMPORTANT**: Contains the direct download links for the Dataset (`20210329_train.csv`, `20210329_test.csv`) and pre-trained models.

## 🔗 References

-   **CBAM**: Woo, S., et al. "CBAM: Convolutional Block Attention Module." ECCV (2018).
-   **Residual Learning**: He, K., et al. "Deep Residual Learning for Image Recognition." CVPR (2016).
-   **BiLSTM**: Graves, A., et al. "Framewise phoneme classification with bidirectional LSTM and other neural network architectures." Neural Networks (2005).
