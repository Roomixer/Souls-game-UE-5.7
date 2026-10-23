<div align="center">
⚔️ CoopSoulsGame
A co-op souls-like action RPG built in Unreal Engine 5 — all gameplay in C++
<img src="Screenshots/Screenshot%202026-08-05%20130619.png" alt="Player at the boss fog gate" width="100%"/> <br/>

Show Image Show Image Show Image Show Image

Features · Gallery · Architecture · Tech Stack · About Me

</div>
🩸 Overview

CoopSoulsGame is a dark fantasy melee combat game inspired by the Souls genre. Every gameplay system is written in C++ — Blueprints are used only for asset assignment. The focus is precise, skill-based combat with a polished, weighty feel.

Built by one developer across gameplay programming, technical animation and world building.

🎮 Features
<table> <tr> <td width="50%" valign="top">
🗡️ Player Combat
Dual combat modes — Two-Handed Sword / Sword & Shield
Light, heavy and hold-release charge attacks
Cross-cancel combos — light ↔ heavy mid-chain
Parry windows driven by anim notifies
Stamina-based guarding with light/heavy reactions
Dodge roll with i-frames
Lock-on with smooth camera interpolation
Backstab executions with positional snap
Jump attacks, sprint, stamina & mana
</td> <td width="50%" valign="top">
👹 Enemies & Boss
ACoopEnemy base class — patrol / chase / attack AI
Poise & stagger — stumble, injured idle, backstab-vulnerable
Randomized 3-attack set with counter-hit stun
Parry-able attacks that deal poise damage
Boss: Greata The Trid — dedicated ACoopBossEnemy (2.5× scale)
Separate boss sword actor with per-tick sweep collision
Smooth tracking rotation, locked during attacks
</td> </tr> <tr> <td width="50%" valign="top">
🎞️ Animation
Montage-driven combat layered over locomotion (DefaultSlot)
Custom C++ anim notify classes for every combat event
Blend-space locomotion fed by GroundSpeed from C++
Separate Animation Blueprints per character type
IK Retargeter pipeline
</td> <td width="50%" valign="top">
🖥️ UI & Split-Screen
Per-player HUD — health, stamina, mana
Enemy health bars isolated per viewport
SetOwnerPlayer / SetOwningLocalPlayer for correct split-screen rendering
</td> </tr> </table>
🖼️ Gallery
Boss Fight — Greata The Trid
<table> <tr> <td><img src="Screenshots/Screenshot%202026-08-05%20130652.png" alt="Boss fight 1"/></td> <td><img src="Screenshots/Screenshot%202026-08-05%20130703.png" alt="Boss fight 2"/></td> <td><img src="Screenshots/Screenshot%202026-08-05%20130754.png" alt="Boss fight 3"/></td> </tr> </table>
Combat
<table> <tr> <td><img src="Screenshots/Screenshot%202026-08-05%20130309.png" alt="Lock-on vs enemy"/></td> <td><img src="Screenshots/Screenshot%202026-08-05%20130359.png" alt="Sword and shield combat"/></td> </tr> <tr> <td><img src="Screenshots/Screenshot%202026-08-05%20130415.png" alt="Sword and shield stance"/></td> <td><img src="Screenshots/Screenshot%202026-08-05%20130254.png" alt="Camp at night"/></td> </tr> </table>
World Building
<table> <tr> <td><img src="Screenshots/Screenshot%202026-08-05%20130428.png" alt="Castle ravine"/></td> <td><img src="Screenshots/Screenshot%202026-08-05%20130447.png" alt="Cliff path"/></td> </tr> <tr> <td><img src="Screenshots/Screenshot%202026-08-05%20130556.png" alt="Approaching the fog gate"/></td> <td><img src="Screenshots/Screenshot%202026-07-07%20164215.png" alt="Forest path"/></td> </tr> </table> <details> <summary><b>🔧 Under the hood — debug view of weapon sweep collision</b></summary> <br/> <img src="Screenshots/Screenshot%202026-06-25%20121639.png" alt="Editor debug view showing sweep collision"/> </details>
🏗️ Architecture
ACharacter
 └── ACoopSoulsGameCharacter
      ├── ACoopSwordCharacter
      └── ACoopArcherCharacter

ACoopEnemy  ─────────────►  ACoopEnemyAIController (timer-based state machine)
 └── ACoopBossEnemy  ──────►  ACoopBossSword (TipMarker → BaseMarker sweep)
Weapon hits — socket-to-socket SweepMultiByChannel every tick during the attack window
Enemy AI — custom controller with timer-driven states and tick-based facing
Scalable enemies — boss inherits from the base enemy, overriding stats, scale and montage set
Split-screen UI — per-player viewport isolation via SetOwnerPlayer / SetOwningLocalPlayer
🛠️ Tech Stack
Area	Tools
Engine	Unreal Engine 5.7
Gameplay	C++ (systems) · Blueprint (asset config only)
IDE / Build	Visual Studio 2022 · Unreal Header Tool
AI	Custom AIController · NavMesh pathfinding
Animation	IK Retargeter · Blend Spaces · Montages · C++ Anim Notifies
🚧 Project Status
System	Status
Single-player combat	✅ Stable
Enemy AI & poise	✅ Stable
Boss encounter	✅ Playable
Co-op split-screen	🔄 Built — re-integrating after solo testing
👤 About Me
<div align="center">

Joel Shajan — Multi-discipline game developer · Bangalore, India

Gameplay Programming · Technical Animation · 3D Art & World Building

Email : joelshajankuttu@gmail.com

Open to roles in gameplay programming, technical animation and generalist game dev.

</div>
