# 🏗️ BIO4EEB Building Refurbishment Predictor

An interactive web dashboard that instantly predicts the energy and thermal comfort impact of refurbishment scenarios for the Belgian residential stock. Powered by a gradient boosting machine learning model trained on **18,142 EnergyPlus simulations** – and it runs **entirely in your browser**, no server needed.

🔗 **[Launch the live tool](https://elkarymy.github.io/bio4eeb-refurbishment-predictor/)**  

<img width="1888" height="960" alt="image" src="https://github.com/user-attachments/assets/002bf9c5-a49a-40b4-8939-4e27d6e12164" />


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

-
---

## 📁 Repository Structure
├── index.html # The complete tool (HTML + CSS + JS)
├── gbm_final.json # The exported GBM model (for reference / regeneration)
├── README.md # You are here

The `index.html` file contains everything; the JSON is included only for transparency.

---

## 🧪 Running Locally

1. Clone the repository or download `index.html`.
2. Open `index.html` in any modern browser (Chrome, Firefox, Edge).
3. No installation, no server – the model loads from an embedded JavaScript object.

---

## 📊 Model Performance

| Target          | R² (5‑fold CV) | Status               |
|-----------------|----------------|----------------------|
| Total EUI       | 0.994          | Excellent            |
| Heating (F0/F1/F2)| 0.998 / 0.995 / 0.999 | Excellent |
| Cooling (F0/F1/F2)| 0.890 / 0.860 / 0.981 | Good / Good / Excellent |
| PMV (F0/F1/F2)  | 0.980 / 0.800 / 0.998 | Excellent / Good / Excellent |
| PPD (F0/F1/F2)  | 0.982 / 0.808 / 0.998 | Excellent / Good / Excellent |

*Floor 1 (mid‑floor) shows slightly lower R² due to more complex interactions with adjacent zones.*

---

## 🛠️ Technologies Used

- **Machine Learning:** Gradient Boosting (Python, scikit‑learn / custom implementation)  
- **Frontend:** Vanilla HTML5, CSS3 (custom properties, grid, animations), JavaScript ES6  
- **Deployment:** GitHub Pages  
- **Fonts:** [Syne](https://fonts.google.com/specimen/Syne) & [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)

---

## 🙋‍♀️ About

This tool was developed as part of the **BIO4EEB** project, aiming to promote bio‑based insulation materials and energy‑efficient building retrofits. It showcases how machine learning can make complex building simulation results accessible to architects, engineers, and building owners.

---

## 📬 Contact

For questions or to share feedback, open an issue in this repository or reach out via [oussama.elkarymy@gmail.com] or [https://www.linkedin.com/in/oussama-elkarymy/].
