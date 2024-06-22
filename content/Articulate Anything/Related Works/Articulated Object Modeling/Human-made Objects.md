---
tags:
  - modeling
---
Engineered systems designed to mimic the natural articulation of [[Organic Objects]] or to serve specific functionalities that require movement.
- Complex assemblies of rigid parts connected by joints.
- Motion is often direct result of interaction with the environment or driven by an active system.

Examples:
- Gadgets, furniture, vehicles, and other mechanical systems

# Representation of Human-made Articulated Objects
Effective modeling of articulated objects requires capturing of a dual representation of geometry and articulation of the object which each influence and inform each other.
- **Cohesive approach needed in articulated object modeling**
There have been challenges with the two representations:
## Geometric Representation
Not the same as geometric modeling of static objects, which concentrates only on object's outer surface; must capture **spatial arrangement of the parts, modeling the part-level surfaces, and constructing the interior structure of the object.**
- Essential to accurately describe **shape, size, relative position, and orientation of each link that os structurally organized within the object.**
Common data formats: 
- **3D Point Cloud:** Set of points sampled from the object surface that can be obtained from 3D scanning or depth projection.
- **3D Mesh:** Collection of polygons that approximate the surface of each link.
- **Implicit Field:** An implicit function that assigns a value to each point in the space to construct a field describing the object shape. Examples: Signed distance field (SDF), occupancy field, density field, etc.
	- Function parameterized by a neural network, known as a neural field, is popular intermediate representation as it is inherently differentiable and easy to integrate with learning-based methods
- **2D Images:** Examples: Single-view RGB-D images and posed RGB images captured from multi-views or stereo cameras.
## Articulation Representation
Includes description of the mobility of each part and the kinematic structure of the object..

**Kinematic Structure**:  Describes how the object's parts are connected and how they can move relative to each other. Typically represented by a tree or graph (Model hierarchical relationships in articulated systems).

**Part mobility** can be described by parameters of each connected joint or the deformation field of the object. 

Articulated motion representation:
- **Deformation field:** General rom of motion representation that describes the displacement of each point as a 3D vector. Can also be used to represent beyond the rigid motion of the shape in a continuous space, such as free-form deformation.
- **Joint Parameters:** Parameters of each joint, including [[Joint Types]], location, and orientation of the **joint axis**, the rotational angle or translational distance as **joint state**, and the left/right bound of joint as joint limit or **motion-range**.
- **Kinematic Tree:** Kinematic structure of the object. represented by a tree or graph, where nodes are links and edges are joint connections.
![[Pasted image 20240614121018.png]]
