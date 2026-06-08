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
