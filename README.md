# CRICK Ecosystem — Investor & Market Analyst Brief
### The Biology Decade: From the Matmul Ceiling to the Pair-Tensor Era

---

## The Single Thesis

Biology AI is the next frontier compute wave — and it is structurally mismatched with the silicon that currently runs it.

Every major biology AI breakthrough of the past three years — AlphaFold 3 (Google DeepMind, *Nature* 2024), Boltz-2 ( + Recursion, 2025), Evo 2 (Arc Institute + NVIDIA, *Nature* 2026), RFdiffusion3 (November 2025), State and Stack virtual-cell models (Arc Institute, 2025–2026) — converges on the same five computational operations. None of those five operations is a matrix multiplication. Yet every one of them is running today on GPU and TPU silicon designed to maximize matrix multiplication. The mismatch costs 3–12× per operation, compounding across workloads. It does not shrink with process-node improvements. It is structural.

**CRICK** is the substrate, software, and strategic playbook built for the workload these architectures actually perform.

---

## The Market Setup

### Biology AI spend is accelerating into the mismatch

| Year | Frontier AI compute (global) | Biology AI share | Biology AI spend | Native-substrate addressable |
|------|------------------------------|-----------------|-----------------|------------------------------|
| 2025 | ~$200B | 6% | ~$12B | 0% |
| 2026 | ~$320B | 8% | ~$26B | 5% |
| 2027 | ~$500B | 11% | ~$55B | 15% |
| 2028 | ~$700B | 14% | ~$98B | 30% |
| 2029 | ~$880B | 16% | ~$140B | 45% |
| 2030 | ~$1.05T | 17% | ~$180B | 55% |

**2030 SAM (native-substrate-addressable biology AI compute):** ~$100B/yr  
**Capture target for an ecosystem-level vendor:** 15–25% of SAM = **$15–25B/yr by 2030**

The comparable historical precedent is NVIDIA's rent capture on the 2014–2024 frontier AI compute wave — achieved not by owning the data or the models, but by owning the substrate, the compiler, and the developer ecosystem.

---

## The Five Structural Overheads (The Mismatch in Numbers)

The five operations that define biology AI workloads, and what it costs to run them on matmul-era silicon:

| Operation | What it is | Matmul emulation overhead | Principal affected workload |
|-----------|-----------|--------------------------|----------------------------|
| **Pair tensor** | The N×N pairwise representation of every residue-residue relationship in a protein or RNA | 4–6× per Pairformer block | AlphaFold 3, Boltz-2, every structure-prediction architecture |
| **SE(3) equivariance** | Exact rotation-translation symmetry preservation for 3D structure | 2–3× per structure module pass | Protein folding, de novo design |
| **Diffusion denoising** | Iterative reverse-time sampling over 200–500 steps | 12–20× on full de novo design runs | RFdiffusion3, AlphaFold 3 structure generation |
| **Long-context genomics** | Processing up to 1 million DNA bases in a single pass | 5–10× on Evo-class inference | Evo 2 40B, full-genome modeling |
| **CRISPR rank-one edit** | Updating a protein representation for a single mutation without re-running the full model | **80–100×** on mutational scanning | CRISPR off-target screening, drug variant scans |

These overheads do not close with the next process node. Moore's Law applies to transistor density; it does not apply to architectural mismatch.

---

## The Economic Translation

Three headline numbers that anchor the ROI case:

| Workload | Matmul-era cost | Native-substrate cost | Ratio |
|----------|----------------|----------------------|-------|
| AlphaFold 3 frontier training run | $40–60M | $6–10M | **6×** |
| Saturation mutational scan (300-residue protein) | ~$40 / scan | ~$0.50 / scan | **80×** |
| Whole-genome CRISPR off-target screen (1B guide RNAs) | ~$2.4M / run | ~$30K / run | **80×** |
| 16K-chip cluster power for equivalent biology throughput | ~60 MW | ~11.5 MW | **5×** |
| Cell-type-specific pharmacogenomics at population scale | **Infeasible** | ~$200M one-time | **Unlocks** |

The last row is the strategic prize. Population-scale cell-type-specific pharmacogenomics — predicting how a specific patient's specific tissue responds to a specific drug — is not a commercial product today because the unit economics do not close on matmul silicon. The native substrate makes it viable. This is the product category that does not currently exist but will define the 2028–2032 personalized medicine market.

---

## The 2028 Ceiling: Why It Arrives Then

Three convergent constraints hit simultaneously in 2028:

**1. Workload share crosses the board-level threshold.**  
A 5× overhead on 6% of $200B in global AI compute is ~$60B in structural waste — absorbable inside R&D budgets. The same overhead on 14% of $700B is ~$490B. That is a capital allocation crisis, not an engineering footnote.

**2. Per-workload cost rigidity is architectural, not nodal.**  
TSMC N2 to N2P buys ~30% transistor density improvement. It buys 0% reduction in an architectural mismatch. After the crossover point, additional process-node generations widen the gap with native-substrate competitors rather than closing it.

**3. The strategic-priority shift hardens substrate decisions.**  
The 2028–2029 cohort of FDA-cleared diagnostics, EMA-authorized therapeutics, and sovereign biomedical compute comments (NHS, EU-1+ Million Genomes, NIH All of Us, Japan AMED, KAUST) will set the substrate base for the 2030s. Once a biology AI product enters clinical deployment at population scale, the substrate decision becomes a regulatory and reimbursement comment — switching cost rises to multi-year, multi-billion-dollar territory.

---

## The CRICK Ecosystem: What Is Being Built

Six integrated layers, from mathematical foundations through deployed applications:

### Layer 1 — Silicon: the Crick-1 chip
Crick-1 is a **pair-tensor-native** compute substrate. Its fundamental operation is the iterative refinement of the N×N pairwise representation under geometric symmetry with diffusion-denoising integration. Seven dedicated hardware blocks replace the software emulations that cost 3–100× overhead on matmul silicon.

**Key specs vs. best comparable matmul chips:**

| | Crick-1 | NVIDIA GB300 | AWS Trainium3 | TPU v7 Ironwood |
|--|---------|-------------|---------------|-----------------|
| Biology-effective $/TFLOPS-eq-W | ~$0.18 | ~$0.78 | ~$0.35 | ~$0.42 |
| On-chip SRAM | 873 MB | ~120 MB | ~96 MB | ~256 MB |
| HBM capacity | 384 GB HBM4 | 288 GB HBM3e | 144 GB HBM3e | 192 GB HBM3e |
| HBM bandwidth | 12.8 TB/s | 8 TB/s | 4.9 TB/s | 7.4 TB/s |
| Native biology ops | Yes (7 blocks) | No | No | No |

16K-chip cluster: **134 PFLOPS effective, 11.5 MW total power** vs. ~60 MW for matmul-equivalent biology throughput.

### Layer 2 — Crick-1 Chip Lineage
Crick-1 is the third chip in a coherent architectural progression:

- **Banach-1 (2026)** — promotes fixed-point iteration to the architectural priive; handles iterative model inference natively. 12.3 PFLOPS FP4, 384 MB SRAM, 288 GB HBM3e.
- **Volder-1 (2026)** — collapses matrix multiplication into rotation-based arithmetic for exact geometric computation. 9.8 PFLOPS FP4-equivalent, 645 MB SRAM, 9.6 TB/s bandwidth.
- **Crick-1 (2026)** — adds the pair-tensor iteration as the native biology operation, inheriting and extending both prior chips. 8.2 PFLOPS FP4 pair-tensor, 873 MB SRAM, 384 GB HBM4, 12.8 TB/s.

Natural hybrid deployment: Crick-1 for biology, Volder-1 for geometric and hyperbolic workloads, Banach-1 for standard language model serving — sharing a common Ethernet-native scale-up fabric.

### Layer 3 — CRICK-IR: the Compiler
An open compiler that ingests standard PyTorch and JAX biology models — AlphaFold 3, Boltz-2, Evo 2, RFdiffusion3, State, Stack, scGPT — and routes each operation to the appropriate hardware block. The compiler recognizes the full DNA → RNA → protein → structure → function pipeline as a single compilation target, scheduling inter-stage data movement to eliminate the memory round-trips that currently dominate biology AI runtime.

This is the CUDA equivalent for biology: the developer adoption flywheel that compounds into multi-year switching cost.

### Layer 4 — Open-Source Software Stack
Four canonical modules covering the full central dogma pipeline, -licensed:

- **CRICK-DNA** — Evo 2 (40B parameters, 1M-token genomic context), HyenaDNA, Nucleotide Transformer, Caduceus, Borzoi, Enformer, CodonFM (Arc + NVIDIA, 2026)
- **CRICK-RNA** — RiNALMo (650M parameters), AIDO.RNA (1.6B, state-of-the-art on 24/26 RNA tasks), RNA-FM, RhoFold+, gRNAde (ICLR 2025 Spotlight, ribozyme-validated inverse design), full splicing, epitranscriptome, and therapeutic mRNA tooling
- **CRICK-Protein** — AlphaFold 3, Boltz-1/2, Chai-1, Protenix, HelixFold3, RFdiffusion, RFdiffusion3, FrameFlow, ESM3, ProteinMPNN
- **CRICK-Cell** — scGPT (33M cells), State (Arc 2025), Stack (Arc 2026), Geneformer, CellFM (100M cells), GEARS, RNA velocity suite

The open-source posture is rational, not altruistic. In biology AI, data provenance, reproducibility, and regulatory transparency mandate open weights. The moat is substrate, compiler, and ecosystem — not model weights. This is the Hugging Face × PyTorch × Linux pattern applied to biology.

---

## The Competitive Map

NVIDIA holds approximately 85% of the current frontier biology compute install base via raw GPU dominance and the BioNeMo platform. That share is the principal asset under competitive attack.

| Substrate | Primary priive | Biology-effective $/TFLOPS-eq-W | Strategic posture |
|-----------|-----------------|--------------------------------|------------------|
| **Crick-1** | Pair-tensor iteration | **~$0.18** | Biology-native, full stack |
| Volder-1 | Rotation iteration | ~$0.32 | Geometric/hyperbolic workloads |
| Banach-1 | Fixed-point iteration | ~$0.50 | Convergent transformer bulk |
| AWS Trainium3 | Matmul (MXFP8) | ~$0.35 | Anthropic-co-designed training |
| TPU v7 Ironwood | Matmul (inference-first) | ~$0.42 | Google internal + Anthropic |
| Microsoft Maia 200 | Matmul (FP4 inference) | ~$0.55 | Azure-captive; Anthropic talks May 21, 2026 |
| Cerebras WSE-3 | Matmul (wafer-scale) | ~$0.61 | Long-context/memory-bandwidth niche |
| NVIDIA GB300 | Matmul | ~$0.78 | General-purpose dominance |

**Anthropic's own May 2026 behavior is the leading indicator.** The company is in active talks with Microsoft to add Maia 200 as a fourth inference substrate alongside AWS Trainium3, Google TPU Ironwood, and NVIDIA Blackwell. A frontier laboratory running at $30B+ annual run-rate is already buying the right substrate for the right workload regardless of single-vendor comments. Biology workloads, with their five distinct structural mismatches, are the natural next layer of specialization.

The competitive risk is explicit: NVIDIA Rubin or post-Rubin generations could add dedicated pair-tensor extensions, compressing the advantage from 4–12× to 2–4× and narrowing the moat window from 2026–2029 to 2026–2027. This is publicly observable. The window must be built and defended before the matmul ecosystem's defensive response ships.

---

## The Moat Structure

Five compounding advantages, each with a defined time-to-replicate:

**1. Substrate-algorithm co-design** — The specific identification of pair tensor + SE(3) + diffusion + long-context genomics + rank-one edit as the five native biology operations, matched to seven dedicated hardware blocks. *Time to replicate by NVIDIA Rubin-class: 3–4 years from architectural decision.* Moat window: 2026–2029.

**2. Compiler / IR adoption** — CRICK-IR's pair tensor and SE(3) frame as first-class compiler constructs. CUDA-equivalent ecosystem inertia compounds with each year of biology AI developer adoption. Once a biology AI pipeline is compiled to CRICK-IR, the switching cost is not a chip swap — it is a compiler rewrite.

**3. Open-source ecosystem gravity** — CRICK-RNA / DNA / Protein / Cell as the canonical, reproducible, benchmarked deployment of every frontier biology model. Developer surplus leads to benchmark control, which leads to the definition of which model wins which capability claim.

**4. Data and benchmark partnerships** — RNAcentral (release 26: 45M sequences, 52 expert databases, 204 organisms), Rfam, PDB, AlphaFold Protein Structure Database, Tahoe-100M, ENCODE, Human Cell Atlas. The benchmark-and-leaderboard control point is the strategic chokepoint in any platform transition.

**5. Pharma and clinical deployment comments** — co-development agreements with top-5 pharma, top-5 AI biotech, and 2–3 hyperscalers; design wins in 3–5 sovereign biomedical compute programs (NHS, EU-1+ Million Genomes, Japan AMED, KAUST, NIH All of Us). Each is a 5–10-year comment with single-digit compute-share defended by clinical and regulatory switching cost.

---

## The Upstream Science: Why Now

The biology AI wave did not begin with compute. It began with a decade of compounding scientific results that converged, in 2024–2026, into a single commercial moment:

- **AlphaFold 2 (Nobel Prize 2024)** — protein structure prediction from sequence solved. The col(F) extraction problem — from one-dimensional amino acid sequence to three-dimensional functional structure — is now operationally feasible.
- **AlphaFold 3 (*Nature*, May 2024)** — extended to all biomolecular interactions: protein-ligand, protein-RNA, protein-DNA, multi-chain complexes. The full drug-target interaction space is now computationally addressable.
- **Evo 2 (*Nature*, March 2026)** — 40B parameters, 1 million DNA-base context, 9.3 trillion training nucleotides spanning bacteria, archaea, eukaryotes, and viruses. The full central dogma — DNA to RNA to protein — in a single foundation model.
- **RFdiffusion3 (November 2025)** — de novo design extended to all-atom biomolecular complexes. Proteins, RNA, ligands designed from scratch.
- **State and Stack (Arc Institute, 2025–2026)** — the first virtual cell foundation models trained on 100M-cell perturbation atlases. The cell is now a computational object.
- **Karkada, Olah, Tegmark et al. (February 2026)** — proved analytically that the geometry of learned representations is forced by the symmetry of the training data. The biology AI workload is not arbitrary; its structure is mathematically determined by the structure of molecular data.

These are not incremental improvements. They are the scientific infrastructure that makes the biology compute decade commercially real.

---

## The Adoption Roadmap

| Milestone | Target date | Signal |
|-----------|-------------|--------|
| Crick-1 first-silicon tape-out; CRICK-IR alpha; CRICK-RNA beta | 2026 Q3 | Design-win count: 3 |
| Volume production; CRICK-IR 1.0; full open-source releases | 2027 H1 | Design-win count: 12 |
| Matmul-era biology compute hits economic ceiling | 2028 | 30–40% of frontier biology training on Crick-1-class silicon |
| First FDA-cleared diagnostic incorporating whole-proteome variant scanning | 2028 | P2 |
| Cell-type-specific pharmacogenomics commercial deployment | 2029 | P3 |
| Integrated central-dogma compiler target as default biology AI deployment | 2030 | P5 |

---

## Key Predictions (Falsifiable)

Each prediction is stated with a defined observable diagnostic. A framework earns the name only if it can be wrong.

**P1.** Pair-tensor-native silicon produces a 3–5× cost reduction for pharma and AI-biotech compute pipelines by 2028. Top-5 AI-biotech labs adopt within 24 months of Crick-1 availability.

**P2.** Saturation mutational scanning moves from $40/scan to $0.50/scan. First FDA-cleared diagnostic incorporating whole-proteome saturation scanning approved by 2028.

**P3.** First commercial cell-type-specific pharmacogenomics product deployed by 2029.

**P4.** The col(F)/ker(F) architectural separation — genome as functional content, epigenome as regulatory modifier — becomes the standard pattern for biology compute substrate design.

**P5.** The current separation between genomic, RNA, structure, and virtual-cell foundation model pipelines is replaced by integrated single-compiler programs by 2030.

**P6.** Hybrid clusters — biology-native silicon + geometric silicon + general-purpose GPU — become the standard biology compute deployment pattern by 2029.

**P7.** Matmul-era biology compute hits its economic ceiling by 2028, driven by three convergent constraints: workload-share growth, per-workload cost rigidity, and the strategic-priority shift to population-genomic medicine.

**P8.** Eroom's Law inverts in 2027–2029. CRICK ecosystem captures 15–25% of the biology AI compute layer's economic rent.

**Failure modes are public and observable.** P7 fails if biology AI workload share plateaus below 8% through 2027 (workload growth slows). P1–P6 compress if NVIDIA Rubin ships dedicated pair-tensor and triangle-attention extensions before end-2027 (matmul substrate closes the gap architecturally). Both are visible in publicly reported data.

---

## The Strategic Summary

The matmul era built the chips of the past decade by making multiplication faster. It made language model training, image generation, and general reasoning feasible at frontier scale. It did not make biology compute feasible at frontier scale — because biology compute is not language compute.

The five structural mismatches between the biology AI workload and the matmul substrate are architectural, not nodal. They compound multiplicatively. They grow in absolute cost as biology's share of frontier compute grows. They will not be resolved by the next process node or the next software optimization pass.

The exit is a substrate designed for the workload: pair-tensor-native, geometry-exact, diffusion-iterating, long-context-genomic, rank-one-update-capable. The exit includes the compiler that routes biology workloads to it and the open-source software stack that gives developers a reason to stay. The economic prize is $100B addressable by 2030. The capture rate for the ecosystem-level vendor is 15–25%.

CRICK is that ecosystem.

> *"The matmul era of biology compute is not failing. It is finishing. Biology's decade is the next one, on the substrate the workload demands."*

---

*Document compiled May 2026. All substrate specifications sourced from published product disclosures. All scientific citations reference peer-reviewed publications or publicly available preprints. Financial projections are scenario estimates, not audited forecasts.*
