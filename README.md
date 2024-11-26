# Community Detection in Social Networks using Graph Neural Networks

## Introduction
Community detection in complex networks is crucial for understanding the structure and dynamics of various systems, including social networks. This project explores the use of **Graph Neural Networks (GNNs)** to enhance community detection, transforming the problem into a **node classification task**.

We used the **Reddit dataset**, leveraging subreddit interactions to classify communities and detect meaningful structures. By implementing **Graph Convolutional Networks (GCNs)** and **Attention-based Graph Neural Networks (AGNNs)**, we compared their performance with traditional algorithms like Louvain.

---

## Data Collection and Preprocessing
### Dataset Summary
- **Source**: Reddit activity spanning 40 months.
- **Nodes**: Subreddits (55,863 total).
- **Edges**: Hyperlinks between subreddits (858,490 total).
- **Node Embeddings**: 300-dimensional vectors representing subreddit features.

### Preprocessing
- Constructed a graph using **NetworkX**.
- Weighted edges based on interaction frequency.
- Filtered nodes with available embeddings (21,000 selected).
- Split the dataset into balanced training and testing sets.

---

## Methods
### Ground Truth Labels
- Used a **socially-primed LSTM model** to classify subreddits into 20 categories based on Reddit's advertisement documentation.

### Models
#### 1. **Louvain Algorithm**
- Optimized network modularity to detect communities.
- Served as a baseline for comparison.

#### 2. **Graph Neural Networks (GNNs)**
- **Graph Convolutional Networks (GCNs)**:
  - Aggregated features from neighboring nodes.
  - Achieved hierarchical feature representation.

- **Attention-based Graph Neural Networks (AGNNs)**:
  - Incorporated attention mechanisms to prioritize important connections.
  - Enhanced accuracy and interpretability.

### Training
- Loss Function: **Cross-Entropy**.
- Optimizer: **Adam**.
- Evaluated using metrics like **Accuracy**, **Normalized Mutual Information (NMI)**, and **Modularity**.

---

## Results
| Metric                  | Louvain | GCN   | AGNN  |
|-------------------------|---------|-------|-------|
| **Accuracy**            | 0.00005 | 0.637 | 0.701 |
| **NMI**                 | 0.038   | 0.412 | 0.492 |
| **Modularity**          | 0.457   | 0.378 | 0.344 |
| **Coverage**            | 0.620   | 0.506 | 0.488 |
| **Clustering Coefficient** | 0.017 | 0.216 | 0.187 |

### Discussion
- GNNs (GCN and AGNN) outperformed Louvain in **accuracy** and **NMI**.
- **AGNN** provided better attention to relevant connections.
- Visualization showed tighter and more distinct clusters for GNN models.

---

## Contributions
- **Ammar Tahir**:
  - Problem formulation and GNN approach.
  - AGNN implementation and tuning.
  - Architecture diagrams and results analysis.
- **Apratim Tripathi**:
  - Documentation, GCN training, and evaluation.
  - Literature review and preliminary baseline analysis.
- **Rohit Chandiramani**:
  - GCN implementation and tuning.
  - Baseline model evaluation and community visualizations.
- **Trisha Banerjee**:
  - Dataset identification and EDA.
  - Infomap algorithm for unsupervised clustering.

---

## References
1. Kumar, S. et al. "Community Interaction and Conflict on the Web." (2018).
2. Blondel, V. D. et al. "Fast unfolding of communities in large networks." (2008).
3. Wang, X. et al. "Unsupervised learning for community detection in attributed networks." (2021).
4. Thekumparampil, K. et al. "Attention-based Graph Neural Network for Semi-supervised Learning." (2018).
5. Ying, R. et al. "GNNExplainer: Generating Explanations for Graph Neural Networks." (2019).

---

## Visualizations
For detailed visuals and model comparisons, refer to the **graphs generated using the Kamada-Kawai layout** in the project.

---

## Contact
For questions or collaboration:
- **Ammar Tahir**: [imammar@uw.edu](mailto:imammar@uw.edu)
- **Apratim Tripathi**: [trips@uw.edu](mailto:trips@uw.edu)
- **Rohit Chandiramani**: [rohitch@uw.edu](mailto:rohitch@uw.edu)
- **Trisha Banerjee**: [tbaner@uw.edu](mailto:tbaner@uw.edu)
