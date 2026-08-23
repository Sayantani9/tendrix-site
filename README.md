# TENDRIX — Bio-Inspired Tentacle Gripper Robotic Arm

<p align="center">
  <b>Bio-Inspired Adaptive Robotic Arm with ML-Assisted Manipulation & Emergency Safe Homing</b>
</p>

<p align="center">
  L&T Techgium Hackathon Finalist • Industrial Robotics • Computer Vision • Machine Learning • Embedded Systems • Safety Engineering
</p>

<p align="center">
  <img src="https://img.shields.io/badge/L%26T-Techgium%20Finalist-0A66C2?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Prototype-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Platform-ESP32-important?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/CAD-SolidWorks-orange?style=for-the-badge"/>
</p>

<p align="center">
  🔗 <b><a href="https://tendrix-site.vercel.app/">Live project site</a></b> · 
  💻 <a href="https://github.com/Sayantani9/tendrix-site">Source (this repo)</a>
</p>

---

## Table of contents

- [Project at a glance](#project-at-a-glance)
- [The industrial problem](#the-industrial-problem)
- [Key innovations](#key-innovations)
  - [1. Bio-inspired tentacle gripper](#1-bio-inspired-tentacle-gripper)
  - [2. Cable-tendon actuation](#2-cable-tendon-actuation)
- [System architecture](#system-architecture)
- [Emergency power-loss system](#emergency-power-loss-system)
- [L&T Techgium recognition](#lt-techgium-recognition)
- [Media](#media)
- [Repository structure](#repository-structure)
- [Running this site locally](#running-this-site-locally)
- [Deployment](#deployment)
- [Roadmap](#roadmap)
- [Project leadership](#project-leadership)
- [License](#license)

---

## Project at a glance

TENDRIX is a **bio-inspired cable-tendon robotic arm** designed for **safe, adaptive industrial manipulation**.

The system combines:

- A multi-segment **tentacle-inspired gripper**
- **Cable-tendon actuation** for lightweight adaptive manipulation
- **Computer vision and machine-learning-assisted grasping**
- A **power-loss emergency control system**
- **Supercapacitor-backed emergency operation**
- Controlled payload release and **safe autonomous homing**

The central idea is simple:

> **Make industrial manipulation more adaptive like biology, while making failure recovery more deliberate and safety-centric.**

Unlike conventional robotic manipulators that may abruptly stop or drop payloads during electrical failures, TENDRIX introduces a **supercapacitor-backed emergency landing control architecture** capable of executing a safe descent, controlled object release, and autonomous homing sequence.

The project focuses on:

- Industrial safety
- Adaptive manipulation
- Modular robotics
- Intelligent automation
- Embedded emergency control

---

## The industrial problem

Modern manufacturing environments use robotic manipulators for:

- Fragile components
- Irregular industrial parts
- Packaging materials
- Precision assemblies
- Glass products
- Electronic modules

A sudden power outage can cause:

- Uncontrolled arm stoppage
- Payload dropping
- Collision with nearby equipment
- Production damage
- Operator safety hazards
- Recovery downtime

Traditional robotic systems can require complex recovery procedures and additional safety hardware.

**TENDRIX addresses this challenge by combining mechanical adaptability with intelligent emergency control**, framed around the guiding question posed at Techgium:

> *"How can robotic manipulators safely handle unexpected power outages while maintaining adaptive grasping capability for objects of varying geometry and fragility?"*

---

## Key innovations

### 1. Bio-inspired tentacle gripper

The end-effector is inspired by **octopus tentacle mechanics**, allowing the gripper to conform around objects rather than relying solely on rigid contact points.

| Capability | Benefit |
|---|---|
| Adaptive surface contact | Better conformity to object geometry |
| Improved grip stability | More reliable manipulation |
| Irregular geometry handling | Wider object compatibility |
| Reduced contact pressure | Safer handling of fragile objects |
| Multi-point contact | Improved grasp distribution |
| Modular segments | Easier experimentation and replacement |

The gripper terminates in a **micro-claw** at each tentacle tip for fine manipulation, and the whole assembly is built from **multi-segmented tentacles** that flex independently.

### 2. Cable-tendon actuation

Instead of mounting heavy actuators directly near the gripper, TENDRIX uses a **cable-tendon transmission architecture** — all servo motors are **base-mounted**, and motion is transmitted up the arm through a **belt-drive transmission** riding on a **360° rotating base plate**.

Benefits:

- Reduced moving inertia
- Faster dynamic response
- Lower end-effector weight
- Improved energy efficiency
- Simplified maintenance
- Modular actuation

---

## System architecture

The manipulation pipeline runs end-to-end from perception to grasp:

```text
Camera
   ↓
Computer Vision
   ↓
Object Classification
   ↓
Grasp Planner
   ↓
Motion Controller
   ↓
Cable-Tendon Arm
   ↓
Bio-Tentacle Gripper
```

Each stage hands off exactly one decision to the next: the camera feeds raw frames to a computer-vision layer, which classifies the object in view; a grasp planner then selects an approach and contact strategy suited to that object's geometry; the motion controller converts that plan into base-motor commands; those commands travel down the cable-tendon transmission to the arm; and the bio-tentacle gripper executes the final adaptive grasp.

---

## Emergency power-loss system

TENDRIX's signature safety feature is its **power-loss emergency control system**:

- A **base-mounted supercapacitor bank** supplies enough reserve energy to carry out a pre-programmed **safe-release-and-homing** sequence
- An **ESP32 microcontroller** continuously monitors power status via **current sensors**
- The backup system activates **instantly** the moment a power drop is detected — no operator intervention required
- **Integrated DC-DC conversion** ensures stable motor operation throughout the emergency sequence
- The arm safely releases its payload (rather than dropping it uncontrolled) and **autonomously returns to a safe home position**

Because of its modularity, low weight, and affordability, this design is intended to be dependable and safe in dynamic manufacturing environments — and feasible for both hackathon-grade rapid prototyping and industrial deployment.

---

## L&T Techgium recognition

TENDRIX was developed and presented as an **L&T Techgium Hackathon Finalist**, under the problem statement:

**"Flexible Robotic Arm for Safe and Adaptive Industrial Operations"** (Digital Manufacturing track)

**Statement:** Design a flexible robotic arm system that can be easily integrated into manufacturing setups. The system should support adaptive gripping for objects of various sizes, include reserve power capabilities to safely release objects during power failures, and enable automatic homing. The solution should also simplify installation and maintenance by minimizing cabling and improving modularity.

**Background:** In industrial environments requiring precise and adaptive movements, traditional robotic arms often face limitations such as positional inaccuracies due to belt flex, complex homing procedures, and vulnerability to abrupt power losses. These issues can disrupt operations and damage equipment or products. Additionally, the ability to grip objects of varying sizes and the complexity of setup — often involving extensive cabling — pose challenges for integration and maintenance.

**Deliverables:** A working prototype or concept design of a robotic arm system featuring adaptive gripping mechanisms for variable object sizes, reserve power functionality for safe object release and homing during outages, and simplified integration and setup with reduced cabling — documented with system architecture, control logic, and use-case demonstrations in industrial scenarios.

---

## Media

The project site ([tendrix-site.vercel.app](https://tendrix-site.vercel.app/)) includes:

- Annotated CAD assembly renders (SolidWorks) — front and side views
- A use-case concept illustration (adaptive sorting by material type)
- Three demonstration videos of the physical prototype
- The full Techgium abstract submission

All source images and videos live in [`/assets`](./assets) in this repository.

---

## Repository structure

```text
tendrix-site/
├── index.html          # Single-page site markup
├── styles.css           # Blueprint/schematic-inspired styling
├── script.js             # Scroll-reveal interaction
├── vercel.json           # Vercel static-site config
├── assets/
│   ├── robotic-arm-hero.jpeg          # Annotated CAD front view
│   ├── robotic-arm-side.jpeg          # Use-case concept illustration
│   ├── robotic-arm-side2.jpeg         # Techgium abstract submission
│   ├── robotic-arm-hero-video.mp4     # Demo — hero
│   ├── robotic-arm-hero-video2.mp4    # Demo — hero alternate
│   └── robotic-arm-video.mp4          # Demo — full run
└── README.md
```

No build step, no package manager, no dependencies — plain HTML/CSS/JS.

---

## Running this site locally

```bash
git clone https://github.com/Sayantani9/tendrix-site.git
cd tendrix-site
# then just open index.html in a browser, or serve it:
python3 -m http.server 8000
# visit http://localhost:8000
```

---

## Deployment

Live on Vercel: **[tendrix-site.vercel.app](https://tendrix-site.vercel.app/)**

To redeploy after changes:

```bash
git add .
git commit -m "update"
git push origin main
```

Vercel auto-deploys on every push to `main`.

---

## Roadmap

- [ ] Publish full CAD assembly files
- [ ] Document the ML-assisted grasp-planning model
- [ ] Add wiring diagrams for the ESP32 / supercapacitor emergency circuit
- [ ] Record a full end-to-end pick-and-place demo under simulated power loss
- [ ] Write up BOM (bill of materials) and cost breakdown

---

## Project leadership

**Sayantani Banerjee**
Project Team Lead • Systems Integration Lead • AI & Robotics Researcher
Founder of SHUDDH • Computer Vision • Embedded Systems • Sustainable Automation • Research & Innovation

- GitHub: [@Sayantani9](https://github.com/Sayantani9)
- LinkedIn: [g-sayantani-mb-65337230b](https://www.linkedin.com/in/g-sayantani-mb-65337230b/)
- Email: [smb.workspace9@gmail.com](mailto:smb.workspace9@gmail.com)

---

## License

MIT — see [LICENSE](./LICENSE) for details.
