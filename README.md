# Blocky — Stack & Smile! 🧱

Blocky is a high-performance, privacy-focused block-stacking game developed as an installable Progressive Web App (PWA). This project serves as the foundational engine for the BKAOS suite, demonstrating a commitment to clean, dependency-free software architecture.

**[Play It Live](https://yofranky.github.io/blocky-pwa/)**

---

## The Experience

Blocky reimagines the classic stacking genre with a focus on deep customization and player-controlled accessibility.

* **Dynamic Gameplay:** Players can rotate through seven hand-tuned color palettes and engage with "Shape KAOS" difficulty decks, which introduce non-standard piece sizes to the core loop.
* **Touch-First Design:** The controls are engineered for mobile, utilizing gesture-based inputs: drag to move, tap to rotate, and swipe to hard-drop. Desktop users retain full keyboard support.
* **Comprehensive Accessibility:** The game includes an accessibility suite that goes beyond standard compliance. Features such as high-contrast modes, Okabe-Ito colorblind-safe palettes, and independent haptic/sound toggles ensure the experience remains inclusive and customizable for every player.

## The Development Process

As with my other projects, Blocky was built through an AI-assisted development workflow. My role as the Technical Program Manager and lead developer was to establish the structural foundation of the game, ensuring that all logic—from score tracking to render cycles—remained decoupled and efficient.

My kids served as the primary testing team for this project. Their direct feedback was instrumental in refining the gesture-based controls and ensuring the "Shape KAOS" difficulty balance provided a satisfying challenge. This project allowed me to successfully implement a robust global settings architecture, which ensures that user preferences are maintained throughout the game session.

## Why a PWA?

I elected to build Blocky as a PWA to prioritize immediate access and maintain total control over the user experience, bypassing the limitations of traditional app store ecosystems.

* **Zero-Friction Access:** The game is accessible via a direct web link, allowing users to start playing immediately without account creation or installation queues.
* **Privacy-First:** The game features zero network calls. There are no trackers, no ad SDKs, and no external font dependencies. All data—including high scores and settings—is stored locally on the user's device.
* **Offline Capability:** Thanks to a custom-built service worker, the game functions perfectly offline once cached, providing the reliability of a native application.

## Technical Implementation

Blocky is built using vanilla HTML, CSS, and JavaScript, ensuring that the codebase remains lightweight and fully auditable.

* **Rendering:** All visuals are handled via the Canvas API.
* **Settings Architecture:** I utilized a centralized `Settings` object and CSS custom properties to apply global accessibility changes, which avoids the complexity of redundant conditional logic.
* **Gesture Handling:** I implemented a custom input system that differentiates between taps, drags, and swipes by utilizing timing and distance thresholds on raw pointer events.

## Deployment and Local Use

This project is hosted via GitHub Pages and is fully installable as a native-feeling app.

1. **Mobile:** Navigate to the game link in your browser, then select "Add to Home Screen" from your browser’s menu.
2. **Desktop:** Select the "Install" icon in your browser’s address bar.

For those interested in the source code, you can run the project locally by executing `npx serve .` in your terminal. A local server is required to trigger the service worker and offline functionality.

---

*Blocky is a BKAOS project.*
