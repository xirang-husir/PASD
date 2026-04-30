# APHD: Anatomy Prior-Guided Hierarchical Decoupling Framework for Fine-Grained Alzheimer’s Disease Staging

<div align="center">

<a href="[https://arxiv.org/abs/2601.xxxxx](https://www.google.com/search?q=https://arxiv.org/abs/2601.xxxxx)" target="_blank"><img src="[https://img.shields.io/badge/arXiv-2601.xxxxx-b31b1b.svg](https://www.google.com/search?q=https://img.shields.io/badge/arXiv-2601.xxxxx-b31b1b.svg)"></a>
<a href="[https://github.com/YourUsername/APHD](https://www.google.com/search?q=https://github.com/YourUsername/APHD)"><img src="[https://img.shields.io/badge/Project-Page-blue](https://img.shields.io/badge/Project-Page-blue)"></a>
<a href="[https://pytorch.org/](https://pytorch.org/)"><img src="[https://img.shields.io/badge/PyTorch-2.5.1-EE4C2C.svg](https://www.google.com/search?q=https://img.shields.io/badge/PyTorch-2.5.1-EE4C2C.svg)"></a>
<a href="[suspicious link removed]"><img src="[https://img.shields.io/badge/MONAI-1.4.0-5C4EE5.svg](https://www.google.com/search?q=https://img.shields.io/badge/MONAI-1.4.0-5C4EE5.svg)"></a>
<a href="https://www.google.com/search?q=LICENSE"><img src="[https://img.shields.io/badge/License-MIT-green.svg](https://www.google.com/search?q=https://img.shields.io/badge/License-MIT-green.svg)"></a>

</div>

<p align="center">
<strong><big>We wil release our complete code and preprocessed dataset after official publication！</big></strong>
</p>

<p align="center">
<strong><big>If you find our work useful, please consider giving us a star 🌟</big></strong>
</p>

<div align="center">
<img src="assets/framework.png" alt="APHD Framework" width="100%">
</div>

## 🔥 News

* **[2026.01.29]** We have submitted a manuscript to the IEEE Transactions on Medical Imaging (TMI)..
* **[2026.03.24]** We have submitted an improved version to IEEE Transactions on Image Processing (TIP) after being rejected by TMI...

## :memo: TODO

* [x] Create a README file
* [x] Submit a manuscript
* [ ] Code Release (Model & Training)
* [ ] Preprocessed Dataset Release
* [ ] Release trained weight

## 🛠️ Installation

### Prerequisites

* Linux or Windows
* Python 3.10+
* NVIDIA GPU + CUDA 12.1

### Setup

We recommend using `conda` to manage the environment.

```bash
# 1. Create and activate environment
conda create -n aphd python=3.10
conda activate aphd

# 2. Install PyTorch (CUDA 12.1)
pip install torch==2.5.1 torchvision==0.20.1 torchaudio==2.5.1 --index-url https://download.pytorch.org/whl/cu121

# 3. Install other dependencies
pip install -r requirements.txt

```

### Dependencies (`requirements.txt`)

<details>
<summary>Click to view full requirements list</summary>

```text
# ---- Core scientific stack ----
numpy==1.26.4
scipy==1.15.3
pandas==2.2.3
scikit-learn==1.6.1
joblib==1.5.1
threadpoolctl==3.6.0

# ---- Visualization / basic utils ----
matplotlib==3.10.3
seaborn==0.13.2
tqdm==4.67.1
psutil==7.0.0

# ---- Medical imaging IO / processing ----
nibabel==5.3.2
nilearn==0.11.1
SimpleITK==2.5.0
pydicom==3.0.1
scikit-image==0.25.2
imageio==2.37.0
opencv-python==4.11.0.86
Pillow==11.0.0
PyWavelets==1.8.0
tifffile==2025.5.10

# ---- DL ecosystem ----
monai==1.4.0
einops==0.8.1
pytorch-lightning==2.5.2
torchmetrics==1.7.4

# ---- Config / serialization / experiment tools ----
PyYAML==6.0.2
omegaconf==2.3.0
safetensors==0.5.3
tensorboard==2.19.0
tensorboard-data-server==0.7.2
rootutils==1.0.7

# ---- Runtime deps ----
packaging>=24.0
requests>=2.31.0

```

</details>

## 💾 Dataset Preparation

This project utilizes the **ADNI** and **NACC** datasets. Due to data usage agreements, we cannot distribute the data directly.

1. **Request Access**: Please apply for access at [ADNI LONI](https://adni.loni.usc.edu/) and [NACC](https://naccdata.org/).
2. **Preprocessing**: Follow the pipeline described in `preprocess/README.md` to convert raw MRI (NIfTI) and tabular data (CSV) into the required format.
* MRI: Skull stripping, registration to MNI152, bias field correction.
* Tabular: Missing value imputation (KNN), normalization.



## 🚀 Quick Start

### 1. Training

To train the APHD model on the ADNI dataset using the default configuration:

```bash
python train.py --config configs/train_adni.yaml

```

**Note:** You can adjust hyperparameters (learning rate, batch size, etc.) in `configs/train_adni.yaml`.

### 2. Inference / Evaluation

To evaluate a pre-trained model:

```bash
python test.py --config configs/test_adni.yaml --checkpoint checkpoints/best_model.ckpt

```

## 📋 Results

Comparison with SOTA methods on ADNI and NACC datasets (5-Class Staging):


## ✒️ Citation

If you find this project useful for your research, please consider citing:


## ❤️ Acknowledgement

This project stands on the shoulders of giants. We appreciate the open-source community:

* [MONAI](https://github.com/Project-MONAI/MONAI) for medical imaging workflows.
* [PyTorch Lightning](https://github.com/Lightning-AI/lightning) for scalable training.
* [Docling](https://github.com/docling-project/docling) for document parsing inspiration.

## 📄 License

This project is licensed under the MIT License. See [LICENSE](https://www.google.com/search?q=LICENSE) for details.
