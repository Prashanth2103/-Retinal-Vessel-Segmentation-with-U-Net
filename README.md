# Retinal Vessel Segmentation with U‑Net

## Project Overview
Automated segmentation of retinal blood vessels in fundus OCT images to aid early disease diagnosis.

## Key Features

1. **ETL & Cleaning**  
   - Load and validate image/mask pairs  
   - Resize images to uniform 256×256 resolution  
   - Normalize intensity values  

2. **Advanced Feature Engineering**  
   - Albumentations augmentations: flips, rotations, brightness/contrast, elastic transforms  
   - Optionally compute vesselness filter channels for richer inputs  

3. **Cross‑Validation Visualization**  
   - Stratified 5‑fold CV on training set  
   - Boxplots of IoU and Dice score per fold  

4. **Hyperparameter Tuning & Model Comparison**  
   - U‑Net variants with different encoders (vanilla vs. ResNet18)  
   - Grid search on learning rate, batch size, and loss function weights  

5. **Metric Curve Plotting**  
   - Training and validation curves for loss, IoU, and Dice over epochs  

6. **Pipeline Saving**  
   - Save best model weights (`unet_retinal.pth`) and preprocessing transforms  

7. **Interactive Streamlit App**
   - save the streamlit part as a different file and name it streamlit_retinal_app.py
     - Upload fundus image  
     - Adjust segmentation threshold slider  
     - View real‑time segmentation overlay and IoU estimate  

## Repository Structure

├── data/
│ ├── train/
│ │ ├── images/
│ │ └── masks/
│ └── val/
│ ├── images/
│ └── masks/
├── notebooks/
│ └── Retinal_Vessel_Segmentation.ipynb
├── streamlit_retinal_app.py
├── models/
│ └── unet_retinal.pth
├── src/
│ ├── dataset.py # ETL & augmentations
│ ├── model.py # U‑Net architecture
│ ├── train.py # CV, hyperparam tuning & metrics
│ └── utils.py # metric functions & plotting
└── README.md

