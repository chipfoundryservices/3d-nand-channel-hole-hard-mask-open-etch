# Chapter 2: Hard Mask Materials - Selection and Properties

## Executive Summary

Hard mask selection fundamentally determines HMO etch performance: etch rate, selectivity to photoresist, uniformity, cost, and downstream compatibility. Three material platforms compete: (1) **SiO₂**—industry standard, excellent selectivity (16:1), mature deposition, low cost (~$0.50/wafer); (2) **Si₃N₄**—superior uniformity (±3% vs. ±5%), moderate selectivity (5-8:1), cost ~$1.50/wafer; (3) **Metal masks** (W, Ta)—excellent selectivity (>20:1), enables thin masks (30-50 nm), cost ~$2.00/wafer, emerging for advanced nodes. This chapter develops materials science: how Si-O (4.8 eV) vs. Si-N (3.8 eV) bond strengths determine etch rates, why Si₃N₄ erodes faster than SiO₂ in CF₄ plasma, and how material properties propagate through CD uniformity and LWR control. Understanding these trade-offs is essential for process design across multiple technology nodes.

---

## Part 1: Silicon Dioxide (SiO₂) Hard Masks

### 1.1 SiO₂ Atomic Structure and Bonding

**Silicon dioxide (SiO₂) structure:**
- Each Si bonded to four O atoms (tetrahedral)
- Each O bridges two Si atoms
- Amorphous (glassy) structure in PECVD films
- Si-O bond energy: **4.8 eV** (very strong)
- Si-O bond length: 1.54 Å
- Density (PECVD): 2.2-2.3 g/cm³
- Thermal conductivity: κ ≈ 1.4 W/m·K (insulator)
- No glass transition temperature (stable >1000°C)

### 1.2 PECVD SiO₂ Deposition

**Reaction chemistry:**
$$\text{SiH}_4 + \text{CO}_2 \rightarrow \text{SiO}_2 + \text{H}_2 + \text{byproducts}$$

**Typical deposition parameters:**

| Parameter | Value | Effect |
|---|---|---|
| Power | 100-500 W | Higher → faster |
| Pressure | 0.3-5 Torr | Lower → faster |
| SiH₄ flow | 10-100 sccm | Proportional |
| Temperature | 250-450°C | Higher → faster |
| Deposition rate | 20-50 nm/min | Tunable |

**Film quality:** Slightly Si-rich PECVD SiO₂ optimal (faster etch, fewer defects)

---

## Part 2: Silicon Nitride (Si₃N₄) Hard Masks

### 2.1 Si₃N₄ Structure

**Silicon nitride properties:**
- Stoichiometry: 3 Si per 4 N atoms
- Si-N bond energy: **3.8 eV** (weaker than Si-O)
- Density: 3.0-3.1 g/cm³ (denser than SiO₂)
- Thermal conductivity: κ ≈ 10-15 W/m·K (5-10× better than SiO₂)

### 2.2 Etch Rate Comparison

**In CF₄ plasma:**

| Material | Etch Rate | vs. Resist |
|---|---|---|
| Photoresist | 100-200 nm/min | 1.0× |
| SiO₂ | 10-15 nm/min | 0.1× |
| Si₃N₄ | 15-25 nm/min | 0.15-0.25× |

**Why Si₃N₄ faster:** Si-N bond (3.8 eV) weaker than Si-O (4.8 eV); F• radicals can break it more easily.

**Consequence:** Si₃N₄ masks must be ~2× thicker for same etch time → higher cost

---

## Part 3: Metal Masks (Tungsten, Tantalum)

### 3.1 Metal Mask Selectivity

**Etch rates:**

| Material | Rate |
|---|---|
| Resist | 100-200 nm/min |
| Tungsten | 1-3 nm/min |
| Tantalum | 1-2 nm/min |

**Selectivity (resist/metal): ~50:1** (exceptional; enables thin masks 30-50 nm)

**Advantages:**
- Excellent selectivity
- Thin mask capable
- Slow, controllable etch

**Disadvantages:**
- High cost ($2.00/wafer)
- Complex deposition/removal
- Emerging (not yet mainstream)

---

## Part 4: Material Selection by Node

### 4.1 Manufacturing Node Choices

| Node | Material | Thickness | Rationale |
|---|---|---|---|
| **28 nm** | SiO₂ | 100-150 nm | Cost, maturity |
| **20 nm** | SiO₂/Si₃N₄ | 100-300 nm | Transition; uniformity pressure |
| **14 nm** | Si₃N₄ | 200-300 nm | Better uniformity needed |
| **Sub-10 nm** | Si₃N₄/Metal | 200-50 nm | Ultimate uniformity; cost secondary |

**Critical insight:** CD uniformity requirements drive material migration. As specs tighten (±8% → ±2%), SiO₂ insufficient; Si₃N₄ or metal masks required despite higher cost.

---

[Continue to Chapter 3: Photoresist and Lithographic Patterning →](./03-photoresist-patterning.md)
