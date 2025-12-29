# Reproducing Fig. 5H–J (TAM dot-plots + endocytosis violin plots) with **BoNE**

This repository contains the **BoNE (Boolean Network Explorer)** workflow used to generate **Figure 5 panels H–J** in *Mullick et al.*:
- **H**: Dot plot (bubble plot) summarizing enrichment of immune / macrophage-state signatures in **F4/80⁺ TAMs** (WT vs GIV-KO).
- **I**: Dot plot (bubble plot) summarizing enrichment of **endocytosis / clathrin-mediated trafficking** signatures in TAMs.
- **J**: **Violin plots** comparing BoNE composite scores for selected endocytic/clathrin signatures in TAMs.

> **Main entry point:** `Fig 5_TAM_PD1.ipynb`

---

## Contents

- `Fig 5_TAM_PD1.ipynb` — notebook that computes BoNE composite scores, ROC-AUC / p-values, and produces dot/violin plots.
- `bone(1).py` — BoNE framework (scoring + plotting utilities).
- `StepMiner(1).py`, `HegemonUtil(1).py` — dependencies used by BoNE.
- Gene-signature files (one gene per line):
  - `KEGG_ENDOCYTOSIS.txt`
  - `CLATHRIN_COATED_ENDOCYTIC_GSEA.txt`
  - `endocytosis_lungC_37920434.txt`
  - `Responders_Reactive`, `response_tolerant.txt`, `Cl18_upR.txt`, `Up_in_CR_PMID36555441.txt`, `up_R_PMID38969631.txt`

---

## 1) Setup
conda create -n bone-fig5 python=3.10 -y
conda activate bone-fig5
pip install numpy pandas scipy matplotlib seaborn scikit-learn requests pillow opencv-python jupyter

### 1.1 Clone

> **Note:** the repository name ends with a dot: `Mullick_et_al.`

```bash
git clone https://github.com/sinha7290/Mullick_et_al..git
cd Mullick_et_al.
---

