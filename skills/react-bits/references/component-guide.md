# Component selection guide

## Match the request

| Goal | Start with |
|---|---|
| Text entrance or emphasis | `BlurText`, `SplitText`, `ShinyText`, `DecryptedText` |
| Hero background | `Aurora`, `LightRays`, `Silk`, `Particles`, `Galaxy` |
| Cards and content blocks | `SpotlightCard`, `TiltedCard`, `PixelCard`, `MagicBento` |
| Navigation | `GooeyNav`, `PillNav`, `StaggeredMenu` |
| Pointer feedback | `ClickSpark`, `Magnet`, `GlareHover`, `TargetCursor` |
| Scroll storytelling | `ScrollReveal`, `ScrollStack`, `AnimatedContent`, `FadeContent` |
| 3D or shader showcase | `Ballpit`, `Orb`, `Iridescence`, `Hyperspeed`, `ModelViewer` |

Confirm current component names and availability on `https://reactbits.dev` before installing; the registry evolves.

## Selection heuristics

- Prefer a small CSS or motion effect over WebGL when both meet the visual goal.
- Use one dominant continuous background effect per viewport.
- Reserve cursor-dependent effects for pointer-capable devices and supply touch behavior or a static fallback.
- Treat 3D, postprocessing, physics, webcam, and face-detection components as high-cost; inspect their dependencies and bundle impact first.
- Avoid combining multiple components that each own global scroll, pointer, or animation loops.
- Keep content and primary controls outside decorative canvases so failure does not remove functionality.

## Adaptation checklist

- Map hardcoded colors and spacing to existing design tokens.
- Ensure the component inherits the project's font and does not reset global styles.
- Constrain absolute-positioned backgrounds to an explicit relative container.
- Add cleanup for listeners, timers, GSAP contexts, animation frames, renderers, and media streams.
- Verify server rendering boundaries in Next.js and lazy-load browser-only heavy effects when appropriate.
- Add meaningful static content or `aria-hidden="true"` for purely decorative output.
