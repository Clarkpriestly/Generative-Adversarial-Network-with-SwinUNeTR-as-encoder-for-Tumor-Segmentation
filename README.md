# 3D GAN-Based Brain Tumor Segmentation using SwinUNETR

This project implements a 3D medical image segmentation framework using a **Generative Adversarial Network (GAN)**. It utilizes the SwinUNETR architecture from MONAI as the **generator** and a custom 3D convolutional neural network as the **discriminator**. The model is trained on the **BraTS 2023 SSA Challenge Dataset** for segmenting brain tumors from T2-FLAIR MRI scans.

---

## 🧠 Project Overview

- **Generator**: SwinUNETR (Vision Transformer-based UNet)
- **Discriminator**: Custom 3D CNN to distinguish real vs. generated segmentation masks
- **Losses**:
  - GAN Loss (MSE)
  - L1 Loss (MAE)
  - DiceCELoss (Dice + CrossEntropy)
- **Transforms**: Preprocessing via [TorchIO](https://torchio.readthedocs.io) including resampling, normalization, and intensity scaling.
- **Evaluation**: Visual comparison of generated vs. real masks; loss tracking via Weights & Biases.

---

## 📁 Dataset

- **Name**: ASNR-MICCAI-BraTS2023-SSA-Challenge-TrainingData_V2
- **Format**: NIfTI (.nii.gz)
- **Modality Used**: T2-FLAIR for input MRI, segmentation mask as label

Ensure the dataset is structured such that each patient folder contains:
- `*_t2f*.nii.gz`: T2-FLAIR MRI
- `*seg.nii.gz`: Segmentation label

---

## 📌 Future Improvements
Add validation and Dice score tracking

Incorporate additional MRI modalities (T1, T1ce, T2)

Export to ONNX or TorchScript

Implement UNETR and compare performance
