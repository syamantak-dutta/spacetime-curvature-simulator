# Spacetime Curvature Simulator 🌌  
*A real-time 3D visualization of how mass affects the geometry of space.*

---

## 🧠 Overview
This project is a **C++ OpenGL simulation** that visualizes the concept of **spacetime curvature** — how massive bodies warp the geometry of the universe around them.  
While full **General Relativity** requires solving Einstein’s field equations, this simulator uses a **Newtonian approximation** of gravity and applies geometric deformation to a 3D grid to mimic curvature effects.

The simulation allows interactive control over gravitational bodies, showing how their presence bends the surrounding space.

---

## 🧱 Features
- 🌍 Real-time gravitational interaction between multiple bodies  
- 🌀 Dynamic grid warping to visualize curvature  
- 💡 Glow and lighting effects for massive stars  
- 🎮 Interactive camera and object creation  
- 🧮 Adjustable mass and motion to observe curvature changes dynamically  

---

## ⚙️ Mathematical Foundation

Although simplified, the simulator is inspired by the fundamental idea in **General Relativity**:

> “Mass-energy tells spacetime how to curve, and spacetime tells mass how to move.”  
> — *John Archibald Wheeler*

In the Newtonian limit, the gravitational field can be expressed as the potential:
\[
\nabla^2 \Phi = 4 \pi G \rho
\]

and the **force** acting on a test mass is given by:
\[
\mathbf{F} = -\nabla \Phi = -\frac{G m_1 m_2}{r^2} \hat{r}
\]

In the simulator:
- Each body exerts a gravitational influence on others via this classical law.
- The **grid vertices** are displaced according to an approximate Schwarzschild metric idea:
  \[
  r_s = \frac{2GM}{c^2}
  \]
  and the vertical distortion of the grid is calculated from  
  \[
  \Delta y = 2\sqrt{r_s (r - r_s)}
  \]
  providing a visual analogy for spacetime curvature.

This blending of Newtonian and relativistic intuitions offers an accessible way to **see how gravity and geometry intertwine**.

---

## 🧰 Technologies
- **C++17**
- **OpenGL** — rendering engine
- **GLFW** — window and input handling
- **GLEW** — OpenGL extension management
- **GLM** — mathematics library for 3D transformations  

---

## 🛠 Build Instructions (MSYS2 + MinGW64)

```bash
pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-glfw mingw-w64-x86_64-glew mingw-w64-x86_64-glm

g++ "src/gravity_sim_3Dgrid.cpp" -I"/mingw64/include" -L"/mingw64/lib" \
-lglew32 -lglfw3 -lopengl32 -lgdi32 \
-o "src/spacetime_curvature_sim.exe"

./src/spacetime_curvature_sim.exe
