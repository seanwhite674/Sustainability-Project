# Aquifer Simulation & Parameter Fitting 🌍💧

This project models and simulates the **height and flux of groundwater aquifers** under drought and rainfall conditions.  
It was completed as part of an *Applied Mathematics group project* focused on sustainability and water resource management.  
The goal was to solve nonlinear PDEs describing aquifer behaviour, compute flux into rivers, and fit model parameters to real hydrograph data from the **U.S. Geological Survey (USGS)**.

---

## Explaining This Repository

- `Drought_Model` → Solves the drought PDE using separation of variables and the **shooting method**  
- `Rainfall_Model` → Solves the rainfall PDE using a **similarity transformation**  
- `Flux_Comparison` → Calculates and compares river flux under rainfall and drought  
- `Parameter_Fitting` → Fits model parameters to real hydrograph data from **Virginia, Georgia, Illinois, and Texas**

---

## 1. Overview of the Model

The aquifer height ![\hat{h}](https://latex.codecogs.com/svg.image?\hat{h}) evolves according to nonlinear diffusion equations representing groundwater flow.

- **Drought:**  
  ```math
  \hat{h}_{\hat{t}} = (\hat{h} \hat{h}_{\hat{x}})_{\hat{x}}
  ```

- **Rainfall:**  
  ```math
  \hat{h}_{\hat{t}} = (\hat{h} \hat{h}_{\hat{x}})_{\hat{x}} + 1
  ```

These equations were solved using similarity methods to reduce them to ODE's and then the **shooting method** to solve their ODE.

---

## 2. Flux Dynamics

The **flux into a river** is proportional to the aquifer gradient at the boundary.  
The model captures transitions between rainfall and drought using a **transition time parameter (A)**, allowing both regimes to be joined smoothly.

> 📈 *Flux increases quadratically with time during rainfall and decays rapidly during drought.*

<img width="450" alt="Flux Graph" src="https://github.com/user-attachments/assets/your-flux-plot-placeholder" />

---

## 3. Parameter Fitting with Real Data

Model parameters were fitted to **USGS hydrograph data** from four U.S. regions using least-squares minimization.

| Region   | Parameter 1 \( \frac{R^{3/2} K^{1/2}}{\phi} \) | Parameter 2 \( \frac{\phi^2 L^3}{K} \) |
|-----------|-----------------------------------------------|----------------------------------------|
| Virginia  | 0.213                                         | 1841.3                                 |
| Georgia   | 0.261                                         | 322.9                                  |
| Illinois  | 0.067                                         | 2027.3                                 |
| Texas     | 0.084                                         | 611.1                                  |

The model shows strong agreement between simulated and observed hydrographs, successfully reproducing peak flow timing and decay across diverse soil and rainfall conditions.

> 🌎 *Insert: Model vs USGS data plots for each region.*

---

## 4. Key Results

- Solved nonlinear PDEs describing aquifer height under rainfall and drought  
- Derived analytical and numerical expressions for **flux into rivers**  
- Estimated transition times between regimes  
- Fitted physical parameters using **real-world hydrograph data** from the USGS  

---

## 5. Conclusion

This project demonstrates how **mathematical modelling and numerical simulation** can be used to predict aquifer behaviour under changing weather conditions.  
By combining theoretical models with **empirical data**, we can better understand groundwater dynamics and improve tools for sustainable water management.

---

> 📘 *Based on the project “Numerical Simulation of Aquifers” (UCD, 2024).*
---



> 🧮 *This notebook integrates mathematical modelling, numerical simulation, and sustainability analysis to study groundwater systems — a cornerstone for long-term environmental planning.*

