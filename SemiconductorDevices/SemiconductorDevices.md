- [Fundamentals of Semiconductor Devices](#fundamentals-of-semiconductor-devices)
  - [Introduction to semiconductors](#introduction-to-semiconductors)
  - [Energy bands](#energy-bands)
  - [Types of Semiconductors](#types-of-semiconductors)
    - [Doping](#doping)
  - [Band Structure](#band-structure)
    - [Band structure \& fermi–dirac distribution](#band-structure--fermidirac-distribution)
    - [Density of states (DOS)](#density-of-states-dos)
    - [Equilibrium carrier concentration](#equilibrium-carrier-concentration)
    - [Temperature dependence](#temperature-dependence)
    - [High doping \& incomplete ionization](#high-doping--incomplete-ionization)
    - [Carrier scattering \& mobility](#carrier-scattering--mobility)
    - [Low \& high field transport](#low--high-field-transport)
    - [Drift–diffusion \& traps](#driftdiffusion--traps)
    - [Charge transport](#charge-transport)
    - [Continuity equation](#continuity-equation)
  - [PN Junction](#pn-junction)
    - [Biasing of PN Junction](#biasing-of-pn-junction)
    - [Depletion Region \& Built-in Potential](#depletion-region--built-in-potential)
    - [Breakdown Mechanisms](#breakdown-mechanisms)
    - [Types:](#types)
  - [Applications of PN Junction](#applications-of-pn-junction)
    - [Rectifier (Diode)](#rectifier-diode)
    - [LED (Light Emitting Diode)](#led-light-emitting-diode)
    - [Photodetector (Photodiode)](#photodetector-photodiode)
    - [Solar Cell](#solar-cell)
  - [Schottky Junction (Metal–Semiconductor Junction)](#schottky-junction-metalsemiconductor-junction)
    - [Formation \& Barrier](#formation--barrier)
    - [Operation](#operation)
    - [Key Characteristics](#key-characteristics)
    - [Advantages](#advantages)
    - [Limitations](#limitations)
  - [Transistors](#transistors)
    - [Key Functions / Applications](#key-functions--applications)
    - [Types of Transistors](#types-of-transistors)
  - [Bipolar Junction Transistor](#bipolar-junction-transistor)
    - [BJT Operation](#bjt-operation)
  - [MOSFET](#mosfet)
    - [MOS (Metal-oxide-semiconductor) CAPACITOR](#mos-metal-oxide-semiconductor-capacitor)
    - [MOSFET definition](#mosfet-definition)
    - [Relation to MOS Capacitor](#relation-to-mos-capacitor)
    - [Operation of MOSFET (nMOS example)](#operation-of-mosfet-nmos-example)
    - [Key Physical Insight](#key-physical-insight)
    - [Important Parameters](#important-parameters)
  - [Compound Semiconductors](#compound-semiconductors)
    - [Key Properties](#key-properties)
    - [Comparison with Silicon](#comparison-with-silicon)
    - [Applications](#applications)
  - [Solar Cells](#solar-cells)
    - [Working Principle](#working-principle)
    - [Loss Mechanisms](#loss-mechanisms)
    - [Types of Solar Cells](#types-of-solar-cells)
  - [Photodetectors](#photodetectors)
    - [Working Principle](#working-principle-1)
    - [Types of Photodetectors](#types-of-photodetectors)
    - [Key Performance Parameters](#key-performance-parameters)
    - [Important Concepts](#important-concepts)
      - [Photodetectors vs Solar Cells](#photodetectors-vs-solar-cells)
  - [Recombination in LEDs](#recombination-in-leds)
    - [Types of Recombination](#types-of-recombination)
    - [Key Concepts](#key-concepts)
  - [LED (Light Emitting Diode)](#led-light-emitting-diode-1)
    - [Operation Principle](#operation-principle)
    - [Key Concepts](#key-concepts-1)
    - [Important Factors Affecting LED Performance](#important-factors-affecting-led-performance)
  - [Advanced transistors](#advanced-transistors)
    - [Transistors for Power Electronics](#transistors-for-power-electronics)
      - [Key Requirements](#key-requirements)
      - [Operation Principle](#operation-principle-1)
      - [Types of Power Transistors](#types-of-power-transistors)
      - [Loss Mechanisms](#loss-mechanisms-1)
    - [Transistors for Memory](#transistors-for-memory)
      - [What are Memory Transistors?](#what-are-memory-transistors)
      - [Operation Principle](#operation-principle-2)
      - [Types of Memory Transistor Structures](#types-of-memory-transistor-structures)
  - [Microelectronic Fabrication](#microelectronic-fabrication)
    - [Key Process Steps](#key-process-steps)
    - [Supporting Processes](#supporting-processes)
    - [Challenges](#challenges)
  - [Books and references](#books-and-references)

--- 

# Fundamentals of Semiconductor Devices

---

## Introduction to semiconductors
- Semiconductors are materials whose electrical conductivity lies between conductors and insulators and can be controlled using doping, temperature, and electric fields.
- They form the foundation of modern electronic devices such as diodes, transistors, and integrated circuits.
- Conduction occurs via two types of charge carriers: **electrons (negative)** and **holes (positive)**.
- Silicon (Si) is the most widely used semiconductor due to its stability and ease of fabrication.
- Their behavior is governed by quantum mechanics and band theory.

**Moore’s Law** states that the number of transistors on an integrated circuit doubles approximately every 18–24 months(~1.5-2 years), leading to exponential growth in computing power.
- This scaling results in higher performance, lower cost per transistor, and increased device density.
- However, physical and thermal limits are slowing down this trend in modern technologies.

---

## Energy bands
- In crystals, atomic energy levels combine to form continuous bands due to interaction between atoms.
- Energy Bands are ranges of allowed electron energies formed due to atomic orbital overlap in a crystal lattice.
- Electrons occupy energy bands: **valence band (VB)** and **conduction band (CB)**.
- Valence Band: Electron rich bands, holds bound electrons
- Conduction Band: Electron deficient bands, allows free electron movement
- The **bandgap (E₉)** is the energy difference between VB and CB.
- Small bandgap allows electrons to move to CB and conduct electricity.
- Insulators have large bandgap, while conductors have overlapping bands. Semiconductors have Moderate & achievable bandgap.
- Band structure determines electrical and optical properties.
- Holes: Absence of electrons
- Fermi level: Shows probability of finding electronics along the energy band gap

---

## Types of Semiconductors
- **Intrinsic Semiconductors**: Pure materials with equal electron and hole concentration ($ n = p = n_i $).
- Intrinsic semiconductor (extremely pure): Materials which have exactly same holes and electrons or Fermi level sits exactly in the middle
- **Extrinsic Semiconductors**: Doped materials with controlled carrier concentration.

### Doping
- **Doping** is a process of adding impurities (either holes of electrons) to the intrinsic semiconductor to make it either n-type or p-type semiconductor
- This process is inherent only to the semiconductors. This cannot be done to conductors or insulators.
  - Eg. Adding Boron or Phosphorus can be added to the Si lattice
- Doping introduces donors (n-type) or acceptors (p-type). Based on these, we get 2 types of Extrinsic Semiconductors:
  - **n-type semiconductor**: Materials which have more electrons than holes or Fermi level is in the upper half
  - electrons are majority carriers in n-type semiconductors.
  - **p-type semiconductor**: Materials which have more holes than electrons or Fermi level is in the lower half
  - holes are majority carriers in p-type semiconductors.
- Doping enables control over conductivity.
- Doping enables control of electrical properties.
- Small doping significantly increases conductivity.
- Intrinsic carrier concentration depends on temperature and bandgap.

---

## Band Structure

### Band structure & fermi–dirac distribution
- Fermi–Dirac distribution gives the probability of an energy state being occupied:
$$
 f(E) = \frac{1}{1 + e^{(E - E_F)/kT}} 
$$
- At $ T = 0K $, all states below $ E_F $ are filled and above are empty (step-like distribution).
- At finite temperature, electrons get thermally excited to higher energy states, smoothing the distribution.
- Fermi level shifts with doping: toward conduction band (n-type) and toward valence band (p-type).
- It directly determines electron and hole concentrations in semiconductors.

### Density of states (DOS)
- Density of states (DOS) represents the number of available energy states per unit energy per unit volume.
- In 3D semiconductors, DOS increases as $$ \sqrt{E - E_c} $$ above the conduction band edge.
- Carrier concentration is obtained by combining DOS with the Fermi–Dirac distribution.
- DOS depends on effective mass and dimensionality of the system.
- It is essential for calculating electron and hole populations in materials.

### Equilibrium carrier concentration
- At thermal equilibrium, carrier concentrations follow: 
$$
 np = n_i^2 
$$
- Charge neutrality ensures total positive and negative charges are balanced.
- Majority carriers are approximately equal to dopant concentration.
- Minority carriers are derived from intrinsic relations.
- Fermi level position uniquely determines equilibrium carrier densities.

### Temperature dependence
- Intrinsic carrier concentration increases exponentially with temperature:
$$
 n_i \propto e^{-E_g/2kT} 
$$
- Three regions: freeze-out (low T), extrinsic (moderate T), intrinsic (high T).
- At high temperatures, intrinsic carriers dominate over dopants.
- Mobility decreases with temperature due to increased phonon scattering.
- Temperature strongly impacts device behavior and reliability.

### High doping & incomplete ionization
- Heavy doping leads to **degenerate semiconductors**, where Fermi level enters a band.
- Bandgap narrowing occurs due to interaction between closely spaced dopants.
- At low temperatures, dopants may not fully ionize (incomplete ionization).
- Carrier concentration deviates from simple doping assumptions.
- Critical in heavily doped regions like MOSFET source/drain.

### Carrier scattering & mobility
- Mobility defines how easily carriers move under an electric field:
$$
 \mu = \frac{q\tau}{m^*} 
$$
- Scattering mechanisms include phonon (lattice) scattering and impurity scattering.
- Higher temperature increases phonon scattering, reducing mobility.
- Higher doping increases impurity scattering, also reducing mobility.
- Mobility directly affects conductivity and switching speed of devices.

### Low & high field transport
- At low electric fields, carrier velocity is proportional to electric field (Ohm’s law).
- At high fields, velocity saturates due to increased scattering.
- Velocity saturation limits current in short-channel devices.
- High-field effects cause deviation from linear transport models.
- Important for modern nanoscale transistor design.

### Drift–diffusion & traps
- Drift current arises due to electric field:
$$
 J_{drift} = q n \mu E 
$$
- Diffusion current arises due to carrier concentration gradient:
$$
 J_{diff} = q D \frac{dn}{dx} 
$$
- Einstein relation links diffusion and mobility:
$$
 \frac{D}{\mu} = \frac{kT}{q} 
$$
- Trap states capture carriers and influence recombination and leakage.
- Traps introduce non-ideal behavior such as reduced carrier lifetime.

### Charge transport
- Total current is the sum of drift and diffusion currents.
- Drift dominates under strong electric fields; diffusion dominates under concentration gradients.
- Both electrons and holes contribute to current flow.
- Carrier mobility determines how quickly carriers respond to applied fields.
- These mechanisms form the basis of all semiconductor device operation.

### Continuity equation
- Ensures conservation of charge:
$$
 \frac{\partial n}{\partial t} = G - R + \frac{1}{q} \nabla J 
$$
- Accounts for generation (G), recombination (R), and current flow (J).
- Used for both steady-state and transient analysis of devices.
- Fundamental equation in semiconductor device modeling and simulation.
- Connects microscopic carrier dynamics to measurable electrical current.

---

## PN Junction

- A PN junction is formed by joining **p-type (hole-rich)** and **n-type (electron-rich)** semiconductor regions.
- Due to carrier concentration difference, electrons (from n-side) and holes (from p-side) **diffuse across the junction**.
- This diffusion leaves behind fixed ionized charges, forming a **depletion region** with no mobile carriers.
- An internal **electric field (built-in potential)** is created, which opposes further diffusion.
- At equilibrium, drift and diffusion currents balance, resulting in **zero net current**.
- The junction has a field and prevents the current from flowing with no field applied across the semiconductors.

### Biasing of PN Junction
1. Forward Bias
- p-side connected to positive terminal, n-side to negative terminal.
- Reduces barrier potential and narrows depletion region.
- Allows majority carriers to cross the junction easily.
- Results in **large exponential current flow**:
$$
 I = I_s (e^{V/V_T} - 1) 
$$
- Turn-on voltage (~0.7V for Si) is required to significantly conduct.

2. Reverse Bias
- p-side connected to negative terminal, n-side to positive terminal.
- Increases barrier potential and widens depletion region.
- Prevents majority carrier flow.
- Only small **reverse saturation current** flows due to minority carriers.
- Acts like an insulator under normal conditions.

### Depletion Region & Built-in Potential
- The depletion region acts as a **barrier** preventing free carrier movement.
- Built-in potential $ V_{bi} $ depends on doping levels:
$$
 V_{bi} \propto \ln\left(\frac{N_A N_D}{n_i^2}\right) 
$$
- Width of depletion region changes with applied voltage.
- This region is crucial for controlling current flow in the device.
- Acts like an insulating layer between p and n regions.
- When voltage is applied, it takes some voltage to overcome the depletion region before current starts flowing. This is called as turn on voltage.
- The semiconductor becomes operational when more voltage is applied than turn on voltage.

### Breakdown Mechanisms
- At high reverse voltage, junction undergoes **breakdown**, causing large current.

### Types:
- **Zener (Tunneling) Breakdown**
  - Occurs in heavily doped junctions at low voltage.
  - Strong electric field enables quantum tunneling.

- **Avalanche Breakdown**
  - Occurs in lightly doped junctions at high voltage.
  - Carriers gain energy and generate more carriers via collisions.

- Breakdown can damage the device unless properly controlled (e.g., Zener diodes).

---

## Applications of PN Junction

### Rectifier (Diode)
- Converts AC to DC by allowing current in one direction only.
- When connected in Forward Bias, the junction allows the current to flow.
- In Reverse Bias, prevents current flow except for a small leakage current.
- Used in power supplies and electronic circuits.

### LED (Light Emitting Diode)
- An LED (Light Emitting Diode) is a PN junction diode that emits light when forward biased.
- Electrons and holes recombine at the junction, releasing energy as photons (light).
- Emits light when forward biased due to **radiative recombination**.
- Electron-hole recombination releases photons:
$$
  E_{photon} \approx E_g  
$$
- Color depends on semiconductor bandgap.
- Used in displays, lighting, and indicators.

### Photodetector (Photodiode)
- A photodetector is a PN junction device that converts light into electrical current.
- When light photons strike the junction, they generate electron-hole pairs in the depletion region.
- Under reverse bias, these carriers are quickly swept across the junction, producing photocurrent.
- Also can be used in any spectrum: IR, UV, Infrared etc.
- Used in optical communication and sensors.
-
### Solar Cell

- A solar cell is a PN junction device that converts sunlight directly into electrical energy using photovoltaic effect.
- Photons striking the junction create electron-hole pairs, generating current.
- It operates under illumination without external bias, using built-in potential to separate charges.
- Only sunlight is the input spectra.
- Used in renewable energy systems.


---

## Schottky Junction (Metal–Semiconductor Junction)
- A Schottky junction is formed when a **metal is brought into contact with a semiconductor** (typically n-type).
- Instead of a p–n interface, it creates a **metal–semiconductor interface** with unique electrical behavior.
- Charge transfer occurs at the interface, leading to formation of a **Schottky barrier**.
- It is also called a **Schottky diode** when used as a device.

### Formation & Barrier
- When metal and semiconductor come in contact, electrons flow to align their Fermi levels.
- This creates a **depletion region in the semiconductor side only** (not in the metal).
- A potential barrier called the **Schottky barrier height ($ \phi_B $)** is formed.
- Barrier height depends on **metal work function and semiconductor properties**.
- The built-in electric field prevents further carrier diffusion at equilibrium.

### Operation

1. Forward Bias
- Reduces the barrier height at the interface.
- Majority carriers (electrons in n-type) easily cross into the metal.
- Results in **low forward voltage drop (~0.2–0.3 V)** compared to silicon PN diodes (~0.7 V).
- Current increases rapidly with applied voltage.

2. Reverse Bias
- Increases barrier height and widens depletion region.
- Prevents majority carrier flow.
- Only small leakage current flows (higher than PN junction).
- No significant charge storage occurs.

### Key Characteristics
- **Majority carrier device** → no minority carrier storage.
- **Fast switching speed** due to absence of charge storage.
- **Low forward voltage drop** → lower conduction losses.
- **Higher reverse leakage current** compared to PN junction.
- Barrier properties depend on **choice of metal**.

### Advantages
- High-speed operation (ideal for RF and switching circuits).
- Low power loss due to low forward voltage.
- Simple structure compared to PN junction.

### Limitations
- Higher reverse leakage current.
- Lower breakdown voltage compared to PN diodes.
- Sensitive to temperature variations.

---

## Transistors
- A transistor is a **three-terminal semiconductor device** used to control current flow and signal behavior.
- It operates by using a **small input signal** to control a much larger current between two terminals.
- The three terminals depend on type of transistor:
  - BJT: Emitter, Base, Collector
  - FET: Source, Gate, Drain
- Transistors are the **fundamental building blocks** of modern electronic circuits.

### Key Functions / Applications
- **Switch**: Turns current ON/OFF (used in digital circuits).
- **Amplifier**: Increases signal strength (analog circuits).
- **Digital Logic**: Forms logic gates and processors (CMOS technology).
- **Sensors**: Used in sensing circuits and signal conditioning.
- **Memory**: Stores data in SRAM, DRAM, and Flash technologies.

### Types of Transistors

1. Field Effect Transistor (FET)
- A **voltage-controlled device** where current is controlled by an electric field at the gate.
- Terminals: **Source, Gate, Drain**.
- Gate voltage controls the conductivity of the channel between source and drain.
- Very high input impedance (almost no gate current).
- Examples: **MOSFET, JFET** → widely used in digital electronics.

2. Bipolar Junction Transistor (BJT)
- A **current-controlled device** that uses both electrons and holes (bipolar conduction).
- Terminals: **Emitter, Base, Collector**.
- A small base current controls a large collector current (current amplification).
- Types: **NPN and PNP transistors**.
- Used in amplification and analog circuits.

---

## Bipolar Junction Transistor
- A BJT (Bipolar Junction Transistor) is a three-terminal semiconductor device (emitter, base, collector) that can amplify or switch signals.
- It uses both electrons and holes as charge carriers, hence the term "bipolar".
- **Base (B)**  Thin, lightly doped region that controls carrier flow from emitter to collector by regulating recombination.
- **Emitter (E)**  Heavily doped region that injects majority carriers into the base.
- **Collector (C)**  Moderately doped region that collects carriers from the base and delivers output current.
- **Currents from E, B, C** : Emitter current splits into base and collector currents:
  $ I_E = I_B + I_C $

- **Gain (Current Gain)** : Ability of BJT to amplify current, defined as ratio of collector current to base current:
  $$ \beta = \frac{I_C}{I_B} $$

- **Beta (β)** : Common-emitter current gain representing amplification capability of the transistor:
  $$ \beta = \frac{I_C}{I_B} $$

- **Base Transport Factor (αₜ)** : Fraction of carriers injected from emitter that successfully reach the collector through the base:
  $$ \alpha_T = \frac{I_C}{I_E'} $$

- **Emitter Injection Efficiency (γ)** : Fraction of emitter current that contributes to useful carrier injection:
  $$ \gamma = \frac{\text{electron injection}}{\text{total emitter current}} $$

- **Transport Ratio / Common-base Gain (α)** : Fraction of emitter current that becomes collector current:
  $$ \alpha = \frac{I_C}{I_E} $$

- **Important Relation** : $$ \beta = \frac{\alpha}{1 - \alpha} $$

### BJT Operation
- When a small positive voltage is applied to the base relative to the - emitter, electrons are injected from the emitter into the base.
- These electrons cross the thin base region and are collected by the - collector, creating a large collector current.
- Thus, a small base current controls a much larger collector-emitter current, enabling amplification or switching.
- Emmiter-Base junction is placed in forward bias & Base-Collector is placed in reverse bias.
- A small current at the base controls a much larger current between collector and emitter.
- For best BJT operation & improving gain, Beta & other parameters, base should be narrow & lightly doped.

- BJTs has 2 types:
  1. NPN: An NPN transistor has an n-type emitter, p-type base, and n-type - collector.
  2. PNP: An PNP transistor has an p-type emitter, n-type base, and p-type - collector.

---

## MOSFET

### MOS (Metal-oxide-semiconductor) CAPACITOR
- A MOS capacitor consists of a Metal–Oxide–Semiconductor structure where the oxide acts as an insulator and the gate voltage controls charge at the semiconductor surface.
- Semiconductor can be p-type or n-type doped.
- Applying a gate voltage changes the surface potential, causing redistribution of carriers near the oxide-semiconductor interface.
- Depending on gate voltage polarity and magnitude, the device operates in accumulation, depletion, or inversion.
- No current flows through the oxide (ideal case); only charge rearrangement occurs.
- MOS capacitor behavior is fundamental to understanding MOSFET operation.

- Accumulation: Occurs when gate voltage attracts majority carriers to the surface, increasing carrier concentration near the interface.

- Depletion: Occurs when gate voltage repels majority carriers, leaving behind fixed ionized charges and forming a depletion region.

- Inversion: Occurs when sufficient gate voltage attracts minority carriers, forming a conductive channel at the surface.

- Threshold Voltage $V_T$: The gate voltage at which strong inversion begins and a conducting channel is formed.

### MOSFET definition
- A MOSFET (Metal–Oxide–Semiconductor Field-Effect Transistor) is a three-terminal device (Gate, Source, Drain) where current between source and drain is controlled by gate voltage.
- It is derived from the MOS capacitor by adding two heavily doped regions (source and drain) in the semiconductor.
- The gate voltage controls the formation of a conductive channel at the semiconductor surface.
- It is a voltage-controlled device with very high input impedance due to the insulating oxide.
- MOSFETs are the fundamental building blocks of modern digital and analog circuits.

### Relation to MOS Capacitor
- The MOSFET structure is essentially a MOS capacitor with source and drain added for current flow.
- The same surface charge control principles (accumulation, depletion, inversion) apply.
- Channel formation in MOSFET occurs under **inversion condition** of MOS capacitor.
- Threshold voltage of MOS capacitor directly determines when MOSFET turns ON.
- Thus, MOSFET operation is an extension of MOS capacitor electrostatics.

### Operation of MOSFET (nMOS example)

1. Cutoff Region (OFF)
- When $ V_{GS} < V_T $, no inversion layer forms and no conduction path exists.
- Only very small leakage current flows.

2. Linear / Triode Region
- When $ V_{GS} > V_T $ and $ V_{DS} $ is small, a continuous channel forms.
- Device behaves like a voltage-controlled resistor.
- Drain current:
$$
  I_D = \mu_n C_{ox} \frac{W}{L} \left[(V_{GS}-V_T)V_{DS} - \frac{V_{DS}^2}{2}\right]  
$$

3. Saturation Region
- When $ V_{DS} \geq (V_{GS} - V_T) $, channel pinches off near drain.
- Current becomes almost independent of $ V_{DS} $.
- Drain current:
$$
  I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS}-V_T)^2
$$

### Key Physical Insight
- Gate voltage controls surface potential → creates inversion layer → forms channel → enables current flow.
- MOSFET current is controlled purely by electric field (no gate current ideally).
- Device transitions from **no channel → resistive channel → pinch-off region** as voltages change.

### Important Parameters
- $ V_T $: Threshold voltage (onset of inversion)
- $$ C_{ox} = \frac{\varepsilon_{ox}}{t_{ox}} $$: Oxide capacitance per unit area
- $ \mu_n $: Carrier mobility
- $ W/L $: Device geometry (width/length ratio)

- Gate voltage controls channel formation.
- Regions: cutoff, linear, saturation.
- Current depends on gate voltage.
- Short-channel effects degrade performance.
- Most important device in digital electronics.

---

##  Compound Semiconductors

- Compound semiconductors are materials formed by combining two or more elements (typically from III–V or II–VI groups) such as GaAs, InP, and GaN.
- They offer superior electronic and optical properties compared to silicon, especially for high-speed and optoelectronic applications.
- Many compound semiconductors have a **direct bandgap**, enabling efficient light emission and absorption.
- Their properties can be engineered by changing composition (e.g., AlGaAs, InGaN).
- Widely used in LEDs, lasers, RF devices, and high-frequency electronics.
- Compound semiconductors enable **high-speed + optical + high-power applications** where silicon falls short.


| Group / Material Type | Example Materials | Key Properties | Typical Applications |
|----------------------|-----------------|---------------|----------------------|
| **III–V Arsenides** | GaAs, AlGaAs | Direct bandgap, high electron mobility, moderate bandgap (~1.4 eV) | RF devices, microwave circuits, LEDs, laser diodes |
| **III–V Phosphides** | InP, GaP | High electron velocity, good thermal stability | High-speed electronics, optical communication, lasers |
| **III–V Nitrides** | GaN, AlGaN, InGaN | Wide bandgap, high breakdown field, high temperature stability | Power electronics, LEDs (blue/white), RF amplifiers |
| **III–V Antimonides** | InSb, GaSb | Very narrow bandgap, very high mobility | Infrared detectors, thermal imaging, sensors |
| **II–VI Semiconductors** | CdS, CdSe, ZnSe | Direct bandgap, strong optical interaction | Photodetectors, LEDs, display technologies |
| **Ternary Compounds** | AlGaAs, InGaN | Tunable bandgap via composition | LEDs, laser diodes, heterostructure devices |
| **Quaternary Compounds** | InGaAsP, AlGaInP | Precise bandgap engineering, lattice matching | Fiber-optic communication, high-efficiency lasers |
| **Heterostructures** | GaAs/AlGaAs, InP/InGaAs | Band offset engineering, carrier confinement | HEMTs, HBTs, high-speed transistors |
| **Wide Bandgap Semiconductors** | GaN, SiC | High breakdown voltage, high temperature operation | Power devices, EV electronics, high-frequency systems |
| **Narrow Bandgap Semiconductors** | InSb, HgCdTe | Sensitive to IR radiation, low energy gap | Infrared photodetectors, night vision systems |

- **Direct bandgap → optoelectronics (LEDs, lasers)**
- **High mobility → high-speed RF devices**
- **Wide bandgap → power electronics**
- **Narrow bandgap → infrared detection**

### Key Properties
- **High electron mobility** → faster carrier transport and high-speed device operation.
- **Direct bandgap (in many materials)** → efficient light emission (used in LEDs and lasers).
- **Wide bandgap (e.g., GaN)** → high power and high-temperature operation.
- **Bandgap engineering** → allows tuning of optical and electrical properties.
- **Heterostructure compatibility** → enables advanced device design.

### Comparison with Silicon
- Compound semiconductors have higher mobility and better optical properties than silicon.
- Silicon has indirect bandgap → poor light emission, while many compounds are direct bandgap.
- Compound semiconductors are more expensive and harder to fabricate.
- Silicon dominates digital ICs, while compound semiconductors dominate optoelectronics and RF.
- Trade-off exists between cost, performance, and manufacturability.

### Applications
- **Optoelectronics**: LEDs, laser diodes (GaAs, InGaN).
- **High-frequency devices**: RF amplifiers, microwave circuits (GaAs, InP).
- **Power electronics**: GaN-based high-voltage devices.
- **Solar cells**: High-efficiency multi-junction cells.
- **Sensors & photodetectors**: Fast optical detection systems.

---

## Solar Cells

- A solar cell is a semiconductor device that converts solar light energy into electrical energy using the photovoltaic effect.
- It is typically a **p–n junction device**, where incident photons generate electron–hole pairs.
- The built-in electric field in the depletion region separates these carriers, producing current.
- When connected to a load, this current flows as usable electrical power.
- Solar cells are the fundamental units of solar panels used in renewable energy systems.
- **Solar cells do not require external voltage application for generating current.**

- **Short-Circuit Current (Isc)** : The current flowing through the solar cell when the output terminals are shorted (i.e., $ V = 0 $), representing the maximum current generated under illumination.

- **Open-Circuit Voltage (Voc)** : The voltage across the solar cell when no external current flows (i.e., $ I = 0 $), representing the maximum voltage developed due to carrier separation.

### Working Principle
- Photons with energy greater than bandgap ($ h\nu \geq E_g $) generate electron–hole pairs.
- The internal electric field drives electrons toward the n-side and holes toward the p-side.
- This separation prevents recombination and creates a voltage across the junction.
- External circuit allows current to flow, delivering power.
- Continuous illumination maintains carrier generation and output.

### Loss Mechanisms
- Recombination of carriers before collection reduces efficiency.
- Reflection losses prevent light from entering the device.
- Resistive losses in contacts and material reduce output power.
- Thermalization losses occur when excess photon energy is lost as heat.
- Imperfect absorption limits carrier generation.

### Types of Solar Cells
- **Silicon Solar Cells**: Most common, reliable, moderate efficiency.
- **Thin-Film Solar Cells**: Lightweight, flexible, lower efficiency.
- **Compound Semiconductor Cells**: High efficiency (GaAs, multi-junction).
- **Perovskite Solar Cells**: Emerging, high efficiency potential.

---

## Photodetectors

- A photodetector is a semiconductor device that converts incident light with a certain wavelength (Infrared, visible, Ultraviolet etc.) into an electrical signal by generating electron–hole pairs.
- It typically operates using a **p–n or p–i–n junction**, where light absorption creates carriers.
- The built-in or applied electric field separates these carriers, producing current.
- Output signal is proportional to incident optical power.
- Widely used in optical communication, sensing, and imaging systems.

### Working Principle
- Incident photons with energy $ h\nu \geq E_g $ generate electron–hole pairs.
- These carriers are separated by the electric field in the depletion region.
- Electrons move toward n-side and holes toward p-side, creating photocurrent.
- Reverse bias is often applied to increase depletion width and speed.
- Faster response is achieved with thinner active regions and strong fields.

### Types of Photodetectors
- **PN Photodiode**: Basic structure, moderate speed and sensitivity.
- **PIN Photodiode**: Wider depletion region give better sensitivity and faster response.
- **Avalanche Photodiode (APD)**: Internal gain via impact ionization → high sensitivity.
- **Photoconductor**: Conductivity changes with light, slower but simple.

### Key Performance Parameters
- **Responsivity (R)**: Output current per unit optical power:
$$
  R = \frac{I_{ph}}{P_{opt}}  
$$
- **Quantum Efficiency (η)**: Fraction of photons converted into carriers.
- **Dark Current**: Leakage current in absence of light.
- **Response Time / Bandwidth**: Speed of detector operation.
- **Noise**: Limits sensitivity and minimum detectable signal.

### Important Concepts
- Higher absorption coefficient results in more carrier generation.
- Larger depletion region yield in higher efficiency but slower response (trade-off).
- Reverse bias improves speed but increases noise.
- Avalanche multiplication enhances signal but adds excess noise.
- Material bandgap determines wavelength sensitivity.


#### Photodetectors vs Solar Cells

| Feature | Photodetectors | Solar Cells |
|--------|---------------|-------------|
| **Purpose** | Detect light and convert it into an electrical signal | Convert light into usable electrical power |
| **Primary Goal** | Sensitivity and speed | Maximum energy conversion efficiency |
| **Operation Mode** | Usually operated in **reverse bias** for fast response | Operated in **zero bias or forward bias** (power generation mode) |
| **Output** | Small signal current proportional to light intensity | Continuous power output (voltage + current) |
| **Speed** | Very fast (ns–ps range for high-speed devices) | Relatively slow (not optimized for speed) |
| **Responsivity** | High sensitivity to small optical signals | Designed for maximum total energy capture |
| **Efficiency Focus** | Detection efficiency (quantum efficiency) | Power conversion efficiency (η) |
| **Structure** | PN, PIN, Avalanche photodiodes | Mainly PN junction (sometimes multi-junction) |
| **Gain Mechanism** | Can include internal gain (APD via avalanche) | No internal gain mechanism |
| **Noise Consideration** | Noise is critical (limits detection capability) | Less critical compared to power output |
| **Applications** | Optical communication, sensors, imaging | Solar panels, renewable energy systems |

---

## Recombination in LEDs

- Recombination is the process where electrons from the conduction band combine with holes in the valence band, releasing energy in the form of photons (light).
- This is primarily **radiative recombination**, which is the desired mechanism for light emission.
- Occurs in the active region (usually a direct bandgap semiconductor).
- Efficiency of LED depends on how many recombinations produce photons.
- Direct bandgap materials (e.g., GaN, GaAs) are used to maximize light emission.

### Types of Recombination
- **Radiative Recombination**: Electron-hole recombination that emits a photon (useful for LEDs).
- **Non-radiative (SRH) Recombination**: Energy lost as heat via trap states, reducing efficiency.
- **Auger Recombination**: Energy transferred to another carrier instead of emitting light, dominant at high carrier densities.

### Key Concepts
- Radiative recombination rate is proportional to electron and hole concentrations:
$$
  R_{rad} \propto np  
$$
- Internal Quantum Efficiency (IQE):
$$
  IQE = \frac{\text{radiative recombination}}{\text{total recombination}}  
$$
- Higher radiative recombination results in brighter LED output.
- Non-radiative processes reduce efficiency and generate heat.
- Carrier confinement (using heterostructures) improves recombination efficiency.
-
---

## LED (Light Emitting Diode)

- An LED is a semiconductor **p–n junction device** that emits light when forward biased due to electron–hole recombination.
- It uses **direct bandgap materials** (e.g., GaN, GaAs) to efficiently convert electrical energy into light.
- The emitted light wavelength (color) depends on the bandgap of the material.
- LEDs are widely used in displays, lighting, and indicators due to high efficiency and long life.
- It is an optoelectronic device combining electrical and optical phenomena.

### Operation Principle
- When forward bias is applied, electrons from n-side and holes from p-side are injected into the junction.
- These carriers recombine in the active region.
- In direct bandgap materials, recombination releases energy as photons (light emission).
- Photon energy is approximately equal to bandgap:
$$
  E_{photon} \approx E_g = h\nu 
$$
- Continuous carrier injection results in continuous light output.

### Key Concepts
- **Forward Bias** is essential for carrier injection and light emission.
- **Radiative recombination** produces light, while non-radiative processes reduce efficiency.
- **Internal Quantum Efficiency (IQE)** measures how efficiently carriers produce photons.
- **External Quantum Efficiency (EQE)** also includes light extraction efficiency.
- Device design focuses on maximizing light output and minimizing losses.

### Important Factors Affecting LED Performance
- Material choice (direct bandgap required).
- Carrier recombination efficiency.
- Light extraction efficiency (internal reflections reduce output).
- Temperature (higher temperature reduces efficiency).
- Device structure (heterostructures improve confinement).

---

## Advanced transistors

### Transistors for Power Electronics
- Power transistors are semiconductor devices designed to handle **high voltage, high current, and high power levels** efficiently.
- They are used as switches or amplifiers in power conversion systems.
- Unlike small-signal devices, they are optimized for **low losses and high reliability**.
- Common types include **Power MOSFETs, IGBTs, and BJTs**.
- Widely used in power supplies, inverters, motor drives, and EV systems.

#### Key Requirements
- **High breakdown voltage** to withstand large voltages in OFF state.
- **Low ON-state resistance** to reduce conduction losses.
- **High current handling capability** for power applications.
- **Efficient heat dissipation** to manage thermal effects.
- **Fast switching capability** to minimize switching losses.

#### Operation Principle
- Power transistors operate mainly as **switches** (ON/OFF states).
- In ON state low resistance path allows current flow.
- In OFF state high resistance blocks current.
- Switching between states enables energy control and conversion.
- Efficiency depends on minimizing conduction and switching losses.

#### Types of Power Transistors
- **Power MOSFET**: Fast switching, low gate power, used in low–medium voltage.
- **IGBT (Insulated Gate Bipolar Transistor)**: Combines MOSFET control with BJT conduction, used in high power.
- **Power BJT**: High current capability but slower switching, less commonly used now.

#### Loss Mechanisms
- **Conduction Loss**: Due to ON resistance or voltage drop.
- **Switching Loss**: During transitions between ON and OFF states.
- **Leakage Loss**: Small current in OFF state.
- **Thermal Loss**: Heat generated affects efficiency and reliability.


### Transistors for Memory

#### What are Memory Transistors?
- Memory transistors are semiconductor devices designed to **store data (bits) by retaining charge or state**.
- They form the basic building blocks of memory technologies like **SRAM, DRAM, and Flash**.
- Unlike logic transistors, they are optimized for **data retention, stability, and low leakage**.
- Information is stored as either charge, voltage level, or stored state.
- Used in caches, RAM, and non-volatile storage systems.

#### Operation Principle
- Memory operation involves **write, store, and read** cycles.
- During write, charge is stored in a node or capacitor.
- During hold, the device retains stored information for a certain duration.
- During read, stored data is sensed without disturbing it significantly.
- Data is represented as binary states (0 or 1).

#### Types of Memory Transistor Structures
- **SRAM (Static RAM)**: Uses multiple transistors (typically 6T) to store a stable state using feedback.
- **DRAM (Dynamic RAM)**: Uses one transistor + capacitor; requires periodic refresh.
- **Flash Memory**: Uses floating gate MOSFET to store charge permanently (non-volatile).
- **EEPROM**: Allows electrical erasing and reprogramming.

---

## Microelectronic Fabrication
- Microelectronic fabrication is the process of creating semiconductor devices and integrated circuits on a wafer (typically silicon).
- It involves a sequence of physical and chemical processes to build structures at micro/nano scale.
- Devices are fabricated layer-by-layer using precise patterning techniques.
- Fabrication is carried out in cleanroom environments to avoid contamination.
- It is the foundation of modern VLSI and semiconductor manufacturing.
- Fabrication is a **repetitive cycle of patterning + modification + deposition**.
- Precision at nanometer scale is critical for device performance.
- Alignment between layers is crucial for circuit functionality.
- Process variations can significantly impact device characteristics.
- Yield (percentage of working chips) is a key manufacturing metric.

### Key Process Steps
- **Oxidation**: Growth of silicon dioxide (SiO₂) layer for insulation and protection.
- **Photolithography**: Pattern transfer using light, masks, and photoresist.
- **Etching**: Removal of material (wet or dry) to define structures.
- **Doping (Diffusion / Ion Implantation)**: Introduction of impurities to form p-type or n-type regions.
- **Deposition**: Addition of material layers (chemical or physical).

### Supporting Processes
- **Annealing**: Heat treatment to repair damage and activate dopants.
- **Planarization (CMP)**: Smoothening wafer surface for uniform layers.
- **Metallization**: Formation of metal interconnects for electrical connections.
- **Passivation**: Protective layer to prevent contamination and damage.

### Challenges
- Scaling down device size increases fabrication complexity.
- Contamination can destroy devices → strict cleanroom control required.
- Process variations affect performance and reliability.
- High cost of fabrication facilities (fabs).
- Thermal and material limits at nanoscale.

---

## Books and references
i. NPTEL course - Fundamentals of Semiconductor Devices By Prof. Digbijoy N. Nath   |   IISc Bangalore
ii. Solid State Electronic Devices, by Ben Streetman and Sanjay Banerjee, Prentice Hall.
iii. Introduction to Semiconductor Materials and Devices, by M. S. Tyagi, Wiley Publications.

---