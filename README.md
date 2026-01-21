# Higgs-Like Resonance Search (Toy Model)
**A computational high-energy physics project implementing an unbinned likelihood search for a narrow Higgs-like resonance and quantifying local and global statistical significance.**

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## Overview
This project performs a simplified Higgs-like resonance search in an invariant-mass spectrum using toy Monte Carlo data. The analysis follows standard techniques used in collider physics searches, including:
- Unbinned profile likelihood construction
- Hypothesis testing for signal-plus-background vs background-only models
- A mass-hypothesis scan to identify localized excesses
- Correction for the Look-Elsewhere Effect (LEE)

The goal is to reproduce, in a controlled setting, the statistical logic underlying real Higgs and new-physics searches at the LHC.

## Physics Motivation
Searches for new particles often involve identifying narrow resonances on top of smooth backgrounds when the particle mass is not known a priori. Scanning over many mass hypotheses inflates statistical significance unless corrected for multiple testing. This project explicitly demonstrates that effect and its correction.

## Key Features
- Toy Monte Carlo Dataset
   - Exponential background model
   - Gaussian signal model with fixed width ($\sigma$ = 1.5 GeV)
   - Invariant-mass range: 110–150 GeV
- Likelihood-Based Analysis
   - Unbinned extended likelihood
   - Signal strength ($\mu$) and resonance mass treated as parameters of interest
   - Background slope treated as a nuisance parameter
- Mass Hypothesis Scan
   - Scan step: $\Delta m$ = 0.5 GeV
   - Profile likelihood ratio test statistic
   - Local significance computed using asymptotic approximations

- Look-Elsewhere Effect
   - Effective trials factor estimation
   - Conversion from local to global significance

- Visualization
   - Invariant-mass spectrum with best-fit model
   - Local significance vs mass plots with 3$\sigma$ and 5$\sigma$ thresholds
 
## Project Contents

| File                           | Description                                                                 |
| :----------------------------- | :-------------------------------------------------------------------------- |
| `notebooks/Higgs_Search.ipynb` | Full Python implementation of the likelihood analysis and significance scan |
| `report/Mini_Higgs_Search.pdf` | Formal write-up describing the physics, statistics, and results             |
| `plots/`                       | Generated figures (mass spectrum, significance scan)                        |

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/abdelrahman-26/mini-higgs-search.git
   ```

2. Install the required libraries:
   ```bash
   pip install numpy scipy matplotlib
   ```

## Usage
Run the Jupyter Notebook to reproduce the analysis:
  ```bash
     jupyter notebook notebooks/Higgs_Search.ipynb
  ```



## Results
1. **Invariant-Mass Spectrum**
The invariant-mass distribution shows a localized excess over the smooth exponential background. A signal-plus-background fit captures this excess with a narrow Gaussian resonance.

2. **Local Significance Scan**
The profile likelihood scan reveals a maximum local significance near 125 GeV, consistent with a Higgs-like resonance prior to multiple-testing corrections.

3. **Look-Elsewhere Effect**
After accounting for the Look-Elsewhere Effect, the global significance is reduced relative to the local peak, illustrating the importance of trial-factor corrections in particle physics searches.

## Conclusion
This project demonstrates a complete end-to-end resonance search workflow using techniques standard in experimental high-energy physics. While the dataset is synthetic, the methodology mirrors real analyses used by collider experiments and highlights the statistical subtleties involved in discovery claims.

## License
Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgments
This project was completed as a computational physics exercise under the supervision of Dr. Ahmed Aly Abdelaleem and is inspired by Higgs boson search methodologies developed by the ATLAS and CMS collaborations.
