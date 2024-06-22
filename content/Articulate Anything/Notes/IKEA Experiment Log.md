---
tags:
  - research
  - log
---
# Setup
[IKEA Manual Dataset](https://cs.stanford.edu/~rcwang/projects/ikea_manual/)
Conda env: articulate-anything
- Python version 3.11.9
- Potentially help create setup.py
# June 17, 2024
[[June 17, 2024 Meeting]]
- Set up Google AI API
- Running into error:
```bash
Traceback (most recent call last):
  File "/Users/dennycao/Projects/articulate-anything/articulate_ikea.py", line 83, in <module>
    articulate_ikea(args.cat, args.name, args.overwrite)
  File "/Users/dennycao/Projects/articulate-anything/articulate_ikea.py", line 40, in articulate_ikea
    for f in sorted(os.listdir(os.path.join(part_obj_dir, "part_imgs"))) if f.endswith(".png")
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
FileNotFoundError: [Errno 2] No such file or directory: 'datasets/ikea_dataset/parts/Chair/applaro/part_imgs'
```
- Try to find what file will generate part images... Goal is to be able to take the pdf and create images for them right?
# June 18, 2024
- Initially started with [[WSL2]]... Ran into issue because [[Vulkan]] is not supported on WSL
- Switched to Windows, but [[Sapien]] 2.2 is not supported on Windows and kept facing error of PCI index error or something
- Switched to [[Ubuntu]] 24.04, but AMD drivers do not support yet... Could not get Vulkan to work
- Switched to Ubuntu 20.04 (Long's distro version) and it worked.
- Began facing issue of `origin` tag being missing from [[URDF]]
- Tried to add `Origin("0 0 0")` to `ikea_to_api.py` when adding `Link` but still not working... 
- Running into issue in `odio_urdf.py` with `origin_element = joint.find("origin")`... It is returning `None`. Even after brute forcing setting the origin
	- Maybe looking at a different file?
	- The URDFs appear to have an extra whitespace after every class. **Attempt to manually edit them and then see if the error persists. Or try it on a different tag.**
# June 19, 2024
- Got it to finally work. Solution was to check if it was `None` and then if it was, add a default value
- Work on how to get proper link/file names rather than just numbers