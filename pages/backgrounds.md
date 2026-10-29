---
title: Low-energy photon backgrounds
---

## Gamma-Ray Absorption

Very High Energy (VHE) and Ultra-High Energy (UHE) gamma rays traveling across cosmological distances interact with low-energy diffuse background photons via electron-positron pair production ($\gamma\gamma \to e^+e^-$). This absorption process attenuates the observed flux from distant extragalactic sources such as blazars and gamma-ray bursts.

The mean free path $\lambda(E, z)$ of a gamma ray with physical energy $E$ at redshift $z$ propagating through a background photon field with number density $n(\omega, z)$ is expressed as:

$$\frac{1}{\lambda(E,z)} = \int_{-1}^{1} d\cos\theta \, \frac{1-\cos\theta}{2} \int_{\omega_{\text{th}}}^{\infty} \frac{d\omega}{\omega} \, n(\omega,z) \, \sigma(s)$$

Transforming variables to $\bar{s} = \frac{s}{4m_e^2}$, the inverse mean free path simplifies to:

$$\frac{1}{\lambda(E,z)} = \frac{m_e^2}{4E^2} \int_{1}^{\infty} d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s}) \int_{\omega_{\text{th}}}^{\infty} d\omega \, \frac{n(\omega,z)}{\omega^2}$$

where:
* $\omega\_{\text{th}} = \frac{\bar{s}m_e^2}{E}$ is the threshold physical energy required for target background photons to undergo pair production.
* $\mathcal{F}\_{\text{BW}}(\bar{s}) = 8\bar{s}m_e^2 \, \sigma\_{\text{BW}}(4m_e^2\bar{s})$ incorporates the Breit–Wheeler pair-production cross-section $\sigma\_{\text{BW}}$.
* $n(\omega,z)$ is the proper photon number density per physical photon energy.

Integrating the interaction rate along the line of sight yields the total optical depth $\tau(E\_0, z\_s)$ for a gamma ray observed in the laboratory frame with energy $E\_0$ originating from a source at redshift $z\_s$:

$$\tau(E_0, z_s) = \int_{0}^{z_s} dz \, \frac{1}{(1+z)H(z)} \, \frac{1}{\lambda(E(z),z)}$$

Relating physical energy $E(z)$ to observed energy $E\_0$ via $E(z) = E\_0(1+z)$, the optical depth becomes:

$$\tau(E_0, z_s) = \frac{m_e^2}{4E_0^2} \int_{0}^{z_s} dz \, \frac{1}{(1+z)^3 H(z)} \int_{1}^{\infty} d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s}) \int_{\omega_{\text{th}}}^{\infty} d\omega \, \frac{n(\omega,z)}{\omega^2}$$

where the redshift-dependent threshold energy is $\omega\_{\text{th}} = \frac{\bar{s}m_e^2}{E\_0 (1+z)}$.

In these formulas, $n(\omega, z)$ denotes the target photon density of any background field encountered along the line of sight, such as the Cosmic Microwave Background (CMB) or the Extragalactic Background Light (EBL).

## The Cosmic Microwave Background (CMB)

The Cosmic Microwave Background (CMB) is the remnant thermal blackbody radiation from the Recombination epoch ($z \approx 1100$). It fills the universe homogeneously and isotropically at a temperature of $T \approx 2.725\text{ K}$, peaking in the microwave region ($h\nu \sim 10^{-3}\text{ eV}$). Because of the high density of microwave photons, the CMB acts as the dominant target photon field $n(\omega, z)$ for ultra-high-energy gamma rays ($E \gtrsim 10^{14}\text{ eV}$).

## The Extragalactic Background Light (EBL)

The Extragalactic Background Light (EBL) is the cumulative diffuse background radiation produced by all extragalactic processes (direct starlight and dust re-emission) across cosmic history. Covering the ultraviolet, optical, and infrared bands ($0.1\text{ }\mu\text{m} - 1000\text{ }\mu\text{m}$), the EBL serves as the main target photon field $n(\omega, z)$ for attenuation of Very High Energy gamma rays ($10\text{ GeV} \lesssim E \lesssim 100\text{ TeV}$).

### The standardization problem

Calculating gamma-ray optical depths requires evaluating $n(\omega, z)$ from tabulated EBL models. However, different published tables use differing definitions regarding reference frames (physical volume $V(z)$ vs. comoving volume $V\_0$) and photon energy variables (physical local energy $\omega(z)$ vs. laboratory/observed energy $\omega\_0$). Misinterpreting the tabulated density quantity can lead to significant discrepancies in the calculated gamma-ray optical depth $\tau(E\_0, z)$.

The four primary conventions encountered in literature are:

1. **Physical density in terms of physical energy:**
   $$n(\omega(z), z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$$

2. **Comoving density in terms of physical energy:**
   $$n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)} = \frac{n(\omega(z), z)}{(1+z)^3}$$

3. **Comoving density in terms of laboratory energy:**
   $$n_0(\omega_0, z) = \frac{dN(z)}{dV_0 \, d\omega_0} = \frac{n(\omega(z), z)}{(1+z)^2}$$

4. **Physical density in terms of laboratory energy:**
   $$n(\omega_0, z) = \frac{dN(z)}{dV(z) \, d\omega_0} = \frac{n(\omega_0, z)}{1+z}$$

### Dominguez et al. 2011

An empirical EBL model based on multi-wavelength galaxy survey data and luminosity functions. Re-calculating optical depths under the assumption that the table provides comoving density per physical energy, $n\_0(\omega(z), z) = \frac{dN(z)}{dV\_0 \, d\omega(z)}$, reproduces the authors' published reference curves with discrepancies under $2\%$.

### Franceschini et al. 2018

An updated evolutionary model based on optical and infrared galaxy counts. The authors explicitly define their tables using physical (proper) photon density per physical energy, $n(\omega(z), z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$, yielding computed opacities that match published reference values within $3\%$.

### Saldana et al. 2021

An EBL model derived using deep survey galaxy light density measurements up to high redshifts. Assuming the tabulated values represent comoving density per physical energy, $n\_0(\omega(z), z) = \frac{dN(z)}{dV\_0 \, d\omega(z)}$, produces agreement with published reference curves to within $0.5\%$.

## Finke et al. 2022

A theoretical cosmological model based on stellar evolution models and dust re-radiation. Testing this model's tables across different density interpretations reveals persistent discrepancies under all assumptions. Assuming comoving density per physical energy, $n\_0(\omega(z), z) = \frac{dN(z)}{dV\_0 \, d\omega(z)}$, gives the smallest discrepancy at $z = 0.1$ ($\sim 10\%$), but using an incorrect assumption at higher redshifts ($z = 1.0$) leads to order-of-magnitude errors in calculated optical depth.