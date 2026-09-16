# opencode-skill-screenshot-to-ui

> Pixel-faithful UI reproduction from a reference image — screenshot, Figma export, mockup, sketch, or a live URL screenshot.

A skill for [opencode](https://github.com/opencode-ai/opencode) that turns a design image into production-ready code with the highest visual fidelity achievable in a bounded number of iterations. Fidelity beats creativity here — this skill does not "improve" the reference unless you ask it to.

## Trigger phrases

- "1:1 clone / pixel-perfect / match this / replicate / mimic"
- "照着做 / 一模一样 / 复刻 / 抄一下 / 还原这张图"
- "clone this / rebuild this page / reproduce the reference"

## Pipeline (5 stages)

1. **Analyze** — read the reference, extract layout grid, spacing, color tokens, typography, radii, shadows into a `DESIGN_TOKENS.md` scratchpad.
2. **HTML plan** — write the DOM skeleton first, with semantic tags and structural comments; no styling yet.
3. **Styled build** — apply Tailwind (default) / CSS with the extracted tokens; use exact hex, exact px, exact font weights.
4. **Visual diff** — take a screenshot of the built page, compare side-by-side with the reference, list every visible delta.
5. **Iterate** — fix the top-N deltas in one pass; repeat until diff budget is exhausted.

## Complementary skills

- `frontend-design` (Anthropic official) — when the aesthetic direction is **open** and you want a new distinctive UI.
- `design-motion-principles` (Kyle Zantos) — layer motion on top of the reproduced static layout.

## Install

Via [opencode-workflow-kit](https://github.com/Yulimfish/opencode-workflow-kit):

```bash
curl -fsSL https://raw.githubusercontent.com/Yulimfish/opencode-workflow-kit/main/install.sh | bash
```

Or manually:

```bash
mkdir -p ~/.config/opencode/skills
git clone --depth=1 https://github.com/Yulimfish/opencode-skill-screenshot-to-ui.git \
  ~/.config/opencode/skills/screenshot-to-ui
```

Restart opencode. The skill loads on demand when your prompt matches a trigger phrase or an attached image.

## License

MIT © Yulimfish · Contact: <epeiuss@waterflames.cn>
