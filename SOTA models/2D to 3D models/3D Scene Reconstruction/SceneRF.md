# SceneRF: Self-Supervised Monocular 3D Scene Reconstruction with Radiance Fields

![image](https://github.com/user-attachments/assets/dd7fdf9f-4e37-4a2e-bc5a-984384e021c2)

## 1. Introduction
**SceneRF** introduces a novel framework for monocular 3D scene reconstruction using radiance fields, trained in a self-supervised manner. Traditional 3D scene reconstruction methods often rely on multi-view stereo or depth sensors, which are challenging to acquire in real-world scenarios. SceneRF leverages **radiance fields** to enable 3D scene reconstruction from a single image, without requiring multi-view consistency. This approach is especially useful for applications where only monocular images are available.

## 2. Architecture Overview
The architecture of SceneRF consists of several key components:
1. **Monocular Image Encoder:** The input image is processed by an encoder network to extract 2D features, which capture both spatial and appearance information.
2. **Neural Radiance Field (NeRF):** A neural network that maps 3D coordinates and viewing directions to RGB colors and densities, enabling the reconstruction of the scene’s 3D structure and appearance.
3. **Ray Sampling Module:** Given the camera parameters, rays are sampled from the scene and passed through the radiance field to predict the color and depth at each point in the scene.
4. **Self-Supervised Training:** The model learns through a self-supervised loss function by predicting pixel colors and matching them with the input image, without requiring ground-truth 3D data.

## 3. Loss Function and Objective Overview
SceneRF employs a combination of loss functions to guide the self-supervised training:
- **Photometric Loss:** Measures the difference between the predicted pixel colors and the actual colors in the input image, ensuring accurate scene reconstruction.
- **Depth Consistency Loss:** Encourages depth predictions to remain consistent with the geometry of the scene.
- **Smoothness Loss:** Regularizes the 3D scene representation by enforcing smoothness in the reconstructed surfaces, preventing noise and artifacts.

## 4. Process Detail
1. **Input Image:** The process begins with a monocular RGB image of the scene.
2. **Feature Extraction:** The image is encoded into feature maps using the Monocular Image Encoder.
3. **Ray Sampling and Scene Reconstruction:** Rays are sampled from the camera view, and the Neural Radiance Field predicts the color and density for each sampled point, generating a volumetric representation of the scene.
4. **Rendering:** The predicted radiance field is rendered back into an image, and the colors are compared to the original input for self-supervised learning.
5. **Self-Supervised Optimization:** The model iteratively updates its parameters through backpropagation, minimizing the photometric and regularization losses.

## 5. Applications
SceneRF has various potential applications, including:
- **Autonomous Driving:** Generating 3D reconstructions from monocular dashcam footage for navigation and obstacle detection.
- **Robotics:** Providing 3D scene understanding from a single camera input, aiding in robot navigation and manipulation.
- **Virtual Reality (VR) and Augmented Reality (AR):** Enhancing real-time scene reconstruction in VR/AR applications where only monocular images are available.
- **3D Scene Modeling:** Creating 3D models from single images, useful for content creation and architectural visualization.

## 6. Advantages and Disadvantages Compared to Other SOTA Models
### Advantages:
- **Monocular 3D Reconstruction:** SceneRF enables accurate 3D scene reconstruction from a single image, eliminating the need for multi-view stereo or depth sensors.
- **Self-Supervised Learning:** The self-supervised approach removes the requirement for expensive 3D ground truth data, making it more scalable and practical for real-world applications.
- **Efficient Representation:** By using radiance fields, the model can represent complex 3D scenes with a continuous volumetric representation, allowing for fine details in the reconstruction.

### Disadvantages:
- **Limited Generalization:** The model may struggle with generalization in highly complex or occluded scenes, where monocular input provides insufficient depth cues.
- **Computation Intensity:** Ray sampling and volumetric rendering can be computationally expensive, especially for high-resolution scenes.
- **Ambiguities in Monocular Input:** Since only one view is available, some ambiguity in depth estimation may persist, especially in feature-poor regions or complex geometries.

[Github](https://github.com/astra-vision/SceneRF)
