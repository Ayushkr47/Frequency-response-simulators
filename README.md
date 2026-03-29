# 🎛️ Frequency Response Simulator

An interactive, browser-based audio engineering tool that simulates frequency response curves across the full audible spectrum (20 Hz – 20 kHz). Built as a standalone HTML file — no installs, no dependencies, just open and run.

> Inspired by the real-world challenges of audio product design in India — from earbuds and home theaters to concert halls and car audio systems.

---

## 🖥️ Live Demo

Open `frequency_response_simulator.html` directly in any modern browser. No server required.

---

## ✨ Features

### 🔊 Device Presets
Six real-world audio profiles to simulate instantly:

| Preset | Description |
|---|---|
| Studio Monitor | Flat reference response for critical listening |
| Hi-Fi Headphones | Elevated treble with ear-canal resonance |
| Bluetooth Speaker | Limited bass extension, mid-focused |
| Car Audio | Cabin-tuned with bass lift |
| In-Ear Monitor | High sensitivity, pronounced upper mids |
| Concert Hall PA | Full-range, high-SPL reinforcement |

### 📈 Frequency Response Chart
- Logarithmic frequency axis (20 Hz – 20 kHz)
- Real-time animated curve with gradient fill
- dB grid with 0 dB reference line
- Overlayable analysis layers:
  - **Reference Curve** — flat ideal target
  - **Room Correction** — simulated acoustic environment effect
  - **Harmonic Distortion** — THD artifact layer
  - **Phase Response** — phase deviation plot

### 🎚️ Signal Controls
- **Input Gain** — ±24 dB global level adjustment
- **Bass Boost** — shelf filter centered around 200 Hz (±12 dB)
- **Treble Roll-off** — variable high-frequency cutoff (8 kHz – 20 kHz)
- **Room Size** — scales acoustic reflections (Small → Arena)

### 🎛️ 10-Band Parametric EQ
Vertical drag sliders for hands-on frequency shaping across:
`32Hz · 64Hz · 125Hz · 250Hz · 500Hz · 1kHz · 2kHz · 4kHz · 8kHz · 16kHz`

Each band shows live dB readout and feeds directly into the main response curve.

### 🏠 Room Acoustics Simulation
Animated 2D room canvas with propagating sound waves and RT60 reverberation estimates for four environments:

| Room | RT60 |
|---|---|
| Studio | ~0.2s |
| Concert Hall | ~1.8s |
| Car Cabin | ~0.1s |
| Outdoor | ~0.05s |

### 📊 Decay Waterfall
A scrolling time-domain spectrogram showing how energy decays across the frequency spectrum over time — updated every ~500ms.

### 📐 Live Metrics
| Metric | Description |
|---|---|
| Flat Range | ±3 dB usable bandwidth |
| Resonance Peak | Frequency of highest deviation |
| THD Estimate | Total harmonic distortion (%) |
| Quality Score | Overall simulation quality out of 100 |

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/Ayushkr47/Frequency-response-simulators.git

# Open in browser
open frequency_response_simulator.html
# or just double-click the file
```

No build step. No npm install. No Python server. Just HTML + vanilla JS + Canvas API.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Rendering | HTML5 Canvas API |
| Styling | Pure CSS with CSS variables |
| Logic | Vanilla JavaScript (ES6+) |
| Fonts | Google Fonts — Syne + Space Mono |
| Animation | `requestAnimationFrame` loop |

Zero external JavaScript libraries. Zero frameworks. Zero dependencies.

---

## 📁 Project Structure

```
Frequency-response-simulators/
└── frequency_response_simulator.html   # Complete app — all HTML, CSS, JS in one file
```

---

## 🧠 How It Works

The simulator models frequency response using a **piecewise linear interpolation** approach across a set of measured anchor points per device preset. On top of the base curve, it applies:

1. **Gain** — flat offset in dB
2. **Bass shelf** — Gaussian-weighted boost/cut centered at 200 Hz
3. **Treble rolloff** — linear attenuation above the cutoff frequency
4. **EQ bands** — Gaussian bell filters at each 1/3-octave center frequency

All curves update in real time as you interact with any control.

---

## 🎯 Use Cases

- Audio engineering education and demos
- Product design exploration (headphones, speakers, PA systems)
- Acoustic consulting presentations
- Conference and classroom demonstrations
- Prototyping DSP filter behavior without hardware

---

## 🗺️ Roadmap

- [ ] Export frequency response curve as PNG/SVG
- [ ] Import measured `.frd` (Frequency Response Data) files
- [ ] Multi-curve comparison mode (A/B testing)
- [ ] Mobile-responsive layout
- [ ] Microphone input for live room measurement (Web Audio API)
- [ ] Save/load custom presets (localStorage)

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

```bash
# Fork the repo, make your changes, then open a PR against main
```

---

## 📄 License

This project is open source. Feel free to use, modify, and distribute.

---

## 👤 Author

**Ayush Kumar**
[@Ayushkr47](https://github.com/Ayushkr47)

---

*Built to bring frequency response simulation to engineers, students, and audio enthusiasts across India and beyond.*
