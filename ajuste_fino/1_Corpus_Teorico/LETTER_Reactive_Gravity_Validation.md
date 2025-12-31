# Large-Scale Structure Formation in a Reactive Entropic Gravity Framework
## A Code-First Validation against SDSS Data

Author and Principal Investigator
DOUGLAS H. M. FULBER Senior Software Engineer | Computational Physics Researcher CTO @asimovtechsystems | Architecting Mathematical Digital Twins Independent Researcher | Code-First Physics & Entropic Gravity

Latest Work: The Reactive Universe: A Computational Solution to the Dark Sector DOI: 10.5281/zenodo.18090702 | Review: Classical and Quantum Gravity Profiles: GitHub | LinkedIn | ORCID
---

### Abstract

We present a computational verification of Entropic Gravity as a viable candidate for large-scale structure formation without Cold Dark Matter (CDM). By interpolating the Newtonian potential with a reactive acceleration scale ($a_0 \approx 1.2 \times 10^{-10} m/s^2$), we simulated the dynamics of 50,000 galaxies from the Sloan Digital Sky Survey (SDSS DR17). Our "Code-First" analysis demonstrates that: (1) The model reproduces flat rotation curves for spiral galaxies (e.g., NGC 0024) using only baryonic mass; and (2) The two-point correlation function $\xi(r)$ of the simulated "Reactive Universe" follows the same power-law clustering ($\gamma \approx 1.8$) as the standard $\Lambda$CDM model. We address the amplitude discrepancy often cited in alternative gravity models by implementing a geometry-aware radial selection function $n(z)$, proving that observed large-scale filaments can emerge from thermodynamic principles.

### 1. Introduction

The standard $\Lambda$CDM cosmological model relies on the existence of non-baryonic Dark Matter to explain both galactic rotation curves and the filamentary structure of the Cosmic Web. However, direct detection of WIMPs remains elusive. An alternative proposition, Entropic Gravity (Verlinde, 2011), suggests that gravity is an emergent phenomenon driven by the entropy of spacetime information. In this Letter, we forego traditional N-body simulations in favor of a "Reactive Mapping" approach, applying entropic corrections directly to observational data to test morphological and statistical consistency.

### 2. Computational Methodology

We developed the `ReactiveCosmoMapper`, a Python-based engine that processes raw astronomical data under the assumption of Reactive Gravity.

#### 2.1 The Reactive Kernel
The core physics engine replaces the gravitational potential with an effective acceleration $g_{obs}$ derived from the interaction between baryonic matter and the Hubble scale:
$$ g_{obs} = \frac{g_N + \sqrt{g_N^2 + 4 g_N a_0}}{2} $$
*(Note: This interpolation kernel effectively captures the transition from area-law to volume-law entropy scaling (Verlinde, 2016).)*

This kernel was applied to:
*   **Galactic Scale:** Converting Spitzer (SPARC) photometry into dynamic mass profiles.
*   **Cosmological Scale:** Transforming SDSS Redshift space ($z$) into Cartesian coordinates ($x, y, z$) to reconstruct the 3D density field.

#### 2.2 Statistical Estimator
To quantify clustering, we utilized the Landy-Szalay estimator:
$$ \xi(r) = \frac{DD - 2DR + RR}{RR} $$
A critical innovation in our pipeline was the implementation of a **Geometry-Aware Random Catalog**. Unlike naive box simulations, our control samples mimic the specific angular footprint and radial selection function $n(z)$ of the SDSS survey, preventing amplitude biases caused by the "cone effect."

### 3. Results

#### 3.1 Galactic Dynamics (NGC 0024)
Using the SPARC dataset, we modeled the rotation curve of NGC 0024. The reactive model predicted a velocity profile **closely reproducing the observed flat velocity profile within observational uncertainties** at $R > 10$ kpc, without the inclusion of a Dark Matter halo.

![Figure 1: Rotation Curve of NGC0024](Validation/NGC0024_rotation.png)
*Figure 1: Comparison of Newtonian (dashed blue), Reactive (solid orange), and Observed (red points) rotation velocities.*

#### 3.2 The Cosmic Turing Test
We analyzed the clustering of 50,000 galaxies ($0.01 < z < 0.2$).

![Figure 2: The Reactive Cosmic Web](Validation/reactive_universe_viz.png)
*Figure 2: 3D Visualization of the 50,000 galaxy sample ("The Reactive Cosmic Web") used for statistical analysis.*

*   **Power Law:** The Entropic Universe exhibited a correlation slope $\gamma \approx 1.8$ for $5 < r < 100$ Mpc, indistinguishable from the $\Lambda$CDM prediction.
*   **Amplitude Correction:** Initial runs showed a high-amplitude bias. By correcting the random catalog with the observed $n(z)$ distribution (Inverse Transform Sampling), we successfully normalized the correlation function, confirming that the clustering signal is physical, not an artifact of survey geometry.

![Figure 3: Two-Point Correlation Function](Validation/correlation_function_analysis.png)
*Figure 3: The Two-Point Correlation Function $\xi(r)$ showing the successful alignment (Orange) with the Standard Model prediction (Black Dashed) after applying Radial Selection Function $n(z)$ correction.*

### 4. Discussion

The alignment of the correlation function slope suggests that the "fractal" nature of the Cosmic Web is not unique to Cold Dark Matter. Instead, it may be a thermodynamic inevitability of any long-range attractive force scaling with information density. The ability of the Reactive model to satisfy both small-scale (rotation curves) and large-scale (clustering) constraints simultaneously—using a single parameter $a_0$—offers a compelling argument for gravity as an emergent entropic force.

### 5. Conclusion

We have computationally verified that a Reactive Entropic Gravity framework can reproduce the essential structural features of the observable universe. The `ReactiveCosmoMapper` establishes a new precedent for "Code-First Physics," proving that open-source software and open data can challenge the current cosmological paradigm.

---
**Data Availability:** The source code and generated datasets (obj/png) are archived in the `Validation/` repository.
