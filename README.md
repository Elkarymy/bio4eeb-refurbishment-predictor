# 🏗️ BIO4EEB Building Refurbishment Predictor

An interactive web dashboard that instantly predicts the energy and thermal comfort impact of refurbishment scenarios for the Belgian residential stock. Powered by a gradient boosting machine learning model trained on **18,142 EnergyPlus simulations** – and it runs **entirely in your browser**, no server needed.

🔗 **[Launch the live tool](https://yourusername.github.io/your-repo-name/)**  
*(Replace with your actual GitHub Pages URL)*

![Tool Screenshot](screenshot.png)  <!-- Add a screenshot if you have one -->

---

## ✨ Features

- 🧱 **Full refurbishment catalogue** – Named dropdowns for walls, roofs, floors, and windows (including bio‑based options like BioPUR, PLAfoam, Posidonia).
- 🎚️ **Fine‑tune sliders** – Adjust U‑values with precision beyond the predefined options.
- ⚡ **Live predictions** – Total EUI, heating & cooling energy, and energy savings update instantly.
- 🌡️ **Thermal comfort analysis** – EN 16798 Category B metrics (PMV & PPD) with target indicators.
- 🔍 **Feature importance** – Interactive bar chart showing which building parameters drive each output.
- 📊 **Model validation** – R² scores from 5‑fold cross‑validation (EUI, heating, cooling, PMV, PPD).
- 🧪 **Floor‑by‑floor breakdown** – View results for individual floors or the whole building.
- 📦 **Self‑contained** – The trained GBM model is embedded directly in the HTML; no backend or dependencies.

---

## 🚀 How It Works

The tool uses a **Gradient Boosting ensemble** (best of three models) that takes seven input features:

| Feature       | Description            |
|---------------|------------------------|
| Wall U‑value  | W/m²K (0.10 – 3.32)   |
| Roof U‑value  | W/m²K (0.10 – 2.38)   |
| Floor U‑value | W/m²K (0.10 – 2.65)   |
| Window U‑value| W/m²K (0.50 – 5.00)   |
| SHGC          | Solar Heat Gain Coef.  |
| Shading       | No shading / Indoor    |
| Orientation   | E‑W / N‑S              |

It predicts:
- Total Energy Use Intensity (EUI) [kWh/m²/y]
- Heating energy for each floor
- Cooling energy for each floor
- PMV and PPD comfort hours (percentage of occupied time)

All computations happen on the fly in JavaScript – the model’s trees and baseline are stored right in the page.

---

## 📸 Screenshot

> *Add a screenshot of the tool showing the full dashboard with a scenario selected.*  
> You can take one with Windows Snip & Sketch, Mac Screenshot tool, or a Chrome extension.  
> Save it as `screenshot.png`, upload to the repo, and the image will appear above.

---

## 📁 Repository Structure
