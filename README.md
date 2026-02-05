# Breast Cancer Multi-Link Prediction Analysis

This repository contains the analysis code and reports for a **multi-link prediction study on breast cancer data** using a subset of the **Hetionet knowledge graph**. The project applies **knowledge graph embedding models (PyKEEN)** to predict biologically meaningful relationships between **diseases, genes, and compounds**, with visualization support from **Neo4j**.

The primary goal of this project was to:
- Predict genes upregulated in breast cancer
- Predict compounds that may downregulate key breast cancer–associated genes
- Evaluate the biological relevance of predicted links using existing biomedical literature

---


---

### Files Description

| File / Folder | Description |
|---------------|------------|
| `source/breastcancer_QuatE_ProjE.ipynb` | Jupyter Notebook containing data preprocessing, model training, and link prediction analysis using **QuatE** and **ProjE** models. |
| `source/BreastCancer_ComplEx_TransE.ipynb` | Jupyter Notebook containing data preprocessing, model training, and link prediction analysis using **ComplEx** and **TransE** models. |
| `report/Report.pdf` | Full project report detailing objectives, dataset description, methodology, results, biological validation, and discussion. |
| `report/Presentation.pdf` | Slide deck summarizing the project for quick presentation and discussion. |

---

#### Analysis

The analysis was conducted using **knowledge graph embedding models** from the **PyKEEN** framework on a subset of the **Hetionet biomedical knowledge graph** containing **Diseases, Genes, and Compounds**.

### Methods Used

The following models were trained and evaluated:

- TransE  
- ComplEx  
- QuatE  
- ProjE  

The workflow included:
- Knowledge graph construction and transformation from Neo4j to PyKEEN format
- Train/validation/test split (80/10/10)
- Multi-link prediction for:
  - Disease → Gene (upregulation)
  - Compound → Gene (downregulation)
- Selection of top predicted entities from each model
- Identification of common predictions across models

### Key Results

- **QuatE, TransE, and ProjE** successfully predicted biologically relevant genes associated with breast cancer
- **SMC4** emerged as a key gene predicted by multiple models and was supported by existing literature as a prognostic biomarker
- Predicted compounds such as **Sorafenib, Vemurafenib, and Perhexiline** showed relevance to breast cancer treatment based on prior studies
- **ComplEx** underperformed in this study, likely due to limited training epochs

A detailed explanation of the methodology, figures, results, and biological interpretation can be found in **`report/Report.pdf`**.

---

## Tools & Technologies

- Python  
- PyKEEN  
- Neo4j  
- Jupyter Notebook  
- Bioinformatics databases (e.g., PubMed)

---

## Notes

- Models were trained on **CPU only**, limiting the number of epochs
- Increasing training epochs and using GPU acceleration may improve results
- This project is intended for **academic purpose**


