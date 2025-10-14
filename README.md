# Numerical Simulation of Aquifers 🌍💧

## 1. Governing Equations

The aquifer height \( \hat{h} \) evolves according to nonlinear PDEs:

### Drought conditions:
\[
\hat{h}_{\hat{t}} = (\hat{h} \hat{h}_{\hat{x}})_{\hat{x}}
\]

### Rainfall conditions:
\[
\hat{h}_{\hat{t}} = (\hat{h} \hat{h}_{\hat{x}})_{\hat{x}} + 1
\]

---

## 2. Analytical and Numerical Setup

### Drought Case

Using **separation of variables**, we set:
\[
\hat{h}(\hat{x}, \hat{t}) = X(\hat{x})T(\hat{t})
\]

This gives the nonlinear ODE:
\[
X'' + \frac{(X')^2}{X} + X = 0
\]

with boundary conditions:
\[
X(0) = 0, \quad X'(1) = 0
\]

This ODE is solved numerically using a **shooting method**.

### Rainfall Case

We apply a **similarity transformation**:
\[
\hat{h}(\hat{x}, \hat{t}) = \hat{t}^a f(\eta), \quad \eta = \frac{\hat{x}}{\hat{t}^b}
\]

Choosing \( a = b = 1 \), we obtain:
\[
f - \eta f' = (f f')' + 1
\]

with boundary conditions:
\[
f(0) = 0, \quad f(\eta) \to 1 \text{ as } \eta \to \infty
\]

Both resulting equations are stiff and nonlinear, requiring iterative numerical solvers.

---

## 3. Numerical Methods

- Insert How we solve this

---

## 4. Flux Calculations

The **flux into a river** from the aquifer is derived from the gradient at the boundary:

### Rainfall:
\[
\hat{Q}_0 = -\hat{t} f(0) f'(0) = -C^2 \hat{t}^2
\]

### Drought:
\[
\hat{Q}_0 = -\frac{X(0) X'(0)}{(\hat{t} + A)^2} = -\frac{D^2}{2(\hat{t} + A)^2}
\]

Transition time \( A \) is calculated by matching the two flux regimes:
\[
A = \sqrt{\frac{2D^2}{C^2 t^*}} - t^*
\]

> 📈 *Insert plot: Flux vs Time for drought and rainfall cases.*

---

## 5. Real-World Data and Parameter Fitting

The model was validated using **USGS hydrograph data** from  
*Khand & Senay (2022), “Unit hydrographs of evolving urban watersheds across the United States”*.

We re-dimensionalised the flux equations to compare model predictions with observed data.

### Rainfall:
\[
Q(t) = -\left(\frac{R^{3/2} K^{1/2}}{\phi}\right) C^2 t^2
\]

### Drought:
\[
Q(t) = -\left(\frac{\phi^2 L^3}{K}\right) \frac{D^2}{2(t + \theta)}
\]

The model parameters were fitted by minimizing the root-mean-square error:
\[
\min_{p_1, p_2} \sqrt{\sum_i |Q(t_i) - Q_{\text{data}}(t_i)|^2}
\]

| Region   | Parameter 1 \( \frac{R^{3/2} K^{1/2}}{\phi} \) | Parameter 2 \( \frac{\phi^2 L^3}{K} \) |
|-----------|-----------------------------------------------|----------------------------------------|
| Virginia  | 0.213                                         | 1841.3                                 |
| Georgia   | 0.261                                         | 322.9                                  |
| Illinois  | 0.067                                         | 2027.3                                 |
| Texas     | 0.084                                         | 611.1                                  |

> 🌎 *Insert plot: Model fit vs observed USGS hydrograph data for each region.*

---



> 🧮 *This notebook integrates mathematical modelling, numerical simulation, and sustainability analysis to study groundwater systems — a cornerstone for long-term environmental planning.*

