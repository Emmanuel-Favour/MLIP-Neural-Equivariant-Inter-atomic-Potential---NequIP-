# Predicting Atomic Energy & Forces with NequIP

This repository contains my first hands-on exploration into the application of machine learning for computational catalysis, using the NequIP model to predict energy and forces of atomic interactions from molecular dynamics trajectory data.
The goal is to train a neural network potential capable of accurately modeling atomic forces and energies for a Silicon system, and to explore the workflow of dataset preparation, training, testing, and deployment.

### 📌 Project Overview
Model: NequIP (Neural Equivariant Interatomic Potentials) using the Equivariant Graph Neural Network (EGNN) architecture

Data: Silicon AIMD (NVT ensemble, T = 800 K) trajectory

Atoms: 64

Frames: 110

Format: Extended XYZ (.extxyz)

Training epochs: 50

*Goal: Predict energies & forces with high accuracy for use in computational catalysis studies*

📂 Dataset
Source: [Bragitoff - sitraj.xyz](https://www.bragitoff.com/wp-content/uploads/2025/01/sitraj.xyz)

Description:
The dataset contains Atomic Interaction Molecular Dynamics (AIMD) simulation data for Silicon, generated in the NVT ensemble at 800 K.

Structure:

64 atoms per frame

110 frames total

Energies and forces included in extended XYZ format

### ⚙️ Workflow
1️⃣ Dataset Preparation
Download .xyz file and convert to .extxyz format if necessary

Split dataset into:

Training set (90%)

Validation set (10%)

The split was defined in the YAML config file:

yaml
Copy
Edit
dataset_file: all_data.extxyz
train_val_split: 0.9
2️⃣ Model Configuration
Created a YAML configuration file specifying:

Dataset path

Model architecture

Training parameters (epochs, learning rate, optimizer)

Target outputs: energy, forces


Loss decreased steadily, indicating good convergence

4️⃣ Testing & Evaluation
Loaded trained model and evaluated test set predictions

Computed metrics:

MAE (Mean Absolute Error)

RMSE (Root Mean Square Error)

Visualized predicted vs. true forces and energies

5️⃣ Deployment
Saved trained model (.pth file)

Deployed for:

Predicting energies/forces of new atomic configurations

Potential integration into molecular dynamics simulations

📖 References
Video Tutorial: [Machine Learning Potentials with NequIP](https://www.youtube.com/watch?v=xuY5-Pf_Wxc&t=1117s)

Dataset Source: [Bragitoff - sitraj.xyz](https://www.bragitoff.com/wp-content/uploads/2025/01/sitraj.xyz)

NequIP Documentation: GitHub Repo

✍️ Author
Favour Emmanuel
Chemical Engineer | Aspiring Computational Catalysis Researcher
This marks my first venture into machine learning for computational chemistry.

Other Areas I will be exploring
1. Experiment with different NequIP architectures

2. Extend to multi-element systems

3. Integrate with active learning pipelines

4. Apply to green catalysis reaction pathways

