# Dataset Documentation

## Overview
This directory contains a **synthetic Dirichlet-Multinomial temporal document corpus** designed for evaluating the Online Multiscale Dynamic Topic Model (MDTM).

## How the Dataset Is Generated
The dataset is generated synthetically in `task_2_1.ipynb` using the following procedure:

1. **Vocabulary**: A fixed vocabulary of 50 words (indexed 0–49).
2. **Topics**: 3 ground-truth topics, each a probability distribution over the 50-word vocabulary.
3. **Topic Evolution**: Topics evolve across 20 epochs:
   - Topic 0: Slow drift (5% perturbation per epoch)
   - Topic 1: Medium drift (15% perturbation per epoch)
   - Topic 2: Abrupt shift at epoch 10 (entire distribution changes)
4. **Document Generation**: 50 documents per epoch, each with ~45 words, generated via:
   - Draw topic proportions θ ~ Dirichlet(1, 1, 1)
   - For each word: draw topic z ~ Multinomial(θ), draw word w ~ Multinomial(φ_z)

## Files
| File | Shape | Description |
|------|-------|-------------|
| `word_counts.npy` | (20, 50, 50) | Word count matrix: (epochs × documents × vocabulary) |
| `true_topics.npy` | (20, 3, 50) | Ground-truth topic-word distributions per epoch |
| `theta_true.npy` | (20, 50, 3) | Ground-truth document-topic proportions |

## How to Load
```python
import numpy as np
word_counts = np.load('data/word_counts.npy')
true_topics = np.load('data/true_topics.npy')
theta_true = np.load('data/theta_true.npy')
```

## Random Seed
All data generation uses `numpy.random.seed(42)` for full reproducibility.

## Usage in Notebooks
- **Task 2.1** (`task_2_1.ipynb`): Generates this dataset
- **Task 2.2** (`task_2_2.ipynb`): Uses `word_counts.npy` and `true_topics.npy` for MDTM reproduction
- **Task 2.3** (`task_2_3.ipynb`): Uses the same data for result comparison
- **Task 3.1** (`task_3_1.ipynb`): Uses the same data for ablation experiments
- **Task 3.2** (`task_3_2.ipynb`): Generates a separate adversarial dataset for failure mode analysis
