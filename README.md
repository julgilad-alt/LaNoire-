# La Noire

> Bit-perfect audio player with DSD upsampling — built with Tauri + Rust

---

## What it does

LaNoire plays your music the way it was recorded# La Noire — Audio Engine (Beta)

La Noire is a high-performance audio player and DSP engine focused on bit-perfect playback, low-level ASIO control, and high-precision digital signal processing.

This is a **technical beta** for advanced users and developers.

---

# Status

- Beta software
- Expect hardware-specific issues
- Not plug-and-play
- Feedback and logs are essential

---

# Core Features

## Playback
- PCM: FLAC, ALAC, WAV, AIFF, MP3, OGG
- DSD: DFF, DSF (ASIO Native + DoP)
- WavPack support
- CUE sheets
- Gapless playback

## Audio Engine
- ASIO native (Steinberg SDK)
- WASAPI exclusive fallback
- Bit-perfect output
- DAC probing (capabilities + stability)

## DSP
- FIR convolution (up to 10M taps experimental)
- Linear / minimum phase filters
- Apodizing filters
- SoXR resampling
- Sigma-Delta modulation (order 5)
- DSD upsampling up to DSD256+

## GPU
- OpenCL DSP acceleration
- NVIDIA / AMD support (tested)

## Analysis
- Spectrum analyzer (real-time)
- Goniometer
- True Peak / LUFS meters
- Test signals (sine, impulse, multitone, noise)

## Library
- Drag & drop playlists
- ReplayGain scanning
- Smart filters
- Radio streaming

## Metadata
- Discogs integration
- Last.fm integration
- Groq AI summaries (albums / artists)

---

# Architecture

- Rust (core engine + UI via Tauri)
- C++ (ASIO engine + JUCE host for VST)
- OpenCL (GPU DSP layer)

---

# DAC Testing

La Noire performs DAC probing for:
- Supported PCM rates
- Native DSD / DoP modes
- Buffer stability
- Driver behavior

Results may vary depending on driver implementation.

---

# Bug Reports

Please include:

- DAC model
- Driver (ASIO / WASAPI) + version
- OS version
- Playback mode (PCM / DSD / DoP)
- Sample rate / DSD rate
- Buffer size
- Expected vs actual behavior
- Logs (ASIO + DSP if available)

---

# Limitations

- DAC behavior varies significantly between manufacturers
- High-tap FIR modes are experimental
- GPU acceleration depends on driver support

---

# Build

(TODO: platform-specific build instructions)

Requires:
- Rust toolchain
- C++ compiler + ASIO SDK
- OpenCL runtime No Windows mixer, no resampling artifacts, no compromises.

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
