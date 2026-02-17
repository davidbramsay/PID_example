# PID Motor Control Lab

An interactive, browser-based lab for learning PID control through progressive simulation exercises. Each lesson adds a new real-world complication to a motor model, teaching students *why* each PID term exists and when it breaks down.

## 🚀 Live Demo

Host this on GitHub Pages: push to a repo, enable Pages in Settings → Pages → Deploy from branch (`main`, root), and visit `https://yourusername.github.io/pid-lab/`.

Or just open `index.html` in a browser — it's a single self-contained file with no dependencies.

## 📚 Lessons

| # | Title | Concept Taught |
|---|-------|----------------|
| 1 | **The Ideal Motor** | Pure integrator. P=10 is deadbeat. P>20 is unstable. Even the simplest system has stability limits (z-plane). |
| 2 | **Adding Inertia** | Double integrator (mass). P alone oscillates forever. Introduces the **D term** as a brake. Critical damping. |
| 3 | **Friction & Stiction** | Coulomb friction creates a dead zone. P can't push through. Introduces the **I term** to accumulate force. |
| 4 | **Integral Windup** | Actuator saturation + I term = massive overshoot. Introduces **anti-windup** clamping. |
| 5 | **Sensor Noise** | High-frequency noise + D term = chaos. Differentiation is a high-pass filter. Introduces **derivative filtering**. |
| 6 | **Backlash** | Gear play creates limit cycles no PID can eliminate. Mechanical quality matters. |
| 7 | **Gear Slippage** | High jerk causes gears to slip. Step commands are mechanically violent. Introduces **S-curve commands**. |
| 8 | **Command Shaping** | Same PID, four different trajectories: step, ramp, S-curve, smootherstep. Command quality > controller quality. |
| 9 | **Sensor Drift** | Encoder drift (dead reckoning). I term amplifies drift. Why absolute references are essential. |
| 10 | **The Full Challenge** | Everything combined. Tune for minimum RMS error. Real-world tradeoffs. |

## 🎯 How to Use

1. Read the lesson description in the left panel
2. Adjust PID gains using the sliders
3. Click **Run** (or press Enter) to simulate
4. Observe three plots: Position, Control Signal, and Error
5. Follow the "Try This" challenges to build intuition
6. Use Alt+← / Alt+→ to navigate between lessons

## 📊 What the Plots Show

- **Position plot**: Gold = setpoint, White = true position, Green = measured position (when noisy/drifting)
- **Control signal**: Blue = force command to motor, Red dashed = actuator saturation limits
- **Error plot**: Blue = true error (setpoint − actual), Orange = measured error (what the controller sees)

## 🔧 Technical Details

- Physics runs at 500 Hz (semi-implicit Euler integration)
- Control loop runs at 100 Hz
- Single self-contained HTML file, no build tools or dependencies
- All simulation in vanilla JavaScript, plots on HTML5 Canvas

## 📖 Course Context

Designed for a systems & control lecture covering:
- 3D printer control chain (G-code → firmware → steppers)
- Dead reckoning and feedback control
- PID tuning (Ziegler-Nichols, empirical)
- State space representation
- Kalman filtering and sensor fusion
- Linear systems and z-plane stability analysis

## License

MIT — use freely for teaching.
