---
tags:
  - datasets
  - research
---
# Sources
[[Objaverse - A universe of annotated 3d objects - Deitke et al. (2022)]]
[[ShapeNet - An Information-Rich 3D Model Repository - Chang et al. (2015)]]
[[PartNet - A Large-Scale Benchmark for Fine-Grained and Hierarchical Part-Level 3D Object Understanding - Mo et al. (2018)]]
[[SAPIEN - A SimulAted Part-based Interactive ENvironment - Xiang et al. (2020)]]
[[GAPartNet - Cross-category Domain-generalizable Object Perception and Manipulation via Generalizable and Actionable Parts Geng et al. (2022)]]

Most objects in these repositories lack articulation.
- ShapeNet and PartNet decompose objects into parts (links) but do not include kinematic joints
- PartNet-Mobility and GAPartNet feature articulated objects with links and joints, but annotations are manually created so small datasets
**Goal:** Automate creation of articulated 3D assets suitable for robotic tasks, reducing reliance on manual annotation