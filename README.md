Here's a README for your project:

CoopSoulsGame
A co-op souls-like action RPG built in Unreal Engine 5 (C++) as a portfolio project demonstrating advanced gameplay systems engineering.
Overview
CoopSoulsGame is a dark fantasy melee combat game inspired by the Souls genre. Built entirely in C++ with Blueprints used only for asset assignment, the project focuses on precise, skill-based combat with a polished feel.
Features
Player Combat

Dual-mode combat system (Two-Handed Sword / Sword & Shield)
Light attacks, heavy attacks, charge attacks with hold-release timing
Cross-cancel combos — cancel light into heavy and vice versa mid-combo
Parry system with anim notify windows
Guard reactions (light/heavy) with stamina-based blocking
Dodge roll with invincibility frames and stamina cost
Lock-on targeting with smooth camera interpolation
Backstab execution system with positional teleport
Jump attacks, sprint, stamina and mana resource management

Enemy System

Custom ACoopEnemy C++ base class with patrol/chase/attack AI
Poise and stagger system with stumble, injured idle, and backstab vulnerability
Randomized 3-attack system with stun interrupt on player counter-hit
Parry-able attacks with poise damage on success
Per-player split-screen health bars using SetOwnerPlayer viewport isolation

Boss System

Dedicated ACoopBossEnemy C++ class (2.5x scale, tuned stats)
Separate ACoopBossSword actor with TipMarker/BaseMarker for per-tick sweep collision
Tick-based smooth rotation toward player, frozen during attack animations
Full montage set — attack, hit react, stumble, death

Animation

Montage-driven combat over locomotion via DefaultSlot
Custom C++ anim notify classes for all combat events
Blend space locomotion driven by GroundSpeed from C++ variables
Separate Animation Blueprints per character type

UI

Per-player HUD (health, stamina, mana)
Dual WidgetComponent enemy health bars with SetOwningLocalPlayer for correct split-screen rendering

Tech Stack

Engine: Unreal Engine 5
Language: C++ (gameplay systems), Blueprint (asset configuration)
Tools: Visual Studio 2022, Unreal Header Tool, NavMesh pathfinding
Animation: IK Retargeter, Blend Spaces, Montages, C++ Anim Notifies

Architecture Highlights

Full C++ class hierarchy — ACoopSoulsGameCharacter → ACoopSwordCharacter / ACoopArcherCharacter
ACoopEnemy → ACoopBossEnemy for scalable enemy architecture
Custom ACoopEnemyAIController with timer-based state machine and tick-based facing
Weapon collision via socket-to-socket SweepMultiByChannel per tick during attack window
Per-player viewport-isolated UI in split-screen using SetOwnerPlayer / SetOwningLocalPlayer

Project Status
Currently in active development. Single-player mode stable. Co-op split-screen systems built and pending re-integration after solo testing phase.
