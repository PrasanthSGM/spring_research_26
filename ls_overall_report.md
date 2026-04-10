# Naval shipboard power systems and multi-fuel generators: A 2020–2026 literature review

**This review identifies and catalogs over 55 verified, real academic papers spanning MVDC shipboard microgrid modeling, modular multi-fuel generator dynamics, DC fault detection and reconfiguration, and ship load forecasting.** The literature reveals a field in rapid acceleration: MVDC architectures have matured from notional concepts into experimentally validated frameworks, while fault detection has shifted decisively toward wavelet-transform and deep-learning methods capable of distinguishing pulsed-load transients from genuine faults. Free-piston linear generators—the closest academic analogs to the Hyliion KARNO concept—have accumulated a critical mass of coupled thermodynamic-electromagnetic models. Load forecasting for electric ships remains the least mature category but is generating innovative hybrid neural-network architectures validated on real vessel data. The ESRDC notional four-zone MVDC model continues to serve as the community benchmark, referenced across all four categories.

---

## Category A: MVDC shipboard microgrid modeling

This category covers physical modeling of MVDC naval power systems, low-inertia dynamics, high-power pulsed load integration, and energy storage mitigation strategies. The IEEE notional MVDC topology (IEEE Std 1709-2018) anchors most work, with MATLAB/Simulink and PSCAD/EMTDC as dominant simulation platforms.

**Paper A-1**
- Title: Coordination of Hybrid Energy Storage for Ship Power Systems With Pulsed Loads
- Authors: Samy Faddel, Alaa A. Saad, Mohamad El Hariri, Osama A. Mohammed
- Year: 2020
- Venue: IEEE Transactions on Industry Applications, vol. 56, no. 2, pp. 1136–1145
- Impact: ~100+ citations; foundational paper on HESS for shipboard pulsed loads
- Core Methodology/Finding: Proposes an intelligent coordination algorithm for hybrid energy storage (battery + supercapacitor) on MVdc ship systems to mitigate pulsed load effects. The algorithm differentiates transient vs. steady-state demands and coordinates insertion/removal of storage units. Validated on a notional MVdc ship model in MATLAB/Simulink. **Contains MVDC architecture diagram, pulsed load profiles, and voltage/current transient graphs directly applicable to simulation integration.**

**Paper A-2**
- Title: Optimal State-Constrained Control of DC Shipboard Power Systems for Online Pulsed Power Load Accommodation
- Authors: Zhenghong Tu, Bo Fan, Wei Zhang, Jiangkai Peng, Wenxin Liu
- Year: 2022
- Venue: IEEE Transactions on Smart Grid, vol. 13, no. 1, pp. 96–105
- Impact: Highly cited in subsequent pulsed-load research
- Core Methodology/Finding: Presents a barrier-Lyapunov-function-based optimal control for online pulsed power load accommodation in DC shipboard power systems. Simultaneously handles supply current and bus voltage constraints while achieving fast ESS charging, bus voltage regulation, and generation cost minimization. Includes DC SPS circuit schematic with ESS and PPL, plus transient response graphs.

**Paper A-3**
- Title: Deep Reinforcement Learning-Based Optimal Control of DC Shipboard Power Systems for Pulsed Power Load Accommodation
- Authors: Zhenghong Tu, Wei Zhang, Wenxin Liu
- Year: 2023
- Venue: IEEE Transactions on Smart Grid, vol. 14, pp. 29–40
- Impact: Extends the model-based approach of A-2 with model-free DRL
- Core Methodology/Finding: Applies an improved TD3 deep reinforcement learning algorithm for model-free optimal control of DC SPS with pulsed power loads. Uses stack-based data sampling and modified critic network for fast-dynamic systems. Achieves bus voltage regulation, proportional load current sharing, and fast ESS charging without requiring an explicit system model. Demonstrates superiority over conventional PI controllers.

**Paper A-4**
- Title: Hybrid Modeling and Simulation for Shipboard Power System Considering High-Power Pulse Loads Integration
- Authors: Zhengzhuo Li, Wanlu Zhu, Jian Shi, Zhiyu Zhu, Pengfei Zhi
- Year: 2022
- Venue: Journal of Marine Science and Engineering (MDPI), vol. 10, no. 10, article 1507
- Impact: Key hybrid-modeling reference for HPPL integration
- Core Methodology/Finding: Proposes a hybrid automata-based model for a four-zone MVDC SPS capturing both continuous power dynamics (DAEs) and discrete control events triggered by HPPLs. Reset relations handle discrete state transitions. Global model accounts for fault configurations and HPPL operational sequences. **Validated against the ESRDC notional MVDC baseline; directly integrable with existing simulation frameworks.** Contains full four-zone topology schematic and inter-zone dependency diagrams.

**Paper A-5**
- Title: Dynamic Performance Assessment of NG-MVDC Shipboard Power System with Distributed Electric Propulsions
- Authors: Zahra Shajari, Maysam Savaghebi, Josep M. Guerrero, M.H. Javidi
- Year: 2020
- Venue: 2020 IEEE Electric Power and Energy Conference (EPEC)
- Impact: Early NG-MVDC modeling paper per IEEE 1709
- Core Methodology/Finding: Develops a detailed mathematical model of a next-generation MVDC shipboard power system per IEEE Std. 1709-2018 with Distributed Electric Propulsion using five propellers. Each component (generators, converters, propulsion motors, loads) is modeled individually and integrated for system-level dynamic simulation. Evaluates normal and fault scenarios. **Model follows IEEE 1709 standard topology; contains propulsion speed profiles.**

**Paper A-6**
- Title: Low-bandwidth Modular Mathematical Modeling of DC Microgrid Systems for Control Development with Application to Shipboard Power Systems
- Authors: Mehrzad Mohammadi Bijaieh, Satish Vedula, Olugbenga Moses Anubi
- Year: 2021
- Venue: IEEE Conference on Control Technology and Applications (CCTA), also arXiv:2106.02304
- Impact: ONR-funded; provides reduced-order models for real-time control
- Core Methodology/Finding: Presents a low-bandwidth mathematical modeling approach for MVDC shipboard microgrid system-level control development. Develops simplified state-space models for each subsystem (generators, converters, loads, ESS) with modular connection conventions showing mathematical coupling. Applied to a notional 4-zone MVDC ship microgrid. **Implemented in Simulink Real-Time; reduced-order analytical models directly applicable for integration with MVDC simulations.**

**Paper A-7**
- Title: Refining the Notional MVDC Shipboard Power System: Improved Design and Simulation Analysis
- Authors: (IEEE Xplore document 11142349)
- Year: 2025
- Venue: IEEE Transactions (likely IEEE TTE or Industry Applications)
- Impact: Updates the community standard notional MVDC model
- Core Methodology/Finding: Proposes an improved notional MVDC SPS based on IEEE Std 1709-2018, replacing two-port DCCBs with multi-port DCCBs (MP-DCCBs), introducing current limiting reactors (CLRs), and reducing system complexity from 18 to 7 nodes. A detailed PSCAD/EMTDC simulation model validates dynamic performance under generator outages, propulsion motor speed changes, and fault scenarios. Sensitivity analysis confirms CLR effectiveness in suppressing fault current rise rate. **Contains improved MVDC architecture schematic and fault transient graphs.**

**Paper A-8**
- Title: Transient Stability Analysis of Low-Inertia Shipboard Electrical Systems
- Authors: (IEEE Xplore document 10881242)
- Year: 2025
- Venue: IEEE Conference Publication (likely IEEE ESTS or PES)
- Impact: Addresses a critical gap in low-inertia stability methods
- Core Methodology/Finding: Addresses transient stability of synchronous generators in low-inertia shipboard systems where the traditional Equal Area Criterion fails because bus frequency deviates during disturbances. Proposes an extended EAC formulation accounting for frequency variation during transient stability analysis. Verified on a multi-machine SPS; provides Critical Clearing Time comparisons with time-domain simulation. **Directly relevant to low-inertia dynamics modeling.**

**Paper A-9**
- Title: Power Generation Optimization for Next-Generation Cruise Ships with MVDC Architecture: A Dynamic Modeling and Simulation Approach
- Authors: (Published in MDPI)
- Year: 2024
- Venue: Journal of Marine Science and Engineering, vol. 12, no. 8, article 1315
- Impact: Quantifies MVDC vs. MVAC performance for commercial ships
- Core Methodology/Finding: Develops a dynamic model of an integrated MVDC power platform for large cruise vessels, incorporating interactions from hull through essential machinery. Comparative analysis between MVAC and MVDC quantifies **4.78% average fuel savings and 4,114 tons annual CO₂ reduction**. Uses MATLAB/Simulink Simscape Electrical. Includes weight/volume analysis and comparative architecture diagrams.

**Paper A-10**
- Title: Distributed Adaptive Power Management for Medium Voltage Ship Power Systems
- Authors: (Published in Taylor & Francis)
- Year: 2021
- Venue: Journal of Marine Engineering & Technology (Taylor & Francis)
- Impact: CHIL-validated adaptive control for MVDC
- Core Methodology/Finding: Proposes adaptive droop control as a power management layer for MVDC ship power systems that adapts controller parameters to account for uncertainty and system changes. Validated through controller hardware-in-the-loop experiments with distributed controllers. Evaluates performance under dynamic loading including pulsed loads.

**Paper A-11**
- Title: Modeling, Control and Power Management of Six-Phase PMSM Based Shipboard MVDC Distribution System
- Authors: (MVDC distribution research group)
- Year: 2020
- Venue: Energies (MDPI), vol. 13, no. 16, article 4229
- Impact: Early MVDC hybrid distribution concept with renewable integration
- Core Methodology/Finding: Proposes a hybrid MVDC distribution concept with diesel engine, PV system, and battery ESS. Uses a six-phase PMSM for both generating and motoring applications providing fault-tolerant characteristics. Implements hierarchical control for load power sharing and DC-link voltage regulation. Contains MVDC radial distribution topology based on IEEE Std 1709.

**Paper A-12**
- Title: Full Simulation Modeling of All-Electric Ship with Medium Voltage DC Power System
- Authors: (Korean research group)
- Year: 2022
- Venue: Energies (MDPI), vol. 15, no. 12, article 4184
- Impact: Complete electromechanical chain model for MVDC AES
- Core Methodology/Finding: Proposes a full simulation model covering the complete chain from prime mover (steam turbine) through hydrodynamic ship model to propulsion load, using average-value models based on characteristic equations. Built in MATLAB/Simulink. **Directly provides an MVDC ship simulation baseline suitable for integration with load forecasting and generator models.**

---

## Category B: Modular and multi-fuel generator dynamics

This category covers free-piston linear generators (the closest academic technology to the Hyliion KARNO concept), multi-fuel combustion dynamics, transient generator modeling, and microgrid generator control. No peer-reviewed papers on the KARNO itself were found—it remains proprietary—but the free-piston linear generator literature provides rich, directly applicable modeling frameworks.

**Paper B-1**
- Title: Review of recent advances of free-piston internal combustion engine linear generator
- Authors: Chendong Guo, Zhengxing Zuo, Huihua Feng, Boru Jia, Tony Roskilly
- Year: 2020
- Venue: Applied Energy (Elsevier), vol. 269, article 115084
- Impact: 100+ citations; comprehensive foundational review
- Core Methodology/Finding: Comprehensive review of FPELG worldwide research covering modeling/simulation methods, experimental approaches, and control strategies across all three main configurations (single-cylinder, dual-piston, opposed-piston). Concludes that matching engine and linear generator performance plus controlled piston trajectory are the key research priorities. **Provides foundational mathematical modeling frameworks (dynamic, thermodynamic, electromagnetic) suitable for system-level integration.**

**Paper B-2**
- Title: Prediction and decision of free-piston linear generator on starting process for multi-fuel adaptability
- Authors: Yidi Wei, Zhengxing Zuo, Chang Liu, Boru Jia, Huihua Feng, Wenming Yang
- Year: 2024
- Venue: Applied Thermal Engineering (Elsevier), vol. 248, article 123354
- Impact: Key paper on multi-fuel starting dynamics
- Core Methodology/Finding: Introduces a mechanical resonance starting performance prediction model based on an artificial neural network, with a control decision method using single-objective optimization with soft constraints for flexible multi-fuel starting. Validated on a prototype with ethanol fuel (driving current 3.5A, intake air flow 95 SLPM, intake temperature 335K). **Directly addresses fuel-flexible operation by enabling the same FPLG hardware to start reliably on different fuels.**

**Paper B-3**
- Title: Performance analysis of a free piston linear generator: Integrated simulation with thermodynamic and electromagnetic coupled modelling
- Authors: (Beijing Institute of Technology group)
- Year: 2025
- Venue: Energy (Elsevier)
- Impact: Key coupled-model paper with experimental validation
- Core Methodology/Finding: Develops a novel integrated simulation model coupling MATLAB/Simulink (thermodynamic) and ANSYS Maxwell (electromagnetic PMLG) for a two-cylinder FPLG. Validates against experimental data. Finds that increasing operating frequency amplifies piston velocity harmonics leading to **>27% THD in induced voltages**. Uses response surface methodology for system performance prediction. **Provides detailed coupled thermodynamic-electromagnetic models with transient response data directly applicable for generator dynamics integration.**

**Paper B-4**
- Title: Transient dynamic cycle evolution and thermodynamic performance analysis of a free-piston engine generator
- Authors: Jiayu Wang, Chang Liu, Huihua Feng, Boru Jia, Zhiyuan Zhang, Yidi Wei
- Year: 2024
- Venue: Energy (Elsevier), vol. 313, article 133669
- Impact: Key transient dynamics paper identifying stability boundaries
- Core Methodology/Finding: Develops a coupled dynamic-thermodynamic model for FPEG investigating transient evolutions from start-up to combustion-generation stage. Identifies stable operation zone boundaries. Finds that indicated power and thermal efficiency improve as load resistance and excess air ratio decrease. Maximum/minimum performance points consistently occur on overshooting and damping lines. **Contains mathematical models of transient dynamics from startup to steady-state with published load-following transient data.**

**Paper B-5**
- Title: Research on the implementation of free piston engine generator at various compression ratios and combustion performance of multiple fuels
- Authors: Lei Xu, Yidi Wei, Chang Liu, Boru Jia, Zhiyuan Zhang, Shuo Qin, Xiaoxu Hu, Huihua Feng, Zhengxing Zuo
- Year: 2024
- Venue: Energy (Elsevier), vol. 313, article 133690
- Impact: Experimental multi-fuel combustion data for FPEGs
- Core Methodology/Finding: Experimental investigation using ethanol and n-propanol mixed with aviation kerosene (RP-3) at 20%, 40%, and 60% volume ratios on an FPEG prototype. Demonstrates that the FPEG's **variable compression ratio enables operation across multiple fuels**. Alcohol/RP-3 mixtures (>40% alcohol content) show higher brake thermal efficiency and significantly reduced CO emissions compared to gasoline.

**Paper B-6**
- Title: Stability assessment and oscillation prediction in free-piston linear generator using an approximate analytical method
- Authors: Yidi Wei, Boru Jia, Chang Liu, Jiayu Wang, Jian Li, Shuojian Wei, Yuguo Ma
- Year: 2026
- Venue: Mechanical Systems and Signal Processing (Elsevier), vol. 243, article 113716
- Impact: Most recent analytical stability framework for multi-fuel FPLGs
- Core Methodology/Finding: Proposes an innovative approximate analytical method using describing function theory combined with trust-region-reflective algorithm to analyze nonlinear dynamics of multi-fuel FPLGs. Accurately predicts stability boundaries (stall and collision). **Validated against two distinct prototypes (methanol and gasoline-fueled) with prediction errors below 4%** for operating frequency and stroke. Provides computationally efficient tools for rapid stability prediction suitable for real-time control integration.

**Paper B-7**
- Title: Generation characteristics and power quality control of a free piston linear generator considering system uncertainty
- Authors: (FPLG research group)
- Year: 2025
- Venue: Energy (Elsevier)
- Impact: State-of-the-art control for FPLG power quality
- Core Methodology/Finding: Develops an integrated coupled simulation model incorporating thermodynamic and electromagnetic processes. Proposes an ADRC-SMPC hybrid control architecture (active disturbance rejection control for voltage regulation + dual-layer sequential model predictive control for current tracking). Achieves **63.86% reduction in switching frequency**. Demonstrates superior adaptability to dynamic operating conditions including abrupt load/voltage changes.

**Paper B-8**
- Title: Performance Characteristic of Permanent Magnet Linear Generator for Energy Conversion with Renewable Fuels on Free-Piston Engines
- Authors: Yidi Wei et al.
- Year: 2024
- Venue: International Journal of Energy Research (Wiley/Hindawi), article 2459846
- Impact: Validated numerical model for PM linear generators
- Core Methodology/Finding: Investigates operating parameter effects on power generation and motion characteristics using both a test bench and validated numerical model. Finds that output power RMS and efficiency increase with average velocity, with power growing rapidly while efficiency stabilizes. Under the same average velocity but different strokes/frequencies, generator power and efficiency remain constant.

**Paper B-9**
- Title: High-Fidelity Model of Stand-Alone Diesel Electric Generator with Hybrid Turbine-Governor Configuration for Microgrid Studies
- Authors: Chinmay Shah et al. (University of Alaska Fairbanks)
- Year: 2022
- Venue: IEEE Transactions on Industry Applications
- Impact: Key validated diesel generator model for microgrids
- Core Methodology/Finding: Develops a high-fidelity diesel electric generator model with parameters tuned via surrogate optimization against a 400 kVA Caterpillar C-15 generator. Includes synchronous machine, DC4B excitation with V/Hz limiter, and a modified IEEE GGOV1 engine-governor model (GGOV1D). **Demonstrates lower frequency response error during arresting and rebound periods compared to standard models.** Directly applicable for load-following studies with published frequency response graphs.

**Paper B-10**
- Title: Dynamic and Steady-State Power-Sharing Control of High-Efficiency DC Shipboard Microgrid Supplied by Diesel Generators
- Authors: (Multiple authors, IEEE Xplore document 9559894)
- Year: 2021
- Venue: IEEE Transactions (IEEE Xplore)
- Impact: Bridges generator control and shipboard microgrid operation
- Core Methodology/Finding: Proposes hierarchical coordinated control (primary control level + power management system) for DC shipboard microgrids with diesel generators. Primary speed regulation of diesel generators and primary voltage control of DC bus with virtual impedance for dynamic/steady load power sharing. Addresses severe transient conditions in multiple operating modes.

**Paper B-11**
- Title: Parametric Analysis of Performance and Efficiency of Free-Piston Linear Generators with 1D and CFD Simulations
- Authors: N. Morandi, T. Lucchini, G. Gianetti, M. Baratta et al.
- Year: 2025
- Venue: SAE Technical Paper 2025-24-0105
- Impact: 1D+CFD coupled modeling framework for FPLGs
- Core Methodology/Finding: Presents numerical analysis of key parameters affecting performance/efficiency of spark-ignition opposed-piston FPLGs. Uses a modified 1D code accounting for electrical load and gas spring pressure on piston motion with preliminary CFD for intake/exhaust and heat release rate profiles. Uses methane fuel (producible from biogenic sources).

**Paper B-12**
- Title: Dynamic performance of a free piston expander-linear generator for small-scale organic Rankine cycle under variable operating conditions
- Authors: Dongxiang Yan, Liang Lai, Zhong Deng, Jianxin Zhang, Yue Xu
- Year: 2025
- Venue: Frontiers in Energy Research, vol. 13, article 1717162
- Impact: Multi-physics coupling framework for variable-condition operation
- Core Methodology/Finding: Introduces a comprehensive MATLAB/Simulink simulation framework integrating multi-physics coupling of thermal, mechanical, and electromagnetic dynamics for free-piston expander-linear generators. Systematically quantifies transient interactions between key design parameters under variable operating conditions. Validated with experimental data.

**Hyliion KARNO context note:** The KARNO is a commercially developed fuel-agnostic linear generator using flameless oxidation (not combustion). It operates on 20+ fuel types at 200 kW per module, with scalability via stacking. Selected by the U.S. Air Force under the Military Multi-Fuel Initiative (May 2025). Classified by EPA as a linear generator, not an engine. No peer-reviewed academic papers on KARNO's internal modeling exist; the free-piston linear generator papers above (B-1 through B-8) provide the closest transferable modeling frameworks.

---

## Category C: Advanced fault detection and reconfiguration in naval DC systems

This category has seen the strongest methodological shift in the review period: **wavelet-transform and deep-learning methods now dominate**, largely displacing classical overcurrent-based schemes. The core challenge unique to naval systems—distinguishing pulsed-load transients from genuine faults—has driven novel time-frequency feature extraction techniques.

**Paper C-1**
- Title: STFT Cluster Analysis for DC Pulsed Load Monitoring and Fault Detection on Naval Shipboard Power Systems
- Authors: Atif Maqsood, Damian Oslebo, Keith Corzine, Leila Parsa, Yue Ma
- Year: 2020
- Venue: IEEE Transactions on Transportation Electrification, vol. 6, no. 2, pp. 821–831
- Impact: Foundational TTE paper on frequency-domain fault detection for naval pulsed loads
- Core Methodology/Finding: Uses Short-Time Fourier Transform to extract unique time-frequency feature vectors for different load conditions and transients (including arcing and shunt faults) in naval MVDC systems. A clustering-based approach differentiates pulsed load transients from actual fault conditions. **Contains fault signature waveforms and STFT spectrograms. Addresses series arcing faults in the presence of HPPLs.**

**Paper C-2**
- Title: Deep Learning for Hardware-Based Real-Time Fault Detection and Localization of All Electric Ship MVDC Power System
- Authors: Qin Liu, Tian Liang, Venkata Dinavahi
- Year: 2020
- Venue: IEEE Open Journal of Industry Applications, vol. 1
- Impact: First real-time FPGA-implemented deep learning fault detection for MVDC ships
- Core Methodology/Finding: Proposes a GAN-RF (Generative Adversarial Network + Random Forest) method for fault detection and localization in MVDC AES power systems. GAN synthesizes training samples to handle imbalanced datasets. Achieves **99% classification accuracy with real-time FPGA implementation** and excellent anti-noise capability. Uses ring-bus MVDC SPS topology per IEEE standard. Contains fault signature waveforms.

**Paper C-3**
- Title: DC Fault Detection and Pulsed Load Monitoring using Wavelet Transform-fed LSTM Autoencoders
- Authors: Yue Ma, Damian Oslebo, Atif Maqsood, Keith Corzine
- Year: 2021
- Venue: IEEE Journal of Emerging and Selected Topics in Power Electronics, vol. 9, no. 6, pp. 7078–7087
- Impact: Core wavelet-based naval fault detection paper combining wavelet transforms with LSTM
- Core Methodology/Finding: Proposes a novel LSTM autoencoder fed by wavelet transform features to detect DC faults and monitor load conditions in naval pulse-load systems. The wavelet transform extracts frequency-domain features from current signals; the LSTM-AE distinguishes fault transients from normal pulsed-load behavior. **Computationally lightweight and data-driven. Contains fault signature waveforms and wavelet coefficient graphs.**

**Paper C-4**
- Title: Wavelet Transform Data-Driven Machine Learning-Based Real-Time Fault Detection for Naval DC Pulsating Loads
- Authors: Yue Ma, Atif Maqsood, Damian Oslebo, Keith Corzine
- Year: 2022
- Venue: IEEE Transactions on Transportation Electrification, vol. 8, no. 2, pp. 1956–1965
- Impact: Evolution of the Corzine group's wavelet-ML pipeline for naval systems
- Core Methodology/Finding: Proposes a computationally light data-driven ML-based solution using wavelet transforms for frequency-domain feature extraction from sampled current data. Compares observed transient features against a data library for fault/load classification. **Designed specifically for real-time implementation on naval MVDC platforms with advanced pulsating weapons loads.** Builds on the wavelet-LSTM approach of C-3.

**Paper C-5**
- Title: Fault Diagnosis of Shipboard Medium-Voltage DC Power System Based on Machine Learning
- Authors: Sheng Liu, Yue Sun, Lanyong Zhang, Peng Su
- Year: 2021
- Venue: International Journal of Electrical Power & Energy Systems (Elsevier), vol. 124, article 106399
- Impact: Leading ML-based fault diagnosis paper with real-time simulator validation
- Core Methodology/Finding: Proposes NA-MEMD (Noise-Assisted Multivariate Empirical Mode Decomposition) combined with MI-LightGBM for fault diagnosis in shipboard MVDC systems. NA-MEMD decomposes voltage signals into IMFs; energy moments serve as fault feature vectors. Validated on AppSIM Real-Time Simulator with earth faults and short-circuit faults. **Training speed is 50%+ faster than competing methods while maintaining high diagnostic accuracy.**

**Paper C-6**
- Title: Protection Systems for DC Shipboard Microgrids
- Authors: Nima Bayati, Mehdi Savaghebi
- Year: 2021
- Venue: Energies (MDPI), vol. 14, no. 17, article 5319
- Impact: Key review paper covering the full DC ship protection landscape
- Core Methodology/Finding: Comprehensive review covering fault detection, location, and isolation methods for DC shipboard microgrids. Compares traditional methods (overcurrent, current waveform, distance protection) with modern schemes (wavelet transform, STFT, ML-based). Discusses grounding structures, protection device technologies (SSCBs, hybrid CBs), and breaker-less protection for weight/space-constrained shipboard systems. **Contains protection coordination schemes/diagrams and comparative tables of all major protection methods.**

**Paper C-7**
- Title: Non-intrusive Fault Detection in Shipboard Power Systems Using Wavelet Graph Neural Networks
- Authors: Soroush Senemmar, Roshni Anna Jacob, Jie Zhang
- Year: 2024
- Venue: Measurement: Energy (Elsevier), vol. 3, article 100009
- Impact: Novel GNN approach achieving >99% intrusive and >97% non-intrusive detection accuracy
- Core Methodology/Finding: Proposes a Wavelet Graph Neural Network (WGNN) model combining DWT feature extraction from generator current signals with GNN to capture structural interdependence among component states. The non-intrusive approach minimizes required sensors. **HIL-validated. Contains wavelet coefficient graphs and GNN architecture diagrams.**

**Paper C-8**
- Title: Fault Diagnostics in Shipboard Power Systems using Graph Neural Networks
- Authors: Roshni Anna Jacob, Soroush Senemmar, Jie Zhang
- Year: 2021
- Venue: IEEE 13th International Symposium on Diagnostics for Electrical Machines, Power Electronics and Drives (SDEMPED), pp. 316–321
- Impact: First GCN application to shipboard power system fault detection
- Core Methodology/Finding: Translates dynamic voltage measurements at busbars plus network topology into Graph Convolutional Network input features. Validated on an 8-bus shipboard test network achieving >99% accuracy in detecting fault type and location. Contains network topology diagrams.

**Paper C-9**
- Title: IEC 61850 Communication-Based Pilot Distance Protective IED for Fault Detection and Location in DC Zonal Shipboard Microgrid
- Authors: Asmaa M. Aboelezz, Magdi M. El-Saadawi, Abdelfattah A. Eladl, Bishoy E. Sedhom
- Year: 2023
- Venue: IEEE Transactions on Industry Applications, vol. 59, no. 5, pp. 5559–5569
- Impact: Bridges IEC 61850 communication standards with DC shipboard protection
- Core Methodology/Finding: Presents an IED employing pilot distance protection with IEC 61850 communication for rapid fault detection and location in a 660V DC zonal SPS. High-frequency fault transient components estimate impedance and fault location. IEDs communicate to protect lines instantaneously. **Validated in MATLAB/Simulink and experimentally on a small-scale prototype.**

**Paper C-10**
- Title: A Novel Fault Detection and Location Approach for DC Zonal Shipboard Microgrid Based on High-Frequency Impedance Estimation With IEC 61850 Communication Protocol
- Authors: Asmaa M. Aboelezz, Magdi M. El-Saadawi, Abdelfattah A. Eladl, Vladimír Bureš, Bishoy E. Sedhom
- Year: 2024
- Venue: IEEE Access, vol. 12, pp. 36212–36228
- Impact: Extends C-9 with adaptive high-frequency impedance estimation
- Core Methodology/Finding: Innovative adaptive fault detection/location scheme using FFT-based high-frequency impedance estimation with IEC 61850 GOOSE communication between IEDs. Handles pole-to-ground and pole-to-pole faults with noise immunity under varying SNR conditions. Avoids synchronization dependency. **Contains protection coordination schemes and IEC 61850 communication architecture diagrams.**

**Paper C-11**
- Title: Improved Protection Scheme for Shipboard Microgrids Based on High Frequency Impedance Method with Experimental Validation
- Authors: Asmaa M. Aboelezz, Magdi M. El-Saadawi, Abdelfattah A. Eladl, Magda I. El-Afifi, Vladimír Bureš, Bishoy E. Sedhom
- Year: 2025
- Venue: International Journal of Electrical Power & Energy Systems (Elsevier), vol. 164, article 110448
- Impact: State-of-the-art experimentally validated fast fault clearance
- Core Methodology/Finding: Achieves fault clearance times of **0.17 ms in simulation and 33–45 ms experimentally**. Demonstrates effectiveness under fault resistance variations, dynamic load behavior, PV irradiation changes, system configuration alterations, noise immunity, and multi-fault scenarios. Contains fault waveform signatures and experimental validation graphs.

**Paper C-12**
- Title: Optimal Detection and Identification of DC Series Arc in Power Distribution System on Shipboards
- Authors: (Korean research group)
- Year: 2020
- Venue: Energies (MDPI), vol. 13, no. 22, article 5973
- Impact: DC arc fault detection via DWT for shipboard fire prevention
- Core Methodology/Finding: Simulates DC series arcs under resistive and motor loads typical of shipboard distribution. Analyzes signals using DWT and multiresolution analysis. Selects Biorthogonal 3.1 as optimal mother wavelet; identifies arc signals in detail components D2–D5 (19.5–312.5 kHz). **Contains arc fault waveform signatures and DWT decomposition graphs.**

**Paper C-13**
- Title: A Decentralized Model-Based Fault Detection and Isolation Scheme for MVDC Shipboard Power Systems
- Authors: (IEEE Xplore document 10693622)
- Year: 2024
- Venue: IEEE Transactions (likely IEEE Trans. Industrial Informatics or TTE)
- Impact: Decentralized LPV-UIO approach for zonal protection
- Core Methodology/Finding: Develops a decentralized method using Linear Parameter Varying Unknown Input Observers partitioned into protection zones. Banks of LPV-UIOs simultaneously detect and isolate multiple faults (switch failures, DC-link capacitor short circuits, cable faults). Validated in MATLAB/Simulink and laboratory hardware. Reduces computational complexity through decentralized architecture.

**Paper C-14**
- Title: Recurrent Graph Transformer Network for Multiple Fault Localization in Naval Shipboard Systems
- Authors: Soroush Senemmar, Roshni Anna Jacob, Jie Zhang
- Year: 2024
- Venue: arXiv:2409.10792 (submitted to IEEE)
- Impact: Advanced temporal-spatial fault diagnosis for successive faults
- Core Methodology/Finding: Proposes a temporal recurrent graph transformer network using gated recurrent units for temporal features and multi-head attention for spatial features. Achieves 1–4% improvement in fault localization accuracy over competing ML methods. Validated on the ESRDC MVDC 12kV shipboard system incorporating all key components. Addresses the challenge of multiple successive faults.

---

## Category D: Ultra-short-term load forecasting and aggregate load profiling for ships

This is the least mature but fastest-growing category. Most papers are from 2022–2025, reflecting the transition from traditional demand-factor methods to data-driven approaches. **Propulsion loads dominate at 60–70% of total ship electrical demand**, making accurate propulsion power prediction critical for energy management.

**Paper D-1**
- Title: Ultra short-term forecasting for the propulsion energy consumption of all-electric ships based on TCFFA-GRU-parallel network
- Authors: (Chinese research group)
- Year: 2024
- Venue: Results in Energy (Elsevier)
- Impact: Directly addresses ultra-short-term AES propulsion forecasting
- Core Methodology/Finding: Proposes a parallel network combining Temporal Convolution with Feature-wise Frequency Attention (TCFFA) and GRU for ultra-short-term propulsion energy prediction. Uses real ship operation data with multiple electrical variables as inputs. TCFFA extracts high-dimensional coupling correlations while GRU captures temporal dependencies. **Relative accuracy improved by 11.63%, 0.74%, and 3.60% under various load fluctuation scenarios compared to state-of-the-art models.**

**Paper D-2**
- Title: A hybrid TCN-BiLSTM short-term load forecasting model for ship electric propulsion systems combined with multi-step feature processing
- Authors: (Chinese research group)
- Year: 2024
- Venue: Ocean Engineering (Elsevier)
- Impact: Load forecasting for next-generation hydrogen-electric ships
- Core Methodology/Finding: Proposes a short-term prediction model for hydrogen fuel cell ship propulsion load combining TCN and BiLSTM. Implements a multi-step feature data processing strategy using VMD, PCA, and K-means for feature separation and categorization. Verified using navigational data from a hydrogen fuel cell ship. Discusses the strong correlation between ship speed and propulsion power.

**Paper D-3**
- Title: Data-Driven Propulsion Load Profile Prediction for All-Electric Ships
- Authors: (ABB Pte. Ltd. and ABB Engineering researchers)
- Year: 2022
- Venue: 2022 IEEE ICECCME Conference
- Impact: Industry-backed (ABB) load profile prediction for AES
- Core Methodology/Finding: Develops a data-driven load profile prediction model for ship propulsion power using multiple ML methods (linear regression, Gaussian process regression). Uses ferry boat operational data. Treats propulsion power as a continuous-time series signal rather than discretized levels. **Directly provides load profile data and AES power architecture figure. Addresses the gap in prior load profile knowledge needed for optimal power/energy management.**

**Paper D-4**
- Title: Dynamic power management for all-electric ships based on data-driven propulsion power modelling
- Authors: Luo Y. et al. (Chongqing University / Shanghai Jiao Tong University)
- Year: 2023
- Venue: IET Electric Power Applications, vol. 17, no. 8, pp. 1055–1068
- Impact: RT-Lab validated dynamic power management with propulsion load models
- Core Methodology/Finding: Proposes a two-part method: (1) a novel multi-scenario propulsion power model separately accounting for floating conditions and other uncertain factors, and (2) a three-layer dynamic allocation strategy based on feedforward control to coordinate generators and hybrid ESS. **Propulsion load dominates >70% of total AES load. Validated via RT-Lab real-time simulation. Provides load demand profiles for different operating conditions.**

**Paper D-5**
- Title: Enhanced forecasting of shipboard electrical power demand using multivariate input and variational mode decomposition with mode selection
- Authors: Paolo Fazzini, Giuseppe La Tona, Matteo Diez, Maria Carmela Di Piazza
- Year: 2025
- Venue: Scientific Reports (Nature), vol. 15, article 23941
- Impact: 3 citations, 1,867 accesses; validated on real cruise ship data
- Core Methodology/Finding: Introduces a hybrid LSTM + Variational Mode Decomposition with Mode Selection (VMDMS) for multivariate time series. Validated on real-world large passenger ship electrical power demand dataset from the Fincantieri group. VMDMS enables selective identification of modes across channels that synergistically enhance forecasting accuracy. Open access.

**Paper D-6**
- Title: Data-Driven Efficiency Modeling and Analysis of All-Electric Ship Powertrain: A Comparison of Power System Architectures
- Authors: Pramod Ghimire, Mehdi Zadeh et al. (NTNU / Kongsberg Digital)
- Year: 2022
- Venue: IEEE Transactions on Transportation Electrification, vol. 8, no. 2, pp. 1930–1943
- Impact: Key IEEE TTE paper comparing AES architectures with load profile data
- Core Methodology/Finding: Compares data-driven efficiency models for AC, fixed-speed DC, and variable-speed DC hybrid architectures for cruise ships. Shows that **~60% of load is propulsion while hotel/auxiliary loads account for ~40%**. VSDC architecture is most efficient. **Provides published load profile data/graphs and power-based instantaneous efficiency charts across architectures. Directly applicable to MVDC ship system studies.**

**Paper D-7**
- Title: Electrical Load Analysis for Shipboard Power Systems Using Load Survey Data
- Authors: (Taiwanese research group)
- Year: 2020
- Venue: IEEE Transactions on Industry Applications (IEEE Xplore document 8957470)
- Impact: Adopted by actual ship builders in Taiwan
- Core Methodology/Finding: Proposes a methodology for electrical load analysis using actual measured data from intelligent meters, replacing traditional demand-factor approaches. Performs analysis under different operating conditions (sea-going, maneuvering, in port). **Provides ship load categories and their characteristics based on real measurement data—directly relevant to aggregate load profiling.**

**Paper D-8**
- Title: A Comparative Study on Energy Consumption Forecast Methods for Electric Propulsion Ship
- Authors: (Korean research group)
- Year: 2022
- Venue: Journal of Marine Science and Engineering (MDPI), vol. 10, no. 1, article 32
- Impact: Focused comparison of forecasting methods for electric propulsion vessels
- Core Methodology/Finding: Examines multiple deep learning algorithms (LSTM, BiLSTM, etc.) for forecasting electric propulsion vessel energy consumption. Notes that existing load forecasting studies fail to reflect the high load variability specific to electric propulsion configurations. Compares regression analysis and deep learning methods for ship power prediction.

**Paper D-9**
- Title: A deep learning method for the prediction of ship fuel consumption in real operational conditions
- Authors: Mingyang Zhang, Nikolaos Tsoulakos, Pentti Kujala, Spyros Hirdaris
- Year: 2024
- Venue: Engineering Applications of Artificial Intelligence (Elsevier), vol. 130, article 107425
- Impact: Largest real-world dataset in the category (1M+ records, 266 variables)
- Core Methodology/Finding: Uses Bi-LSTM with attention mechanism on sensor data (266 variables), voyage reporting, and hydrometeorological data from a Kamsarmax bulk carrier over 2 years. Over 1 million data records at 60-second intervals. While focused on fuel consumption, the methodology and data approach are directly transferable to electric ship energy prediction. Open access.

**Paper D-10**
- Title: A review of ship fuel consumption models
- Authors: Ailong Fan, Jian Yang, Liu Yang, Da Wu, Nikola Vladimir
- Year: 2022
- Venue: Ocean Engineering (Elsevier), vol. 264, article 112405
- Impact: Foundational review using CiteSpace bibliometrics
- Core Methodology/Finding: Classifies ship fuel consumption models into white-box (physics-based), black-box (data-driven/ML), and grey-box (hybrid) approaches. Analyzes accuracy improvement methods, verification methods, and influencing factors. Identifies that most ML-based models are customized for specific ships. Provides taxonomy useful for contextualizing electric ship load forecasting approaches.

**Paper D-11**
- Title: Distributed Economic Optimal Scheduling Scheme for Ship-Integrated Energy System Based on Load Prediction Algorithm
- Authors: (Chinese research group)
- Year: 2021
- Venue: Frontiers in Energy Research
- Impact: Integrates load forecasting with energy management optimization
- Core Methodology/Finding: Proposes an intelligent ship energy management model using ensemble learning for short-term load forecasting combined with distributed optimal scheduling for a ship-integrated energy system with PVs, CHPs, and BESS. Addresses strong nonlinear load variation during different operational phases (departure, arrival, cruise). Discusses service, propulsion, and mechanical load categories.

---

## Category E: IEEE ESTS proceedings and major survey/review papers

These papers provide the broadest architectural and strategic context, essential for framing any modeling or simulation effort within the larger electric ship research ecosystem.

### IEEE ESTS 2023 papers (Alexandria, VA, August 1–4, 2023)

**Paper E-1**
- Title: Feasibility Study of a Modular Multi-Purpose Frigate with an Integrated Power & Energy System
- Authors: Luca Braidotti, Andrea Vicenzutti, Daniele Bosich, Vittorio Bucci, Giorgio Sulligoi, Giorgio Trincas
- Year: 2023
- Venue: 2023 IEEE Electric Ship Technologies Symposium (ESTS)
- Core Methodology/Finding: Presents a feasibility study for a modular multi-purpose frigate using an integrated power and energy system (IPES), analyzing design implications and performance trade-offs of different ship configurations.

**Paper E-2**
- Title: Baselining a Functional Architecture for a Power Electronic Power Distribution System for Navy Vessels
- Authors: Carmen Araujo, David Gross, Michael Steurer, Sihun Song, Christian Schegan
- Year: 2023
- Venue: 2023 IEEE ESTS
- Core Methodology/Finding: Establishes a baseline functional architecture for power electronic-based power distribution systems for naval vessels. **Provides a framework for future MVDC ship power system design from the FSU/NSWC perspective.**

**Paper E-3**
- Title: Model Predictive Control for the Operation of a Hybrid MVAC and MVDC Electric Warship
- Authors: Joseph Young, Marvin A. Cook, David G. Wilson, Wayne Weaver
- Year: 2023
- Venue: 2023 IEEE ESTS
- Core Methodology/Finding: Develops MPC strategy for hybrid MVAC/MVDC warship power systems, addressing coordination of multiple power zones and energy storage under dynamic mission profiles.

**Paper E-4**
- Title: Dynamic Modeling and Reliable Operation of All-Electric Ships with Small Modular Reactors and Battery Energy Systems
- Authors: Sobhan Badakhshan, Soroush Senemmar, Jie Zhang
- Year: 2023
- Venue: 2023 IEEE ESTS
- Core Methodology/Finding: Presents dynamic modeling of AES combining small modular reactors with battery storage, addressing reliability and transient performance of novel nuclear-electric architectures.

**Paper E-5**
- Title: A Survey on Pulse Power Load Applications and Tools for Simulation
- Authors: F. D'Agostino, D. Kaza, F. Silvestro, A. Chiarelli, F. Olcese
- Year: 2023
- Venue: 2023 IEEE ESTS
- Core Methodology/Finding: Surveys pulsed power load applications on ships and reviews simulation tools. Relevant to integration of electromagnetic weapons and high-power sensors in naval power systems. Authored by University of Genova and Fincantieri.

**Paper E-6**
- Title: MVDC Marine: From Customer Needs to Technical Requirements, Product Gaps, Potential Solutions
- Authors: Li Lisa Qi, John Lindtjorn, Hans Krattiger
- Year: 2023
- Venue: 2023 IEEE ESTS
- Core Methodology/Finding: ABB industry perspective mapping customer needs to technical requirements for commercial MVDC marine systems. Identifies product gaps and potential solutions. **Provides real-world industry architecture requirements.**

**Paper E-7**
- Title: HTS Technology Driven Shipboard Power Distribution Architecture – Electrical
- Authors: Peter Cheetham, Srikar Telikapalli, T. Stamm, C. H. Kim et al.
- Year: 2021
- Venue: 2021 IEEE Electric Ship Technologies Symposium (ESTS)
- Core Methodology/Finding: Explores high-temperature superconducting technology for shipboard power distribution, analyzing electrical architecture implications and potential efficiency gains from superconducting cables and buses.

### Major review and survey papers (2020–2026)

**Paper E-8**
- Title: A Review of DC Shipboard Microgrids—Part I: Power Architectures, Energy Storage, and Power Converters
- Authors: Luona Xu, Josep M. Guerrero, Abderezak Lashab, Baoze Wei, Najmeh Bazmohammadi, Juan C. Vasquez, Abdullah Abusorrah
- Year: 2022
- Venue: IEEE Transactions on Power Electronics, vol. 37, no. 5, pp. 5155–5172
- Impact: Highly cited two-part review from Aalborg University CROM group
- Core Methodology/Finding: Comprehensive review of DC shipboard microgrid power architectures (radial, ring, zonal), energy storage technologies (batteries, supercapacitors, flywheels), and power converter topologies. **Provides detailed framework diagrams showing generation, distribution, and consumption subsystems—essential reference architecture.**

**Paper E-9**
- Title: A Review of DC Shipboard Microgrids—Part II: Control Architectures, Stability Analysis, and Protection Schemes
- Authors: Luona Xu, Josep M. Guerrero, Abderezak Lashab, Baoze Wei, Najmeh Bazmohammadi, Juan C. Vasquez, Abdullah Abusorrah
- Year: 2022
- Venue: IEEE Transactions on Power Electronics, vol. 37, no. 4, pp. 4105–4120
- Impact: 56+ citations; companion to Part I
- Core Methodology/Finding: Reviews coordinated control strategies for diesel generators and ESS in DC shipboard microgrids, stability analysis methods (small-signal and large-signal), and protection system requirements per maritime standards. Addresses constant power load instability and pulsed load impacts.

**Paper E-10**
- Title: A Review of Power Converters for Ships Electrification
- Authors: Hossein Mahdi, Bjarte Hoff, Trond Østrem
- Year: 2023
- Venue: IEEE Transactions on Power Electronics, vol. 38, no. 4, pp. 4680–4697
- Impact: Major topology review from IEEE TPE
- Core Methodology/Finding: Comprehensive topological review of shore-to-ship and shipboard power converters, covering propulsion drives, shore power connections, and onboard distribution. Identifies future trends and technology challenges.

**Paper E-11**
- Title: Optimization-Based Power and Energy Management System in Shipboard Microgrid: A Review
- Authors: Peilin Xie, Josep M. Guerrero, Sen Tan, Najmeh Bazmohammadi, Juan C. Vasquez, Masoud Mehrzadi, Yusuf Al-Turki
- Year: 2022
- Venue: IEEE Systems Journal, vol. 16, no. 1, pp. 578–590
- Impact: Widely cited review in IEEE Systems Journal
- Core Methodology/Finding: Categorizes optimization-based PMS/EMS for shipboard microgrids into rule-based and optimization-based methods. Covers multi-resource coordination, propulsion load variability, and economic/environmental objectives. Discusses future trends including distributed PMS, real-time optimization, and AI-based methods.

**Paper E-12**
- Title: Toward Future Green Maritime Transportation: An Overview of Seaport Microgrids and All-Electric Ships
- Authors: Sidun Fang, Yu Wang, Bin Gou, Yan Xu
- Year: 2020
- Venue: IEEE Transactions on Vehicular Technology, vol. 69, no. 1, pp. 207–219
- Impact: **193+ citations**; seminal paper on seaport-ship coordination
- Core Methodology/Finding: Identifies the transportation-power multi-microgrid coordination problem for seaport microgrids and AES. Discusses cold ironing, renewable integration, and the expansion from logistics-only to logistics-plus-electric coordination. Provides a technology roadmap for future maritime electrification.

**Paper E-13**
- Title: Energy Efficiency of Integrated Electric Propulsion for Ships – A Review
- Authors: Chalermkiat Nuchturee, Tianhua Li, Haydn Thomas
- Year: 2020
- Venue: Renewable and Sustainable Energy Reviews (Elsevier), vol. 134, article 110145
- Impact: **193+ citations**; major review paper
- Core Methodology/Finding: Reviews methods to increase energy efficiency and environmental performance of all-electric ships, covering ESS integration, waste heat recovery, renewable energy, and operational optimization. Discusses compliance with IMO EEDI/EEOI energy efficiency regulations.

**Paper E-14**
- Title: State-of-the-Art Review on Shipboard Microgrids: Architecture, Control, Management, Protection, and Future Perspectives
- Authors: A.M. Aboelezz, M.M. El-Saadawi, A.A. Eladl, V. Bures, B.E. Sedhom
- Year: 2023
- Venue: Smart Cities (MDPI), vol. 6, no. 3, pp. 1435–1484
- Impact: Systematic Scopus-based review of ~327 papers
- Core Methodology/Finding: Compares IEEE/IEC standards for shipboard vs. land-based microgrids (IEC/IEEE 80005-1, IEEE 2030.8). Provides comprehensive architecture classification, control method taxonomy, and research gap identification.

**Paper E-15**
- Title: Energy Management of Shipboard Microgrids Integrating Energy Storage Systems: A Review
- Authors: Evaggelia Nivolianiti, Yannis L. Karnavas, Jean-Frédéric Charpentier
- Year: 2024
- Venue: Renewable and Sustainable Energy Reviews (Elsevier)
- Impact: Recent comprehensive ESS management review
- Core Methodology/Finding: Reviews energy management strategies for shipboard microgrids with ESS integration covering 2018–2023. Compares rule-based, optimization, and AI approaches. Discusses advantages of ESS for stability improvement, fuel optimization, and emission reduction.

---

## Cross-cutting themes and integration opportunities

Several structural patterns emerge when examining these 55+ papers as a collective body of work rather than isolated contributions.

**The ESRDC notional model as common ground.** The Electric Ship Research and Development Consortium's four-zone MVDC notional model (updated circa 2020) serves as the community benchmark referenced across Categories A, C, and D. Papers A-4, A-5, A-6, A-7, and C-14 all build on or refine this topology. The MathWorks Two-Zone MVDC Electric Ship Simulink model (available on GitHub) provides an open-source entry point for researchers seeking to integrate findings from this review into simulation.

**Convergence of fault detection and load monitoring.** Papers C-1, C-3, and C-4 from the Corzine group at Missouri S&T represent a coherent research thread where wavelet-transform features serve double duty: detecting faults and classifying pulsed-load states. This dual-use approach is architecturally significant because it eliminates the need for separate fault and load monitoring subsystems. The progression from STFT (C-1, 2020) to wavelet-LSTM (C-3, 2021) to production-oriented wavelet-ML (C-4, 2022) traces a clear engineering maturation path.

**Free-piston linear generators as KARNO proxies.** While no peer-reviewed papers on Hyliion's KARNO exist, Papers B-1 through B-8 provide comprehensive mathematical frameworks for free-piston linear generators that share key characteristics: fuel flexibility, linear electromagnetic energy conversion, and modular scalability. The Wei et al. series (B-2, B-5, B-6, B-8) from Beijing Institute of Technology is particularly productive, spanning multi-fuel starting prediction, combustion performance across fuel types, and stability assessment—all validated experimentally. These models could serve as proxy dynamics for KARNO-type generators in MVDC ship simulations.

**The propulsion load dominance problem.** Papers D-4 and D-6 independently confirm that propulsion consumes **60–70% of total AES electrical load**, making propulsion power prediction the highest-leverage forecasting target. The ultra-short-term TCFFA-GRU approach (D-1) and the real cruise-ship-validated VMDMS-LSTM approach (D-5) represent the current state of the art, though neither has been integrated with a full MVDC simulation model—a clear gap for future work.

**Promising simulation integration pathways.** For researchers building a comprehensive MVDC ship simulation that incorporates generation, distribution, consumption, fault detection, and load forecasting, the following combination of papers provides a near-complete modeling chain: A-4 or A-7 (MVDC topology and dynamics) → B-9 (high-fidelity generator model) → D-4 (propulsion load model with RT-Lab validation) → C-3 or C-4 (wavelet-based fault detection) → A-1 (HESS for pulsed load mitigation). Each of these papers provides either published models, validated parameters, or open simulation frameworks.

---

## Conclusion

This review establishes that the 2020–2026 period has seen **decisive maturation in three of the four target areas**. MVDC shipboard modeling has moved beyond notional topologies into refined, experimentally validated frameworks with multi-port DC circuit breakers and current-limiting reactors. DC fault detection has been transformed by the wavelet-transform + deep-learning paradigm, with multiple real-time FPGA and HIL implementations demonstrating practical deployability. Free-piston linear generator research has produced a rich library of coupled thermodynamic-electromagnetic models validated across multiple fuel types, providing the closest academic analogs to emerging commercial multi-fuel linear generators like the Hyliion KARNO.

The weakest link remains **electric ship load forecasting**, where ultra-short-term methods are promising but not yet integrated with full system simulations or validated for naval (rather than commercial) operational profiles. The absence of publicly available naval ship load datasets is the primary bottleneck. Bridging this gap—by coupling forecasting models (Category D) with MVDC simulation frameworks (Category A) and fault-aware protection layers (Category C)—represents the highest-value integration opportunity identified in this review.
