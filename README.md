# La Noire

> Bit-perfect audio player with DSD upsampling — built with Tauri + Rust

---

## What it does

LaNoire plays your music the way it was recorded. No Windows mixer, no resampling artifacts, no compromises.

- **DSD native playback** — DSF files over DoP, straight to your DAC
- **PCM → DSD upsampling** — converts FLAC/WAV/MP3 to DSD64/128/256/512 in real time
- **GPU-accelerated FIR filtering** — OpenCL OLS convolution engine, up to 10M taps
- **SoXR resampling** — VHQ sample rate conversion before the DSD modulator
- **5th-order Σ-Δ modulator** — Hermite cubic interpolation + look-ahead trellis (depth 3)
- **VST plugin chain** — JUCE-powered VST3 processing before the DSD stage
- **ASIO + WASAPI** — bit-perfect on ASIO, F32 on WASAPI shared
- **ReplayGain** — track/album normalization with configurable preamp
- **Radio streaming** — HTTP/ICY with metadata, M3U/PLS support

---

## Stack

| Layer | Technology |
|---|---|
| UI | Tauri + Vue.js |
| Audio engine | Rust (cpal, symphonia, ringbuf) |
| DSP / VST | JUCE (C++ DLL via FFI) |
| Resampling | SoXR (C++ → Rust FFI) |
| GPU FIR | OpenCL 1.2+ (AMD / NVIDIA / Intel) |
| DSD modulator | Pure Rust Σ-Δ V2.3 |

---

## Supported formats

`FLAC` `WAV` `MP3` `AAC` `M4A` `OGG` `DSF`

---

## Requirements

- Windows 10/11 64-bit
- ASIO driver recommended for DSD output
- OpenCL GPU for FIR filtering (optional — bypassed if unavailable)
- DAC with DoP support for DSD playback

---

## Status

Early development. No releases yet.
