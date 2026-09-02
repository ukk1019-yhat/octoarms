# 🦾 OCTOARMS

**8-DOF Modular Robotic Arm System — Interactive 3D Showcase**

OCTOARMS is a high-precision, eight-armed robotic system inspired by the flexibility of an octopus. This repository contains an interactive, browser-based 3D showcase built with **Three.js** — explore the full robot, swap tools, cycle poses, browse components, and even take the robot for a walk.

> 🔗 **Live demo:** [https://octoarms.vercel.app](https://octoarms.vercel.app)

---

## ✨ Features

- **8 independent arms · 8 DOF each** — fully articulated in real time
- **Pose system** — Idle, Reach, Wave, Compact, Inspect, and Walk modes with smooth transitions
- **Interchangeable end effectors** — Precision Gripper, Vacuum Gripper, Screw Driver, Micro Manipulator
- **Mounting options** — Table, Wall, and Ceiling orientations
- **Component browser** — click any part (base, hub, joints, links, tools) to view specs, materials, and engineering details
- **Detach / reattach** — yank components off the robot and animate them back
- **Walk mode** — keyboard (WASD / arrows) on desktop, touch D-pad on mobile, plus voice commands
- **Microphone control** — say "reach", "walk", "forward", "speed 1.5" and more
- **Live joint-angle readout** — per-arm degrees for every joint

### Specs
| | |
|---|---|
| DOF | 8 / arm |
| Payload | 2.5 kg |
| Reach | 850 mm |
| Repeatability | ±0.05 mm |
| Power | 48V DC |
| Communication | EtherCAT |
| Weight | 28 kg |

---

## 🎮 Controls

| Desktop | Mobile |
| --- | --- |
| Drag — rotate view | Drag — rotate view |
| Scroll — zoom | Pinch — zoom |
| Right-click — pan | Two-finger drag — pan |
| WASD / Arrow keys — walk | On-screen D-pad — walk |
| Click robot part — inspect component | Tap robot part — inspect component |

### Voice commands 🎤
`idle` · `reach` · `wave` · `compact` · `inspect` · `walk` · `stop` · `forward` / `back` / `left` / `right` · `faster` / `slower` / `speed 1.5` · part names (`shoulder`, `elbow`, `gripper`, …) · `detach` · `attach` · `flip` · `help`

---

## 🛠 Built With

- **Three.js** — 3D rendering (loaded via import maps + CDN, no bundler needed)
- **HTML / CSS** — custom design system, fully responsive (mobile drawers, touch controls, safe-area aware)
- **Vercel** — static deployment

The entire experience is a single static `index.html` — no build step, no server.

---

## 🚀 Run Locally

```bash
# clone it
git clone https://github.com/ukk1019-yhat/octoarms.git
cd octoarms

# it's static — just serve the folder
python -m http.server 8000
# or
npx serve .
```

Then open **http://localhost:8000**.

> Implementation note: Web Speech (voice control) requires `https` or `localhost`, so run via HTTPS in production.

---

## ☁️ Deploy to Vercel

```bash
npm i -g vercel
vercel --prod
```

Or connect the repo in the [Vercel dashboard](https://vercel.com) — it auto-detects a static site.

---

## 📁 Project Structure

```
octoarms/
├── index.html      # entire app — scene, robot, UI, interactions
├── favicon.svg     # octagon tab icon
└── README.md
```

---

## 🔍 Feature Walkthrough

1. **Inspect parts** — click any joint or link. A panel opens with material, purpose, and specs; the camera auto-focuses and the part highlights copper.
2. **Browse components** — hit `BROWSE` (desktop) or `≡` (mobile), pick a category, and the robot highlights every matching part.
3. **Swap tools** — pick a different end effector and all 8 arms update instantly.
4. **Change mounting** — flip the robot from table to wall to ceiling.
5. **Go for a walk** — select *Walk* (or use the D-pad / voice), then steer and adjust speed with the slider.

---

## 📄 License

© 2026 OCTOARMS. Open for personal and educational use.