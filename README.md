# mezcalSVM
# Mezcal Classification Using Dark-Field Microscopy and SVM

This repository contains the code and image data used in the study:  
**"Classifying Mezcal by Agave Species Using Dark-Field Microscopy and Support Vector Machine"**

## Overview

This project explores the use of image-based classification to differentiate between two mezcal varietals: *Agave salmiana* and *Agave marmorata*. Dark-field microscopy images of evaporated mezcal droplets were analyzed using a Support Vector Machine (SVM) classifier.

- **Methodology**: 1 μL droplets of diluted mezcal (20% ABV) were deposited on cleaned slides and imaged under dark-field illumination at 4× magnification.
- **Classification**: SVM models were trained on raw images (224×224 px), using a grid search over `kernel` (linear, rbf, poly), `C` (0.1, 1, 10), `degree` (1–3), and `gamma` (scale, auto).
- **Performance**: Achieved 75.6% classification accuracy and AUC = 0.73 on the validation set.

## Directory Structure

```plaintext
C:\Edgar\Dropbox\CIACYT\Projects\2021\darkfield\paper\Analytical_Methods\code
├── list.txt                      # Empty list file
├── mezcal_code.zip               # Zipped code archive
├── ROC_Curves_CM_2.ipynb         # Notebook for ROC curves and confusion matrix
├── SVM_4Classes.ipynb            # Notebook for 4-class SVM experiments
├── SVM_Aged_Young.ipynb          # Notebook for aging vs young SVM
├── SVM_All_Tepeztate.ipynb       # Notebook for Tepeztate classification
├── SVM_All_Tepeztate-Copy4.ipynb # Copy of Tepeztate notebook variant
├── SVM_Cuishe_Tepeztate.ipynb    # Notebook for Cuishe vs Tepeztate
├── SVM_Espadin_Tepeztate.ipynb   # Notebook for Espadín vs Tepeztate
└── SVM_Salmiana_Tepeztate.ipynb  # Notebook for Salmiana vs Tepeztate
```

## Requirements

- Python 3.8+
- scikit-learn
- NumPy
- Matplotlib
- OpenCV (for image loading and preprocessing)
- joblib (for model serialization)

Install dependencies:

```bash
pip install -r requirements.txt
```

## Usage

**Run the SVM model:**
   ```bash
   python src/SVM_Salmiana_Tepeztate.ipynb
   ```

## Training Output

The `SVM_Salmiana_Tepeztate.ipynb` script logs include:

```text
Start time:         2025-04-04 15:49:29.191100
Best Parameters:    {'C': 0.1, 'degree': 1, 'gamma': 'scale', 'kernel': 'rbf'}
Best CV Score:      0.64375
Validation Accuracy:0.7561

Classification Report:
  - Class 0 (Salmiana): precision 0.74, recall 0.81, f1-score 0.77 (n=21)
  - Class 1 (Tepeztate): precision 0.78, recall 0.70, f1-score 0.74 (n=20)

Confusion Matrix:
[[17  4]
 [ 6 14]]

Duration All Training: 0:31:11.817562
```

Model and label encoder are saved to `models/` for reproducibility.

## Data Availability

All image data and labels are archived at Zenodo:  
🔗 [https://doi.org/DOI_PLACEHOLDER](https://doi.org/DOI_PLACEHOLDER)

## Citation

If you use this code or data, please cite:

> Ramírez-Elías M.G., Torres-Galván J.C., Ramírez-González P.E., Langarica L.A., & Guevara E. (2025).  
> *Classifying Mezcal by Agave Species Using Dark-Field Microscopy and Support Vector Machine.*

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, provided appropriate credit is given.
