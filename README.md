# Topic-Toxicity Analysis in Online News Comments

A comprehensive analysis investigating which topics attract the most toxicity in online news comments, and whether article context influences toxicity perception.

## 📋 Table of Contents
- [Overview](#overview)
- [Research Questions](#research-questions)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)

## 🔍 Overview

This project analyzes the **SFU Opinion and Comments Corpus (SOCC)**, containing 663,173 comments from The Globe and Mail (2012-2016), to identify which discussion topics attract the most toxic discourse. We employ multiple topic modeling techniques and investigate whether the same topics receive different toxicity ratings depending on the article context.

**Key Contributions:**
- Systematic ranking of topics by toxicity using 6,043 annotated comments
- Investigation of context-dependency in toxicity perception
- Comparative evaluation of 4 topic modeling methods (LDA, ProdLDA, BERTopic, NMF)
- Actionable insights for content moderation strategies

## ❓ Research Questions

**RQ1:** Which comment topics attract the most toxicity in online news discussions?

**RQ2:** Does the article context (article topic/framing) modulate the perceived toxicity of comment topics?

**RQ3:** How do different topic modeling methods compare for toxicity-topic analysis?

## 📊 Dataset

### SFU Opinion and Comments Corpus (SOCC)

**Source:** [SOCC GitHub Repository](https://github.com/sfu-discourse-lab/SOCC)

**Contents:**
- 10,339 opinion articles from The Globe and Mail
- 663,173 unique comments
- 303,665 comment threads
- Time period: January 2012 - December 2016

**Annotated Subset:**
- 1,043 comments with expert toxicity labels (original)
- 5,000 additional comments annotated using pretrained models (our work)
- **Total:** 6,043 annotated comments

**Toxicity Scale:**
1. Not toxic
2. Mildly toxic
3. Toxic
4. Very toxic

## 🔬 Methodology

### Pipeline Overview
```
Phase 1: Toxicity Annotation
    ├── Select pretrained model (Perspective API / toxic-BERT)
    ├── Validate on 1,043 expert-labeled comments
    └── Annotate 5,000 additional comments

Phase 2: Data Preparation
    ├── Stratified sampling (5,000 comments)
    ├── Quality control validation
    └── Merge datasets (total: 6,043 comments)

Phase 3: Preprocessing
    ├── Text cleaning and normalization
    ├── Link comments to article metadata
    └── Prepare for topic modeling

Phase 4: Topic Modeling (4 Methods)
    ├── LDA (Latent Dirichlet Allocation)
    ├── ProdLDA (Product of Experts LDA)
    ├── BERTopic (Transformer-based)
    └── NMF (Non-Negative Matrix Factorization)

Phase 5: Topic Evaluation
    ├── Coherence scores (c_v, c_npmi, u_mass)
    ├── Topic diversity metrics
    └── Model selection

Phase 6: Toxicity-Topic Analysis
    ├── Statistical testing (ANOVA/Kruskal-Wallis)
    ├── Effect size calculations
    └── Control variable analysis

Phase 7: Context-Dependency Analysis
    ├── Article topic categorization
    ├── Duplicate comment analysis
    ├── Topic-context interaction modeling
    └── Context effect quantification

Phase 8: Visualization & Interpretation
    ├── Topic-toxicity heatmaps
    ├── Context interaction visualizations
    └── Temporal trend analysis
```


