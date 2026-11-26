# Decomposing the Hamiltonian Neural Network Advantage in the Chaotic Three-Body Problem

**Arnav Mehta · May 2026**

[**Interactive research website**](https://mehtaarnav.github.io/hnn-threebody-mechanism/) · [**Research paper (PDF)**](./three_body_hnn_paper.pdf)

## Research question

Does the advantage of Hamiltonian neural networks (HNNs) in chaotic dynamics arise from second-order mechanical structure, soft energy regularization, or the Hamiltonian formulation itself? How does that advantage change with chaos intensity?

## Approach

- Generated 5,000 gravitational three-body trajectories across eight mass configurations using REBOUND/IAS15.
- Stratified systems by maximal Lyapunov exponent and evaluated 454 held-out systems.
- Compared four models with matched residual-network backbones (~530,000 parameters): MLP, MechanicsNN, MLP+E, and HNN.
- Evaluated pointwise trajectory divergence and phase-independent orbit geometry under both Euler and RK4 rollout integration.

## Key results

| Chaos regime | Median Hausdorff distance: MLP | Median Hausdorff distance: HNN | Reduction |
| --- | ---: | ---: | ---: |
| Low | 8.46 | 5.21 | 39% |
| Medium | 7.36 | 2.53 | 66% |
| High | 6.91 | 2.21 | 68% |

The study reports no detectable improvement in pointwise divergence time under the tested protocol. The geometric advantage increases with chaos intensity: the Hamiltonian-specific share of the improvement rises from 41% to 71% across the low- and high-chaos bins. These observations support a distinction between temporal prediction and geometric fidelity.

## Interactive demonstration

The [research website](https://mehtaarnav.github.io/hnn-threebody-mechanism/) includes an interactive three-body visualization, the four-model comparison, quantitative results, and methodology. The browser simulation illustrates the proposed error mechanisms using synthetic perturbation models; it does **not** execute the trained neural networks.

## Scope and limitations

The paper reports a single-seed study of the sampled stable planar three-body systems. Conservation of the learned Hamiltonian in continuous time does not guarantee conservation of the true mechanical energy or preservation of the exact orbit under numerical integration. The geometric mechanism is an interpretation of the reported results, not a proof of exact orbit preservation.

This repository currently hosts the research paper and interactive presentation website, rather than a complete reproducibility package containing the training code, datasets, and model weights.

## Citation

Mehta, A. (2026). *Decomposing the Hamiltonian Neural Network Advantage in the Chaotic Three-Body Problem.* Research report, May 3, 2026.
