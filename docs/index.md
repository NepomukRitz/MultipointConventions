# KeldyshQFT

Conventions for real-frequency quantum field theory in the Keldysh formalism, as used in [^1], [^2], [^3], [^4].

## Partition function
$$
    \mathcal{Z} = \int \mathcal{D}[\overline{c},c]\, e^{iS[\overline{c},c]}
$$

## Action
$$
S[\overline{c},c] = S_0[\overline{c},c] + S_{\mathrm{int}} [\overline{c},c] = \overline{c}_{1'} [G_0^{-1}]_{1'|1} c_{1} + \tfrac{1}{4} \overline{c}_{{1'}}  \overline{c}_{{2'}} [\Gamma_0]_{{1'}{2'}|{1}{2}} c_{{2}} c_{{1}}
$$
The multi-indices comprise all dependencies of the Grassmann variables, i.e., time, Keldysh contour index, spin, and all other dependencies and quantum numbers there might be. Einstein summation convention is used. Contracting time and Keldysh indices thus means an integration along the Keldysh contour. 

## Bare inverse propagator
$$
    [G_0^{-1}]_{1'|1} = \delta_{1'|1} i\partial_{t_1} - h_{1'|1}\, ,
$$
where $h_{1'|1}$ is extracted from the single-particle Hamiltonian, $H_0[\overline{c},c] = \overline{c}_{1'}h_{1'|1}c_1$.

## Bare interaction
<img src="img/bare.png" alt="Alt Text" width="400"/>

In terms of explicit Keldysh **contour** indices $j$, spin indices $\sigma$, and time indices $t$, where the indices $q$ shall label all other indices there might be, the bare interaction reads
$$
[\Gamma_0]^{j_{1'}j_{2'}|j_1 j_2}_{\sigma_{1'}\sigma_{2'}|\sigma_1 \sigma_2}(t_{1'},t_{2'}|t_1,t_2 ; q_{1'},q_{2'}|q_1 q_2) 
= -j_1 \delta_{j_{1'}=j_{2'}=j_{1}=j_{2}} \delta(t_{1'}=t_{2'}=t_{1}=t_{2})
(\delta_{\sigma_{1'},\sigma_2}\delta_{\sigma_{2'},\sigma_1} - \delta_{\sigma_{1'},\sigma_1}\delta_{\sigma_{2'},\sigma_2}) [\Gamma_0](q_{1'},q_{2'}|q_1 q_2)\, .
$$

## Bare two-point function
$$
[G_0]_{1|1'} = -i \langle \mathcal{T_\mathcal{C}}\,  c_1 \overline{c}_{1'}\rangle_0 = \frac{-i}{\mathcal{Z}_0} \int \mathcal{D}[\overline{c},c]\, c_1 \overline{c}_{1'} e^{iS_0[\overline{c},c]}
$$
with the non-interacting partition function $\mathcal{Z}_0 = \int \mathcal{D}[\overline{c},c]\,  e^{iS_0[\overline{c},c]}$.

## Full two-point function (propagator)
$$
G_{1|1'} = -i\langle \mathcal{T_\mathcal{C}}\, c_1 \overline{c}_{1'}\rangle = \frac{-i}{\mathcal{Z}} \int \mathcal{D}[\overline{c},c]\, c_1 \overline{c}_{1'} e^{iS[\overline{c},c]}
$$

## Dyson equation
$$
 G_{1|1'} = [G_0]_{1|1'} + [G_0]_{1|2'} \Sigma_{2'|2} G_{2|1'}  \qquad \Leftrightarrow  \qquad G^{-1}_{1'|1} = [G_0^{-1}]_{1'|1} - \Sigma_{1'|1}
$$

## Four-point correlation function
$$
G^{(4)}_{12|1'2'} = i\langle \mathcal{T_\mathcal{C}}\, c_1 c_2 \overline{c}_{2'} \overline{c}_{1'} \rangle
$$
Can be decomposed by employing the *tree expansion*,
$$
i G^{(4)}_{12|1'2'} = G_{1|1'} G_{2|2'} - G_{1|2'} G_{2|1'} + i G^{(4)}_{c;\,12|1'2'}\, ,
$$
yielding the connected contribution,
$$
G^{(4)}_{c;\,12|1'2'} = - G_{1|3'} G_{2|4'} \Gamma_{3'4'|34} G_{3|1'} G_{4|2'}\, 
$$
which involves the **four-point vertex** $\Gamma$.

## Still to do

- Keldysh contour
- Keldysh rotation
- FDT
- spin components
- symmetries (crossing, parity, ...)
- more diagrams


# References

[^1]: Elias Walter, [Ph.D. Thesis](https://www.asc.physik.lmu.de/lsvondelft/publications/pdf/walter_elias.pdf), LMU Munich, 2022

[^2]: Ge et al., [Real-frequency quantum field theory applied to the single-impurity Anderson model](https://doi.org/10.1103/PhysRevB.109.115128), PRB, 2024

[^3]: Ritz et al., [KeldyshQFT: A C++ codebase for real-frequency multiloop functional renormalization group and parquet computations of the single-impurity Anderson mode](https://doi.org/10.1063/5.0221340), JCP, 2024

[^4]: Ritz et al., [Testing the parquet equations and the U(1) Ward identity for real-frequency correlation functions from the multipoint numerical renormalization group](https://arxiv.org/abs/2504.05910), arXiv, 2025
