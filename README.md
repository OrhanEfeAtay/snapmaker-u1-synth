# Snapmaker U1 Stepper Synth

Turn **MIDI** and **audio files** (`.MID`, `.MIDI`, `.MP3`, `.WAV`) into 3-axis stepper motor music for your **Snapmaker U1**—directly in your web browser.

No installation, no server, and no command-line setup required.

---

## How to Use

1. **Download the app:** Click **`index.html`** in the file list above, then click the **Download raw file** icon in the top-right corner.
2. **Open in your browser:** Double-click `index.html` to launch the studio locally in Chrome, Safari, Edge, or Firefox.
3. **Pick or upload a track:** Choose one of the 4 built-in presets or drop in your own `.MID`, `.MIDI`, `.MP3`, or `.WAV` file.
4. **Preview & export:** Test the melody in the 2D simulator, then copy the G-code into the **Fluidd Console** or save it as a `START_CHIME` macro in `printer.cfg`.

> [!IMPORTANT]
> Always run **Home All (`G28`)** on your printer before sending generated G-code.

---

## Key Features

- **3-Axis Polyphonic Sound** — Plays lead melodies and harmonies on **CoreXY Motors A & B** while vibrating the **steel Z-bed** for bass notes.
- **Built-In & Custom Tracks** — Includes 4 ready-to-play presets plus drag-and-drop support for `.MID`, `.MIDI`, `.MP3`, and `.WAV` files.
- **Stereo `L+R` Audio Detection** — Combines both stereo channels and includes an optional **Low-Volume Sensitivity** toggle for quiet intros and soft fades.
- **Visual Waveform Trimmer** — Drag handles directly on the waveform to isolate any chorus, hook, or intro.
- **Live 2D Kinematic Simulator** — Preview toolhead movement, motor frequencies (`Hz`), and WebAudio sound before running anything on your printer.
- **Fluidd & OrcaSlicer Ready** — Export straight to the **Fluidd Console** or as a `[gcode_macro START_CHIME]` block for print-start chimes.

---

## Tuning Controls

| Setting | What It Does |
| :--- | :--- |
| **Voice Mode** | Switch between **3-Axis** (`X + Y + Z`), **2-Axis** (`X + Y`), or **1-Axis** (unison lead). |
| **Staccato Articulation** | Adds brief `G4` pauses (`0–60 ms`) between notes for cleaner, plucked separation. |
| **Transient Acceleration** | Boosts cornering punch (`M204 S10000`–`S20000`) during playback, then resets to `M204 S6000`. |
| **Octave Shift** | Shifts pitches (`-1`, `0`, `+1` octave) into the loudest acoustic sweet spot of the U1 frame. |
| **Continuous Glide** | Chains rising and falling pitches smoothly in one direction, bouncing only at safe box walls. |

---

## Safety & Bed Limits

All toolpaths stay strictly inside a centered safe zone (`X135.0 Y135.0 Z15.0`) with **`0.000 mm` net drift**:

| Axis | Safe Travel Range | Role |
| :--- | :--- | :--- |
| **X Axis** | `102.0 mm – 168.0 mm` | CoreXY Lead & Harmony |
| **Y Axis** | `98.0 mm – 172.0 mm` | CoreXY Lead & Harmony |
| **Z Axis** | `12.8 mm – 17.2 mm` | Steel Bed Bass Resonance |

> [!WARNING]
> Always ensure your build plate is clear and home all axes (`G28`) before running custom G-code. Use at your own risk.

---

## License

Released under the [MIT License](LICENSE) · Created by **orhan.prints**
