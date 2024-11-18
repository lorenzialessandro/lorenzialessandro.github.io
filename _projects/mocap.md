---
layout: page
title: Motion Capture
description: Processing and animating MoCap data using Python, Unreal Engine 5, and Blender
img: https://github.com/lorenzialessandro/CV-project/raw/main/media/skeletonProjection.png
importance: 1
category: research
related_publications: false
---

This project combines computer vision techniques with state-of-the-art tools to process, analyze, and visualize motion capture (MoCap) data. It addresses key challenges in visualizing human motion, mitigating data inconsistencies, and integrating motion data into virtual environments.

## Key Objectives
1. **Visualization of MoCap Data**: Create dynamic 3D models of skeletons and rigid bodies from various file formats.
2. **Occlusion Handling**: Mitigate flickering and inconsistencies in motion caused by marker loss.
3. **3D-to-2D Projection**: Seamlessly integrate motion data into Unreal Engine 5 for rendering and projection.
4. **Blender Integration**: Enhance data interoperability for advanced neural network and rendering applications.


## Data Reading and 3D Visualization
Motion capture systems generate large datasets in formats like CSV, BVH, and C3D. This task focused on reading, processing, and visualizing data to represent the structure and motion of skeletons and rigid bodies.  
- **CSV Files**: Extracted 3D joint coordinates (`x, y, z`) and connected them to form a complete skeleton, visualized using Python libraries like Matplotlib.  
- **BVH Files**: Parsed motion data to retrieve joint rotations, bone lengths, and connections, enabling detailed skeletal modeling.  
- **C3D Files**: Extracted marker positions for rigid bodies and visualized their trajectories over time.  

The result was a set of interactive 3D plots showcasing skeleton connectivity, bone structures, and marker paths.  
  
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/skeleton.gif" title="3D Skeleton Visualization" class="img-fluid rounded z-depth-1">
    </div>
</div>

---

## Flickering and Occlusion Handling
Motion capture often suffers from marker occlusion, leading to flickering or gaps in motion data. To address this, two advanced filtering techniques were implemented:  
- **Kalman Filter**: A computationally efficient method that predicts and corrects motion states based on linear dynamics, offering smooth and reliable results.
- **Particle Filter**: A probabilistic technique that models non-linear systems by simulating particles and resampling based on observations.  

By comparing the outputs, the Kalman Filter proved more accurate and computationally efficient, though the Particle Filter offered greater flexibility in handling irregular data.  
**Comparison:**  

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/ragnetto-basic.gif" title="Original Data" class="img-fluid rounded z-depth-1" >
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/ragnetto-KF.gif" title="Kalman Filter Correction" class="img-fluid rounded z-depth-1" >
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/ragnetto-PF.gif" title="Particle Filter Correction" class="img-fluid rounded z-depth-1" >
    </div>
</div>


---

## 3D-to-2D Projection in Unreal Engine 5
This task integrated MoCap data into Unreal Engine 5 (UE5) to animate virtual characters and project 3D joint positions onto a 2D image plane. The workflow included:  
1. **Scene Creation**: Actors and cameras were added to a virtual environment using UE5 Blueprints. Animations were retargeted from Adobe Mixamo skeletons.  
2. **Coordinate System Alignment**: Transformation matrices were used to convert between UE5’s left-handed and OpenCV’s right-handed coordinate systems.  
3. **Projection**: Camera intrinsics were calculated to accurately map 3D joint positions onto 2D camera planes, enabling video rendering of the animated skeleton.  

The result was a dynamic scene showcasing precise projection and animation in a controlled virtual environment.  

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/skeletonProjection.png" title="Unreal Engine 5 Projection" class="img-fluid rounded z-depth-1" >
    </div>
</div>

---

## Blender Integration
Blender was utilized to enhance MoCap data visualization and support advanced applications like skeleton-aware neural networks. Using Blender’s Python API, the motion data was seamlessly imported, enabling precise rendering and compatibility with frameworks for animation refinement and style transfer.  

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img src="https://github.com/lorenzialessandro/CV-project/raw/main/media/bvhFrame.png" title="Blender Integration" class="img-fluid rounded z-depth-1">
    </div>
</div>

---

## Results and Achievements
1. Successfully processed and visualized MoCap data from multiple formats.  
2. Mitigated motion flickering using advanced filtering techniques.  
3. Integrated motion data into UE5 for animation and projection.  
4. Enhanced data compatibility with Blender for future applications.  

---

## Resources

<div class="repositories">
  {% include repository/repo.liquid repository="lorenzialessandro/CV-project" %}
</div>

- **Code Repository**: [GitHub Repository](https://github.com/lorenzialessandro/CV-project/)  
- **Media Outputs**: [Project Highlights and Videos](https://www.lucazzola.it/mocap.html)
