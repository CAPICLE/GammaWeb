---
title: Low-energy photon backgrounds
---

## The Cosmic Microwave Background (CMB)

The Cosmic Microwave Background (CMB) is the relic thermal blackbody radiation emitted during the Recombination epoch of the early universe ($z \approx 1100$). It fills the universe homogeneously and isotropically at a temperature of $T \approx 2.725\text{ K}$, forming the dominant background photon field at microwave and millimetric wavelengths. Very High Energy (VHE) cosmic rays and gamma rays interact with CMB photons through electron-positron pair production ($\gamma\gamma \to e^+ e^-$), making the CMB the primary attenuating field for gamma rays at ultra-high energies ($E \gtrsim 10^{14}\text{ eV}$).

## The Extragalactic Background Light (EBL)

The Extragalactic Background Light (EBL) is the diffuse background radiation field encompassing all light emitted by extragalactic sources (stars, active galactic nuclei, and dust re-emission) throughout cosmic history. It spans the ultraviolet (UV), optical, and infrared (IR) spectrum ($0.1\text{ }\mu\text{m} - 1000\text{ }\mu\text{m}$).

VHE gamma rays ($E \gtrsim 10\text{ GeV}$) emitted by distant sources (such as blazars) collide with low-energy EBL photons to produce electron-positron pairs ($\gamma_{\text{VHE}} + \gamma_{\text{EBL}} \to e^+ + e^-$), causing flux attenuation[cite: 2, 3].

The mean free path $\lambda(E,z)$ in the local comoving frame for a gamma ray of physical energy $E$ at redshift $z$ is given by[cite: 2]:

$$\frac{1}{\lambda(E,z)}=\int_{-1}^{1}d\cos\theta \, \frac{1-\cos\theta}{2}\int_{\omega_{\text{th}}}^{\infty}\frac{d\omega}{\omega} \, n(\omega,z) \, \sigma(s)$$

By making the change of variables to $\bar{s} = s / (4m_e^2)$, the expression becomes[cite: 2]:

$$\frac{1}{\lambda(E,z)}=\frac{m_e^2}{4E^2}\int_{1}^{\infty}d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s})\int_{\omega_{\text{th}}}^{\infty}d\omega \, \frac{n(\omega,z)}{\omega^2}$$

where:
* $\omega_{\text{th}} = \frac{\bar{s}m_e^2}{E}$ is the threshold physical energy for background photons[cite: 2].
* $\mathcal{F}_{\text{BW}}(\bar{s}) = 8\bar{s}m_e^2 \, \sigma(4m_e^2\bar{s})$ incorporates the Breit–Wheeler cross-section $\sigma_{\text{BW}}$[cite: 2].
* $n(\omega,z)$ is the proper photon number density per physical photon energy[cite: 2].

Integrating along the path length gives the total optical depth $\tau(E_0, z_s)$ for an observed laboratory energy $E_0 = \frac{E}{1+z}$ from a source at redshift $z_s$[cite: 3]:

$$\tau(E_0, z_s) = \frac{m_e^2}{4E_0^2}\int_{0}^{z_s}dz \, \frac{1}{(1+z)^3 H(z)}\int_{1}^{\infty}d\bar{s} \, \mathcal{F}_{\text{BW}}(\bar{s})\int_{\omega_{\text{th}}}^{\infty}d\omega \, \frac{n(\omega,z)}{\omega^2}$$

with threshold energy $\omega_{\text{th}} = \frac{\bar{s}m_e^2}{E_0 (1+z)}$[cite: 3].

### The standardization problem

Different authors and published EBL tables express photon number densities using different reference frames (physical vs. comoving) and energy variables (physical local energy $\omega(z)$ vs. laboratory/observed energy $\omega_0$)[cite: 4, 5]. Misinterpreting these definitions leads to significant discrepancies when computing the opacity $\tau(E_0,z)$[cite: 4, 11].

The four primary density definitions used across various EBL models are[cite: 4]:

1. **Physical density in terms of physical energy:**
   $n(\omega(z), z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$[cite: 4]

2. **Comoving density in terms of physical energy:**
   $n_0(\omega(z), z) = \frac{dN(z)}{dV_0 \, d\omega(z)} = \frac{n(\omega(z), z)}{(1+z)^3}$[cite: 4]

3. **Comoving density in terms of laboratory energy:**
   $n_0(\omega_0, z) = \frac{dN(z)}{dV_0 \, d\omega_0} = \frac{n(\omega(z), z)}{(1+z)^2}$[cite: 4]

4. **Physical density in terms of laboratory energy:**
   $n(\omega_0, z) = \frac{dN(z)}{dV(z) \, d\omega_0} = \frac{n(\omega(z), z)}{1+z}$[cite: 4]

### Dominguez et al. 2011

An empirical model derived from galaxy luminosity functions and multi-wavelength survey data. Assuming that the published table provides comoving density per physical energy, $n_0(\omega(z),z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$, yields calculated opacities $\tau(E_0, z=0.1)$ with discrepancies of less than $2\%$ compared to reference curves[cite: 6].

### Franceschini et al. 2018

An updated EBL model based on galaxy optical and infrared observations. The paper explicitly specifies its density tables as physical (proper) density per physical energy, $n(\omega(z),z) = \frac{dN(z)}{dV(z) \, d\omega(z)}$, producing opacities that match published reference values within $3\%$[cite: 7].

### Saldana et al. 2021

An EBL model based on galaxy light density determinations from deep survey fields. Assuming the tabulated data represents comoving density per physical energy, $n_0(\omega(z),z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$, yields near-exact agreement with published references, with discrepancies under $0.5\%$[cite: 8].

## Finke et al. 2022

A theoretical EBL model constructed from stellar evolution models and dust re-emission. Evaluating this model's tables under various density definitions results in discrepancies across all assumptions[cite: 9]. The closest match occurs when assuming comoving density per physical energy, $n_0(\omega(z),z) = \frac{dN(z)}{dV_0 \, d\omega(z)}$, though discrepancies still reach up to $10\%$ at low redshift ($z=0.1$)[cite: 9] and produce substantial errors at higher redshifts ($z=1.0$)[cite: 11].