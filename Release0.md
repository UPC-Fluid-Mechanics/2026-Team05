
# Release 0 – Team 5

**Design of an Axial Fan for a Car Radiator**

## 1. Team

| Name | Role | GitHub username |
|------|------|-----------------|
| Emma | Design | emamandelbaum |
| Romane | CFD | romanedaguin |
| Filippo | Experimentation | FilippoRossi37 |

## 2. Project description

The objective of this project is to design an axial fan for a car radiator and to evaluate its performance using CFD. The work is organised in three parts: preliminary design (mean-line sizing), detailed design of the blades, and numerical validation of the resulting geometry.

## 3. Applications
- Automotive engine cooling

## 4. Reference designs

- Ambdekar et al. (2014), *Design and Analysis of Engine Cooling Fan* – [201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf](201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf)
- Elhaj et al. (2024), *CFD Modeling of a Radiator Axial Fan for Air Flow* – [CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf](CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf)
- Pereira et al. (2021), *Improved Aerodynamics of a Hollow-Blade Axial Flow* – [Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf](Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf)

## 5. Target specifications

| Parameter | Target range |
|-----------|--------------|
| Flow rate $Q$ | 0.5 – 2.5 m³/s |
| Pressure rise $\Delta p_0$ | 1000 – 1200 Pa |
| Rotational speed $N$ | 1500 – 2500 rpm (about 2000 rpm) |

## 6. Preliminary design calculations

Preliminary calculation based on the course notebook D1 (fundamentals and dimensional analysis)

### 6.1 Assumptions

The values below are not part of the specification. They are standard engineering values taken from general knowledge

| Symbol | Value | Meaning |
|--------|-------|---------|
| $\rho$ | 1.2 kg/m³ | Air density (about 20 °C) |
| $\nu = D_h/D$ | 0.30 | Hub-to-tip ratio (typical range 0.3 – 0.4) |
| $\eta$ | 1 | Total efficiency of ideal machine |
| $\Delta p_0$ | 1100 Pa | Middle of the specified range |
| $N$ | 2500 rpm | Upper end of the range (see 6.4) |

### 6.2 Method

1. Angular speed:

   $$\omega = \frac{2\pi N}{60}$$

2. Specific speed, then the specific diameter $D_s$ read on the Cordier diagram (rough guide in this range: $D_s \approx 2.7/\sqrt{\Omega_s}$, our own approximation, to be checked on the diagram):

   $$\Omega_s = \frac{\omega\, Q^{1/2}}{(\Delta p_0/\rho)^{3/4}}, \qquad D = \frac{D_s\, Q^{1/2}}{(\Delta p_0/\rho)^{1/4}}$$

3. Annulus area and axial velocity:

   $$A = \frac{\pi}{4}\left(D^2 - D_h^2\right), \qquad c_x = \frac{Q}{A}$$

4. Mean radius and blade speed:

   $$r_m = \sqrt{\tfrac{1}{2}\left(r_h^2 + r_t^2\right)}, \qquad U = \omega\, r_m$$

5. Euler equation with axial inlet flow ($c_{\theta 1} = 0$). The ideal pressure rise is $\rho U c_{\theta 2}$ and the real rise is $\eta_h$ times that. The value with $\eta = 1$ is also given, as requested in D1 for a first estimate:

   $$c_{\theta 2} = \frac{\Delta p_0}{\eta_h\, \rho\, U}$$

6. Flow angles at the mean radius:

   $$\tan\beta_1 = \frac{U}{c_x}, \qquad \tan\beta_2 = \frac{U - c_{\theta 2}}{c_x}$$

7. Coefficients:

   $$\phi = \frac{Q}{\omega D^3}, \qquad \psi = \frac{\Delta p_0}{\rho\,\omega^2 D^2}$$

8. Power:

   $$P_{air} = Q\,\Delta p_0, \qquad P = \frac{P_{air}}{\eta}$$

### 6.3 Results

Three flow rates inside the specified range, all at 1100 Pa and 2500 rpm. Values are rounded.

| Quantity | Q = 1.0 m³/s | Q = 1.5 m³/s | Q = 2.5 m³/s |
|----------|--------------|--------------|--------------|
| Tip diameter $D$ | 0.40 m | 0.46 m | 0.50 m |
| Hub diameter $D_h$ | 0.12 m | 0.14 m | 0.15 m |
| Axial velocity $c_x$ | 8.7 m/s | 9.9 m/s | 14.0 m/s |
| Blade speed $U$ (mean / tip) | 38.7 / 52.4 m/s | 44.5 / 60.2 m/s | 48.3 / 65.4 m/s |
| Outlet swirl $c_{\theta 2}$ ($\eta_h = 0.75$ / $\eta = 1$) | 23.7 m/s | 20.6 m/s | 19.0 m/s |
| Flow angles $\beta_1$ / $\beta_2$ | 77° / 39° | 77° / 60° | 74° / 59° |
| Relative velocity ratio $w_2/w_1$ | 0.28 | 0.43 | 0.54 |
| $\phi$ / $\psi$ | 0.060 / 0.084 | 0.059 / 0.063 | 0.076 / 0.053 |
| $\Omega_s$ / $D_s$ | 1.57 / 2.20 | 1.92 / 2.07 | 2.48 / 1.74 |
| Air power $P_{air} = Q\,\Delta p_0$ | 1.1 kW | 1.65 kW | 2.75 kW |
| Shaft power ($\eta \approx 0.65$) / torque | 1.7 kW / 6.4 N·m | 2.5 kW / 9.7 N·m | 4.2 kW / 16.1 N·m |

## 7. Team's work regulations
- One meeting per week.
- Discussion on a WhatsApp group when needed (information exchange, meeting time, questions).
