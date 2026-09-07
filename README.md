# 🛠 Arabic / Persian Text Shaper
### Game Localization Tool by AnyThing — v4.2.0

A standalone, offline tool that reshapes and reverses Arabic and Persian text for use in game engines. No installation, no coding, no internet required — just run the app and it works.

---

## a video demonstration

this video denominstrate how to use this app and its features, 

https://youtu.be/RramiEbmf-k?si=xl1170Dj6cbeVR9c

the version used in this video is an early version of the app (v1.x). Features added in v2.x, v3.x, and v4.x are not covered — they may get their own videos if advanced enough to need one.

---

## The Problem

Arabic and Persian text injected directly into game assets appears **broken** — letters are disconnected and the string is rendered in the wrong direction. Game engines require pre-shaped, pre-reversed strings to display RTL text correctly through their own rendering system.

**Without this tool:**
```
ل ا ي ع ت ل ا    ←  disconnected, wrong direction
```
**With this tool:**
```
ﻞﻴﻌﺘﻟﺍ    ←  correct, game-ready
```

---

## How to Use

1. **Run** the app — no installation or setup needed
2. **Type or paste** your Arabic or Persian text in the Input box
3. **Set** the box width and font size to match your in-game text component
4. **Copy** the Combined output and paste it into your game's text field

That's it. No coding. No modifying game files.

---

## Features

- **Live Arabic & Persian reshaping** — all 4 contextual letter forms (isolated, initial, medial, final)
- **Full harakat support** — فَتْحَة، ضَمَّة، كَسْرَة، شَدَّة، تَنْوِين، سُكُون — diacritics stay correctly attached to their letters during reversal
- **Harakat delay compensation (◌ً↑)** — shifts every diacritic one letter forward for game engines that render harakat one position early; a space is used as a landing spot (or inserted) when there's no following letter to advance onto
- **Bracket mirroring (⇄)** — automatically swaps `(`↔`)`, `[`↔`]`, `{`↔`}`, and matching curly quotes so they still open and close on the correct side after RTL reversal; toggle off if your engine already handles this itself
- **Pixel-accurate line wrapping** — set your exact in-game box width and font size; lines break exactly as they will in the game
- **Custom font support** — upload your game's `.ttf` / `.otf` font for perfectly matched line breaks
- **Live preview** — see exactly how the text will render in-game, with alignment controls (Right / Center / Left); width/height respected on both desktop and mobile
- **Custom Tag Definitions (🏷)** — teach the tool your game's own rich-text tags:
  - **Color aliases** — give a short symbol its own color (e.g. `≈` → `#ff6600`) so you can write `<color=≈>` instead of typing a hex code every time
  - **Sprites** — map a key to an uploaded image or an emoji/text fallback, shown inline via `<sprite=KEY>`
  - **Custom tag aliases** — invent your own tag name and make it behave like an existing tag (bold, italic, underline, or one of your color/sprite aliases), with a choice of bracket style (`<>`, `()`, `{}`, or `[]`) so you can avoid angle brackets entirely if you want
  - Definitions are saved automatically and applied instantly across Lines, Flipped, Combined, and Preview
- **Two-way editing** — paste a previously exported game string back and click **↑ Import** to recover the original editable Arabic text for re-editing
- **Line order reversal** — ⇅ button to reverse line order for game engines that read lines bottom-up
- **Persian support** — پ چ ژ گ ک ی fully supported with correct contextual shaping
- **Built-in virtual keyboard** — insert Arabic/Persian letters and harakat without switching your system keyboard
- **Unlimited presets** — start with three renamable slots (P1/P2/P3) and add as many as you need; each stores your box width, font size, separator, and font name for instant switching between different in-game text boxes; export/import presets as a file to back up or share
- **Per-line copy** — hover any line in the Lines or Flipped panels to copy just that line
- **Minimizable panels** — collapse any panel you don't need open to save screen space
- **Bilingual UI** — English / عربي toggle, including every button and field tooltip, with correct right-to-left layout throughout
- **Image ruler** — drop a screenshot directly into the ruler panel, drag the selection box over any text, and the measured width and height are applied to your settings automatically; supports zoom from 25% to 400%, right-click drag to pan, and keyboard shortcuts for precise control
- **Multi-string mode** 🔀 — treat each input line as a completely independent string with its own shaping and output; useful when localizing multiple short labels at once
- **Fully offline** — works with no internet connection; font is embedded in the app

---

## Output Boxes

| Box | Contents | Use |
|-----|----------|-----|
| **Input** | Your original text | Edit here |
| **Lines — Reshaped Only** | Each line after letter-shaping, not reversed | Visual verification |
| **Reshaped & Flipped** | Each line shaped + reversed | Per-line game string |
| **Combined** | All lines joined by separator | **Paste this into your game** |
| **Preview** | Live render at your box dimensions | Visual check |

---

## Settings

| Setting | Description |
|---------|-------------|
| **Box Width (px)** | Width of your in-game text box in pixels |
| **Font Size (px)** | Your in-game font size |
| **Separator** | Character between lines in combined output (default `\n`) |
| **Font File** | Upload your game font for pixel-perfect wrapping |
| **⇅** | Reverse line order (for bottom-up reading systems) |
| **◌ً↑** | Advance harakat one letter forward, for engines that render diacritics one position early. Applies to the Lines, Flipped, and Combined panels — the Preview is unaffected |
| **( ⇄ )** | Toggle bracket mirroring for RTL-reversed output |
| **🔀 Multi-string** | Treat each input line as a separate independent string |

---

## Custom Tag Definitions

Open the **🏷** button to define how special game tags render in the preview. Changes apply instantly and are saved automatically.

- **Color aliases** — a short key (like `≈` or `?`) that stands in for a CSS color (hex code or name), written as `<color=KEY>text</color>`
- **Sprites** — a key that displays an uploaded image, or an emoji/short text fallback if you skip the image, written as `<sprite=KEY>`
- **Tag aliases** — a custom tag name that behaves like an existing tag (**b**, **i**, **u**, **s**, or one of your color/sprite aliases). Pick which brackets trigger it — the native `<>`, or `()`, `{}`, `[]` if you'd rather avoid angle brackets — and use the matching pair for both the opening and closing tag (e.g. `(liner)text(/liner)`). Your closing tag is automatically matched to whatever the alias represents; sprite-based aliases are self-closing and never take a closing tag at all

Each section has its own **🗑 Clear all** button to wipe just that section, and a **↺ Reset All** button to erase every color alias, sprite, and tag alias at once.

---

## Image Ruler

Drop any screenshot into the ruler panel to measure your in-game text boxes at the pixel level.

| Control | Action |
|---------|--------|
| **Drag image / right-click drag** | Pan the image |
| **Arrow keys** | Move selection box 1px |
| **Shift+Arrow** | Move selection box 10px |
| **Ctrl+Arrow** | Resize selection box 1px |
| **Ctrl+Shift+Arrow** | Resize selection box 50px |
| **Zoom − / +** | Zoom image from 25% to 400% |
| **1:1** | Reset zoom to 100% |
| **📐 Use once** | Apply measurements without saving to a preset |
| **Make new preset** | Save measurements as a new preset slot |

At 100% zoom the image fits the panel exactly. At any other zoom scrollbars appear and you can pan with right-click drag.

---

## Presets

Unlimited renamable slots store your box width, font size, separator, and font file name so you can switch between different game text boxes instantly. Start with three slots and add as many as you need with the **＋ Add** button.

- **Load** — click a preset button to load it (highlights green); press **1–9** or **0** to load presets 1–10 from the keyboard
- **Save 💾** — select a preset, then click Save to overwrite it with your current settings
- **＋ Add** — create a new preset slot
- **🗑 Delete** — enter delete mode, then click any preset to remove it
- **Rename ✎** — click the pencil icon next to a preset to rename it
- **Export ↓** — downloads all presets as a file you can back up or share
- **Import ↑** — loads presets from a previously exported file

*Note: if a preset was saved with a custom font that isn't currently uploaded, a warning appears when you load it.*

---

## Why Not Other Tools?

Other tools are either outdated, online-only, or simply not good enough:

- ❌ No support for Persian letters
- ❌ No separator or line management features
- ❌ Cluttered or outdated UI
- ❌ Require coding knowledge or modifying game files
- ❌ Don't work offline

**This tool:**
- ✅ Supports Arabic and Persian fully
- ✅ Separator and line ordering features built-in
- ✅ Clean modern UI — accessible to any beginner with zero coding knowledge
- ✅ Works with any game engine's text rendering — no code modifications needed inside the game; it uses the engine's own special character rendering
- ✅ Native, free, lightweight, and customizable
- ✅ Fully offline

---

## Technical Details

- Pure HTML/CSS/JavaScript — zero external dependencies at runtime
- Arabic shaping engine built from scratch using Unicode Presentation Forms (FE70–FEFF, FB50–FDFF)
- Lam-Alef ligature support (لا، لإ، لأ، لآ)
- Cluster-aware reversal — harakat/diacritics stay attached to their base letter during string flip
- Tatweel (ـ) correctly handled as a connector, not a diacritic
- Hamza on Ya (ئ) correctly handled as a 4-form connector letter
- Harakat-advance uses a token-barrier model: letters and spaces are valid landing spots for a shifted diacritic, other punctuation acts as a hard barrier; a space is inserted if a shifted diacritic would otherwise fall off the end of the text
- Custom tag aliases are normalized to standard `<tag>` markup before shaping so they flow through the same shaping/reversal pipeline as built-in tags, then their chosen bracket style is restored afterward
- Sprite tags carry no visible text of their own, so line/emptiness checks look for either shaped text or a sprite tag — a line containing only a sprite is never dropped from the output
- Mobile-responsive layout — the live preview box always honors your chosen pixel width on phones, capped only to avoid overflowing the screen
- Font: [Vazirmatn](https://github.com/rastikerdar/vazirmatn) — embedded, open source (OFL 1.1)

---

## License

MIT — see [LICENSE](LICENSE)

---

## Credits

Built by **اي حاكَة (AnyThing)** for the Arabic game localization community — to provide a better, more accessible tool for anyone working on Arabic or Persian game localization, without the need for any coding background.

Font: [Vazirmatn](https://github.com/rastikerdar/vazirmatn) by Saber Rastikerdar (SIL Open Font License 1.1)
