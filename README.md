# 🧪Research Repository

> *Exploring the intersection of machine learning, organic chemistry, and olfactory science — with a focus on building AI-native perfumery tools for the Indian market.*

**Vaibhav Kumar Singh** · B.S. Chemistry + CS & Healthcare dual minor · IIT Bombay · `24B2725`

[![IIT Bombay](https://img.shields.io/badge/Institution-IIT%20Bombay-003B6F?style=flat-square)](https://www.iitb.ac.in)
[![Field](https://img.shields.io/badge/Field-Computational%20Olfaction-8B4513?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Active%20Research-brightgreen?style=flat-square)](#)

## 📌 Why This Exists

The global fragrance industry is undergoing a paradigm shift driven by predictive odor modeling, generative formulation, and digital olfaction. However, the Indian market—the fastest-growing fragrance ecosystem in the Asia-Pacific region—remains visually and computationally absent from this transformation.

### The Computational & Data Gap:

* **Dataset Underrepresentation:** Iconic Indian olfactory profiles—such as *Oudh, Mogra, Sandalwood,* and *Khus (Vetiver)*—are completely missing or fundamentally mislabeled in massive Western datasets like GoodScents, Dravnieks, or Arctander.
* **The 2D Topology Failure:** Current open-source baseline models heavily rely on 2D molecular graphs (SMILES). This approach fails to differentiate key stereochemical structures and optical enantiomers crucial to natural Indian botanicals.
* **The Mixture (Blend) Problem:** Perfumery is an art of complex mixtures, not isolated molecules. Predicting the emergent olfactory qualities of 50+ blended ingredients under tropical, high-humidity, and high-temperature conditions remains an unsolved chemical-ML problem.

This repository tracks my research journey toward building an **AI-Native Indic Olfaction Engine**, bridging the gap between advanced graph neural networks, stereoselective natural synthesis, and traditional Indian perfumery.

---

## 🔬 Computational Research Focus

Moving past traditional Quantitative Structure-Activity Relationship (QSAR) models, this framework targets the frontier of biological receptor simulations and deep multi-label graph modeling.

### 1. 3D Conformer Graph Neural Networks

Instead of mapping 1D/2D topological representations, we utilize **3D Graph Convolutional Networks (GCNs)** and **Graph Attention Networks (GATs)**. By generating 3D spatial conformations, the model captures geometric coordinates and binding-pocket affinities capable of distinguishing enantiomers (e.g., $l$-menthol vs. $d$-menthol) where standard SMILES strings fail.

### 2. Multi-Label Dynamic Thresholding & Focal Loss

Odor profiles are highly imbalanced and non-exclusive (a molecule can simultaneously be *woody, sweet, and smoky*). We treat this as a correlated graph problem using **Classifier Chains**, optimizing a localized decision threshold $\tau$ per label. To combat extreme data sparsity for specific Indian notes (like *Mitti* or *Ruh Khus*), the training pipeline implements **Focal Loss** rather than standard Cross-Entropy to penalize the model heavily for missing rare, high-impact descriptors.

### 3. Blend Graph Modeling & Mixture Embeddings

To model actual perfumes rather than isolated aroma chemicals, our architecture shifts input tensors from a singular molecular graph to a **weighted blend graph matrix**. The network processes components scaled by their respective mole fractions $x_i$, predicting the *emergent* scent profiles that appear exclusively when molecules interact in a liquid state.

### 4. Climate-Adaptive Volatility Retardation

Modeling top-note retention, diffusion, and longevity under extreme tropical conditions (high humidity, elevated temperatures $\ge 40^\circ\text{C}$).

---

## 📂 Repository Structure

```text
├── 01_literature/          # Annotated PDFs, mathematical breakdowns, & reviews
│   ├── computational_olfaction/
│   ├── natural_product_synthesis/
│   └── indian_fragrance_industry/
│
├── 02_datasets/            # Curation of molecular & preference databases
│   ├── odor_descriptors/   # GoodScents, Arctander, Dravnieks
│   ├── molecular_structures/ # 3D SDF conformer files
│   └── indian_preferences/ # Scraped/surveyed Indic sensory data
│
├── 03_models/              # Neural architecture & evaluation scripts
│   ├── 3d_gnn_prediction/  # PyG-based structural odor predictors
│   ├── blend_modeling/     # Mixture-fraction embedding experiments
│   └── loss_functions/     # Multi-label Focal Loss implementations
│
├── 04_notes/               # Lab notebook, mathematical proofs, architecture ideas
└── 05_presentations/       # Slide decks, research proposals, and reports

```

---

## 🛠️ Technical Stack

```python
languages   = ["Python", "SQL"]
deep_learning = ["PyTorch", "PyTorch Geometric (PyG)", "HuggingFace"]
chem_informatics = ["RDKit", "Open Babel", "PubChemPy"]
data_science = ["pandas", "numpy", "scikit-learn", "matplotlib", "seaborn"]

```

> **Note on RDKit Integration:** `RDKit` is embedded deeply into the data pipeline to handle 3D conformer generation (`AllChem.EmbedMolecule`) and convert raw molecular structures directly into spatial tensor inputs for PyTorch Geometric.

---

## 📑 Literature & Reference Papers

### Core Baselines

* **Sanchez-Lengeling et al. (2023)** | *A Principal Odor Map Unifies Diverse Tasks in Human Olfactory Perception* (Science)
*Relevance:* Establishes the foundational GNN framework for structural odor prediction using message-passing neural networks.
* **Dravnieks & Sanchez-Lengeling (2019)** | *Machine Learning for Scent* *Relevance:* Core perceptual embedding structures and multi-label benchmark creation.

### Advanced Computational Additions (2024–2026)

* **Wang et al. (2025)** | *Graph Neural Networks vs. Traditional QSAR: A Comprehensive Comparison for Multi-Label Molecular Odor Prediction* (Molecules/MDPI)
*Relevance:* Proves GNN superiority over MLPs on imbalanced odor datasets and outlines the necessity of dynamic thresholding $\tau$ per label.
* **ACS Omega (2025)** | *Deep Learning for Odor Prediction on Aroma-Chemical Blends* *Relevance:* Blueprint for modern blend-graph modeling using weighted matrices to compute emergent mixture smells rather than isolated pure compounds.
* **PMC (2024/2025)** | *Molecular Odor Prediction Using Olfactory Receptor Information* *Relevance:* Outlines a three-tier structure-to-receptor-to-odor architecture that uses human olfactory receptor binding spaces to solve the 3D optical isomer problem.
* **Analytical Chemistry** | *Machine-Learning-Based Olfactometry: Prediction of Odor Perception from Physicochemical Features* *Relevance:* Establishes validation protocols using GC/MS data and feature extraction via Boruta wrappers to verify synthetic ML models against real-world human sensory panels.
* **Gharpure Group (IIT Bombay, Ongoing)** | *Vinylogous Carbonates in Stereoselective Synthesis / Flavans and Isoflavans via o-Quinone Methides* *Relevance:* Core synthetic methodologies for organic aroma molecules and natural perfume compound stabilization.

---

## 📈 Current Roadmap & Progress

* [x] Replicate the Principal Odor Map baseline on the Dravnieks dataset.
* [x] Configure the `RDKit` execution pipeline to parse SMILES into 3D conformer geometries.
* [ ] Implement a custom PyTorch training loop utilizing **Multi-Label Focal Loss** to combat sparse descriptor distributions.
* [ ] Build a prototype mixture-composition vector model (Blend Engine) for multi-chemical perfume configurations.
* [ ] Initiate testing and collaboration avenues with the **IIT Bombay Organic Synthesis Lab (Prof. S.J. Gharpure)** and the **Unilever Fragrance Hub @ IIT Bombay**.

---

## 🤝 Contact & Collaboration

I am a second-year undergraduate student actively searching for computational research mentorship, data sharing, and engineering collaborations at the intersection of ML and chemistry.

* **Email:** [24b2725@iitb.ac.in](mailto:24b2725@iitb.ac.in)
* **Institution:** Department of Chemistry, IIT Bombay
* **Inquiries:** Open to discussions with industry perfumers, ML engineers, and computational chemists interested in building localized, adaptive olfaction tools.
