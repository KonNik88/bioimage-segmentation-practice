# Bioimage Segmentation Practice
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1.0-red.svg)](https://pytorch.org/)
[![segmentation_models_pytorch](https://img.shields.io/badge/SMP-0.3.0-green.svg)](https://github.com/qubvel/segmentation_models.pytorch)
[![Albumentations](https://img.shields.io/badge/Albumentations-1.3.0-orange.svg)](https://albumentations.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project explores **semantic segmentation** of biological microscopy images using different architectures:
- **UNet**
- **DeepLabV3**
- **PSPNet**

Additionally, we experimented with **ensemble models**:
- Soft voting (probability averaging)
- Shallow CNN
- Residual meta-model

## Results
- Base models achieved moderate performance (Dice ~0.3–0.35).
- Ensemble models did not significantly improve results due to weak individual predictions and GPU limitations.
- BCEWithLogitsLoss proved more stable than Focal Loss.
- Local cross-validation (IoU / Dice): ~0.40  
- Final competition metric (Dice on hidden test set): **0.633**  

Despite limited compute resources (RTX 2070, 8 GB VRAM), we achieved a competitive score by experimenting with multiple architectures (U-Net, DeepLabV3+, PSPNet) and ensemble strategies.  

Despite modest metrics, this work demonstrates the **full experimental workflow**:
1. Training and evaluation of segmentation models  
2. Building and testing ensembles  
3. Analysis of reasons behind success/failure  

## Key Takeaways
- Ensembles amplify weak predictions → “garbage in, garbage out”.  
- Strong base models are critical for ensembles to be effective.  
- Limited GPU memory (RTX 2070) constrained batch sizes and model choice.  
- Negative results are still valuable: they highlight real-world limitations.

## Requirements
See `requirements.txt` for dependencies.

## License
MIT License — see `LICENSE` for details.
