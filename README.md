# Mapping the Human Connectome: Computational Analysis of Structural and Functional Networks


This repository contains the **complete computational pipeline and analytical framework** developed for mapping, modeling, and analyzing the human connectome. By integrating advanced **neuroimaging data processing principles** with **graph theory metrics**, this project explores the intricate structural and functional interactions across distinct brain regions to decode whole-brain network topology.

---

## 🧠 **Project Overview & Motivation**
The human connectome represents the **comprehensive wiring diagram** of neural pathways and functional interactions across the nervous system[cite: 1]. While genomics decodes the molecular building blocks of life, connectomics addresses the far more complex architecture of the brain, comprising an estimated **$10^{11}$ neurons and $10^{15}$ synaptic connections**[cite: 1]. 

Understanding this system requires a clear distinction between:
* **Structural Connectivity:** The physical white matter fiber tracts mapped via **diffusion tensor imaging (DTI)**[cite: 1].
* **Functional Connectivity:** The statistical dependencies and temporal synchrony in regional brain activity measured via **resting-state fMRI (BOLD signals)**[cite: 1].

This project models the brain as a **complex mathematical graph**, applying computational network analysis to identify central hub regions (such as the prefrontal cortex, hippocampus, and amygdala) and evaluate whole-brain topological organization.

---

## 🔬 **Comprehensive Methodology & Analytical Pipeline**

The methodology implemented in this pipeline bridges neurobiology and computational data science through a rigorous, multi-step workflow:

### **1. Neuroimaging Data Extraction & Atlas Partitioning**
* **Parcellation Schema:** We utilized the standardized **Schaefer 2018 cortical and subcortical atlas**, which systematically partitions the human brain into **100 functionally distinct regions of interest (ROIs)**. This ensures anatomical uniformity and standard reference coordinates across subjects.
* **Time-Series Extraction:** Resting-state **Blood-Oxygen-Level-Dependent (BOLD)** time-series data were extracted from each of the 100 ROIs, capturing dynamic fluctuations in regional neural activity over time.

### **2. Functional Connectivity Matrix Computation**
* **Pairwise Correlation:** To quantify how strongly different brain regions communicate with one another, we calculated **Pearson correlation coefficients** for all possible pairs of BOLD time-series.
* **Matrix Construction:** This resulted in a symmetric **$100 \times 100$ Functional Connectivity Matrix**, where each cell $(i, j)$ represents the statistical correlation strength between region $i$ and region $j$. Positive values indicate synchronized co-activation, while negative values reflect anti-correlated dynamics.

### **3. Graph Theory Modeling & Network Construction**
* **Graph Representation:** Using the **NetworkX** library, the brain was transformed into a weighted graph $G = (V, E)$, where:
  * **Nodes ($V$):** Represent the **100 distinct brain regions** derived from the Schaefer 2018 atlas.
  * **Edges ($E$):** Represent the **functional interaction strengths** (correlation coefficients) connecting these regions.
* **Thresholding & Filtering:** To isolate meaningful functional networks from background noise, a **custom correlation threshold (e.g., $r > 0.15$ to $0.45$)** was applied. Edges falling below the threshold were filtered out, leaving a robust structural representation of high-confidence brain connections.

### **4. Topological Metric Extraction & Hub Identification**
* **Degree Centrality:** We computed the **node degree** (connection count) for every region in the network to determine how many robust functional links each region maintains.
* **Hub Region Profiling:** Regions exhibiting exceptionally high degree centrality—specifically the **prefrontal cortex, hippocampus, and amygdala**—were classified as critical **functional hubs**. These hubs act as vital integrative centers that balance segregated local processing with global information transfer across distant brain networks.

---

## 📊 **Generated Visualizations & Analytical Plots**

The automated pipeline generates **four core academic visual outputs** designed for high-impact presentations and scientific posters:

1. **`A. Functional Connectivity Heatmap`**: A matrix-based visualization rendered via **Seaborn**, mapping pairwise Pearson correlation coefficients ($r$ values ranging from $-1.0$ to $+1.0$) across all 100 ROIs.
2. **`B. Brain Network Graph`**: A circular network layout generated via **NetworkX and Matplotlib**, illustrating 15 key brain regions with **dense internal edge connections** to visually demonstrate whole-brain integration and wiring complexity.
3. **`C. Connection Degree Bar Plot`**: A ranked horizontal bar plot highlighting the **top brain regions by degree centrality**, emphasizing the structural dominance of primary hubs like the hippocampus and prefrontal cortex.
4. **`D. Correlation Strength Distribution`**: A statistical distribution curve displaying the **frequency of Pearson correlation values** across the connectome, proving the predominance of moderate-to-high positive functional couplings.

---

## 🛠️ **Tech Stack & Dependencies**
The pipeline is built entirely in **Python**, utilizing industry-standard data science and graph theory libraries:
* **`Python 3.8+`**: Core programming language.
* **`NumPy & Pandas`**: High-performance numerical computing, matrix manipulations, and data structuring.
* **`NetworkX`**: Graph theory algorithms, network topology extraction, and structural modeling.
* **`Matplotlib & Seaborn`**: Advanced, publication-quality scientific data visualization and aesthetic styling.

---

## 🚀 **Getting Started & Installation**

### **Prerequisites**
Ensure you have Python installed on your system. Install the required data science packages using `pip`:
```bash
pip install numpy pandas matplotlib seaborn networkx
