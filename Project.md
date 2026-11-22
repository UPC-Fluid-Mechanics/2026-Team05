
# Release 1 – Team 5

**Design of an Axial Fan for a Car Radiator**

## 1. Introduction

The objective of this project is to design an axial fan for a car radiator and to evaluate its performance using CFD. The work is organised in three parts: preliminary design (mean-line sizing), detailed design of the blades, and numerical validation of the resulting geometry.

### 1.1 Reference designs

- Ambdekar et al. (2014), *Design and Analysis of Engine Cooling Fan* – [201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf](References/201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf)
- Elhaj et al. (2024), *CFD Modeling of a Radiator Axial Fan for Air Flow* – [CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf](References/CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf)
- Pereira et al. (2021), *Improved Aerodynamics of a Hollow-Blade Axial Flow* – [Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf](References/Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf)
- SPAL VA18-AP71/LL-59A, Commercial 12 V automotive axial fan - [VA18-AP71-LL-59A-42S.pdf](References/VA18-AP71-LL-59A-42S.pdf)

### 1.2 Target specifications

The SPAL VA18-AP71/LL-59A is used as a commercial benchmark. Its external dimensions and performance curve provide a reference, while the blade geometry will be independently designed.
The preliminary design ranges below are based on the literature. 

| Parameter | Target range / value | Source |
|-----------|---------------------|--------|
| Flow rate $Q$ | 0.5 – 2.5 m³/s | Literature review |
| Pressure rise $\Delta p$ | 100 Pa | Literature review |
| Rotational speed $N$ | 1500 – 2500 rpm | Literature review |
| Tip diameter $D$ | 385 mm | SPAL reference |
| Hub diameter $D_h$ | Approximately 128 mm | SPAL reference |
| Power supply | 12 V DC | SPAL reference |

The SPAL performance curve provides the following reference operating points in suction configuration:

| Flow rate $Q$ (m³/h) | Flow rate $Q$ (m³/s) | Static pressure $\Delta p_s$ (Pa) |
|---------------------:|---------------------:|----------------------------------:|
| 3090 | 0.858 | 49.0 |
| 2840 | 0.789 | 73.5 |
| 2510 | 0.697 | 98.1 |
| 2170 | 0.603 | 122.6 |

The selected nominal operating point is approximately 2840 m³/h (0.789 m³/s) at 73.5 Pa static pressure.

## 2. Design

### 2.1 Specification and dimensionless parameters

### Assumptions

The following values are preliminary design assumptions. Some are taken from the SPAL reference, while others are based on standard engineering assumptions.

| Symbol | Value | Meaning | Source |
|--------|-------|---------|--------|
| $\rho$ | 1.2 kg/m³ | Air density (approximately 20 °C) | Engineering assumption |
| $D$ | 0.385 m | Tip diameter | SPAL reference |
| $D_h$ | 0.128 m | Hub diameter | SPAL reference |
| $\nu = D_h/D$ | 0.332 | Hub-to-tip diameter ratio | Calculated from SPAL dimensions |
| $N$ | 1500 rpm | Preliminary rotational speed | Literature range; selected design value |
| $\eta$ | 1 | Ideal efficiency for the first theoretical estimate | Ideal assumption |
| $Q$ | 0.789 m³/s | Selected nominal flow rate | SPAL performance curve |
| $\Delta p_s$ | 73.5 Pa | Static pressure at the nominal operating point | SPAL performance curve |
| $\Delta p_0$ | 100 Pa | Preliminary pressure rise | Total pressure rise required for the mean-line analysis | To be established |


### Method

1. Angular speed:

   $$\omega = \frac{2\pi N}{60}$$

2. Annulus area and axial velocity:

   $$A = \frac{\pi}{4}\left(D^2-D_h^2\right), \qquad c_x = \frac{Q}{A}$$

3. Mean radius and blade speed:

   $$r_m = \sqrt{\frac{r_h^2+r_t^2}{2}}, \qquad U_m = \omega r_m$$

4. Euler equation, assuming axial inlet flow ($c_{\theta 1}=0$):

   $$\Delta p_0 = \rho U_m(c_{\theta 2}-c_{\theta 1})$$

5. Flow angles at the mean radius:

   $$\tan\beta_1 = \frac{U_m}{c_x}, \qquad \tan\beta_2 = \frac{U_m-c_{\theta 2}}{c_x}$$

6. Dimensionless flow and pressure coefficients:

   $$\phi = \frac{Q}{\omega D^3}, \qquad \psi = \frac{\Delta p_0}{\rho\omega^2D^2}$$

7. Power estimation:

   $$P_{\mathrm{air}} = Q\Delta p_0, \qquad P_{\mathrm{shaft}} = \frac{P_{\mathrm{air}}}{\eta}$$


### Preliminary results

For the selected nominal flow rate, using the SPAL reference dimensions and a rotational speed of 1500 rpm:

| Quantity | Preliminary result |
|----------|-------------------|
| Tip diameter $D$ | 0.385 m |
| Hub diameter $D_h$ | 0.128 m |
| Annulus area $A$ | 0.10355 m² |
| Angular speed $\omega$ | 157.08 rad/s |
| Axial velocity $c_x$ | 7.62 m/s |
| Mean radius $r_m$ | 0.1434 m |
| Blade speed $U_m$ (mean) | 22.53 m/s |
| Blade speed $U_{\mathrm{tip}}$ | 30.24 m/s |
| Flow coefficient $\phi$ | 0.0880 |
| Pressure coefficient $\psi_s$ | 0.0228 |
| Pressure power $Q\Delta p_s$ | 78.9 W |


### 2.2 Geometry description of all parts of the axial fan

### 2.3 Materials and characteristics

### 2.4 Mean line analysis


## 3. CFD

### 3.1 CAD description

### 3.2 Mesh description

### 3.3 Boundary conditions


## 4. Experimentation

### 4.1 Relevant variables of the axial fan

### 4.2 Proposed instrumentation for measuring and data acquisition

### 4.3 ISO 5801:2019 application to the axial fan
