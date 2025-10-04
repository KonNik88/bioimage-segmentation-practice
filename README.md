# Bioimage Segmentation Practice

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
