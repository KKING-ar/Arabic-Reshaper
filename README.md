# 🛠 Arabic / Persian Text Shaper
### Game Localization Tool by AnyThing

A standalone, offline tool that reshapes and reverses Arabic and Persian text for use in game engines. No installation, no coding, no internet required — just run the app and it works.

---

## a video demonstration

this video denominstrate how to use this app and its features, 

https://youtu.be/RramiEbmf-k?si=xl1170Dj6cbeVR9c

the version used in this video is an early version pf the app, any future features added in update won't be here, they might get thier own videos IF it was advanced to use.

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
- **Pixel-accurate line wrapping** — set your exact in-game box width and font size; lines break exactly as they will in the game
- **Custom font support** — upload your game's `.ttf` / `.otf` font for perfectly matched line breaks
- **Live preview** — see exactly how the text will render in-game, with alignment controls (Right / Center / Left)
- **Two-way editing** — paste a previously exported game string back and click **↑ Import** to recover the original editable Arabic text for re-editing
- **Line order reversal** — ⇅ button to reverse line order for game engines that read lines bottom-up
- **Persian support** — پ چ ژ گ ک ی fully supported with correct contextual shaping
- **Built-in virtual keyboard** — insert Arabic/Persian letters and harakat without switching your system keyboard
- **Bilingual UI** — English / عربي toggle
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
- Font: [Vazirmatn](https://github.com/rastikerdar/vazirmatn) — embedded, open source (OFL 1.1)

---

## License

MIT — see [LICENSE](LICENSE)

---

## Credits

Built by **اي حاكَة (AnyThing)** for the Arabic game localization community — to provide a better, more accessible tool for anyone working on Arabic or Persian game localization, without the need for any coding background.

Font: [Vazirmatn](https://github.com/rastikerdar/vazirmatn) by Saber Rastikerdar (SIL Open Font License 1.1)

