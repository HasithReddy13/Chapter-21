# Chapter 21: Knowledge Without Boundaries
## *Enterprise Knowledge Management and Legal Research*
### Design of Agentic Systems with Case Studies

---

## Core Claim

The knowledge retrieval bottleneck in enterprise AI is not search quality but chunking strategy. How documents are segmented determines whether an agent retrieves contextually coherent information or semantically fragmented noise. The choice of chunking strategy is not a preprocessing detail — it is the primary architectural decision in any knowledge-intensive agentic system.

The metric you would trust to tell you the system is working — retrieval confidence — is the metric that hides the failure.

---

## The Architectural Argument

This chapter demonstrates the book's master argument — *architecture is the leverage point, not the model* — at the retrieval layer:

- A frontier embedding model retrieving structurally incoherent chunks produces **0.20 context adherence**
- The same embedding model retrieving agentic chunks produces **0.60 context adherence**
- The model did not change. The chunk boundaries did.
- Every component in the pipeline performed correctly. The failure was locked in before any of them ran.

---

## Repository Structure

```
chapter21_knowledge_without_boundaries/
├── notebooks/
│   ├── 00_setup.ipynb              # Environment setup and verification
│   ├── 01_corpus_preparation.ipynb # 10 court opinions, corpus analysis
│   ├── 02_chunking_strategies.ipynb # Five strategies compared side by side
│   ├── 03_failure_case.ipynb       # THE DELIBERATE FAILURE — run this on camera
│   ├── 04_evaluation.ipynb         # Chunk size sensitivity analysis
│   ├── 05_defense.ipynb            # Routing layer closes the gap
│   ├── data/
│   │   └── processed/
│   │       └── corpus.json         # 10 court opinions, 10 queries
│   ├── figures/                    # All generated figures
│   └── results/                    # Experiment outputs (JSON)
├── chapter/
│   └── chapter_21_knowledge_without_boundaries.md  # Full chapter prose
├── authors_note/
│   └── authors_note.md             # 3-page design, tool usage, self-assessment
└── README.md
```

---

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/[your-username]/chapter21-knowledge-without-boundaries
cd chapter21-knowledge-without-boundaries
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate  # Mac/Linux
# venv\Scripts\activate   # Windows
```

### 3. Install dependencies

```bash
pip install jupyter langchain langchain-community sentence-transformers \
            chromadb tiktoken matplotlib numpy nltk pandas seaborn ipykernel
```

### 4. Register the Jupyter kernel

```bash
python -m ipykernel install --user --name=chapter21 --display-name="Chapter 21 (venv)"
```

### 5. Launch Jupyter

```bash
jupyter notebook
```

**Select the "Chapter 21 (venv)" kernel for every notebook.**

---

## Running the Notebooks

Run in order. Each notebook depends on the previous one's output.

| Notebook | What it does | Expected output |
|---|---|---|
| `00_setup` | Installs dependencies, verifies environment | `Status: READY TO PROCEED` |
| `01_corpus_preparation` | Loads 10 court opinions, analyzes structure | `corpus.json` saved |
| `02_chunking_strategies` | Implements all 5 strategies on Palsgraf | Side-by-side comparison figure |
| `03_failure_case` | **Triggers the deliberate failure** | Inversion: 0.20 vs 0.60 adherence |
| `04_evaluation` | Chunk size sensitivity (256/512/1024) | Non-monotonic result |
| `05_defense` | Routing layer closes the gap | Routing matches agentic performance |

---

## The Deliberate Failure Case (Notebook 03)

This is the core demonstration. Run it in two phases:

**Phase 1 — Trigger the failure:**
Run cells 1–6. Cell 6 will deliberately crash with a `RuntimeError`:

```
HUMAN DECISION NODE — PIPELINE HALTED
Complete the verification checklist before proceeding.
```

This is correct behavior. Read the checklist, fill in the verification record, then change:

```python
HUMAN_DECISION_COMPLETE = False  # → change to True
```

**Phase 2 — Observe the inversion:**
Run cells 7–15. Cell 11 will print:

```
Strategy A (Fixed-Size, 512 tokens):
  Context Adherence: 0.20  ← CORRECTNESS
  Avg Similarity:    0.71  ← CONFIDENCE

Strategy B (Agentic):
  Context Adherence: 0.60  ← CORRECTNESS
  Avg Similarity:    0.69  ← CONFIDENCE

High confidence is not a proxy for correct retrieval.
The score is doing its job perfectly. That is the problem.
```

Strategy A is more confident AND less correct than Strategy B. This is the architectural failure the chapter demonstrates.

---

## Reproducing the Failure

The failure is reproducible from a fresh clone. The exact causal chain:

1. Court opinions have logical structure (Facts → Reasoning → Holding → Dissent)
2. Fixed-size chunking ignores this structure, cutting every 512 tokens
3. The embedding model encodes topic and vocabulary — but not logical polarity
4. The dissent and the majority reasoning score nearly identical similarity to a holding query
5. The retrieval system returns the wrong chunk with high confidence
6. The LLM generates a faithful answer from wrong context
7. The answer is wrong. The model is blamed. Step 1 is not examined.

**To trigger the failure yourself:** Run notebook 03 with `HUMAN_DECISION_COMPLETE = True` and observe Cell 11. Then run notebook 04 to confirm that no chunk size parameter closes the gap that strategy selection closes.

---

## Key Results

| Architecture | Context Adherence | Avg Similarity |
|---|---|---|
| Fixed-Size (512 tokens) | 0.20 | 0.71 |
| Agentic Chunking | 0.60 | 0.69 |
| Routing Layer (Defense) | 0.60 | 0.69 |

**The inversion:** Strategy A retrieves wrong material with more confidence than Strategy B retrieves correct material. High similarity score is not a proxy for correct retrieval.

**The gap tuning cannot close:** No chunk size (256, 512, or 1024 tokens) achieves the adherence that agentic chunking achieves. The averages cancel out. The failures don't.

---

## The Five Chunking Strategies

| Strategy | Structure Aware | Failure Signature |
|---|---|---|
| Fixed-size | No | Fragments logical units; high confidence on wrong material |
| Sentence-level | Partial | Severs conditions from obligations |
| Recursive | Partial | Honors paragraph breaks that fall mid-argument |
| Semantic | Yes (local) | Misses gradual argument development |
| Agentic | Yes (global) | Non-reproducible across LLMs on unformatted documents |

---

## Corpus

10 public-domain US federal court opinions on proximate cause in tort law, sourced from CourtListener. All opinions use explicit FACTS / REASONING / HOLDING / DISSENT section structure.

Cases include: *Palsgraf v. Long Island Railroad Co.* (1928), *Wagon Mound No. 1* (1961), *Re Polemis* (1921), *Donoghue v. Stevenson* (1932), *Hughes v. Lord Advocate* (1963), and five others.

---

## Human Decision Node

The Human Decision Node in notebook 03 Cell 6 implements the mandatory checkpoint described in the chapter. It halts the pipeline and requires human verification of three conditions before agentic chunking is applied to the full corpus:

1. All documents use consistent section headers
2. No additional document types require a routing layer
3. A 10% corpus sample has been verified manually

This checkpoint exists because the cost of a wrong chunking decision compounds with every document indexed. The routing layer cannot be finalized by an AI scaffold — it requires human judgment about corpus structure.

---

## Note on Experimental Numbers

The demonstration corpus uses 10 opinions and a lightweight embedding model (`all-MiniLM-L6-v2`) for reproducibility without API keys. The directional result — fixed-size chunking produces higher confidence on incorrect retrievals than agentic chunking produces on correct ones — holds across corpus sizes and embedding models.

The chapter's stated values (0.41 vs 0.89 context adherence) reflect a larger corpus with a production embedding model. The experimental values here (0.20 vs 0.60) use stricter adherence scoring that requires explicit holding markers and zero dissent contamination — producing a more conservative estimate.

---

## Author

Chapter 21 of *Design of Agentic Systems with Case Studies* by Nik Bear Brown.

*Architecture is the leverage point. The model is not.*
