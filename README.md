# 🧠 Ultimate Attentional Selection Simulator

An interactive, browser-based neural microcircuit simulation demonstrating the **Biased Competition Model** of visual attention. Watch signal-vs-noise competition happen in real-time, driven by Wilson-Cowan population dynamics and visualized with live action-potential spike particles.

![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen)
![Vanilla JS](https://img.shields.io/badge/Tech-Vanilla_JavaScript-f7df1e)
![HTML5 Canvas](https://img.shields.io/badge/Render-HTML5_Canvas-e34f26)

## 🎯 What is this?

The brain processes hundreds of competing stimuli at any given moment. How does it decide what to focus on? 

According to the Biased Competition Model, **inhibitory interneurons** act as a dynamic filter. They amplify attended signals and suppress distracting noise through local and lateral inhibition. This project simulates a simplified cortical layer containing three sensory columns. You can interact with the neuromodulatory environment and watch the circuit resolve the competition.

### ✨ Features
* **Live Spike Particle Engine:** Watch action potentials travel along axons in real-time based on calculated firing rates.
* **Wilson-Cowan Dynamics:** Mathematically rigorous integration of Excitatory (Pyramidal) and Inhibitory (PV+, SST+, VIP+) cell populations running at 60fps.
* **LFP Oscilloscope:** Real-time waveform generation showing the emergence of Gamma (~40Hz) and Alpha (~10Hz) band oscillations.
* **Dynamic SNR Meters:** Live Signal-to-Noise ratio calculations for each column.
* **Interactive Dashboard:** Tweak Acetylcholine (ACh) levels, top-down attentional bias, noise floors, and sensory input strengths on the fly.
* **Interneuron Inspector:** Click through the cell types to learn how PV+, SST+, and VIP+ cells wire together to create attentional gating.

## 🔬 The Science (How it Works)

The simulation uses **Wilson-Cowan rate equations** to model the average firing rates ($r$) of the four neural populations. The differential equation for each population updates continuously:

$$\tau \frac{dr_i}{dt} = -r_i + f(W_{EE}E_i - W_{IE}\sum I_{competitors} + Input + Bias)$$

The magic happens in the specific wiring of the interneurons:
1. **Top-Down Bias** (Attention) strongly excites **VIP+** interneurons.
2. **VIP+** cells inhibit **SST+** cells (which normally suppress the column). This is called *disinhibition*.
3. Released from suppression, the **Pyramidal** (Excitatory) cells fire rapidly, generating a strong signal.
4. Pyramidal cells excite local fast-spiking **PV+** basket cells.
5. **PV+** cells send powerful **lateral inhibition** across to the other columns, shutting down the competitor/distractor signals.

## 🚀 Getting Started

This project is built with **100% Vanilla HTML, CSS, and JavaScript**. There is no backend, no build step, and no `node_modules` folder.

1. Clone the repository:
   ```bash
   git clone [https://github.com/zaros67tg/attentional-selection-sim.git](https://github.com/zaros67tg/attentional-selection-sim.git)

2. Open index.html in any modern web browser.

       Start tweaking the sliders!

## 🛠️ Tech Stack
     
    Logic & Math: Vanilla JavaScript (requestAnimationFrame loop, Euler method integration).

    Rendering: HTML5 <canvas> for the circuit routing, spike particles, and the live oscilloscope traces.

UI/UX: CSS Grid/Flexbox with glassmorphic styling and CSS transitions.

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page. If you want to expand this to a 2D cortical sheet or add NMDA/AMPA receptor kinetics, open a pull request!

## 📝 License
  ![This project is MIT licensed](https://choosealicense.com/licenses/mit/))
