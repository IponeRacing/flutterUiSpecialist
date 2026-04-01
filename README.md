# Flutter UI Specialist

> A Claude Code sub-agent that crafts **Apple-quality** Flutter UIs — liquid glass,
> candy gradients, jelly animations, and Impeller-native effects. Not a basic Material 3
> agent. A visual craftsman.

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![Flutter](https://img.shields.io/badge/Flutter-3.27%2B-02569B?logo=flutter)](https://flutter.dev)
[![Impeller](https://img.shields.io/badge/Impeller-enabled-FF6B6B)](https://docs.flutter.dev/perf/impeller)

---

## Why this exists

Flutter's default tooling produces generic Material 3 screens. This agent knows the
**craft layer** — the techniques that separate "it works" from "it's beautiful":
liquid glass blur, multi-layer candy tile shadows, spring physics animations,
grain noise textures, gyroscope tilt, Rive state machines, and fragment shaders.

---

## What it delivers

| Visual effect | Technique |
|--------------|----------|
| 🍬 Candy / glossy buttons | 3-layer gradient fill + gloss highlight + 3× BoxShadow |
| 🌊 Liquid glass cards | `BackdropFilter` + `ClipRRect` + Fresnel highlight overlay |
| 🫀 Jelly tile bounce | `AnimatedScale` + `Curves.elasticOut` (250ms) |
| ✨ Gradient connection line | `Paint()..shader = gradient.createShader(rect)` via CustomPainter |
| 🎨 Animated gradient background | `AnimationController.repeat(reverse: true)` + `Color.lerp` |
| 📝 Gradient text | `ShaderMask` + `LinearGradient.createShader` |
| 🎊 Confetti celebration | `confetti` package + `HapticFeedback.heavyImpact()` |
| 🪨 Grain texture | `mesh_gradient` `noiseIntensity: 0.20` |
| 📐 Staggered entrance | `flutter_animate` with delay chains |
| 📱 Haptic pairing | lightImpact/mediumImpact/heavyImpact mapped to gesture weight |

---

## Installation

### Project-level

```bash
mkdir -p your-project/.claude/agents
cp agents/flutter-ui-specialist.md your-project/.claude/agents/
```

### Global (all Claude Code sessions)

```bash
mkdir -p ~/.claude/agents
cp agents/flutter-ui-specialist.md ~/.claude/agents/
```

---

## Usage examples

```
Redesign the home screen with a candy-colored UI:
- Animated lavender gradient background
- Glossy game mode cards with gradient icons and soft shadows
- Staggered entrance animations with flutter_animate
```

```
Make the letter tiles in my word game look like colorful candy pills.
Each tile should have a different gradient, spring-bounce on selection,
and a 3-layer shadow system.
```

```
Add a confetti explosion + animated star reveal to the level complete screen.
```

---

## Packages used

```yaml
flutter_animate: ^4.5.2      # Staggered animations, spring effects
confetti: ^0.8.0             # Celebration bursts
mesh_gradient: ^1.0.4        # Grain + mesh backgrounds
google_fonts: ^6.2.1         # Variable fonts
lottie: ^3.3.1               # Rive/Lottie animations
```

---

## Anti-patterns prevented

| ❌ Causes jank | ✅ Correct |
|--------------|-----------|
| `Opacity` widget (creates layer) | `FadeTransition` or `AnimatedOpacity` |
| `AnimatedContainer` for bounce | `AnimatedScale` + `Curves.elasticOut` |
| Single `BoxShadow` | 3× layered shadows (key + ambient + bottom edge) |
| `BackdropFilter` without `ClipRRect` | Always clip before filter |
| Flat icon containers | Gradient `BoxDecoration` + white icon |

---

## Compatibility

| Flutter | Rendering | iOS | Android |
|---------|----------|-----|---------|
| 3.27+ | Impeller (default) | 14+ | API 21+ |

---

## License

MIT — [EngageEngine](https://engageengine.ch)
