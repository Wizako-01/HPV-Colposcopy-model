# Multi-View Deep Learning for Cervical Abnormality Detection using Colposcopy Images

## Overview

Cervical cancer remains a major public health challenge in sub-Saharan Africa, where access to expert colposcopy and structured screening programs is limited. Although artificial intelligence (AI) has demonstrated potential in supporting cervical screening, concerns remain regarding its ability to generalize to diverse real-world clinical settings.

This study evaluates whether integrating multi-view colposcopic images (pre- and post-acetic acid) improves the robustness of AI-based detection of cervical abnormalities in a Nigerian dataset.

---

## Objectives

- Evaluate baseline model performance using all available images  
- Compare single-view models (pre-acetic vs post-acetic)  
- Assess multi-view fusion for improved robustness  
- Perform patient-level 5-fold cross-validation  

---

## Dataset

- Total patients: 332  
- Total images: 3,356  
- Classification: Normal vs Abnormal  

Image types:
- Pre-acetic images (`p*.jpg`)  
- Post-acetic images (`po*.jpg`)  

The dataset is organized at the patient level to prevent data leakage.

---

## Methodology

### Model
- Architecture: DenseNet-121 (pretrained on ImageNet)  
- Loss function: Binary Cross-Entropy with Logits  
- Optimizer: Adam  

### Evaluation
- Patient-level 5-fold cross-validation  
- Metrics:
  - Accuracy  
  - Area Under the ROC Curve (AUC)  

### Experimental Setup

1. Baseline model  
   - Trained on all images (pre- and post-acetic combined)  

2. Pre-only model  
   - Trained using pre-acetic images  

3. Post-only model  
   - Trained using post-acetic images  

4. Fusion model  
   - Combines pre- and post-acetic predictions at the patient level  
   - Fusion performed via probability averaging  

---

## Results

| Model       | Patient AUC (Mean ± SD) | Patient Accuracy |
|------------|------------------------|-----------------|
| Baseline   | 0.620 ± 0.029          | 0.648 ± 0.041   |
| Pre-only   | 0.593 ± 0.057          | 0.580 ± 0.061   |
| Post-only  | 0.591 ± 0.103          | 0.577 ± 0.055   |
| Fusion     | 0.619 ± 0.080          | 0.610 ± 0.037   |

---

## Key Findings

- Single-view models demonstrate limited and variable performance  
- Post-acetic images alone are not sufficient for robust classification  
- Multi-view fusion improves consistency across folds  
- Performance variability reflects challenges in generalization under heterogeneous imaging conditions  

---

## Significance

This work highlights the importance of:

- Multi-view learning in colposcopy  
- Addressing generalization challenges in African populations  
- Developing AI systems suitable for real-world clinical deployment  

---

## Future Work

- Integration of explainability methods (e.g., Grad-CAM)  
- Exploration of deep multi-view fusion architectures  
- External validation on independent datasets  
- Investigation of domain adaptation techniques  

---

## Author

Jonathan Wisdom  
Final Year Medical Student  
Niger Delta University, Nigeria  

---

## License

For research and educational use only.
