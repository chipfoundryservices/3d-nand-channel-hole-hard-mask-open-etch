# Chapter 2: Hard Mask Materials (SiO₂, Si₃N₄, Metal)

## Executive Summary

Hard mask material selection determines etch rate, selectivity, cost, and thermal properties. This chapter compares SiO₂ (industry standard), Si₃N₄ (alternative), and metal masks (emerging). SiO₂ dominates due to high selectivity (16:1 Si/SiO₂), good etch rate control, and cost. Si₃N₄ offers lower selectivity (2-3:1) but better etch uniformity. Metal masks (tungsten, tantalum) provide highest selectivity but cost and complexity concerns. The chapter develops material selection criteria and etch characteristics for 3D NAND hard mask open applications.

---

## Part 1: SiO₂ Hard Masks

### 1.1 Properties and Etch Rates

**SiO₂ characteristics:**
- Deposition: PECVD or thermal oxidation
- Thickness: 50-200 nm (thicker masks more erosion-resistant)
- Etch rate in CF₄ plasma: 5-15 nm/min
- Selectivity to silicon: 16:1 (excellent)
- Cost: Low (mature process)

### 1.2 Etch Rate Uniformity

**Pressure/power dependence:**

| Pressure | RF Power | Etch Rate | Uniformity |
|---|---|---|---|
| **10 mTorr** | 150 W | 8 nm/min | ±5% |
| **20 mTorr** | 200 W | 12 nm/min | ±3% |
| **30 mTorr** | 250 W | 15 nm/min | ±4% |

**Industry standard:** 20 mTorr, 150-200 W for best uniformity

---

## Part 2: Si₃N₄ Hard Masks

### 2.1 Properties

**Si₃N₄ characteristics:**
- Deposition: PECVD, LPCVD, or ALD
- Etch rate: 10-20 nm/min (faster than SiO₂)
- Selectivity Si/Si₃N₄: 2-3:1 (moderate)
- Uniformity: Excellent (better than SiO₂)

### 2.2 Selectivity Trade-off

**Si₃N₄ etches faster; requires thicker mask (~300 nm) for same etch time**

**Cost impact:** Thicker nitride → more material → higher cost

---

## Part 3: Metal Masks (Emerging)

### 3.1 Tungsten and Tantalum

**Metal mask characteristics:**
- Etch rate: 1-3 nm/min (very slow; excellent selectivity)
- Thickness: 30-50 nm sufficient (thin masks acceptable)
- Cost: High ($500-1000 per wafer)
- Complexity: Additional deposition/removal steps

### 3.2 Applications

**Metal masks used for:**
- Sub-10 nm features (extreme resolution)
- High-uniformity requirements
- Advanced nodes (N3, N2)

---

## Summary

| Material | Selectivity | Cost | Uniformity | Status |
|---|---|---|---|---|
| **SiO₂** | 16:1 | Low | Good | Standard (mature) |
| **Si₃N₄** | 2-3:1 | Medium | Excellent | Alternative |
| **Metal** | >20:1 | High | Excellent | Emerging (advanced) |

**Industry choice for 3D NAND:** SiO₂ (cost/performance balance)

---

[Continue to Chapter 3: Photoresist and Patterning →](./03-photoresist-patterning.md)
