# LiteMcraft PC (low-end fork notes)

This fork adds a **desktop-oriented low-end profile** designed for keyboard-first play and smoother framerate on weak PCs.

## What changed

- Added CMake option `LITEMCRAFT_DESKTOP_LOWEND` (enabled by default).
- Added compile define `LITEMCRAFT_DESKTOP_LOWEND=1` when the option is ON.
- In low-end mode, default graphics options are tuned for performance:
  - `fpsLimit = 1` (intended 60 FPS target in this codebase)
  - Fancy graphics OFF
  - Ambient occlusion OFF
  - Clouds OFF

## Visual Studio 2012 compatibility

- The main CMake target now falls back to **C++11** when building with **MSVC 1700 (VS2012)**.
- GCC/Clang-specific flags are now gated to non-MSVC compilers.
- GNU/Clang linker options for whole-archive are disabled on MSVC.

> Note: This repository is still a decompilation project and may require additional platform/toolchain work before a complete Windows runtime is fully playable.

## Usage

Default (low-end mode ON):

```bash
cmake -S . -B build
```

Disable low-end defaults:

```bash
cmake -S . -B build -DLITEMCRAFT_DESKTOP_LOWEND=OFF
```
