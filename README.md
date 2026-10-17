Mapping the Human Connectome: Computational Analysis of Structural and Functional Networks
This repository contains the computational pipeline and analytical framework developed for mapping and analyzing the human connectome. By integrating neuroimaging data processing principles with graph theory, this project explores the intricate structural and functional interactions across distinct brain regions.

🧠 Project Overview
The human connectome represents the comprehensive map of neural pathways in the brain. Understanding this architecture requires distinguishing between:

Structural Connectivity: Physical white matter pathways mapped via diffusion imaging[cite: 1].

Functional Connectivity: Statistical dependencies and temporal synchrony in regional brain activity (fMRI)[cite: 1].

This project models the brain as a complex network graph, applying graph theory metrics to identify central hub regions (such as the prefrontal cortex, hippocampus, and amygdala) and evaluate whole-brain network topology.

📊 Visualizations Included
The analytical pipeline generates four core visual outputs designed for academic presentation:

Functional Connectivity Heatmap: Visualizes pairwise Pearson correlation coefficients across brain regions.

Brain Network Graph: A dense circular network representation illustrating intra- and inter-regional connectivity pathways.

Connection Degree Bar Plot: Ranks key brain regions by their connection count (degree centrality).

Correlation Strength Distribution: Displays the statistical distribution of functional coupling strengths across the connectome.

🛠️ Tech Stack & Libraries
Python (Core programming language)

NumPy & Pandas (Data manipulation and matrix operations)

NetworkX (Graph theory modeling and network topology analysis)

Matplotlib & Seaborn (High-quality scientific data visualization)

🚀 Getting Started
Prerequisites
Make sure you have Python installed along with the required libraries:

Bash
pip install numpy pandas matplotlib seaborn networkx
Running the Analysis
Clone the repository and run the main script or Jupyter Notebook to generate the connectivity matrices and visual plots:

Bash
git clone https://github.com/your-username/human-connectome-analysis.git
cd human-connectome-analysis
python connectome_pipeline.py
📄 Academic Poster & Documentation
The methodologies and results derived from this repository were compiled into an academic poster presented under the NEXAGEN initiative.

👥 Authors
Nuray İsmayılova

Susan Hasanova
