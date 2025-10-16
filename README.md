# Aquifer Simulation & Parameter Fitting 

This project models and simulates the height and flux of groundwater aquifers under drought and rainfall conditions.  
It was completed as part of a group project in an undergraduate module on the Mathematics of Sustainability and the Environment.  
The goal was to solve nonlinear PDEs describing aquifer behaviour, compute flux into rivers, and fit model parameters to real hydrograph data from the U.S. Geological Survey (USGS).

---

## Explaining This Repository

- `Final_notebook` → Contains the bulk of the work. Solving the simplified PDEs and fitting the Flux to data.
- `hyrdodata` → Contains real hydrograph data from **Virginia, Georgia, Illinois, and Texas**

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

These equations were solved using seperation of variables and similarity methods to reduce them to ODE's and then the **shooting method** to solve their ODE.

<img width="261" height="176" alt="image" src="https://github.com/user-attachments/assets/7cbcef9f-fa14-49d3-8b22-dc9a01443238" /> <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/efc13cab-fe74-4f32-a21b-9b97631880a6" /> <img width="261" height="176" alt="image" src="https://github.com/user-attachments/assets/a20118da-1a6d-46db-bc31-930bf523a69a" />




---

## 2. Flux Dynamics

Using the solved PDE's for the height of the aquifier with rain and drought. We find that the flux of the aquifier is proportional to the height of the aquifier at the boundary. 
The model captures transitions between rainfall and drought using a transition time parameter (A), allowing both regimes to be joined smoothly. 

<img width="1019" height="704" alt="image" src="https://github.com/user-attachments/assets/45498530-54b6-4fe0-8937-3312e7b07956" />


---

## 3. Parameter Fitting with Real Data

Model parameters were fitted to USGS hydrograph data from four U.S. regions using least-squares minimization.

| Region   | Parameter 1  | Parameter 2 |
|-----------|-----------------------------------------------|----------------------------------------|
| Virginia  | 0.213                                         | 1841.3                                 |
| Georgia   | 0.261                                         | 322.9                                  |
| Illinois  | 0.067                                         | 2027.3                                 |
| Texas     | 0.084                                         | 611.1                                  |

The model shows strong agreement between simulated and observed hydrographs, successfully reproducing peak flow timing and decay across diverse soil and rainfall conditions.

<img width="270.5" height="198" alt="image" src="https://github.com/user-attachments/assets/98d190bf-f095-4db6-87ee-82c4a50a2216" />  <img width="270.5" height="198" alt="image" src="https://github.com/user-attachments/assets/875c807b-2ae1-4809-818a-b5df3cac966f" /> 

<img width="270.5" height="198" alt="image" src="https://github.com/user-attachments/assets/c57ac734-b766-4319-a110-cff382d3e467" />  <img width="270.5" height="198" alt="image" src="https://github.com/user-attachments/assets/40a53201-58f5-4ef8-b980-c4282e1125fc" />




## 4. Conclusion

This project demonstrates how mathematical modelling and numerical simulation can be used to predict aquifer behaviour under changing weather conditions.  
By combining theoretical models with empirical data, we can better understand groundwater dynamics and improve tools for sustainable water management.

