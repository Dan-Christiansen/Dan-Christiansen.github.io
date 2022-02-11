---
title: 'Calculating Conductivity from Molecular Dynamics Simulation'
date: 2022-02-11
permalink: /posts/2022/02/Calculating-Conductivity/
tags:
  - research
  - ionic conductivity
  - Green-Kubo
  - Nernst-Einstein
  - tutorials
---

Methods to calculate the conductivity of a species from molecular dynamics simulation

## Green-Kubo relations
The velocity autocorrelation function, $$C_V(t)$$, is

<p style="text-align: center;">$$C_V(t)=\frac{1}{N}\sum_{i=1}^{N}(\vec{v_i}(0)\cdot\vec{v_i}(t))=<\vec{v_i}(0)\cdot\vec{v_i}(t)>$$</p>

where $$N$$ is the total number of particles (atoms/molecules in the selection) and $$\vec{v_i}$$ is a vector storing the three components of the velocity ($$v_x$$, $$v_y$$, and $$v_z$$) for the $$i$$-th particle.

$$\vec{v_i}(0)=\vec{v_i}(t=t_0)$$ and $$\vec{v_i}(t)=\vec{v_i}(t=t_0+n \Delta t)$$, where $$n$$ is the timestep and $$\Delta t$$ is the timestep size

Given this function decays to zero at long time, the diffusion constant $$D$$ may be found from the integral of $$C_V(T)$$ as

<p style="text-align: center;">$$D=\frac{1}{3}\int_{t=0}^{t=\infty}<\vec{v_i}(0)\cdot\vec{v_i}(t)>dt$$</p>

Electrical conductivity, $$\sigma$$, is calculated using the normalized autocorrelation function of the total current $$J(t)$$ as

<p style="text-align: center;">$$J(t)=<(\sum_{i}\vec{v}_{i+}(t)-\sum_{j}\vec{v}_{j-}(t))>\times<(\sum_{i}\vec{v}_{i+}(0)-\sum_{j}\vec{v}_{j-}(0))>$$</p>

where $$\vec{v}_{i+}$$ and $$\vec{v}_{j-}$$ are the velocity vectors for the cations and anions in the system, respectively

Conductivity is then calculated as

<p style="text-align: center;">$$\sigma=\frac{e^2}{3Vk_BT}\int_{0}^{\infty}J(t)dt$$</p>

## Nernst-Einstein
Compute the mean-square displacement ($$MSD$$) of atoms or molecules from a set of initial positions

<p style="text-align: center;">$$MSD\equiv<(\vec{x}(t)-\vec{x_0})^2>=\frac{1}{N}\sum_{i=1}^{N} |\vec{x}^{(i)}(t)-\vec{x}^{(i)}(0)|^2$$</p>

where $$N$$ is the total number of particles (atoms/molecules) in the selection, vectors $$\vec{x}^{i}(t)$$ and $$\vec{x}^{(i)}(0)$$ are the position of the $$i$$-th particle at time $$t$$ and the reference position of the $$i$$-th particle.

The command will calculate a diffusion constant, $$D$$, from $$MSD$$ according to the Einstein relation

<p style="text-align: center;">$$MSD=2Dt$$</p>

where $$t$$ is the simulation time used to calculate the $$MSD$$

Calculating $$D$$ for cations and anions in the system ()$$D_+$$ and $$D_-$$, respectively), the ionic conductivity can be calculated by the Nernst-Einstein equation

<p style="text-align: center;">$$\sigma=\frac{e^2}{Vk_BT}(N_+z_+D_++N_-z_-D_-)$$</p>

where $$e$$ and $$k_B$$ are the unit charge and Boltzmann constant; $$V$$, $$T$$, $$N\pm$$, and $$z\pm$$ are the volume, temperature, number of each ionic species, and charge of the ionic species in the system.

## References
[The Velocity Autocorrelation Function](https://www.ucl.ac.uk/~ucfbasc/Theory/vaf.html#:~:text=The%20velocity%20autocorrelation%20function%20)

[Statistical mechanics of dense ionized matter. IV. Density and charge fluctuations in a simple molten salt](https://doi.org/10.1103/PhysRevA.11.2111)
