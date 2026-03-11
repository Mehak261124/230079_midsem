# Advanced Machine Learning: Mid-Semester Examination

This repository contains my submissions for the Advanced Machine Learning Mid-Semester Examination (Part A and Part B).

**Student Name**: Mehak Jain  
**Roll Number**: 230079  
**Course**: Advanced Machine Learning  

## Repository Structure

### Part A: Paper Selection and Proposal
Part A involved selecting a classical machine learning paper, justifying its selection, and proposing an experimental reproduction plan.
- The LLM usage disclosure for Part A is located in the root directory as `llm_usage_partA.json`.
- The selected paper is **"Online Multiscale Dynamic Topic Models"** by Iwata, Yamada, Sakurai, & Ueda (KDD 2010).

### Part B: Reproduction, Experimentation & Analysis (MDTM)
Part B focuses on building, running, and critically analyzing the selected paper through reproduction, baselines, and ablations. All Part B materials are located in the `partB/` directory.

- **`partB/`**: The main directory for Part B deliverables.
  - **`task_1_1.ipynb` - `task_1_3.ipynb`**: Markdown notebooks detailing the core contribution, key assumptions, and baseline comparisons (Question 1).
  - **`task_2_1.ipynb` - `task_2_3.ipynb`**: Jupyter notebooks containing the toy dataset setup, MDTM and baseline (LDA) algorithm implementation, and result analysis (Question 2).
  - **`task_3_1.ipynb` - `task_3_2.ipynb`**: Jupyter notebooks containing the ablation studies (multiscale removal and online learning removal) and failure mode analysis (Question 3).
  - **`report.pdf`**: The synthesized 4-page report spanning all tasks. A `report.md` copy is also provided.
  - **`data/`**: Contains the synthetically generated toy dataset (`word_counts.npy`, etc.) and a specific `README.md` explaining data generation.
  - **`results/`**: Contains all generated plots and visualisations resulting from the experiments.
  - **`llm_task_1_1.json` - `llm_task_4_2.json`**: The 10 mandatorily structured LLM usage disclosure files.
  - **`requirements.txt`**: The CPU-installable Python dependencies necessary to run the notebooks.

## Setup and Reproducibility
To reproduce the Part B experiments locally:
1. Navigate to the `partB` directory: `cd partB`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Execute the Jupyter notebooks sequentially from `task_2_1.ipynb` through `task_3_2.ipynb`.
