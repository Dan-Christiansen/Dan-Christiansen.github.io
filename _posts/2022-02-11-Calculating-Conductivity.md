---
title: 'Calculating Conductivity from Molecular Dynamics Simulation'
date: 2022-02-11
permalink: /posts/2022/02/Calculating-Conductivity
/
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

## References
[The Velocity Autocorrelation Function](https://www.ucl.ac.uk/~ucfbasc/Theory/vaf.html#:~:text=The%20velocity%20autocorrelation%20function%20)

[Statistical mechanics of dense ionized matter. IV. Density and charge fluctuations in a simple molten salt](https://doi.org/10.1103/PhysRevA.11.2111)
