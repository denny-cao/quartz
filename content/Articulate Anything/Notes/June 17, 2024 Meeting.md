---
tags:
  - research
---
# Update
- Jason is working on articulating from text, videos, images
- Run experiments to test. What if we could articulate from files? Ex. IKEA Manual
- IKEA Dataset with 100 objects with meshes of parts and manual
# IKEA Experiment
**Goal**: 
- INPUT: IKEA manual, part meshes
- Name part meshes into something of semantic importance (Back, leg, etc.)
- Properly orient meshes
	- `object_placement_examples.py` (Look at `align_robot_orientation()`)
- Parse PDF: Skip some steps, combine some steps, etc.
	- **Should this be automated? How so? VLM do it?**
- Articulate objects with the steps
	- Create different methods for each step, and then each method will have link joins