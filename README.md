# CloudRain3D
 A Python project that visualizes an animated 3D scene of stylized raindrops falling under a volumetric cloud using Plotly. Combines mathematical modeling and scientific cloud formation concepts for a realistic and interactive visualization.

# 🌧️ Animated 3D Raindrops with Plotly

This project visualizes an animated 3D scene of stylized raindrops falling under a volumetric cloud using Python and Plotly.  
The raindrops have a custom curved shape combining semicircular and logarithmic curves, and gently bounce in a loop to simulate falling motion.

---

## 🔢 Mathematical Description of Raindrop Shape

The raindrop shape consists of two parts:

1. **Upper semicircle (top dome):**

\[
\begin{cases}
x(t) = r \cos(t) \\
y(t) = r \sin(t)
\end{cases} \quad t \in [0, \pi]
\]

where \(r=0.05\) is the radius.

2. **Logarithmic tail (bottom taper):**

\[
\begin{cases}
x(t) = r \log(t) \\
y(t) = a t
\end{cases} \quad t \in [0.1, 1]
\]

with \(a=0.03\), shaping the tapered tail.

3. **3D extrusion:**

The 2D curve is extended in 3D with a small \(z\) component:

\[
z(t) = b t, \quad b=0.02
\]

The 2D points \((x,y)\) are triangulated via Delaunay triangulation to form a mesh.

---

## 🌥️ Scientific Explanation of Cloud Formation

Clouds are composed of tiny water droplets or ice crystals suspended in the atmosphere. The main processes behind cloud formation are:

- **Evaporation and moisture accumulation:** Water vapor rises from Earth's surface.
- **Air uplift and cooling:** Warm, moist air ascends and cools adiabatically.
- **Condensation:** When the temperature reaches the dew point, vapor condenses on aerosols forming droplets.
- **Suspension:** Tiny droplets remain suspended by air currents, forming clouds.

---

### In This Model

The cloud is simulated as a 3D **point cloud** generated from Gaussian distributions centered at multiple points with different spreads, mimicking real cloud density variations. This provides a volumetric fuzzy cloud appearance.

---

## 🎥 Features

- Custom 3D raindrop shape based on semicircle + logarithmic tail  
- Smooth animated bouncing motion simulating falling drops  
- Volumetric cloud rendered as a semi-transparent Gaussian point cloud  
- Fully interactive 3D scene with zoom, pan, and rotate  
- Adjustable parameters for rows, columns, spacing, and animation frames

---

## 🧩 Installation

Make sure to install required packages:

```bash
pip install numpy scipy plotly
