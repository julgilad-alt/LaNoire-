<div align="center">

# LA NOIRE

**Audio player Windows 64bits**

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11%2064--bit-0a0a0a?style=flat-square)
![Status](https://img.shields.io/badge/status-Beta-orange?style=flat-square)
![Rust](https://img.shields.io/badge/core-Rust-b7410e?style=flat-square&logo=rust)
![Tauri](https://img.shields.io/badge/UI-Tauri%20%2B%20Vue.js-24c8db?style=flat-square&logo=tauri)
![License](https://img.shields.io/badge/license-TBD-lightgrey?style=flat-square)

</div>

> ⚠️ **Beta software.** Expect hardware-specific issues, especially with DACs. Not plug-and-play.

---

## Screenshots

<p align="center">
  <img src="now-playing.jpg" width="800" alt="Now Playing view"><br>
  <sub>Now Playing — tracklist, system telemetry, audio chain status</sub>
</p>

<p align="center">
  <img src="library.jpg" width="800" alt="Library view"><br>
  <sub>Library — filters by decade, format, rating</sub>
</p>

<p align="center">
  <img src="artist-discography.jpg" width="800" alt="Artist discography view"><br>
  <sub>Artist page — local + Discogs discography</sub>
</p>

<p align="center">
  <img src="audio-chain.jpg" width="800" alt="Audio chain view"><br>
  <sub>Audio chain — signal path from source to output</sub>
</p>

---

## Features

**Formats**
FLAC · WAV · ALAC · AIFF · MP3 · AAC · M4A · OGG · WavPack · DSF/DFF (ASIO Native + DoP) · CUE sheets · gapless
**Audio engine**
ASIO native / WASAPI exclusive / DAC capability/stability probing.
**DSP**
- FIR convolution (up to 10M taps, experimental) — GPU-accelerated via OpenCL (AMD / NVIDIA / Intel)
- SoXR VHQ resampling
- PCM → DSD real-time upsampling (DSD64 → DSD256+), 5th-order Σ-Δ modulator with Hermite interpolation + look-ahead trellis
- VST3 plugin chain (JUCE host)
- ReplayGain (track/album, configurable preamp)
**Analysis**
Real-time spectrum analyzer · goniometer · True Peak / LUFS meters · test signal generator (sine, impulse, multitone, noise)
**Library**
Drag & drop playlists · smart filters · radio streaming (HTTP/ICY, M3U/PLS)
**Metadata**
Discogs · Last.fm · Groq AI summaries (albums/artists)
---
