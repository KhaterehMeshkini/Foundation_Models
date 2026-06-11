# 🛰️ EO Foundation Models — Hands-on Session

> **Can an AI model read the Earth's surface — without ever being told what to look for?**
> In this hands-on session, we explore **geospatial foundation models** and put them to work on real satellite imagery — extracting deep structural and spectral fingerprints of the landscape across time, reducing millions of features into interpretable patterns, and letting the model reveal what changed, when, and where. No labels. No manual rules. Just intelligence learned from the Earth itself.

---

## 🚀 Open the Notebooks

|Open in Colab |
|--------------|
|  [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1pBF4zSwGvV0aodrZwLFz_XeCwvqCciU5?usp=sharing) |


---

## 📋 Requirements

Before running the notebooks, make sure you have the following free accounts set up:

- 🌍 **Google Earth Engine** — free account + GEE Cloud Project ID → [earthengine.google.com](https://earthengine.google.com)
- 💾 **Google Drive** — for exporting image chips (~100 MB) → [drive.google.com](https://drive.google.com)
- 🤗 **Hugging Face** — free account + accept Prithvi EO v2 model license → [huggingface.co](https://huggingface.co)
- ⚡ **Google Colab** — free GPU (T4) runtime → [colab.research.google.com](https://colab.research.google.com)

> ⚠️ **Important:** Enable the GPU runtime before running — `Runtime → Change runtime type → T4 GPU`

---

## 🔬 Case Study

**Val di Fiemme, Trentino — Vaia Storm (October 2018)**

We use the Vaia storm as a ground-truth anchor to validate whether the model can autonomously detect an abrupt landscape change without any labelled data.

---

## 🗺️ Pipeline Overview

1. **Load HLS data from GEE** — Harmonized Landsat Sentinel-2 imagery over Val di Fiemme (2018–2019)
2. **Load foundation model** — Prithvi EO v2 or Clay v1.5 via `terratorch`
3. **Generate embeddings** — each scene encoded as a high-dimensional feature vector
4. **Dimensionality reduction** — PCA and t-SNE to visualise temporal change
5. **Change detection** — identify the date of maximum embedding shift
