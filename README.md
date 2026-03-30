# Web Harmonium

A browser-based Indian harmonium — no installs, no dependencies, just open and play.

**Live:** [web-harmonium-by.losthusky.qzz.io](https://web-harmonium-by.losthusky.qzz.io)

---

## What it is

A fully functional harmonium in the browser, built on the Web Audio API. It uses a real recorded harmonium sample (`harmonium-kannan-orig.wav`) pitch-shifted across 27 keys, giving it an authentic tone instead of synthesized sound. Everything runs client-side — no server, no frameworks, no build step.

---

## Features

### Keyboard & Swaras
- 27 keys spanning **F3 to G5** (Mạ to Pȧ)
- Full **Indian swara notation** — Sa Re Ga Ma Pa Dha Ni with sharp/flat (komal/tivra) variants
- QWERTY keyboard mapped to physical key positions (layout-independent)
- `E` = Sa (C4, tonic) · `P` = Sȧ (C5) · `F` = Sustain hold

### Sound Engine
- Real harmonium sample with **pitch-shifted looping** across the entire range
- **Reed stacking** — layer up to multiple voices with ±14 cents random chorus detune per layer for that thick harmonium "reed" texture
- **Convolution reverb** using a real impulse response (`reverb.wav`)
- Waveform modes: **Sample** (default), Sine, Sawtooth, Square
- **ADSR envelope** — Attack and Release sliders with live canvas preview
- **Drone** — continuous Sa, Sa+Pa, or Low Sa drone underneath your playing

### Tuning
- **Transpose** ± semitones
- **Octave** shift
- **Fine tune** ± 50 cents
- Arrow keys: `↑↓` Octave · `←→` Transpose ±1 semitone

### Raga Scale Presets
Chromatic · Bilawal (Major) · Bhairav · Yaman (Kalyan) · Kafi · Bhairavi · Todi · Marwa · Purvi · Pentatonic

Selecting a raga highlights the active scale degrees and suppresses keys outside the scale.

### MIDI Support
Plug in any MIDI controller — auto-detected via Web MIDI API.
- Sustain pedal (CC 64)
- Volume (CC 7)
- Pitch bend (±2 semitones)

### Sequence Player
Type swaras or key characters as text, set gap/hold timing, hit Play. Supports looping and saving named sequences.

### Record & Playback
- Record your playing with precise timing
- Playback with a live **piano roll** display
- **Export** notation as plain text

### Visualizer
Three real-time audio visualizer modes — **Spectrum**, **Waveform**, **Bars** — driven by a Web Audio `AnalyserNode`.

---

## Keyboard Reference

| Keys | Swaras |
|------|--------|
| `S` | Mạ (F3) |
| `` ` 1 Q 2 W `` | Pạ → Nị (G3–B3) |
| `E` | **Sa (C4) — Tonic** |
| `4 R 5 T Y` | re → Ma (C#4–F4) |
| `7 U 8 I 9 O` | ma → Ni (F#4–B4) |
| `P` | Sȧ (C5) |
| `- [ = ] \ ' ;` | rė → Pȧ (C#5–G5) |
| `F` | Sustain hold |
| `R` | Toggle Record |
| `Space` | Add separator / Play if stopped |
| `Backspace` | Undo last notation token |
| `Delete` | Clear notation |
| `Esc` | Help overlay |

---

## Files

```
warm-harmonium-v5.html    — the entire app (HTML + CSS + JS, self-contained)
harmonium-kannan-orig.wav — real harmonium sample (loop root: D4)
reverb.wav                — impulse response for convolution reverb
index.html                — redirect entry point for GitHub Pages
```

---

## Running locally

Just open `warm-harmonium-v5.html` in any modern browser. No build step needed.

> Audio requires a user gesture to start (browser autoplay policy). Click "Play Harmonium" on the launch screen.

For local development with the audio files, serve from a local HTTP server (e.g. `npx serve .`) to avoid CORS restrictions on `file://`.

---

## Browser support

Works in any browser with Web Audio API and (optionally) Web MIDI API support — Chrome, Edge, Firefox, Safari. MIDI requires Chrome/Edge for full support.
