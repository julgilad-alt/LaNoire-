# LaNoire-
Bit-perfect audio player with DSD upsampling — built with Tauri + Rust


What it does
LaNoire plays your music the way it was recorded. No Windows mixer, no resampling artifacts, no compromises.

DSD native playback — DSF files over DoP (DSD over PCM), straight to your DAC
PCM → DSD upsampling — converts any FLAC/WAV/MP3 to DSD64/128/256/512 in real time
GPU-accelerated FIR filtering — OpenCL convolution engine (OLS partition method) with 10M-tap filter support
SoXR resampling — VHQ sample rate conversion before the DSD modulator
5th-order Σ-Δ modulator — Hermite cubic interpolation + look-ahead trellis (depth 3)
VST plugin chain — load and process VST3 plugins via JUCE before the DSD stage
ASIO + WASAPI — low-latency output, bit-perfect on ASIO, F32 on WASAPI shared
ReplayGain — track and album normalization with configurable preamp
Radio streaming — HTTP/ICY streams with metadata, M3U/PLS playlist resolution


Stack
LayerTechnologyUITauri + Vue.jsAudio engineRust (cpal, symphonia, ringbuf)DSP / VSTJUCE (C++ DLL via FFI)ResamplingSoXR (wrapped C++ → Rust FFI)GPU FIROpenCL 1.2+ (AMD / NVIDIA / Intel)DSD modulatorPure Rust Σ-Δ V2.3

Supported formats
FLAC WAV MP3 AAC M4A OGG DSF

Requirements

Windows 10/11 (64-bit)
ASIO driver recommended for DSD output
OpenCL-capable GPU for FIR filtering (optional — bypassed if unavailable)
DAC with DoP support for DSD playback


Status
Early development. No releases yet
