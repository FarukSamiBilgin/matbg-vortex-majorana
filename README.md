# Can a vortex in magic-angle graphene host a Majorana zero mode?

*A geometric obstruction, and the measurement that settles it*

**Author:** Faruk Sami Bilgin, Independent Researcher, ORCID [0009-0001-9064-4410](https://orcid.org/0009-0001-9064-4410)

**Status:** Manuscript in preparation (not peer reviewed). This repository holds the extended abstract (`paper/ABSTRACT.md`) and the computed result artifacts (`results/`); the full draft is not included.

## Question

Can a vortex pinned in a gate-defined magic-angle graphene mesa host a Majorana zero mode, given that the superconducting gap may be nodal? And if not, is the reason material (pairing symmetry) or geometric (device design)?

## Method

Analytic desk calculation, every number emitted to a machine-readable artifact (`results/m40_nodal.json`, 16 self-checks, 0 failures):

- Volovik zero-energy density of states at the working field by three independent routes (extrapolated √B fit; Doppler estimate via the coherence length from the critical field; Doppler estimate via velocity and gap).
- Fluxoid / Little–Parks identity for a mesa of area `A_mesa`, and a two-parameter feasibility map (critical field × estimation route).
- Gapped vs power-law Majorana hybridisation for two vortices 500 nm apart (sensitivity scan over the exponent p).
- Chern-parity (Pfaffian at the four time-reversal-invariant momenta) evaluations: minimal lattice model (`results/m45_pfaffian.json`) and Bistritzer–MacDonald continuum bands at the magic angle (`results/m46_bm_pfaffian.json`, independent re-verification in `results/m46b_verify13.json`).

## Key results

| quantity | value |
|---|---|
| Working field of the design, `B(L=2) = 2Φ₀/A_mesa` (A_mesa = 1.5 μm²) | 2.76 mT |
| Zero-energy DOS at the working field, three routes | 5.1 % to 26.3 % of normal (criterion: 5 %) |
| Feasibility map (5 critical fields × 2 routes) | 9 of 10 combinations infeasible; the survivor clears the 0.5 mT floor by 5 % |
| Zero-field hard-gap check for a clean nodal gap at 20 mK | `G(0)/G_N` = 0.92 % (passes a 5 % check: the trap) |
| Two-vortex splitting at 500 nm, gapped law | 10.6 neV |
| Two-vortex splitting at 500 nm, nodal p = 1 / 2 / 3 | 26.5 μeV / 2.72 μeV / 0.279 μeV |
| Separation needed for δE < k_BT_e at p = 1 | 7694 nm (mesa linear size 1225 nm) |
| Physical inter-valley channel on BM bands, Chern parity | even at every grid point |
| Intra-valley channel at generic director angle (β = π/8) | odd at 13 grid points (each re-verified at the larger basis and with a Schur-form Pfaffian) |
| BM flat-band width reproduced on the BdG side | 2.922032 meV |

**The core identity.** `B(L=1) = Φ₀/A_mesa` is simultaneously the working field and the width of the Little–Parks window. Lowering the field to suppress the nodal density of states narrows the vortex-counting window by the same factor. No improvement in fridge, etch or pinning moves it.

## Negative and limiting results

- **Withdrawn by the author:** the inference "nodal, therefore no minigap, therefore no Majorana"; the zero-field hard-gap rung as a kill criterion; the quantised-peak rung; the earlier 12 neV parity-splitting figure; the earlier field-window analysis.
- The exponent p of nodal-mediated two-vortex hybridisation is **not established**; the table is a sensitivity scan. A two-vortex BdG solve addressing it is in progress in a separate code base: [josim-cpr-bridge, open PR "feat(nodal_majorana): two-vortex BdG solver and the anisotropic Majorana hybridization law"](https://github.com/FarukSamiBilgin/josim-cpr-bridge/pulls).
- No vortex BdG solve is contained here. The BM-band Pfaffian evaluation does not include the Kekulé-spiral reconstruction of the actual normal state (a registered inconsistency).
- Routes B and C differ by a factor 3.26 because the coherence length from the critical field (51.3 nm) and from the velocity and gap (15.75 nm) disagree; reported, not resolved.

## Verification

Every quantitative statement in the manuscript carries a trace comment naming the artifact key it comes from. `m40_nodal.json` carries 16 automated self-checks (0 failed). The Pfaffian code reproduces two known benchmarks (spinless p+ip weak/strong-pairing transition; s-wave/Rashba/Zeeman criterion) before any production run; BM-band parities are shell-converged (production and next-larger basis agree at every checked point).

## Reproducing

`results/` contains the JSON artifacts as emitted by the computation scripts. The generating scripts live in the author's private research repository and will be released with the manuscript; this repository does not yet contain runnable code.

## The measurement that settles it

`G(0)/G_N` vs perpendicular field in ~0.5 mT steps through one point contact, at two fillings: a `√B` law means nodal and the route is dead; flat then activated means a full gap and the route survives. The full protocol is in the companion repository [matbg-pairing-symmetry-proposal](https://github.com/FarukSamiBilgin/matbg-pairing-symmetry-proposal).

## Related work by the author

- Twisted hBN preprint: https://doi.org/10.5281/zenodo.24201814
- Twisted MoS₂ hole-spin coherence: https://www.alphaxiv.org/abs/2611.twisted-mos2-hole-spin-coherence
- Moiré microwave loss: https://doi.org/10.5281/zenodo.24204124
- josim-cpr-bridge: https://github.com/FarukSamiBilgin/josim-cpr-bridge
- Companion: [twist-disorder-topological-gap](https://github.com/FarukSamiBilgin/twist-disorder-topological-gap)

## AI assistance

AI assistance: AI coding assistants were used for code development and for adversarial review. All load-bearing results were re-derived by independent methods and checked by automated tests; the author is responsible for every claim.

## Citation

See `CITATION.cff`. Code: MIT (`LICENSE`); text, figures and data: CC BY 4.0 (`LICENSE-CONTENT`).
