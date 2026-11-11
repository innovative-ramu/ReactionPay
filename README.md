# ReactionPay
# ReactionPay 💝

> Live face-to-face video gifting with instant PayPal Sandbox transactions and automated multimodal AI emotion memory capture.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## 📌 Live Demo
* **Cloudflare Pages Deployment:** `YOUR_CLOUDFLARE_PAGES_URL_HERE`
* **Demo Video:** `YOUR_YOUTUBE_UNLISTED_LINK_HERE`

---

## 💡 About the Project
ReactionPay was born out of a real-life long-distance relationship. When transferring money or gifting loved ones abroad, existing payment systems feel cold and transactional—you send funds, numbers change on a screen, and the human moment is lost. ReactionPay merges real-time video calling with in-call gifting, automatically capturing the recipient's genuine smile the exact second the gift lands.

The entire application was designed, coded, debugged, and deployed exclusively on an **Android smartphone** using **Acode**, version controlled with Git, and hosted on **Cloudflare Pages**.

---

## 🛠️ Technology Stack & Core Integrations

### 1. PayPal Developer Platform (Sandbox)
* **SDK Used:** PayPal JavaScript SDK (`client-id=sb`, universal Sandbox mode).
* **Role in Project:** 
  * Powers an in-call glassmorphism payment drawer over the live video call without pausing media playback.
  * Dynamically manages the order lifecycle via `actions.order.create` for preset tiers ($5, $20, $50, $100) or custom gift values.
  * Employs `actions.order.capture()` on payment approval to reconcile the in-app wallet balance and trigger a WebRTC DataChannel event across devices.

### 2. Artificial Intelligence Engine
* **Model Used:** Google Gemini 2.5 Flash Multimodal Vision API (`gemini-2.5-flash:generateContent`) with on-device heuristics fallback.
* **Role in Project:**
  * Synchronously captures a video frame from the recipient's live stream via an off-screen HTML5 `<canvas>` element the moment payment confirms.
  * Analyzes micro-expressions to evaluate facial joy and compute a happiness index ($0\text{--}100\%$).
  * Generates a poetic, context-aware memory caption that is stamped onto a retro downloadable Polaroid card saved to the in-app Memory Vault.

### 3. Open-Source Real-Time Video (WebRTC)
* **Library Used:** PeerJS with distributed Google STUN servers (`stun.l.google.com:19302`).
* **Role in Project:** Enables zero-setup peer-to-peer browser video and bidirectional data streaming using human-readable room IDs, avoiding proprietary backend servers or user authentication hurdles.

---

## 🚀 Local Setup & Quick Start

Because ReactionPay is built entirely with client-side web standards, running it locally requires no runtime installations (like Node.js or Python):

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_GITHUB_USERNAME/ReactionPay.git](https://github.com/YOUR_GITHUB_USERNAME/ReactionPay.git)
   cd ReactionPay
   
