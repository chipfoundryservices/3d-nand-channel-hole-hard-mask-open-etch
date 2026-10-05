# Chapter 4: Etch Chemistry for Hard Mask Materials

## Executive Summary

Hard mask open etch relies on fluorine-based plasmas (CF₄, SF₆) to selectively remove SiO₂ and Si₃N₄ hard masks while minimizing damage to underlying layers and protecting photoresist. This chapter develops plasma dissociation chemistry, radical generation mechanisms, etch rate kinetics, temperature/pressure dependencies, and selectivity control. Understanding hard mask etch chemistry is essential for recipe optimization: fluorine radical density determines etch rate (~100-200 nm/min for SiO₂), ion energy affects selectivity (SiO₂ vs. photoresist), and pressure tuning balances uniformity vs. etch rate. The chapter emphasizes **selectivity trade-offs**: higher fluorine radicals improve SiO₂ etch rate but worsen photoresist protection; ion-assisted etch improves uniformity but increases resist damage. Modern recipes use multi-phase approaches (high selectivity early; higher speed later after resist stripped) to optimize across competing objectives.

---

## Part 1: CF₄ Plasma Dissociation and Radical Generation

### 1.1 CF₄ Dissociation in ICP Plasma

**Electron-impact dissociation:**

$$e^- + \text{CF}_4 \rightarrow \text{CF}_3 + \text{F} + 2e^-$$
$$e^- + \text{CF}_4 \rightarrow \text{CF}_2 + 2\text{F} + 2e^-$$
$$e^- + \text{CF}_4 \rightarrow \text{CF} + 3\text{F} + 2e^-$$
$$e^- + \text{CF}_4 \rightarrow \text{C} + 4\text{F} + 2e^-$$

**Dissociation threshold:** ~9 eV

**Product distribution (100 W ICP, 20 mTorr):**

| Species | Density | Role in SiO₂ etch |
|---|---|---|
| **F• radicals** | 10¹³ cm⁻³ | Primary etch species |
| **CF₃• radicals** | 10¹² cm⁻³ | Secondary etch |
| **CF₂• radicals** | 10¹² cm⁻³ | Polymer deposition |
| **CF⁺ ions** | 10⁹ cm⁻³ | Ion-assisted etch |
| **F⁺ ions** | 10⁹ cm⁻³ | Sputtering |

### 1.2 SiO₂ Etch Mechanism

**Fluorine radical attack on oxide:**

1. **F• radical approach and initial attack:**
   $$\text{Si-O + F•} \rightarrow \text{Si-F + O•}$$

2. **Silicon fluoride formation:**
   $$\text{Si-F}_1 + \text{F•} \rightarrow \text{Si-F}_2 + e^-$$
   $$\text{Si-F}_2 + \text{F•} \rightarrow \text{Si-F}_3$$
   $$\text{Si-F}_3 + \text{F•} \rightarrow \text{SiF}_4 (volatile)$$

3. **Product volatility:**
   - SiF₄ boiling point: -86°C
   - Vapor pressure at 20°C: ~300 Pa (gaseous)
   - Readily escapes from etch chamber

**Overall reaction:**
$$\text{SiO}_2 + 4\text{F•} \rightarrow \text{SiF}_4 ↑ + \text{O}_2 ↑$$

---

## Part 2: Selectivity Control and Etch Rates

### 2.1 SiO₂ vs. Photoresist Selectivity

**Selectivity challenge in hard mask open:**

| Material | Etch Rate (nm/min) | Selectivity vs. Resist |
|---|---|---|
| **SiO₂** | 12-15 | 0.1-0.15× (resist faster!) |
| **Photoresist** | 100-150 | 1.0 (baseline) |

**Problem**: Resist erodes FASTER than SiO₂ during HMO etch!

**Selectivity tuning strategies:**

- **Low RF power**: Reduces fluorine radical generation → slower SiO₂ etch, even slower resist etch; improve selectivity slightly
- **Higher pressure (30-40 mTorr)**: Increases radical density but also recombination; complex effect
- **Temperature control**: Cooler etch → slower overall etch; selectivity maintained

### 2.2 Temperature Scaling

**Etch rate Arrhenius behavior:**

$$R(T) = R_0 e^{-E_a/k_B T}$$

**Activation energy for SiO₂ etch in CF₄:** E_a ≈ 8-12 kJ/mol

**Temperature dependence:**

| Temperature | SiO₂ Rate | Relative |
|---|---|---|
| **0°C** | 8 nm/min | 0.6× |
| **25°C** | 12 nm/min | 1.0× |
| **50°C** | 18 nm/min | 1.5× |
| **75°C** | 27 nm/min | 2.25× |

**Rule**: Etch rate ~2× per 20-25°C increase

---

## Part 3: Multi-Gas Recipes and Optimization

### 3.1 CF₄ + Ar Mixtures

**Argon dilution (20-40% Ar):**

- Improves plasma stability (easier ignition/maintenance)
- Slightly changes etch rate (dilution effect)
- Increases ion current (more Ar⁺ sputtering)

**Typical mix:** 60-80% CF₄ + 20-40% Ar

### 3.2 SF₆ as Alternative

**SF₆ characteristics:**

$$e^- + \text{SF}_6 \rightarrow \text{SF}_5 + \text{F} + 2e^-$$

| Property | CF₄ | SF₆ |
|---|---|---|
| **SiO₂ etch rate** | 12-15 nm/min | 15-20 nm/min |
| **Selectivity Si/SiO₂** | 16:1 | 20:1 |
| **Resist protection** | Good | Excellent |
| **Uniformity** | Good | Excellent |
| **Cost** | Low | Higher |

**SF₆ advantage**: Better resist selectivity; higher etch rate

---

## Summary: Hard Mask Etch Chemistry

| Parameter | Effect on Rate | Effect on Selectivity |
|---|---|---|
| **Higher F radical density** | ↑ etch rate | ↓ selectivity (resist erodes faster) |
| **Lower temperature** | ↓ etch rate | ↔ selectivity maintained |
| **Higher pressure** | Varies | Improves slightly |
| **Ion assistance** | ↑ etch rate | ↓ selectivity (resist damage) |
| **SF₆ vs. CF₄** | SF₆ ~1.3× faster | SF₆ better selectivity |

**Key Insight**: Hard mask open etch chemistry is fundamentally about managing resist erosion while achieving adequate hard mask etch rate. Selectivity is typically unfavorable; process windows are tight.

