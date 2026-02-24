*2026-02-11 11:18:32*

## Evaluation
60% - 6 assignments every two weeks with two written defenses.
40% - Exam

We are going to program for the GPU instead of the CPU. The GPch U is capable of working with big matrices in much less clock cycles than the CPU. Eg. matrix of 4 slots multiplying with a matrix of 4 is 7 cycles (4 for multiplying and 3 for adding up).

## Computer Graphics Areas
- Geometry
- Materials
- Colorimetry
- Rendering
- Simulation
- Kinematics
  - Inverse Rendering
  - Inverse Kinematics
  - Computer-Aided Design (AutoCAD)
  - GPU Computing
  - Non-Visible Rendering
  - Imaging
  - Fabrication

Virtual sets, led panels behind actors in movies are made with unreal engine 5 

### Advice
There are very little people around that **really** know computer graphics, anyone with a decent paper is easily employed.

## Bibliography
- Computer graphics fourth edition
- GPU Gems
- Real time Shadorows
- Ray Tracing Gems

## GPU
GPU has hundreds to thousahunds of cores, we work with all of them at once, its made for working with huge matrices. GPU has its own programming languages, not the same as CPU.

**GLSL** GPU programming language, the most common, its like a simple C with extra variables for the GPU. it has a main function then has the code inside. 
There is an API that allows the CPU orchestrate the GLSL code and tasks to GPU and back. The current API have limitations and the most known are:

#### For most tasks
- CUDA
- Tensort
- OpenCL
#### For video graphics (games)
- Vulkan (**most** used, works in every OS)
- DirectX (Windows, was used before Vulkan)
- Metal (MacOS)

## First Assignment - Vulkan boilerplate
Create the first objects that are part of the boilerplate for Vulkan.
There are many objects we need to create and things we need to define before we get it working. 

### How it works
- Instance (VK)
  - InstanceInfo
  - Surface (Window, created with GLFW) <-> GLFW
    - PhysicalDevice (= GPU, basically an ID) 
      - LogicalDevice (The actual device we use and interact with)
        - Queue (were we submit the tasks)

**Vulkan Launchpad (VKL):** framework that simplifies vulkan things used for learning.
**Swap Chain:** used all the parts of vulkan. It makes it so there is no screen tearing (parts of different frames rendered at the same time). Has two frames that are swapped between them. We render an image in a frame while the other is showing, then we keep swapping and rendering.
**Extensions:** there are man extensions for vulkan
