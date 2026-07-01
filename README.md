# 🧪 frag.ai — Research Repository

> *Exploring the intersection of machine learning, organic chemistry, and olfactory science — with a focus on building AI-native perfumery tools for the Indian market.*

**Vaibhav Kumar Singh** · B.S. Chemistry + CS & Healthcare dual minor · IIT Bombay · `24B2725`

[![IIT Bombay](https://img.shields.io/badge/Institution-IIT%20Bombay-003B6F?style=flat-square)](https://www.iitb.ac.in)
[![Field](https://img.shields.io/badge/Field-Computational%20Olfaction-8B4513?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Active%20Research-brightgreen?style=flat-square)](#)

---

## Why This Exists

The global fragrance industry is being reshaped by AI — predictive odor modeling, generative formulation, and consumer personalization at scale. Yet the Indian market, the **fastest-growing fragrance market in Asia Pacific**, remains almost entirely absent from this transformation.

Indian olfactory preferences — oudh, mogra, sandalwood, vetiver — are underrepresented in every major ML dataset. Climate-adapted formulation for tropical conditions is unsolved. AI-driven personalization for Indian consumers is a white space.

This repository tracks my research journey toward filling that gap, starting from first principles in both organic chemistry and machine learning.

---

## Research Focus Areas

### 🔬 1. Computational Olfaction
Applying graph neural networks and molecular embeddings to predict odor characteristics from chemical structure. Building on the Sanchez-Lengeling et al. (2023) principal odor map framework.

### 🇮🇳 2. Indian Fragrance Dataset & Preferences
Surveying and structuring Indian consumer scent preference data — a dataset that does not currently exist at any meaningful scale. Target ingredients: traditional Indian fragrance materials (attars, ouds, florals specific to South Asian culture).

### 🌡️ 3. Climate-Adaptive Formulation
Modeling fragrance longevity and performance under Indian climate conditions (high humidity, elevated temperatures). Identifying formulation parameters that maximise top-note retention in tropical environments.

### 🤖 4. AI-Assisted Perfumery Tools
Building prototype tools for fragrance recommendation, note-combination scoring, and personalization — targeting both B2C consumer interfaces and B2B creation assistance.

---

## Repository Structure

```
├── 01_literature/          # Paper summaries, annotated PDFs, reading notes
│   ├── computational_olfaction/
│   ├── natural_product_synthesis/
│   └── indian_fragrance_industry/
│
├── 02_datasets/            # Raw and processed data
│   ├── odor_descriptors/   # GoodScents, Arctander, Dravnieks datasets
│   ├── molecular_structures/
│   └── indian_preferences/ # (in progress)
│
├── 03_models/              # Experiments and model code
│   ├── odor_prediction/
│   ├── formulation_scoring/
│   └── recommendation_engine/
│
├── 04_notes/               # Lab notebook, meeting notes, ideas
│
└── 05_presentations/       # Slides, reports, posters
```

---

## Key Papers Being Studied

| Paper | Authors | Year | Relevance |
|---|---|---|---|
| A Principal Odor Map Unifies Diverse Tasks in Human Olfactory Perception | Sanchez-Lengeling et al. | 2023 | Core GNN framework for odor prediction |
| Machine Learning for Scent | Dravnieks + Sanchez-Lengeling | 2019 | Foundational perceptual embedding model |
| Vinylogous Carbonates in Stereoselective Synthesis | Gharpure et al. (IIT Bombay) | ongoing | Synthetic methodology for aroma compounds |
| Flavans and Isoflavans via o-Quinone Methides | Gharpure group | ongoing | Natural product synthesis relevant to fragrance |

---

## Technical Stack

```python
# Core tools
languages   = ["Python", "SQL"]
ml_libs     = ["PyTorch", "scikit-learn", "HuggingFace", "RDKit"]
chem_tools  = ["RDKit", "Open Babel", "PubChemPy"]
data        = ["pandas", "numpy", "matplotlib", "seaborn"]
```

**RDKit** is the key library here — it handles molecular graph construction directly from SMILES strings, which is the input format for odor prediction models.

---

## Current Progress

- [x] Read and annotated Sanchez-Lengeling et al. (2023) — *Science*
- [x] Set up RDKit environment and SMILES parsing pipeline
- [ ] Reproduce principal odor map baseline on Dravnieks dataset
- [ ] Survey existing Indian fragrance preference studies
- [ ] First prototype: odor descriptor predictor for common Indian aroma molecules
- [ ] Begin outreach to IIT Bombay Organic Synthesis Lab (Prof. S.J. Gharpure)
- [ ] Explore collaboration with Unilever Fragrance Hub @ IIT Bombay

---

## Broader Vision

> *The perfumer of the future will work alongside AI — not to replace creativity, but to navigate a chemical space too large for any human to explore alone. A library of ~10,000 aroma molecules, each with complex perceptual properties and formulation interactions, is exactly the kind of problem machine learning is built to solve.*

The specific opportunity in India is this: every AI fragrance model in existence today was built on Western data and Western preferences. The Indian market — 1.4 billion people, distinct cultural fragrance traditions, a tropical climate, and the fastest-growing luxury consumption story in the world — deserves its own model.

This is what I'm working toward.

---

## Contact & Collaboration

I'm a second-year undergraduate actively looking for research mentorship and collaboration in this space.

- 📧 [24b2725@iitb.ac.in](mailto:24b2725@iitb.ac.in)
- 🏛️ Department of Chemistry, IIT Bombay
- 💼 [LinkedIn](#https://www.linkedin.com/in/vaibhavkumarsingh776/) 

*Open to discussions with researchers, industry professionals, and fellow students interested in computational chemistry, AI, or the Indian fragrance industry.*

---

<sub>Started June 2026 · IIT Bombay · All research conducted independently unless otherwise noted</sub>

The literature surrounding computational olfaction is currently exploding. While the field was historically dominated by traditional Quantitative Structure–Activity Relationship (QSAR) models, the period from 2023 to early 2026 marks a definitive shift toward Graph Neural Networks (GNNs) and biological binding simulations.

Because you are already familiar with the foundational Sanchez-Lengeling (2023) paper, this breakdown focuses on the most critical recent papers categorized by the exact engineering problem they solve for your architecture.

## 1. Multi-Label Classification & Class Imbalance

The core challenge in olfaction is that a single molecule rarely has one odor. It has a primary, secondary, and tertiary profile, and the training data is massively skewed (e.g., "fruity" appears in 27% of molecules, but "fennel" in <1%).

### **Graph Neural Networks vs. Traditional QSAR: A Comprehensive Comparison for Multi-Label Molecular Odor Prediction** (Wang et al., *Molecules/MDPI*, 2025)

* **The Problem:** Do modern GNNs actually outperform traditional machine learning (Random Forest, SVM, MLP) on imbalanced, multi-label odor datasets like GoodScents?
* **The Methodology:** The researchers tested 23 model configurations across 3,304 molecules targeting the six most frequent odor types (fruity, green, sweet, floral, woody, herbal). They compared Graph Convolutional Networks (GCN), Graph Attention Networks (GAT), and NNConv against traditional descriptor-based models.
* **The Findings:** GNNs won definitively. The GCN achieved a macro F1-score of 0.5193 compared to the best traditional MLP at 0.4766 (a 24.1% relative improvement).
* **Key Takeaway for You:** The paper proves that **threshold optimization** is critical. You cannot use a standard $0.5$ probability threshold for binary relevance classification in olfaction; the threshold $\tau$ must be dynamically optimized per label (e.g., the threshold to classify a scent as "woody" must be mathematically lower than "fruity" due to dataset sparsity).

### **Predicting odor from molecular structure: a multi-label classification approach** (Saini & Ramanathan, 2022)

* **The Problem:** Handling the overlapping perceptual space of odor vocabularies (e.g., a dataset labeling a molecule as "apple" and another as "fruity").
* **The Methodology:** Applied Louvain community detection to group 109 unique odor labels into mathematically correlated clusters.
* **The Findings:** Demonstrated that odor prediction must be treated as a multi-label correlated graph problem (Classifier Chains), where the prediction of node $A$ ("citrus") dynamically updates the probability of node $B$ ("fresh").

---

## 2. The Formulation Problem: Predicting Blends

Mapping a single molecule is solved. Mapping a perfume (a mixture of 50+ molecules) is the current frontier.

### **Deep Learning for Odor Prediction on Aroma-Chemical Blends** (*ACS Omega*, 2025)

* **The Problem:** The Principal Odor Map (POM) maps pure isolated molecules. But perfumery is about *accords*. How do you predict the emergent scent when two molecules are blended?
* **The Methodology:** Shifts the input from a single molecular graph to a "blend graph" or weighted matrix. They utilized Message-Passing Neural Networks (MPNN) to capture the relationship between molecules interacting in a liquid state.
* **The Findings:** The model successfully predicts olfactory qualities that *emerge* only upon blending, which neither constituent molecule possesses on its own.
* **Key Takeaway for You:** If you are building an API for B2B formulation, this is your blueprint. Your input tensor cannot just be a single SMILES string; it must be a vector of SMILES strings weighted by their mole fractions $x_i$ to predict the resulting mixture embedding.

---

## 3. The Stereochemistry & Biological Constraint

A major failing of pure 2D topological GNNs (like basic RDKit implementations) is that they are "blind" to 3D spatial orientation.

### **Molecular Odor Prediction Using Olfactory Receptor Information** (*PMC*, 2024/2025)

* **The Problem:** Optical isomers (enantiomers). For example, $d$-menthol and $l$-menthol have the exact same 2D chemical graph, functional groups, and molecular weight. Yet, $l$-menthol has a significantly stronger minty odor. Standard GNNs predict they smell identical.
* **The Methodology:** The researchers built a three-tier model. Instead of directly mapping structure-to-odor, they mapped **structure-to-receptor**, then **receptor-to-odor**. They used classification models to predict if a molecule binds to specific human olfactory receptors, and regression models to predict binding affinity (strength).
* **The Findings:** By using *predicted receptor activation patterns* as the intermediate latent space rather than pure structural descriptors, the model successfully discriminated between the odors of highly similar optical isomers.
* **Key Takeaway for You:** To make your Indian Fragrance model robust, your neural network architecture should include a 3D conformational analysis layer (using something like conformer generation in RDKit) before the GNN message-passing phase.

---

## 4. The Dataset Construction Blueprint

If you are building the "Indic Odor Map," you need to know how to structure the raw perceptual data.

### **Machine-Learning-Based Olfactometry: Prediction of Odor Perception from Physicochemical Features** (*Analytical Chemistry*)

* **The Problem:** Replacing human sensory panels in Gas Chromatography/Olfactometry (GC/O) with an ML model.
* **The Methodology:** Extracted physicochemical features using DRAGON (molecular calculation software) and optimized feature extraction using Boruta (a random-forest wrapper). They mapped 1,026 odorants against ten high-frequency verbal odor descriptors.
* **The Findings:** Achieved 97.08% accuracy for specific odor descriptors.
* **Key Takeaway for You:** This provides the exact validation protocol for your dataset. When you scrape or collect data on Indian ingredients (e.g., Ruh Khus), you must run them through GC/MS first, extract the structural parameters, and validate your ML predictions against human panelist labels.

---

## Synthesizing This for Your Repo

Looking at your `03_models` directory, you need to transition from the 2023 baseline to the 2025 blend-and-receptor frontier.

1. **Drop pure SMILES strings for 3D graphs:** You cannot rely solely on 1D SMILES for the Indian market, as naturals heavily rely on complex stereochemistry. Use RDKit to generate 3D conformers (`AllChem.EmbedMolecule`).
2. **Shift to Multi-Label Focal Loss:** Because descriptors like *Mitti* (baked earth) will be rare in your dataset compared to *Floral*, standard Cross-Entropy loss will ignore them. You must implement Focal Loss in your PyTorch training loop to heavily penalize the model for missing rare Indian notes.
