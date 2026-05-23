
# 🛑 ScrollSnap: The Local-First Doomscrolling Interceptor

Most app blockers just lock your screen. ScrollSnap takes a different approach: it physically counts how many short-form videos (Reels, Shorts) you consume and uses **On-Device Edge AI** to intervene when you hit a toxic threshold. 

Crucially, **ScrollSnap does not have internet permissions.** It is a 100% offline, privacy-first application. Your scrolling habits never leave your device.

## 🧠 Core Architecture

This project bridges traditional Android system architecture with next-generation local AI inference:

* **The Tracker (Java):** Utilizes an Android `AccessibilityService` to monitor `TYPE_VIEW_SCROLLED` events specifically within targeted package names (e.g., Instagram, YouTube) while the screen is active.
* **The Vault (Room DB / SQLite):** Logs swipe metrics and session durations strictly to an encrypted local database.
* **The Edge AI (Google AICore / Gemini Nano):** Orchestrates a local Small Language Model (SLM) to generate personalized, context-aware interventions completely offline.

## 🚀 Why This Exists (The Privacy Problem)
Existing screen-time apps either rely on simple timers (which are easily ignored) or require invasive permissions that send your usage data to third-party servers. ScrollSnap solves this by executing the tracking, data storage, and AI generation entirely on the local device's NPU (Neural Processing Unit).

## 🛠️ Tech Stack
* **Language:** Java
* **Framework:** Native Android SDK
* **Local Storage:** Room Persistence Library
* **On-Device ML:** Google AICore / LiteRT

## 🚧 Current Development Status
Currently in active development.
- [ ] **Phase 1:** Implement core Accessibility Service to capture scroll events.
- [ ] **Phase 2:** Integrate Room database for local session logging.
- [ ] **Phase 3:** Orchestrate local AI inference for user intervention.

---
*Built as a showcase of bridging enterprise Java development with local-first AI engineering.*
