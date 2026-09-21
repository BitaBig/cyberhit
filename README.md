# CyberHit

A 3D beat-'em-up built in Unity. Move a martial artist through a side-scrolling arena, chain combo attacks, and fight off waves of enemies that close in and attack.

<img width="661" height="340" alt="Screenshot 2026-09-21 at 12 46 12 PM" src="https://github.com/user-attachments/assets/da92f4b2-b76a-4282-8277-2a47754cbbec" />




## Gameplay

- **Move** with the horizontal/vertical input axes — movement is arena-relative and clamped to a fixed play space, with the character turning to face the direction of movement.
- **Attack** by pressing Z repeatedly within a short window to chain up to a 3-hit combo.
- **Enemies** track and follow the player, closing to an attack range, then throwing one of several random attack animations before resuming the chase.
- **Waves** of enemies spawn in from designated spawn points on a timer, with a new wave starting once the previous one is cleared.
- The camera follows the player along the side-scrolling axis.

## Tech Stack

- **Engine:** Unity 2022.3.17f1
- **Rendering:** 3D, built-in render pipeline
- **Effects:** MK Glow (bloom/glow post-processing)

## Project Structure

```
Assets/
  Animations/                   Animator controllers and clips for Player and Enemy
  EnemyControls.cs               Enemy AI (chase, attack, animation triggers)
  FBX Models/                    Loot and health pickup models
  Fonts/                         UI font
  Martial Arts Assets Free/      Third-party character models, materials, and demo scene
  Materials/                     Project-specific materials
  Prefabs/                       Player, Enemy, EnemySpawner, SpawnPoints, platform
  Scenes/                        CyberFu (main scene), SampleScene
  Scripts/                       Core gameplay scripts (see below)
  _MK/MKGlowFree/                Third-party glow/bloom effect asset
Packages/                        Unity package manifest
ProjectSettings/                 Unity project configuration
```

### Scripts

| Script | Responsibility |
|---|---|
| `ThirdPersonController.cs` | Player movement, turning, and speed/animation blending, clamped to the arena bounds |
| `ComboAttacks.cs` | Tracks consecutive Z presses within a time window to trigger combo attack animations |
| `EnemyControls.cs` | Enemy AI — chases the player, attacks at close range, triggers random attack animations |
| `CameraFollowSideScroller.cs` | Keeps the camera following the player along the side-scrolling axis |
| `WaveSpawner.cs` | Spawns enemies in waves from a set of spawn points, advancing once each wave is cleared |

## Getting Started

1. Install **Unity Hub** and **Unity 2022.3.17f1** (or a compatible 2022.3 LTS patch version).
2. Clone the repository:
   ```
   git clone https://github.com/BitaBig/cyberhit.git
   ```
3. Open the project folder in Unity Hub (Unity will resolve packages from `Packages/manifest.json` on first open — this can take a few minutes).
4. Open `Assets/Scenes/CyberFu.unity` and press **Play**.
