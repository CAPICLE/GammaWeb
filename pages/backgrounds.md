---
title: Low-energy photon backgrounds
---

## Gamma-Ray Absorption

Very High Energy (VHE) and Ultra-High Energy (UHE) gamma rays traveling across cosmological distances interact with low-energy diffuse background photons via electron-positron pair production ($\gamma\gamma \to e^+e^-$). The total optical depth $\tau(E_0, z_s)$ for an observed gamma ray of energy $E_0$ originating from a source at redshift $z_s$ is given by:

$$\tau(E_0, z_s) = \int_{0}^{z_s} dz \, \frac{1}{(1+z)H(z)} \int_{-1}^{1} d\cos\theta \, \frac{1-\cos\theta}{2} \int_{\omega_{\text{th}}}^{\infty} d\omega \, n(\omega,z) \, \sigma(s)$$

where:
* $n(\omega,z) = \frac{dN(z)}{dV \, d\omega}$ is the proper background photon number density per physical volume $V$ and physical photon energy $\omega$.
* $\sigma(s)$ is the total Breit–Wheeler cross-section for pair production as a function of center-of-mass energy squared $s$.
* $\omega_{\text{th}}$ is the threshold physical energy required for target background photons to undergo pair production.

This formalism applies to any diffuse target field along the line of sight, such as the Cosmic Microwave Background (CMB) or the Extragalactic Background Light (EBL).

## The Cosmic Microwave Background (CMB)

The Cosmic Microwave Background (CMB) is the remnant thermal blackbody radiation from the Recombination epoch ($z \approx 1100$). It fills the universe homogeneously and isotropically at a temperature of $T \approx 2.725\text{ K}$, peaking in the microwave region ($h\nu \sim 10^{-3}\text{ eV}$). Because of its high photon density, the CMB acts as the dominant target field $n(\omega, z)$ for attenuating ultra-high-energy gamma rays ($E \gtrsim 10^{14}\text{ eV}$).

## The Extragalactic Background Light (EBL)

The Extragalactic Background Light (EBL) is the cumulative diffuse background radiation produced by direct starlight and dust re-emission across cosmic history ($0.1\text{ }\mu\text{m} - 1000\text{ }\mu\text{m}$). The EBL serves as the primary target photon field $n(\omega, z)$ for attenuation of Very High Energy gamma rays ($10\text{ GeV} \lesssim E \lesssim 100\text{ TeV}$).

### The standardization problem

Calculating gamma-ray optical depths requires evaluating $n(\omega, z)$ from tabulated EBL models. However, published EBL tables use differing conventions regarding reference frames (physical volume $V(z)$ vs. comoving volume $V_0$) and photon energy variables (physical local energy $\omega(z)$ vs. laboratory energy $\omega_0$). Misinterpreting these definitions leads to noticeable discrepancies in computed optical depths $\tau(E_0, z)$.

The four primary density conventions encountered in literature are:

1. **Physical density in terms of physical energy:**

   $$n(\omega(z), z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$$

2. **Comoving density in terms of physical energy:**

   $$n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)} = \frac{n(\omega(z), z)}{(1+z)^3}$$

3. **Comoving density in terms of laboratory energy:**

   $$n_0(\omega_0, z) = \frac{dN(z)}{dV_0 \, d\omega_0} = \frac{n(\omega(z), z)}{(1+z)^2}$$

4. **Physical density in terms of laboratory energy:**

   $$n(\omega_0, z) = \frac{dN(z)}{dV(z) \, d\omega_0} = \frac{n(\omega_0, z)}{1+z}$$

### Dominguez et al. 2011

An empirical EBL model based on multi-wavelength galaxy survey data and luminosity functions. Re-calculating optical depths under the assumption that the table provides comoving density per physical energy, $n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$, reproduces reference curves with discrepancies under $2\%$.

* EBL Data File: [`11dominguez.txt`](https://raw.githubusercontent.com/CAPICLE/GammaWeb/refs/heads/main/_data/ebl/11dominguez.txt)

### Franceschini et al. 2018

An updated evolutionary model based on optical and infrared galaxy counts. The authors explicitly define their tables using physical photon density per physical energy, $n(\omega(z), z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$, matching published reference values within $3\%$.

* EBL Data File: [`18franceschini.txt`](https://raw.githubusercontent.com/CAPICLE/GammaWeb/refs/heads/main/_data/ebl/18franceschini.txt)

### Saldana et al. 2021

An EBL model derived using deep survey galaxy light density measurements. Assuming comoving density per physical energy, $n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$, produces agreement with published reference curves within $0.5\%$.

* EBL Data File: [`21saldana.txt`](https://raw.githubusercontent.com/CAPICLE/GammaWeb/refs/heads/main/_data/ebl/21saldana.txt)

### Finke et al. 2022

A theoretical cosmological model based on stellar evolution models and dust re-radiation. Testing this model's tables across density interpretations reveals discrepancies under all assumptions, with the smallest discrepancy ($\sim 10\%$) occurring when assuming comoving density per physical energy, $n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$.

* EBL Data File: [`22finke.txt`](https://raw.githubusercontent.com/CAPICLE/GammaWeb/refs/heads/main/_data/ebl/22finke.txt)

### EBL models comparison

{% include ebl_plotter.html %}