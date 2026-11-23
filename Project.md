
# Release 1 – Team 5

**Design of an Axial Fan for a Car Radiator**

## 1. Introduction

The objective of this project is to design an axial fan for a car radiator and to evaluate its performance using CFD. The work is organised in three parts: preliminary design (mean-line sizing), detailed design of the blades, and numerical validation of the resulting geometry.

### 1.1 Reference designs

- Ambdekar et al. (2014), *Design and Analysis of Engine Cooling Fan* – [201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf](References/201314DesignandAnalysisofEngineCoolingFan-Tushar.pdf)
- Elhaj et al. (2024), *CFD Modeling of a Radiator Axial Fan for Air Flow* – [CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf](References/CFD_MODELING_OF_A_RADIATOR_AXIAL_FAN_FOR_AIR_FLOW_.pdf)
- Pereira et al. (2021), *Improved Aerodynamics of a Hollow-Blade Axial Flow* – [Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf](References/Improved_Aerodynamics_of_a_Hollow-Blade_Axial_Flow-1.pdf)
- SPAL VA18-AP71/LL-59A, Commercial 12 V automotive axial fan - [VA18-AP71-LL-59A-42S.pdf](References/VA18-AP71-LL-59A-42S.pdf)
- Domo PA66 technical informations - [Domo PA66  TECHNYL A 218 V30 BK 34NG.pdf](References/Domo PA66  TECHNYL A 218 V30 BK 34NG.pdf)

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
| Annulus area $A$ | 0.10355 m² |
| Angular speed $\omega$ | 157.08 rad/s |
| Axial velocity $c_x$ | 7.62 m/s |
| Mean radius $r_m$ | 0.1434 m |
| Blade speed $U_m$ (mean) | 22.53 m/s |
| Blade speed $U_{\mathrm{tip}}$ | 30.24 m/s |
| Flow coefficient $\phi$ | 0.0880 |
| Pressure coefficient $\psi$ | 0.0228 |
| Pressure power $Q\Delta p$ | 78.9 W |


### 2.2 Geometry description of all parts of the axial fan
| Geometry | Preliminary result |
|----------|-------------------|
| Tip diameter $D$ | 0.385 m |
| Hub diameter $D_h$ | 0.128 m |
| Number of blades | 8 |
| Inlet relative angle $\beta_1$ | 71.32 deg |
| Outlet relative angle $\beta_2$ | 67.97 deg |

The axial fan geometry is based on the dimensions of the commercial SPAL VA18-AP71/LL-59A fan.
The fan has an external diameter of 385 mm and a hub diameter of approximately 128 mm.
The preliminary design has eight blades distributed uniformly around the hub.
The blade inlet and outlet angles are determined from the preliminary velocity triangle analysis at the mean radius. 

### 2.3 Materials and characteristics

The fan blades can be made of PA66-GF30 (30% glass fibre reinforced polyamide 66). This material is commonly used in automotive applications, including cooling fans. It offers good mechanical strength, stiffness and thermal resistance, making it suitable for the operating conditions of an automotive radiator fan.
The material is chsoen according to the technical information provided by [DOMO Chemicals – TECHNYL](https://www.domochemicals.com/).

### 2.4 Mean line analysis

| Quantity | Preliminary result |
|----------|-------------------|
| Diffusion factor $DF$ | 0.40 |
| Drag coefficient $C_D$ | 0.02 |
| Pitch chord ratio $s/l$ | 3.2592  |
| Pitch $s$ | 112.6261 mm |
| Minimum chord $l_{min}$ | 34.5560 mm |
| Chord for CL=1 | 35.9235 mm |
| Camber angle  $\theta$ |  9.8717 deg |
| Deviation angle $\delta$ | 6.5217 deg |
| Stagger angle $\xi$ | 72.9058 deg |

The mean line analysis is performed to obtain a preliminary aerodynamic design of the axial fan. 
The blade geometry is characterised using aerodynamic parameters such as the diffusion factor, drag coefficient and pitch-to-chord ratio.
The diffusion factor provides an indication of the aerodynamic loading and the risk of flow separation on the blade suction side and the pitch-to-chord ratio describes the spacing between adjacent blades relative to their chord length.
These results represent a preliminary design and will be refined through the CFD analysis.

## 3. CFD

### 3.1 CAD description

The 3D geometry of the axial fan will be designed using the methodology presented in the C4 course session. The CAD model consists of a central hub and eight uniformly distributed blades.
The blade geometry is based on the preliminary parameters obtained in the design part.
The main geometrical dimensions are based on the selected SPAL reference: an external diameter of 385 mm and a hub diameter of 128 mm.

### 3.2 Mesh description

The computational domain is discretised using a three-dimensional mesh. It has to be refined near the blade surfaces, leading and trailing edges.
We will use Simscale for the mesh generation. Local mesh refinement is required in regions with strong velocity and pressure gradients to capture the main aerodynamic features of the flow.

### 3.3 Boundary conditions

Air is defined as the working fluid. The rotor is modelled using a rotating reference frame (MRF), with a rotational speed of 1500 rpm. The hub, blades and casing are defined as no-slip walls. 
A pressure driven configuration is adopted, with a total pressure inlet of 0 Pa and a static pressure outlet of 0 Pa.
The simulation will be used to analyse the velocity and pressure fields and to evaluate the aerodynamic performance of the designed rotor.

## 4. Experimentation

To characterise and evaluate fan performance in accordance with ISO 5801 and AMCA 210, a set of primary variables must be recorded on the test bench and the corresponding derived quantities computed. These are grouped below into ambient conditions and fluid properties, machine operating quantities, and synthetic indicators and dimensionless parameters.

### 4.1 Relevant Variables of the Axial Fan

*Table 1a. Ambient conditions and fluid properties*

| Quantity | Symbol | Unit | How obtained / Notes |
|---|---|---|---|
| Barometric pressure | $P_a$ | Pa | Measured in the test environment with an absolute barometer |
| Air temperature | $T_a$ | K | Measured at the fan inlet |
| Air density | $\rho$ | kg/m³ | Computed from the ideal-gas equation of state: $\rho = P_a / (R \cdot T_a)$ (1), where $R = 287.05$ J/(kg·K) is the specific gas constant of dry air |
| Dynamic viscosity | $\mu$ | Pa·s | Computed with the linear correlation recommended by ISO 5801:2019 for temperatures between −20 °C and 100 °C: $\mu(T) = (17.1 + 0.048 \cdot T_a) \times 10^{-6}$ (2) |

*Table 1b. Machine operating quantities*

| Quantity | Symbol | Unit | How obtained / Notes |
|---|---|---|---|
| Volumetric flow rate | $Q$ | m³/s | Air flow processed by the machine |
| Mass flow rate | $\dot{m}$ | kg/s | Air flow processed by the machine |
| Static pressure rise | $\Delta p_s$ | Pa | Pressure increase imparted by the fan to the fluid stream |
| Total pressure rise | $\Delta p_0$ | Pa | Pressure increase imparted by the fan to the fluid stream: $\Delta p_0 = \Delta p_s + \tfrac{1}{2}\rho c_2^2$ (3) |
| Rotational speed | $N$ | rpm | Measured on the test bench |
| Angular velocity | $\omega$ | rad/s | $\omega = 2\pi N / 60$ (4) |
| Shaft torque | $M$ | N·m | Resisting torque opposed by the fan rotor |
| Absorbed mechanical power | $P_m$ | W | $P_m = M \cdot \omega$ (5) |

*Table 1c. Synthetic indicators and dimensionless parameters*

| Quantity | Symbol | Unit | Formula | Notes |
|---|---|---|---|---|
| Specific mechanical energy | $Y$ | J/kg | $Y = \Delta p_0 / \rho$ (6) | – |
| Mechanical (overall) efficiency | $\eta$ | – | $\eta = \dfrac{\Delta p_0 \cdot Q}{P_m} = \dfrac{\Delta p_0 \cdot Q}{M \cdot \omega}$ (7) | – |
| Flow coefficient | $\varphi$ | – | $\varphi = c_x / U$ (8) | $c_x$ = axial velocity; $U$ = blade peripheral speed |
| Loading (pressure) coefficient | $\psi$ | – | $\psi = \Delta p_0 / (\rho U^2)$ (8) | $U$ = blade peripheral speed |

### 4.2 Proposed Instrumentation for Measurement and Data Acquisition

The measurement chain follows the standard logical flow: physical sensor → analogue transducer → data acquisition (DAQ) system → post-processing and error analysis (Figure 1).

```text
Physical sensor  →  Analogue transducer  →  DAQ board                →  Processing
                                            (e.g. National Instruments)   (Python / PC)
```

*Figure 1. Measurement and data acquisition chain.*

The instruments proposed for each physical quantity, together with their technical specifications and the rationale for their selection, are listed in Table 2.

| Physical quantity | Proposed device / sensor | Specifications and rationale |
|---|---|---|
| Volumetric flow rate, $Q$ | Bellmouth inlet nozzle | Installed at the intake of the plenum chamber. The bellmouth offers a high discharge coefficient ($C_d \approx 0.98$) and minimal pressure loss, avoiding throttling of the flow at high flow rates (0.5-2.5 m³/s). |
| Differential pressure, $\Delta p$ | WIKA differential pressure transmitter (air2guide A2G-50 or DPT-10/20 series) | High-accuracy piezoresistive sensor for low differential pressures in air. Selectable full scale 0–250 Pa or 0–500 Pa; analogue output 4–20 mA or 0–10 V. The selected range must be verified against the design pressure rise ($\Delta p_0 \approx$ 100–120 Pa). |
| Static pressure taps | Wall static taps | Holes normal to the chamber wall, small diameter ($d < 1.5$ mm) with burr-free edges to avoid recirculation or parasitic vortices in the cavity that would alter the measurement ($L/d < 1.5$). |
| Temperature, $T_a$ | Pt100 resistance thermometer (or Type T/K thermocouple) | High-accuracy sensor (±0.1 °C) placed in the intake flow to continuously correct air density and viscosity. |
| Rotational speed, $N$ | Laser optical tachometer / incremental encoder | Contactless speed detection on the shaft, so as not to introduce parasitic friction in the torque measurement. |
| Torque, $M$ | Strain-gauge dynamic torque transducer | Flanged between the driving electric motor and the fan shaft. |
| Data acquisition (DAQ) | Multifunction DAQ board (e.g. National Instruments / Modbus) | Converts analogue signals into digital inputs, which are distributed and processed in Python. |

*Table 2. Proposed instrumentation*

### 4.3 Application of ISO 5801:2019 to the Axial Fan

#### 4.3.1 Test Rig Layout: Plenum Chamber Configuration

For a low-pressure, high-flow axial fan, the most suitable standardised configuration according to ISO 5801:2019 is the plenum-chamber test rig on the inlet side (Installation Category A or C). The layout is shown schematically in Figure 2.

```text
Ambient → Bellmouth → Plenum chamber    → Fan under test → Blast gate  → Exhaust
                      (honeycomb grid)    (axial fan unit)   (throttle)
```

*Figure 2. Schematic layout of the plenum-chamber test rig.*

The main elements of the rig are:

- **Air inlet:** ambient air enters the chamber through the bellmouth inlet nozzle.
- **Plenum chamber:** a large rectangular or circular volume with an area ratio greater than 10:1 with respect to the fan duct.
- **Flow conditioner (flow straightener / honeycomb):** turbulence-breaking grids and honeycomb straighteners installed inside the plenum damp inlet vortices and ensure a uniform velocity profile at the fan inlet.
- **Fan under test:** the radiator axial fan is flanged onto the outlet wall of the plenum.
- **Load regulation (blast gate / throttle valve):** a throttling damper at the discharge varies the circuit resistance, allowing the full characteristic curve to be measured from maximum flow (free delivery) to the blocked / stall condition.

### 4.3.2 Performance Correction and Scaling (Similarity)

Because the motor speed may vary slightly under load during the test, ISO 5801 requires all measured points to be rescaled to a constant reference speed $N_0$ by means of the similarity relations:

$$
Q_0 = Q \cdot \frac{N_0}{N} \qquad \text{(9)}
$$

$$
Y_0 = Y \cdot \left(\frac{N_0}{N}\right)^{2} \qquad \text{(10a)}
$$

$$
\Delta p_{0,0} = \Delta p_0 \cdot \left(\frac{N_0}{N}\right)^{2} \qquad \text{(10b)}
$$

$$
P_{m,0} = P_m \cdot \left(\frac{N_0}{N}\right)^{3} \qquad \text{(11)}
$$

$$
\eta_0 = \eta \qquad \text{(12)}
$$

Equation (10b) follows from (10a) since $Y = \Delta p_0 / \rho$ and the density is unchanged by the rescaling. Equation (12) states that the efficiency is invariant under the rescaling.

Rescaled points are then used to build the performance curves of the fan at the reference speed: total pressure rise $\Delta p_0$ versus $Q$, absorbed power $P_m$ versus $Q$, and efficiency $\eta$ versus $Q$.
