# HTP — Projectile Life System

**A micro-framework that gives every skill/projectile its own HP — enabling decay, clash, damage, and energy drain — to create deep, emergent combat in RPG/ARPG/MMO systems.**

---

## 🧠 Overview

The **Projectile Life System** redefines how skills and projectiles behave in combat. Instead of being static, scripted effects, each projectile becomes a **living entity** with its own **HP (SkillLife)** that can decay, clash, be damaged, or drained. This creates a **dynamic combat ecosystem** where skills interact with each other, not just with enemies.

This framework is designed for **RPGs, ARPGs, MMOs, MOBAs, and fantasy shooters**, and is fully compatible with other HTP systems like **Relative Defense** and **Armor Layering**.

---

## 🔍 Core Mechanics

1. **Skill HP (SkillLife)**  
   - Each skill has a base HP:  
     \[
     SkillLife = BaseLife \times UserMagicPowerScaling
     \]  
   - Represents the energy durability of the skill.

2. **Distance Decay**  
   - Skills lose HP over distance:  
     \[
     HP_{loss} = Distance \times DecayRate
     \]  
   - Prevents infinite-range spam; encourages positioning.

3. **Projectile Clash**  
   - When two skills collide:  
     - Higher Life wins and continues with reduced HP.  
     - Equal Life → both explode.  
     - Lower Life → destroyed.

4. **Projectile Damage Taken**  
   - Skills can be damaged by:  
     - Other projectiles  
     - Melee hits  
     - Traps, auras, terrain effects

5. **Skill Drain (Energy Leech)**  
   - Some skills can drain Life from others to:  
     - Increase damage  
     - Extend duration  
     - Alter properties

6. **Death Behavior**  
   - When SkillLife = 0 → skill “dies”:  
     - Explodes  
     - Dissipates  
     - Triggers secondary effects

---

## 🔥 Examples

- **Fireball**  
  - BaseLife: 100, DecayRate: 2 HP/m  
  - Travels 30m → loses 60 HP → arrives with 40 HP  
  - Collides with Ice Lance (Life = 50) → Fireball destroyed, Ice Lance continues with 10 HP

- **Lightning Beam (Drain Type)**  
  - Drains 5 HP/s from nearby enemy projectiles  
  - Hits 3 projectiles → 15 HP/s drained → beam grows, damage increases

---

## ⚠️ Design Impacts

- **Adds counterplay**: “Fight skill with skill”  
- **Enables emergent combat**: Skills interact dynamically  
- **Encourages positioning, timing, and build diversity**  
- **Supports advanced mechanics**: Spell ecosystems, energy dynamics

---

## 🧪 Applications

- **RPG / ARPG / MMO Combat Systems**  
- **MOBA Skill Design**  
- **Fantasy Shooters**  
- **AI Combat Simulation**  
- **Spell Ecosystem Architectures**

---

## 🆓 License

**Public Domain.** Use, fork, modify, or integrate freely. No attribution required — but linking back is appreciated.

---

## 🔗 Original Gist
  
Full gist archive (100+ frameworks): [ChaosGod208 gist](https://gist.github.com/ChaosGod208)

---

**Made with raw insight & zero corporate fluff.**  
— ChaosGod208
