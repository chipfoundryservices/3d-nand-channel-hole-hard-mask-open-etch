# Chapter 3: Photoresist and Lithographic Patterning

## Executive Summary

Photoresist is the critical first patterning layer in 3D NAND manufacturing. Modern extreme ultraviolet (EUV) lithography at 13.5 nm wavelength creates sub-25 nm features through chemically amplified resist (CAR) exposed to photomasks. This chapter develops resist chemistry, lithographic process windows, CD accuracy requirements, and resist interactions with hard mask open etch. Critical topics: resist types (positive vs. negative CAR), thickness selection (50-200 nm), glass transition temperature (Tg) for thermal stability, line width roughness (LWR) minimization (<2.5 nm 3-sigma spec), and CD uniformity (±1 nm across 300 mm wafer). Special emphasis on **LWR propagation**: initial lithographic roughness of 2 nm becomes 8-12 nm after 50 µm VCH etch—meaning lithography quality directly determines final channel uniformity. Understanding resist-etch interactions is essential: resist erosion rate (~100 nm/min in CF₄) far exceeds hard mask erosion rate (~10 nm/min), requiring careful protection strategies during hard mask open etch.

---

## Part 1: Photoresist Chemistry and Materials

### 1.1 Chemically Amplified Resist (CAR)

#### Positive-Tone CAR Mechanism

**Composition and structure:**

| Component | Weight % | Function |
|---|---|---|
| **Resin (Novolac/Acrylic)** | 65-75% | Base polymer matrix |
| **Photoacid Generator (PAG)** | 5-10% | Generates H+ upon UV exposure |
| **Dissolution Inhibitor** | 5-10% | Protects unexposed regions |
| **Surfactant** | 0.5-2% | Improves film properties |

**Lithographic process flow:**

```
Step 1: Exposure (193 nm or EUV light)
  └─ PAG absorbs photon
  └─ Generates strong Brønsted acid (H+)
  └─ Acid concentration: 10-100 mM in exposed regions

Step 2: Post-Exposure Bake (PEB), ~110°C, 60-120 sec
  └─ Acid diffuses (mean free path ~50 nm)
  └─ Catalyzes deprotection: R-CO-O-C(CH₃)₃ → R-CO-OH + isobutene
  └─ Deprotected regions become hydrophilic
  └─ Unexposed regions remain protected (hydrophobic)

Step 3: Development
  └─ Alkaline developer (TMAH 2.38%, tetramethylammonium hydroxide)
  └─ Developer dissolves deprotected (exposed) regions
  └─ Dissolution rate (deprotected): ~100-300 nm/min
  └─ Dissolution rate (protected): <1 nm/min
  └─ Selectivity: 100-300:1

Result: Positive pattern
  └─ Exposed regions removed
  └─ Unexposed regions remain as resist pattern
```

#### Negative-Tone CAR (Emerging for 3D NAND)

**Inverse mechanism:**

- Exposure generates acid
- Acid causes **cross-linking** in exposed regions
- Cross-linked regions become **insoluble**
- Unexposed regions dissolve in developer
- Result: **Negative pattern** (exposed = solid; unexposed = removed)

**Advantages over positive-tone:**

| Property | Positive | Negative |
|---|---|---|
| **CD uniformity** | Good | Excellent (no diffusion during PEB) |
| **LWR** | 2.0-2.5 nm | 1.5-2.0 nm (better) |
| **Contrast** | Moderate | High (sharp transitions) |
| **Cost** | Lower | Higher (new materials) |

**Industry trend**: Moving to negative-tone for advanced 3D NAND (better LWR)

---

### 1.2 Resist Properties for 3D NAND HMO

#### Thickness Selection and Impact

**Resist thickness range: 50-200 nm**

**Thickness trade-offs:**

| Thickness | CD Control | Etch Durability | Etch Time | Cost |
|---|---|---|---|---|
| **50 nm** | Excellent | Poor | Fast (~30 sec) | Low |
| **100 nm** | Good | Moderate | Moderate (~1 min) | Medium |
| **150 nm** | Moderate | Good | Slow (~1.5 min) | Medium |
| **200 nm** | Marginal | Excellent | Very slow (~2 min) | High |

**Industry standard for 3D NAND**: 70-120 nm (balance of CD and durability)

#### Glass Transition Temperature (Tg)

**Thermal stability during hard mask open plasma etch:**

**Resist temperature rise during 150 W plasma etch:**

$$\Delta T = \frac{Q}{C} = \frac{50 \text{ W}}{0.15 \text{ kg} × 1800 \text{ J/kg·K}} ≈ 0.2°C/\text{sec}$$

**Over 2-minute etch:** ΔT ~24°C (not extreme, but cumulative)

**But locally at ion impact: T can spike >300°C (picosecond duration)**

| Resist Type | Tg | Thermal Stability | Degradation Risk |
|---|---|---|---|
| **Standard CAR** | 90-110°C | Moderate | Significant above 150°C |
| **High-Tg CAR** | 120-150°C | Good | Marginal above 180°C |
| **Super-high-Tg** | 160-200°C | Excellent | Minimal below 250°C |

**For hard mask open etch (local heating risk)**: High-Tg CAR recommended

#### Dissolution Contrast

**Selectivity between exposed and unexposed regions:**

$$\text{Contrast} = \frac{R_{exposed}}{R_{unexposed}}$$

**Typical CAR contrast:** 100-300:1 (excellent)

**Required for sharp CD definition; poor contrast causes CD rounding**

---

## Part 2: Lithographic Resolution and CD Accuracy

### 2.1 Diffraction-Limited Resolution

#### Rayleigh Criterion

**Minimum resolvable feature size:**

$$L_{min} = k_1 \frac{\lambda}{NA}$$

Where:
- k₁ = process factor (0.3-0.5; lower = better process)
- λ = wavelength
- NA = numerical aperture

**Comparison of lithographic wavelengths:**

| Lithography | λ | NA | L_min (k₁=0.4) | Status |
|---|---|---|---|---|
| **ArF 193nm immersion** | 193 nm | 1.35 | 57 nm | Mature |
| **ArF 193nm immersion** | 193 nm | 1.55 | 50 nm | Advanced |
| **EUV 13.5nm** | 13.5 nm | 0.33 | 16 nm | Current (3D NAND) |
| **EUV 13.5nm** | 13.5 nm | 0.55 | 10 nm | Future |

**For 25 nm 3D NAND channels**: EUV (13.5 nm) is required; 193 nm ArF cannot reliably achieve this

#### Multiple Patterning Techniques

**When single lithography insufficient:**

**Self-aligned double patterning (SADP):**

```
Pitch = 50 nm (ArF limit)
       ↓
Spacer material deposited (20 nm spacers)
       ↓
Pitch = 20 nm (doubled resolution!)
       ↓ (transfer to hard mask)
```

**Cost: Additional deposition + etch steps, but enables 20 nm features with 193 nm lithography**

---

### 2.2 Critical Dimension Accuracy and Uniformity

#### CD Measurement and Specification

**Resist CD measured via SEM after development:**

**Specification for 25 nm channel:**

$$\text{CD} = 25.0 \text{ nm} ± 2.0 \text{ nm} \quad \text{(±8% tolerance)}$$

**Breakdown of tolerance budget:**

| Error Source | Contribution | Notes |
|---|---|---|
| **Lithographic dose variation** | ±0.8 nm | Across 300 mm wafer |
| **Resist composition uniformity** | ±0.5 nm | Chemical batch variation |
| **Temperature drift (PEB)** | ±0.3 nm | Thermal stability |
| **Development time variation** | ±0.4 nm | Timing control |
| **Measurement SEM error** | ±0.2 nm | Optical calibration |
| **Total 3-sigma** | ±1.8 nm | Cumulative |

#### Within-Wafer and Wafer-to-Wafer Variation

**Typical CD distribution (100-wafer lot):**

| Position | Measured CD | Std Dev | Notes |
|---|---|---|---|
| **Center** | 25.0 nm | 0.3 nm | Reference |
| **Mid-radius (r=75mm)** | 25.3 nm | 0.4 nm | +1.2% |
| **Edge (r=150mm)** | 25.8 nm | 0.5 nm | +3.2% |
| **Wafer-to-wafer** | 25.2 ± 0.6 nm | 0.6 nm | ±2.4% |

**Root causes of non-uniformity:**
- Dose non-uniformity (illumination variation across wafer)
- Temperature gradients during PEB
- Development rate variation (concentration/temperature)
- Resist thickness non-uniformity

**Mitigation strategies:**
- Precise dose control (±2% target)
- Temperature stabilization (±1°C during PEB)
- Developer concentration monitoring
- Resist thickness uniformity (<±5%)

---

## Part 3: Line Width Roughness (LWR) and Its Impact

### 3.1 LWR Sources and Measurement

#### Roughness Origins

**Multiple contributions to sidewall roughness:**

1. **Photon shot noise** (~0.5-1 nm contribution)
   - Statistical fluctuation in photon arrival
   - Fundamental limit; cannot be eliminated

2. **Acid diffusion during PEB** (~0.8-1.2 nm)
   - Acid molecule random walk (~40 nm mean free path)
   - Broadens exposure profile edge
   - Larger diffusion = rougher edges

3. **Development kinetics** (~0.6-1.0 nm)
   - Stochastic material removal
   - Resist dissolution follows Poisson statistics

4. **Photomask roughness** (~0.5-0.8 nm)
   - Pattern on photomask transferred to resist
   - Advanced masks have <0.5 nm edge roughness

**Total LWR (3-sigma): typically 2-2.5 nm for modern lithography**

#### LWR Measurement

**Standard metrology: SEM line-edge analysis**

**Procedure:**
1. SEM image resist sidewall at high magnification
2. Extract edge pixels vs. ideal vertical line
3. Calculate root-mean-square (RMS) deviation
4. Report as 3-sigma (99.7% confidence level)

**Example measurement:**

```
Ideal edge: x = 0
Actual edge at height z:
  z=0µm:    x = +0.8 nm
  z=5µm:    x = -1.2 nm
  z=10µm:   x = +0.5 nm
  z=15µm:   x = -0.9 nm
  ...
RMS deviation: 0.95 nm
3-sigma LWR = 3 × 0.95 = 2.85 nm
```

### 3.2 LWR Propagation Through Etch

#### Amplification During Hard Mask Open

**LWR growth through HMO etch:**

**Initial lithographic LWR: 2.0 nm (3-sigma)**

**During hard mask open etch:**

- Plasma creates **slight additional roughness** from ion bombardment
- Ions preferentially strike edges (edge-field enhancement)
- Sidewall erosion rate varies locally (~±10%)

**After HMO (~1-2 µm etch):**

$$\text{LWR}_{HMO} ≈ 2.2 \text{ nm} \quad \text{(~10% increase)}$$

#### Severe Amplification During VCH Etch

**LWR growth through 50 µm VCH etch:**

**Mechanism:**
- Initial roughness wavelength: ~100-500 nm
- Etch rate varies at each peak/valley
- Small local variations amplified over 50 µm

**Roughness growth model:**

$$\text{LWR}_{final} = \sqrt{\text{LWR}_{initial}^2 + \text{ARDE\_induced}^2}$$

**ARDE-induced roughness (VCH):**
- Radical diffusion varies at feature edges
- Creates ~1-2 nm additional roughness per µm of etch
- Over 50 µm: 50-100 nm amplitude!

**Final VCH LWR:**

| Initial LWR | After HMO | After VCH (50 µm) | Amplification |
|---|---|---|---|
| **2.0 nm** | 2.2 nm | 9-12 nm | 4.5-6× |
| **2.5 nm** | 2.8 nm | 11-15 nm | 4.4-6× |
| **3.0 nm** | 3.3 nm | 13-18 nm | 4.3-6× |

**Critical insight**: **Lithographic LWR is amplified 5-6× through 50 µm etch!**

---

## Part 4: Resist-Etch Interactions During Hard Mask Open

### 4.1 Resist Erosion During HMO Etch

#### Comparative Etch Rates

**During hard mask open etch (CF₄ plasma, 150 W, 20 mTorr):**

**Etch rates by material:**

| Material | Etch Rate | Selectivity vs. Resist |
|---|---|---|
| **Photoresist (CAR)** | 100-150 nm/min | Baseline (1×) |
| **SiO₂ hard mask** | 10-15 nm/min | 8-12× slower |
| **Si₃N₄ hard mask** | 15-25 nm/min | 5-7× slower |
| **Silicon substrate** | 40-80 nm/min | 1.3-2× slower |

**Paradox**: Resist erodes **faster** than hard mask! This is backward for protection.

**Why?**
- Resist is organic polymer (weak C-C, C-H bonds)
- SiO₂ has strong Si-O bonds (4.8 eV)
- CF₄ radicals and ions easily break organic bonds

#### Selectivity Challenge

**To protect resist during HMO etch:**

**Required selectivity (hard mask / resist):**

$$S = \frac{R_{HM}}{R_{resist}} > 0.1 \quad \text{(hard mask erodes slower than resist)}$$

**Typical selectivity in CF₄**: 0.08-0.12 (not ideal)

**Problem**: Over 1-2 µm HMO etch (100-150 seconds):

```
Resist erosion: 100 nm/min × 1.5 min = 150 nm
If resist thickness = 100 nm: COMPLETELY ERODED!

Hard mask: 12 nm/min × 1.5 min = 18 nm
Adequate selectivity needed!
```

### 4.2 Resist Protection Strategies

#### Strategy 1: Reduce RF Power

**Lower power → fewer ions → less resist erosion**

| RF Power | Resist Rate | HM Rate | Selectivity | Duration |
|---|---|---|---|---|
| **100 W** | 60 nm/min | 8 nm/min | 0.13 | 12-15 min |
| **150 W** | 100 nm/min | 12 nm/min | 0.12 | 8-10 min |
| **200 W** | 140 nm/min | 18 nm/min | 0.13 | 6-8 min |

**Trade-off**: Lower power → slower etch → longer fab time

#### Strategy 2: High-Tg Resist

**Thermally stable resist resists ion bombardment better:**

| Resist Type | Tg | Peak Erosion Rate | Notes |
|---|---|---|---|
| **Standard CAR** | 100°C | 100 nm/min | Begins degrading >150°C |
| **High-Tg CAR** | 140°C | 80 nm/min | More stable; slight reduction |
| **Super-high-Tg** | 180°C | 60 nm/min | Excellent; 40% lower erosion |

**Cost**: High-Tg resist ~2-3× more expensive

#### Strategy 3: Thin Resist

**Thinner resist etches through faster; less cumulative damage:**

| Resist Thickness | Etch Time | Total Resist Loss |
|---|---|---|
| **50 nm** | 30 sec | ~50 nm (complete erosion!) |
| **100 nm** | 60 sec | ~100 nm (complete erosion!) |
| **150 nm** | 90 sec | ~150 nm (complete erosion!) |

**Conclusion**: **NO resist survives HMO etch!** Resist is always completely removed.

**Mitigation**: Use post-etch O₂ plasma to strip remaining resist carbon after HMO etch.

---

## Summary: Lithography-HMO Integration

| Factor | Criticality | Impact |
|---|---|---|
| **CD accuracy** | Critical | ±2 nm spec determines channel size |
| **LWR minimization** | Critical | 2 nm LWR → 9-12 nm after VCH |
| **Resist thickness** | High | Thinner = faster HMO; thicker = more durable |
| **Resist Tg** | Medium | Higher Tg provides better thermal stability |
| **Lithography wavelength** | Critical | EUV required for 25 nm features |
| **Dose uniformity** | High | Affects CD uniformity across 300 mm |

**Key Insight**: **Perfect lithography + optimized hard mask etch required for 3D NAND success. Neither alone is sufficient.**

---

[Continue to Chapter 4: Etch Chemistry for Hard Mask Materials →](./04-etch-chemistry.md)
