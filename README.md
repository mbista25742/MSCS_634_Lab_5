# MSCS_634_Lab_5
# Wine Dataset Clustering Analysis

## Overview
This lab explores clustering techniques using Hierarchical and DBSCAN algorithms on the Wine dataset from scikit-learn. The analysis compares both methods' effectiveness in identifying wine classes and evaluates their performance using multiple metrics.

## Dataset Information
- **Dataset**: Wine dataset from sklearn.datasets
- **Samples**: 178 wine samples
- **Features**: 13 chemical properties
- **Classes**: 3 wine classes (59, 71, and 48 samples respectively)
- **Preprocessing**: Features standardized using StandardScaler

## Key Results

### Hierarchical Clustering
- **Best Configuration**: n_clusters = 3
- **Silhouette Score**: 0.277
- **Homogeneity Score**: 0.790
- **Completeness Score**: 0.783

### DBSCAN Clustering
- **Best Configuration**: eps = 2.0, min_samples = 5
- **Silhouette Score**: -0.033
- **Homogeneity Score**: 0.362
- **Completeness Score**: 0.325
- **Noise Points Identified**: 85 (47.8% of dataset)

## Analysis and Insights

### Algorithm Performance
**Hierarchical clustering significantly outperformed DBSCAN** on this dataset:
- Achieved much higher silhouette score (0.277 vs -0.033)
- Better homogeneity and completeness scores
- Successfully identified the 3 natural wine classes

### Parameter Impact
- **Hierarchical**: n_clusters = 3 matched the true number of wine classes perfectly
- **DBSCAN**: Required high eps value (2.0) to form clusters, but resulted in excessive noise points

### Key Observations
1. **Dataset Characteristics**: The wine dataset has well-separated, globular clusters that favor hierarchical clustering
2. **DBSCAN Limitations**: Struggled with the dataset's density distribution, classifying nearly half the samples as noise
3. **Standardization Impact**: Feature scaling was crucial for both algorithms due to varying measurement scales
4. **Dendrogram Insights**: Clear hierarchical structure visible with natural separation at 3 clusters

### Algorithm Strengths Observed
- **Hierarchical**: Excellent for globular clusters, deterministic results, interpretable dendrogram
- **DBSCAN**: Better suited for arbitrary-shaped clusters and outlier detection (though not optimal for this dataset)

## Challenges and Decisions
- **DBSCAN Parameter Tuning**: Required extensive parameter testing; most combinations resulted in all points being classified as noise
- **Visualization**: Used PCA for 2D visualization while maintaining 13-dimensional clustering
- **Evaluation Metrics**: Multiple metrics used to provide comprehensive performance assessment

## Conclusion
For the Wine dataset, **Hierarchical clustering proved more effective** due to the dataset's natural globular cluster structure. The results demonstrate the importance of algorithm selection based on data characteristics and domain knowledge.

## Requirements
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- scipy

## Usage
Run the Jupyter notebook `lab5.ipynb` to reproduce the analysis and visualizations.
