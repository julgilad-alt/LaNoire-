La Noire

Bit-perfect audio player for Windows 64-bit — no mixer, no resampling artifacts, no compromises.

Beta software. Expect hardware-specific issues, especially on DACs. Not plug-and-play.

Features

Playback — FLAC, WAV, ALAC, AIFF, MP3, AAC, M4A, OGG, WavPack, DSF/DFF (ASIO Native + DoP), CUE sheets, gapless.

Audio engine — ASIO native (Steinberg SDK) with WASAPI exclusive fallback, bit-perfect output, DAC capability/stability probing.

DSP

FIR convolution (up to 10M taps, experimental) — GPU-accelerated via OpenCL (OLS convolution, AMD/NVIDIA/Intel)
SoXR VHQ resampling
PCM → DSD real-time upsampling (DSD64 to DSD256+), 5th-order Σ-Δ modulator with Hermite interpolation + look-ahead trellis
VST3 plugin chain (JUCE host)
ReplayGain (track/album, configurable preamp)

Analysis — real-time spectrum analyzer, goniometer, True Peak/LUFS meters, test signal generator (sine, impulse, multitone, noise).

Library — drag & drop playlists, smart filters, radio streaming (HTTP/ICY, M3U/PLS).

Metadata — Discogs, Last.fm, Groq AI summaries (albums/artists).

Stack
Layer	Technology
UI	Tauri + Vue.js
Audio engine	Rust (cpal, symphonia, ringbuf)
DSP / VST	JUCE (C++ DLL via FFI)
Resampling	SoXR (C++ → Rust FFI)
GPU FIR	OpenCL 1.2+
DSD modulator	Pure Rust Σ-Δ V2.3
Requirements
Windows 10/11 64-bit
ASIO driver recommended for DSD output
OpenCL GPU for FIR filtering (optional, bypassed if unavailable)
DoP-capable DAC for DSD playback
Build

Requires: Rust toolchain, C++ compiler + ASIO SDK, OpenCL runtime.

(Platform-specific instructions: TODO)

Bug reports

Please include: DAC model, driver (ASIO/WASAPI) + version, OS version, playback mode (PCM/DSD/DoP), sample rate/DSD rate, buffer size, expected vs actual behavior, and logs (ASIO + DSP if available).

Known limitations

DAC behavior varies significantly between manufacturers. High-tap FIR modes are experimental. GPU acceleration depends on driver support.

---

## Status

Early development. No releases yet.
