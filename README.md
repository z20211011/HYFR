# Note: This codebase is currently being organized. The complete source code, configuration files, and pre-trained weights will be uploaded and organized shortly—well before the final publication date.

# HYFR
Physics-Informed Hybrid Flow Refinement (HyFR) for PET. Combines Conditional Flow Matching priors with a dynamic fusion schedule and exact FISTA convergence.
# HyFR: Physics-Informed Hybrid Flow Refinement for PET Reconstruction

Official PyTorch implementation of the paper **"PET Reconstruction via Physics-Informed Hybrid Flow Refinement"**.

## 📖 Overview

**HyFR** is a novel physics-informed iterative framework that synergistically integrates a pre-trained Conditional Flow Matching (CFM) prior with rigorous data fidelity constraints for high-fidelity, dose-agnostic PET reconstruction. 

Unlike conventional plug-and-play (PnP) methods, HyFR features a **hybrid update mechanism** and a **two-phase optimization strategy**:
- **Phase I (Strict Contraction):** The flow prior and data consistency term jointly steer the optimization via a dynamically scheduled fusion weight. Anatomy-aware regularization is enforced early on.
- **Phase II (Frozen Schedule):** The schedule is frozen to exactly reduce to a preconditioned FISTA, ensuring fast $\mathcal{O}(1/n^2)$ convergence and strict quantitative reliability.

---

## 🛠️ Environment Setup

We recommend using Anaconda to manage the environment. All experiments were conducted on an NVIDIA RTX 5880 Ada (48 GB).

```bash
# 1. Clone the repository
git clone https://github.com/z20211011/HyFR.git
cd HyFR

# 2. Create and activate a virtual environment
conda create -n hyfr python=3.9
conda activate hyfr

# 3. Install dependencies
pip install -r requirements.txt
