# Questionable

**Questionable** is a real-time, AI-powered multiplayer guessing game where players face off against **JOD THE ALMIGHTY**—an all-knowing, cryptic AI entity powered by Llama 3.1. 

Players take turns submitting questions to uncover the secret target word before running out of questions. Will you decipher JOD’s cryptic hints, or will he be disappointed in your efforts?

[![Play Game](https://img.shields.io/badge/PLAY_GAME-Vercel-3b82f6?style=for-the-badge&logo=vercel&logoColor=white)](https://question-able.vercel.app)
---

## 🚀 Tech Stack & Architecture

### **Frontend**
* **React (Vite):** Fast, modern UI rendering with state-driven view routing.
* **Socket.io-Client:** Handles real-time event streaming, turn order synchronization, lobby settings, and live streaming AI response chunks.
* **Vercel:** Optimized static hosting with global CDN delivery.

### **Backend**
* **Node.js & Express:** Lightweight server setup and WebSocket orchestration.
* **Socket.io:** Manages stateful game rooms, sequential turn enforcement, player disconnections, and real-time room configuration updates.
* **Groq SDK (`llama-3.1-8b-instant`):** Delivers lightning-fast AI completions and streaming responses for hint generation and secret word selection.
* **Custom Token Bucket Rate Limiter:** Protects the Groq API pipeline against spam and rate-limit abuse.
* **Render:** Continuous deployment and hosting for the WebSocket server.

---

## 📜 How to Play

1. **Enter the Realm:** Pick a unique username at the entry portal.
2. **Create or Join a Lobby:**
   * **Host:** Initialize a new lobby, customize the number of rounds, maximum questions per round, and player capacity. Share your generated Room Code with friends.
   * **Player:** Enter a Room Code to join an existing lobby.
3. **The Game Begins:**
   * **JOD Speaks:** At the start of every round, JOD selects a secret noun (10 letters or fewer).
   * **Turn-Based Inquiries:** Players take strict turns submitting questions to JOD.
   * **Cryptic Hints:** JOD streams truthful, cryptic hints to guide the active player without revealing the target word.
4. **Winning & Losing:**
   * **Guessing the Word:** If a player's query contains or matches the exact secret word, JOD bestows victory for that round!
   * **Running Out of Questions:** If the lobby reaches the maximum question limit before guessing the word, JOD wins the round.
   * After all rounds conclude, players return to the lobby to adjust settings or start a fresh match.

---

## ✨ Features

* **Streaming AI Responses:** Real-time token streaming from Groq via Socket.io chunk events for quick feedback.
* **Turn Synchronization:** Enforces strict sequential player turns and cycling logic across all connected clients.
* **Token-Bucket Rate Limiting:** Built-in rate-limiting algorithm to manage request spikes gracefully.
* **Dynamic Room Management:** Real-time player listings, host reassignment on disconnection, player kicking mechanisms, and customizable game parameters.
* **In-Game Player Chat:** Separate player-to-player chat sidebar running concurrently alongside the main AI game feed.
