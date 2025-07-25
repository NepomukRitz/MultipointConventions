---
layout: default
title: MultipointConventions
---


# KeldyshQFT

Conventions for real-frequency quantum field theory in the Keldysh formalism, as used in [^1] [^2] [^3] [^4].

## Basic building blocks

<table class="booktabs">
  <thead>
    <tr>
      <th>Variable</th>
      <th>Definition</th>
      <th>Diagram</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>Partition function</td>
        <td>
        \[
            \mathcal{Z} = \int \mathcal{D}[\overline{c},c]\, e^{iS[\overline{c},c]}
        \]
        </td>
        <td> \(-\) </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> Action </td>
        <td> 
            \[
                \begin{aligned}
                    S[\overline{c},c] &= S_0[\overline{c},c] + S_{\mathrm{int}} [\overline{c},c] \\
                    &= \overline{c}_{1'} [G_0^{-1}]_{1'|1} c_{1} + \tfrac{1}{4} \overline{c}_{1'}  \overline{c}_{2'} [\Gamma_0]_{1'2'|12} c_{2} c_{1}
                \end{aligned}
            \]
        </td>
        <td> \(-\) </td>
        <td> Multi-indices: time, Keldysh contour index, spin, etc. Einstein summation convention is used.<br> Contracting time and Keldysh indices means an integration along the Keldysh contour.  </td>
    </tr>
    <tr>
        <td> Bare interaction </td>
        <td> 
            \[
                \begin{aligned}
                &[\Gamma_0]^{j_{1'}j_{2'}|j_1 j_2}_{\sigma_{1'}\sigma_{2'}|\sigma_1 \sigma_2}(t_{1'},t_{2'}|t_1,t_2 ; q_{1'},q_{2'}|q_1 q_2) \\
                &= -j_1 \delta_{j_{1'}=j_{2'}=j_{1}=j_{2}}  \delta(t_{1'}=t_{2'}=t_{1}=t_{2}) \\
                &\quad \times
(\delta_{\sigma_{1'},\sigma_2}\delta_{\sigma_{2'},\sigma_1} - \delta_{\sigma_{1'},\sigma_1}\delta_{\sigma_{2'},\sigma_2}) [\Gamma_0](q_{1'},q_{2'}|q_1 q_2)
                \end{aligned}
            \]
        </td>
        <td> <img src="assets/bare.png" alt="Bare_vertex" width="100"> </td>
        <td>
            $j$: Keldysh contour index <br>
            $\sigma$: Spin index <br>
            $t$: real time variable <br>
            $q$: everything else
         </td>
    </tr>
    <tr>
        <td> Bare inv. propagator </td>
        <td> $$[G_0^{-1}]_{1'|1} = \delta_{1'|1} i\partial_{t_1} - h_{1'|1}$$ </td>
        <td> \(-\) </td>
        <td> $h_{1'\mid 1}$ is the single-particle Hamiltonian, $H_{0}[\overline{c},c] =\overline{c}_{1'} h_{1'\mid 1} c_1$</td>
    </tr>
    <tr>
        <td> Bare propagator </td>
        <td>
            \[
                \begin{aligned}
                    {[G_0]}_{1|1'} &= -i \langle \mathcal{T_\mathcal{C}}\,  c_1 \overline{c}_{1'}\rangle_0 \\
                    &= \frac{-i}{\mathcal{Z}_0} \int \mathcal{D}[\overline{c},c]\, c_1 \overline{c}_{1'} e^{iS_0[\overline{c},c]}
                \end{aligned}    
            \]
        </td>
        <td> <img src="assets/bare_G0.png" alt="Bare_propagator" width="100"> </td>
        <td> with the non-interacting partition function $\mathcal{Z}_0 = \int \mathcal{D}[\overline{c},c]\,  e^{iS_0[\overline{c},c]}$ </td>
    </tr>
    <tr>
        <td> Full propagator </td>
        <td>
            \[
                \begin{aligned}
                    G_{1|1'} &= -i\langle \mathcal{T_\mathcal{C}}\, c_1 \overline{c}_{1'}\rangle \\
                    &= \frac{-i}{\mathcal{Z}} \int \mathcal{D}[\overline{c},c]\, c_1 \overline{c}_{1'} e^{iS[\overline{c},c]}
                \end{aligned}    
            \]
        </td>
        <td> <img src="assets/full_G.png" alt="Full_propagator" width="100"> </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> Dyson equation </td>
        <td>
        \[
            \begin{aligned}
                G_{1|1'} &= [G_0]_{1|1'} + [G_0]_{1|2'} \Sigma_{2'|2} G_{2|1'} \\
                \Leftrightarrow \quad G^{-1}_{1'|1} &= [G_0^{-1}]_{1'|1} - \Sigma_{1'|1}
            \end{aligned}
        \] 
        </td>
        <td> <img src="assets/dyson.png" alt="Dyson_equation" width="300"> </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> Four-point (4p) function </td>
        <td> $G^{(4)}_{12|1'2'} = i\langle \mathcal{T_\mathcal{C}}\, c_1 c_2 \overline{c}_{2'} \overline{c}_{1'} \rangle$ </td>
        <td> <img src="assets/4p_fct.png" alt="4p_fct" width="150"> </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> Tree expansion </td>
        <td> $i G^{(4)}_{12|1'2'} = G_{1|1'} G_{2|2'} - G_{1|2'} G_{2|1'} + i G^{(4)}_{c;\,12|1'2'}$ </td>
        <td> <img src="assets/tree_exp.png" alt="Tree_expansion" width="300"> </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> Connected 4p function </td>
        <td> $G^{(4)}_{c;\,12|1'2'} = - G_{1|3'} G_{2|4'} \Gamma_{3'4'|34} G_{3|1'} G_{4|2'}$ </td>
        <td> <img src="assets/4p_connected.png" alt="4p_connected" width="150"> </td>
        <td> \(-\) </td>
    </tr>
    <tr>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
    </tr>
  </tbody>
</table>



# Still to do

## Two-particle channels

- parquet decomposition
- frequency parametrization

## Spin components

## Keldysh contour, Keldysh rotation, FDT

## Symmetries

- crossing
- parity
- complex conjugation
- ...




# References

[^1]: Elias Walter, [Ph.D. Thesis](https://www.asc.physik.lmu.de/lsvondelft/publications/pdf/walter_elias.pdf), LMU Munich, 2022

[^2]: Ge et al., [Real-frequency quantum field theory applied to the single-impurity Anderson model](https://doi.org/10.1103/PhysRevB.109.115128), PRB, 2024

[^3]: Ritz et al., [KeldyshQFT: A C++ codebase for real-frequency multiloop functional renormalization group and parquet computations of the single-impurity Anderson mode](https://doi.org/10.1063/5.0221340), JCP, 2024

[^4]: Ritz et al., [Testing the parquet equations and the U(1) Ward identity for real-frequency correlation functions from the multipoint numerical renormalization group](https://arxiv.org/abs/2504.05910), arXiv, 2025
