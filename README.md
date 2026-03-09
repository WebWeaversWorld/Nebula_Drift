# Nebula Drift

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Java](https://img.shields.io/badge/Java-17+-orange)
[![Download](https://img.shields.io/badge/Download-Nebula_Drift.jar-purple?logo=github)](https://github.com/WebWeaversWorld/Nebula_Drift/releases/download/java/Nebula_Drift.jar)

---

[![Open Issues](https://img.shields.io/github/issues/WebWeaversWorld/Nebula_Drift)](https://github.com/WebWeaversWorld/Nebula_Drift/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/WebWeaversWorld/Nebula_Drift)](https://github.com/WebWeaversWorld/Nebula_Drift/pulls)

A fast-paced **arcade space survival game** built in pure **Java Swing**.

Pilot a drifting spacecraft through a colourful nebula, dodge enemies, collect power-ups, and rack up points while surviving increasingly chaotic waves.

This project is part of the **Web Weavers World Code Lab**.

---

# Gameplay

The player controls a triangular spacecraft drifting through a starfield while enemies spawn continuously from the top of the screen.

Enemies appear in **rainbow colours**, each shape representing different types and point values.

Power-ups fall from above and grant temporary abilities like shields, missiles, and speed boosts.

The goal is simple:

**Survive as long as possible and achieve the highest score.**

---

# Controls

| Action          | Key               |
| --------------- | ----------------- |
| Move            | Arrow Keys / WASD |
| Fire Laser      | Space             |
| Fire Missile    | M                 |
| Start Game      | Enter             |
| Restart         | R                 |
| Return to Title | ESC               |

---

# Features

### Arcade Gameplay

* Continuous enemy spawning
* Score system based on enemy colour
* Increasing difficulty over time

### Player Weapons

* Laser cannon (multi-shot upgrades)
* Missile launcher
* Weapon upgrades through power-ups

### Power-Ups

| Power   | Effect                         |
| ------- | ------------------------------ |
| Shield  | Temporary protection           |
| Slow    | Slows enemy movement           |
| Bomb    | Destroys all enemies on screen |
| Bonus   | Instant score bonus            |
| Boost   | Increased speed and multi-shot |
| Missile | Enables missile weapon         |

Power-ups are handled through the `PType` enum and applied using the `applyPower()` method. 

---

# Enemy Types

Enemies are procedurally spawned with different behaviours using the `EType` enum. 

| Enemy    | Behaviour              |
| -------- | ---------------------- |
| GRUNT    | Basic falling enemy    |
| DIVER    | Tracks player position |
| SHOOTER  | Fires projectiles      |
| TANK     | High HP, slower        |
| SWARMER  | Moves horizontally     |
| WANDERER | Random drifting        |
| BOSS     | High HP enemy          |

Enemies are represented by different polygon shapes and colours. 

---

# Graphics

The game renders using **Java2D** with anti-aliasing enabled.

Visual elements include:

* Animated starfield background
* Polygon enemies
* Glowing player ship
* Drift trails
* Engine thrusters
* Power-up glow effects

The starfield is generated using layered stars with different velocities. 

---

# Audio System

Nebula Drift uses a **low-latency procedural sound synthesizer** instead of audio files.

The `SFX` system generates sound waves in real time using:

* Sine
* Square
* Triangle
* Noise

Sounds are produced using `SourceDataLine` from the Java Sound API. 

Sound effects include:

* Laser shots
* Explosions
* Power-ups
* Score pings
* Player hits

This allows extremely small builds without external sound assets.

---

# Scoreboard

Scores are saved locally using Java's **Preferences API**.

The game stores and displays a persistent **Top 10 leaderboard**. 

---

# Resolution

```
720 x 480
```

Configured in the game constants.

---

# Architecture

Main class:

```
Nebula_Drift
```

Game loop uses:

```
javax.swing.Timer (≈60 FPS)
```

Core components:

```
Nebula_Drift
├── Bullet
├── Missile
├── Enemy
├── Power
├── Star
└── SFX
```

Rendering and logic are handled inside the main JPanel.

---

# Building

Compile:

```bash
javac -d out Nebula_Drift.java
```

Create the JAR:

```bash
jar cfe Nebula_Drift.jar Nebula_Drift.Nebula_Drift -C out .
```

Run:

```bash
java -jar Nebula_Drift.jar
```

---

# Requirements

* Java JDK 17+
* Works on Windows / Linux / macOS

---

# Future Ideas

Possible upgrades:

* Menu system
* Wave progression
* Boss battles
* Enemy projectiles
* Helper drones
* Soundtrack support
* Particle explosions

---

# Author

**Web Weavers World**

Experimental Java game project from the Code Lab.
