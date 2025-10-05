
# Yeast Dataset Manifold Visualization

## Data Veracity Analysis using t-SNE and Isomap

---

**Name: Singara Harendra**

**Roll No: DA25M028**

**Course:** DA5401 - Data Analysis Lab  

**Assignment:** A5 - Manifold Visualization & Data Veracity Inspection  

**Dataset:** Yeast Gene Expression (Multi-Label Classification)

---

## 🎯 Objectives

1. Apply **t-SNE** (t-Distributed Stochastic Neighbor Embedding) to visualize local data structure
2. Apply **Isomap** (Isometric Mapping) to reveal global manifold geometry
3. Identify and analyze three types of data veracity issues:
   - Noisy/Ambiguous Labels
   - Outliers
   - Hard-to-Learn Samples
4. Compare global vs local structure preservation between methods
5. Assess manifold complexity and its impact on classification difficulty

---

## 📁 Dataset Information

**Source:** Yeast Gene Expression Data (Multi-Label)
- **Features:** 103 gene expression attributes (Att1 - Att103)
- **Labels:** 14 functional class categories (Class1 - Class14)
- **Samples:** ~2,417 experiments
- **Type:** Multi-label classification (samples can belong to multiple classes)

**File Required:** `yeast.csv`

### Dataset Structure
```
Columns:
- Att1 to Att103: Gene expression levels (continuous values)
- Class1 to Class14: Binary labels (0 or 1) indicating functional category membership
```

---


---

## 🚀 Usage

### 1. Setup
Ensure `yeast.csv` is in the same directory as the notebook/script.

### 2. Run the Complete Analysis
```python
# Simply execute all cells in order
# The script is self-contained and will:
# 1. Load and preprocess data
# 2. Create visualizations
# 3. Generate analysis outputs
```

### 3. Key Parameters You Can Modify

**t-SNE Parameters:**
```python
perplexity_values = [5, 30, 50]  # Test different perplexities
# Recommended: Keep 30 for optimal results
```

**Isomap Parameters:**
```python
n_neighbors = 10  # Number of neighbors for graph construction
# Typical range: 5-15
```



---

## 📊 Output Structure

### Part A: Data Preprocessing
1. **Dataset Overview**
   - Shape, features, labels count
   - Label distribution visualization
   - Single-label vs multi-label distribution

2. **Simplified Target Creation**
   - 4-category grouping for visualization
   - Category distribution summary

3. **Feature Scaling**
   - Before/after standardization comparison
   - Statistical validation (mean≈0, std≈1)

### Part B: t-SNE Analysis (20 points)
1. **Perplexity Experimentation**
   - Three separate plots (perplexity = 5, 30, 50)
   - Comparative analysis

2. **Veracity Inspection**
   - Annotated plot highlighting:
     - Ambiguous labels (misclassified samples)
     - Outliers (anomalous patterns)
     - Hard-to-learn regions (class overlap)

3. **Detailed Analysis**
   - Written interpretation of each veracity issue
   - Classification implications

### Part C: Isomap Analysis 
1. **Isomap Projection**
   - Global structure visualization
   - Comparison with t-SNE

2. **Manifold Complexity Assessment**
   - Curvature analysis
   - Topology evaluation
   - Classification difficulty implications

3. **Side-by-Side Comparison**
   - t-SNE vs Isomap visualization
   - Global vs local structure discussion

---

## 🔍 Key Findings (Expected)

### Data Quality Issues
- **Noisy Labels:** Samples with features similar to one class but labeled as another
- **Outliers:** 5-10% of samples showing unusual expression patterns
- **Mixed Regions:** Significant class overlap in certain areas of feature space

### Manifold Characteristics
- **High Curvature:** Non-linear structure requiring complex models
- **Complex Topology:** Multiple clusters with curved connections
- **Classification Challenge:** Linear models inadequate; need non-linear approaches

### Method Comparison
- **t-SNE:** Superior for local cluster inspection
- **Isomap:** Better for global topology understanding
- **Recommendation:** Use both for comprehensive analysis

---

## 📝 Interpretation Guide

### Reading t-SNE Plots
- **Tight Clusters:** Well-separated classes
- **Scattered Points:** Potential outliers or noise
- **Mixed Colors:** Regions of class confusion
- **Isolated Points:** Anomalous samples

### Reading Isomap Plots
- **Stretched Layout:** Preservation of global distances
- **Curved Paths:** Manifold curvature
- **Bridges Between Clusters:** Geodesic connections
- **Overall Shape:** True high-dimensional topology

### Perplexity Effects
- **Low (5):** Over-fragmentation, noise sensitivity
- **Medium (30):** Balanced, generally optimal
- **High (50):** Over-smoothing, detail loss

---

## 🎓 Assignment Grading Breakdown

### Part A: Preprocessing
- Data loading and inspection
- Simplified target creation with justification
- Scaling explanation and implementation

### Part B: t-SNE
- Implementation with perplexity experimentation
- Quality visualization
- Noisy/ambiguous labels identification
- Outlier detection and hypothesis
- Hard-to-learn regions analysis

### Part C: Isomap
- Implementation and conceptual explanation
- Visualization
- Global structure comparison
- Manifold complexity and classification difficulty

**Total: 50 points**

---



---

## 📚 Theoretical Background

### Why Dimensionality Reduction?
High-dimensional data (103 features) cannot be directly visualized. Dimensionality reduction projects data to 2D while preserving important structure.

### t-SNE vs Isomap

| Aspect | t-SNE | Isomap |
|--------|-------|--------|
| **Objective** | Preserve local neighborhoods | Preserve global geodesic distances |
| **Method** | Probabilistic embedding | Graph-based MDS |
| **Best For** | Cluster visualization | Topology understanding |
| **Speed** | Slower (O(n²)) | Faster |
| **Parameters** | Perplexity | n_neighbors |

### Why Standardization Matters
Distance-based algorithms are sensitive to feature scales. Without standardization:
- Large-scale features dominate distance calculations
- Small-scale features become irrelevant
- Results are biased and unrepresentative

---



