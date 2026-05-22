# Spectral, Wavelet Packet, and Fractal Characterisation of MedMNIST Datasets

Wavelet packet decomposition, spectral analysis, and fractal complexity characterisation of medical image modalities in the MedMNIST benchmark.

This repository extends a previous spectral-analysis study by introducing multiscale wavelet packet representations and fractal complexity measures for the comparative analysis of **OrganSMNIST** (CT-derived anatomical images) and **PathMNIST** (histopathology patches).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pronabpaul/medimg-wavelet-spectral-analysis/blob/main/WaveletPacket_Fractal_Analysis_MedMNIST.ipynb)


## Overview

Deep learning models can achieve excellent performance on medical imaging tasks, yet the intrinsic structural properties of the image modalities themselves are often less explored. This study investigates whether interpretable signal-processing descriptors can capture modality-specific characteristics in medical images.

Building upon our earlier Fourier- and texture-based analysis framework, this work introduces:

- Wavelet packet decomposition for multiscale spatial-frequency analysis
- Relative subband energy and Shannon entropy descriptors
- Box-counting fractal dimension as a complexity measure
- Rigorous statistical validation and repeated cross-validation
- Sensitivity analysis across multiple wavelet families

All experiments are conducted using the official **28 × 28 MedMNIST representations**.


## Datasets

The analysis focuses on two widely used MedMNIST datasets:

- **OrganSMNIST** - abdominal CT-derived organ classification images
- **PathMNIST** - histopathology image patches

These datasets provide a useful test bed for studying structural differences between radiological and histopathological imaging modalities.




## Key Findings

| Analysis | Main Result |
|-----------|-------------|
| Wavelet packet energy | All 16 subbands significantly different after FDR correction |
| Wavelet packet entropy | 15 of 16 subbands significantly different |
| FFT radial power | ROC-AUC = **0.978 ± 0.002** |
| Wavelet energy + entropy | ROC-AUC = **0.991 ± 0.001** |
| FFT + Wavelet | ROC-AUC = **0.994 ± 0.001** |
| Wavelet family sensitivity | Consistent performance across `db2`, `db4`, and `sym4` |
| Fractal dimension | Sensitive to threshold selection; limited discriminative value at 28 × 28 resolution |

Overall, wavelet packet descriptors consistently outperformed the FFT baseline, indicating that multiscale spatial-frequency representations provide additional information for modality characterisation beyond global frequency statistics alone.



## Relationship to Previous Work

This repository extends our earlier spectral-analysis study, which examined modality differences using:

- Fourier spectral slope analysis
- Local Binary Patterns (LBP)
- Grey-Level Co-occurrence Matrix (GLCM) statistics

The present work expands that framework by incorporating wavelet packet decomposition, entropy-based descriptors, and fractal complexity analysis, enabling a more detailed multiscale characterisation of medical image structure.



## Repository Structure

```text
medimg-wavelet-spectral-analysis/
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
└── WaveletPacket_Fractal_Analysis_MedMNIST.ipynb
```





