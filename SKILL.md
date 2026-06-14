---
name: webgl-water-ripple
description: "Interactive WebGL water-ripple / displacement background effect — three implementations: PixiJS (RenderTexture + displacement filter), Curtains.js (custom GLSL shader), jQuery Ripples (fluid simulation). Mouse-hover and touch/swipe driven, multi-device. Use when adding a water-surface / liquid distortion background that reacts to the pointer. WebGL水面リップル背景の3実装集。"
---

# webgl-water-ripple (WebGL Water Ripple Collection)

A collection of **WebGL water-ripple / displacement** background effects that react to mouse-hover and touch/swipe (no click needed), multi-device. Three library implementations with different trade-offs — pick one.

マウスホバー／スワイプに反応する **WebGL 水面リップル（変位）** 背景の集合。3 ライブラリの実装を収録（特性が違うので用途で選ぶ）。

## When to use / 使いどころ
- **EN:** adding an interactive, pointer-driven water-surface / liquid-distortion background to a hero or section. Choose by need: performance, shader control, or easiest setup.
- **JP:** ヒーローやセクション背景に、ポインタ追従の水面／液体歪みエフェクトを入れるとき。性能・シェーダ制御・導入の手軽さで選ぶ。

## Implementations / 実装パターン（選択肢）
| # | Library | Strength | Mechanism |
|---|---|---|---|
| 1 | **PixiJS** (v7) | highest performance, natural spread / 最高性能 | dynamic normal-map brush at cursor → displacement map on background |
| 2 | **Curtains.js** (v8) | best DOM affinity, direct GLSL control / DOM親和・シェーダ直制御 | offscreen canvas ripple data → texture → per-pixel distort in shader |
| 3 | **jQuery Ripples** | most realistic (physics), easiest setup / 物理ベース・最も簡単 | built-in fluid simulation |

## Technique / 仕組み
Displacement mapping: **R** channel = horizontal shift, **G** = vertical shift, **A** = distortion strength. Generated dynamically at the cursor so a static image looks submerged in water.

## Bundled assets / 同梱アセット
- `pixijs/index.html` — PixiJS implementation
- `curtainsjs/index.html` — Curtains.js (GLSL) implementation
- `jquery-ripples/index.html` — jQuery Ripples implementation
- `index.html` — entry / index
- `README.md` — full bilingual doc

## How to apply / 適用方法
1. **Pick** the implementation by trade-off (above). Copy that folder's `index.html` as the starting point.
2. **Run via a local server** — WebGL + external images need it to avoid CORS: `python3 -m http.server 8000` or `npx serve` (or VS Code Live Server). Opening the file directly will fail.
3. Swap the background image and tune brush size / strength.

> License: MIT. Full per-pattern details: see **`README.md`** / 詳細は README.md。
