# Historical Portals: Mixed Reality Pipeline 

An ongoing Mixed Reality (MR) spatial computing prototype that bridges contemporary physical spaces with archival memory. Based on the historic context of **Linz Hauptplatz (Austria)**, this project uses Meta Quest 3 Passthrough and custom shaders to overlay historical 360° environments into the real world.

> 🔒 **Status:** Active Work in Progress (Initial prototype demo uploaded).

---

## Project Visuals

### Final Prototype Concept (Linz Hauptplatz)
The final experience places an ornate, physical-virtual Baroque portal frame within the modern busy square of Linz Hauptplatz. Gazing through the aperture reveals an 8K historic equirectangular view of the square and the Holy Trinity Column (Dreifaltigkeitssäule), seamlessly blending the past directly into the today's passing tram and pedestrian traffic.

![Linz Hauptplatz Concept Sketch](https://github.com/Atousa98/Historical_Portals/releases/download/V1/Ornate.Frame.Over.a.Sketchy.City.Street.png)

### 360° Historical Photosphere
The historical panorama is projected on inverted sphere geometry, calibrated with Custom Y-axis alignment to perfectly overlay onto the real-world sightlines of the square.

![Linz Hauptplatz 360 Archive](https://github.com/Atousa98/Historical_Portals/releases/download/V2/photo_2026-10-19_10-07-40.jpg)

---

## System & Architecture Pipeline

Below is the technical data-flow and hardware mapping of the interactive portal prototype.

### Core Pipeline Components:
1. **Camera & Pose Data**: Captures real-time stereo passthrough and IMU/pose tracking on the Meta Quest 3 headset.
2. **Unity URP Engine**: Handles main render loop, camera setups, and custom shaders.
3. **Custom Stencil Shader**: Disables standard color output to create a 3D depth-masked aperture (Stencil ID: 1) only where the 3D baroque frame sits, allowing the 360° photosphere inside to be masked appropriately.
4. **Environment Integration**: Fuses raw passthrough live footage with the 360° historical projection, anchored and pinned precisely to physical cobblestone ground grids via Spatial Anchors.

---

## Tech Stack

* **Game Engine**: Unity 6 (Universal Render Pipeline - URP)
* **SDKs**: Meta XR Core SDK (v60+), OpenXR
* **Shaders**: Custom HLSL Stencil Shaders
* **Rendering**: Low-latency Passthrough Underlays & Alpha 0 Skyboxes
* **Graphics**: 8K Equirectangular projection, inverted sphere geometry with back-face culling.
* **Tracking & Persistence**: Spatial Anchors & Eye-level Tracking Origins.

---

## Get Started

1. Clone this repository into your local directory.
2. Open the project in Unity (Version 6 or newer).
3. Ensure the **Meta XR SDK** is installed and configured in `Project Settings > XR Plug-in Management`.
4. Run the Scene: Play the scene through **Oculus Link** with Quest 3 connected, or build the APK and deploy to headset.

> **Build Note:** For the passthrough to work seamlessly on PC / Oculus Link play mode, ensure you allow Passthrough realtime data feeds on Meta Link Developer settings first.

---

## 📌 To-Do / Ongoing Roadmap
- [x] Create custom URP Stencil Shader
- [x] Configure inverted 360° photosphere mapping
- [x] Initial tracking origin fixes (Floor-to-Eye level) & Passthrough tests
- [ ] Improve spatial anchoring persistence for wider outdoor environments
- [ ] Refine 3D frame high-polygon optimization
