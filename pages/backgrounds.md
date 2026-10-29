---
title: Low-energy photon backgrounds
---

## The Cosmic Microwave Background (CMB)

The Cosmic Microwave Background (CMB) is the remnant thermal blackbody radiation left over from the epoch of recombination in the early Universe (at redshift $z \approx 1100$). It constitutes the most dominant and isotropic cosmic photon field in the Universe, characterized today by a temperature of $T_0 \approx 2.7255 \text{ K}$ and peaking in the microwave frequency range (wavelengths around $\lambda \sim 1 \text{ mm}$, corresponding to photon energies $\omega \sim 10^{-3} \text{ eV}$).

In high-energy astrophysics, the CMB plays a crucial role as a target photon field for pair production ($\gamma \gamma \to e^+ e^-$) with ultra-high-energy (UHE) gamma rays ($E \gtrsim 10^{15} \text{ eV}$ or PeV energies) and for photo-pion production ($p + \gamma_{\text{CMB}} \to \Delta^+ \to N + \pi$) responsible for the Greisen-Zatsepin-Kuzmin (GZK) cutoff in ultra-high-energy cosmic rays.

## The Extragalactic Background Light (EBL)

The Extragalactic Background Light (EBL) is the second most energetic diffuse isotropic background in the Universe, spanning from the ultraviolet (UV) through optical to the far-infrared (FIR) spectrum ($\sim 0.1 \ \mu\text{m}$ to $1000 \ \mu\text{m}$). Unlike the CMB, which originates from a single primordial event, the EBL is an integrated record of cosmic structure formation:
* **UV-Optical-Near IR Peak ($\sim 1 \ \mu\text{m}$):** Directly emitted starlight integrated over all stellar generations across cosmic time.
* **Far IR Peak ($\sim 100 \ \mu\text{m}$):** Starlight absorbed by interstellar dust grains and re-emitted at thermal infrared wavelengths.

The primary astrophysical importance of the EBL lies in its attenuation of Very High Energy (VHE, $E_0 \sim 10 \text{ GeV} - 100 \text{ TeV}$) gamma rays emitted by distant extragalactic sources (such as blazars and gamma-ray bursts). VHE gamma-ray photons collide with ambient EBL photons through electron-positron pair production ($\gamma_{\text{VHE}} + \gamma_{\text{EBL}} \to e^+ e^-$).

The mean free path $\lambda(E, z)$ for a gamma ray of physical energy $E$ at redshift $z$ interacting with background photons of physical energy $\omega$ is expressed as:

$$\frac{1}{\lambda(E,z)} = \frac{m_e^2}{4E^2} \int_1^\infty d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s}) \int_{\omega_{\text{th}}}^\infty d\omega \, \frac{n(\omega, z)}{\omega^2}$$

where:
* $m_e$ is the electron mass,
* $\bar{s} = \frac{s}{4m_e^2}$ is the normalized center-of-mass energy squared,
* $\omega_{\text{th}} = \frac{\bar{s} m_e^2}{E}$ is the threshold physical energy for background photons,
* $\mathcal{F}_{\text{BW}}(\bar{s}) = 8 \bar{s} m_e^2 \times \sigma_{\text{BW}}(4 m_e^2 \bar{s})$ incorporates the Breit-Wheeler cross-section $\sigma_{\text{BW}}$,
* $n(\omega, z)$ is the proper photon number density per physical photon energy.

By integrating along the line of sight from a source at redshift $z_s$ to an observer at $z = 0$, the total optical depth $\tau(E_0, z_s)$ for an observed gamma-ray energy $E_0$ (where physical energy $E(z) = E_0(1+z)$) is given by:

$$\tau(E_0, z_s) = \frac{m_e^2}{4 E_0^2} \int_0^{z_s} \frac{dz}{(1+z)^3 H(z)} \int_1^\infty d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s}) \int_{\omega_{\text{th}}}^\infty d\omega \, \frac{n(\omega, z)}{\omega^2}$$

with threshold condition $\omega_{\text{th}} = \frac{\bar{s} m_e^2}{E_0 (1+z)}$ and Hubble parameter $H(z)$.

### The standardization problem

To compute $\tau(E_0, z_s)$, researchers rely on published numerical data tables produced by various EBL modeling teams. However, a major issue arises due to non-standardized conventions regarding how background photon number densities and energy variables are tabulated in literature.

Specifically, the tabulated photon density $n$ can represent different physical or comoving quantities defined relative to either physical (redshifted) photon energy $\omega(z)$ or laboratory (observed $z=0$) photon energy $\omega_0$:

1. **Physical density in terms of physical energy:**
   $$n(\omega(z), z) = \frac{dN(z)}{dV(z) d\omega(z)}$$

2. **Comoving density in terms of physical energy:**
   $$n_0(\omega(z), z) = \frac{dN(z)}{dV_0 d\omega(z)} = \frac{n(\omega(z), z)}{(1+z)^3}$$

3. **Comoving density in terms of laboratory energy:**
   $$n_0(\omega_0, z) = \frac{dN(z)}{dV_0 d\omega_0} = \frac{n(\omega(z), z)}{(1+z)^2}$$

4. **Physical density in terms of laboratory energy:**
   $$n(\omega_0, z) = \frac{dN(z)}{dV(z) d\omega_0} = \frac{n(\omega(z), z)}{1+z}$$

Because papers frequently omit precise mathematical definitions of their table columns or use ambiguous variable labels (such as listing "photon density $n$" without specifying physical vs. comoving volume $V$ or frame energy $\omega$), analysts risk applying incorrect cosmological scaling factors $(1+z)^k$. An incorrect assumption leads to non-negligible discrepancies in the calculated optical depth $\tau$, ranging from a few percent at low redshifts ($z \sim 0.1$) to orders of magnitude at high redshifts ($z \gtrsim 1.0$).

### Dominguez et al. 2011

* **Model Type:** Empirical / Inferred evolution model based on multi-wavelength galaxy Spectral Energy Distributions (SEDs) from deep surveys (e.g., AEGIS).
* **Table Convention & Discrepancy:**
  * The published numerical tables list EBL intensities across redshift.
  * Re-computing opacity $\tau(E_0, z = 0.1)$ yields **discrepancies of less than 2%** relative to the reference values when assuming the tabulated density corresponds to comoving density in terms of physical energy:
    $$n_0(\omega(z), z) = \frac{dN(z)}{dV_0 d\omega(z)}$$

### Franceschini et al. 2018

* **Model Type:** Backward evolution model updated with galaxy luminosity functions from optical, near-IR, and sub-millimeter survey data.
* **Table Convention & Discrepancy:**
  * The authors explicitly state their tabulated quantities in terms of proper physical photon density per physical photon energy:
    $$n(\omega(z), z) = \frac{dN(z)}{dV(z) d\omega(z)}$$
  * Re-computed optical depths show excellent agreement with reference values, with **discrepancies remaining under 3%**.

### Saldana et al. 2021

* **Model Type:** Updated empirical model incorporating recent deep galaxy survey datasets spanning UV to FIR wavelengths.
* **Table Convention & Discrepancy:**
  * Assuming the tabulated data represents comoving photon density in terms of physical energy:
    $$n_0(\omega(z), z) = \frac{dN(z)}{dV_0 d\omega(z)}$$
  * The calculated optical depth $\tau(E_0, z = 0.1)$ matches the published reference curve with high precision, showing **discrepancies of less than 0.5%**.

### Finke et al. 2022

* **Model Type:** Inferred evolution model based on stellar population synthesis, main-sequence and post-main-sequence star evolution, and dust reprocessing.
* **Table Convention & Discrepancy:**
  * Unlike earlier models, Finke et al. 2022 exhibits significant ambiguity in table interpretations. Discrepancies exist under *every* conventional assumption.
  * The lowest discrepancy at low redshift ($z = 0.1$) is obtained when assuming comoving density per physical energy $n_0(\omega(z), z)$, but discrepancies still **reach up to 10%**.
  * At higher redshifts (e.g., $z = 1.0$), misinterpreting the table conventions (e.g., confusing $n$, $n_0$, $\omega$, and $\omega_0$) produces severe discrepancies in calculated opacities $\tau(E_0, z)$, demonstrating the pressing need for a standard notation across the field.