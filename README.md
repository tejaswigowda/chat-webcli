# Chat webCLI

A browser-based LLM chat app that runs large language models **entirely in your browser** using [WebLLM](https://webllm.mlc.ai/) and WebGPU - no server, no API keys, no data leaves your device.

► **Live app:** [https://tejaswigowda.com/chat-webCLI/](https://tejaswigowda.com/chat-webCLI/)

First in the webCLI family of zero-egress, offline-first browser tools, alongside [ffmpeg-webCLI](https://github.com/tejaswigowda/ffmpeg-webCLI) and [whisper-webCLI](https://github.com/tejaswigowda/whisper-webCLI). Same look and feel, same privacy promise: your conversations never leave your device.

---

## Key Features

✔ **No Server Uploads** – All inference happens entirely on your device

✔ **Dropdown of WebLLM Models** – 30+ models with VRAM requirements shown

✔ **One-Click Model Loading** – Live progress bar; model cached locally on first use

✔ **Streaming Responses** – Token-by-token output as the model generates

✔ **Multi-Chat Support** – Create multiple conversations, all stored locally with full history

✔ **Chat Management** – Edit chat titles, view which model was used in each conversation

✔ **Local Data Persistence** – All conversations and history automatically saved to browser storage

✔ **Offline-First PWA** – Works completely offline after first use; install as a native app

✔ **Screen Wake Lock** – Screen stays active during long model inference

✔ **Privacy First** – Zero data collection, zero telemetry; your conversations stay private

---

## What It Replaces

| Service | What webCLI does instead |
|---|---|
| ChatGPT / Claude | Run any WebLLM-compatible model locally in your browser |
| Copilot | No API keys, no auth, no cloud dependency |
| Google Bard / Gemini | Conversation stays on your device; model weights cached locally |
| Hugging Face Chat | Same models, but zero server uploads |

The difference that matters: every cloud LLM tool uploads your prompt to a server. Some are free with limits, some charge per message - but all of them see what you write, and all are subject to data breaches, subpoenas, and privacy-policy changes.

Chat webCLI handles conversations for free, with prompts and responses that never leave your device.

---

## Usage

1. **Create or Switch Chats** – Click **New Chat** in the sidebar to start a conversation, or click any existing chat to switch to it
2. **Rename Conversations** – Double-click a chat title to edit it; press Enter to save or Escape to cancel
3. **Pick a Model** – Select from the dropdown (smaller models load faster)
4. **Load Model** – Click Load Model; the model downloads and caches on first use (subsequent loads are instant)
5. **Start Chatting** – Type your message and press `Enter` (or `Shift+Enter` for a new line)
6. **Stream Output** – Watch responses generate token-by-token
7. **View Chat Details** – Each chat shows the model used below its title in the sidebar
8. **Delete Conversations** – Click the trash icon next to a chat to remove it

All conversation data is automatically saved to your browser's local storage and persists across sessions.

## Requirements

- A browser with **WebGPU support** (Chrome 113+, Edge 113+, or Firefox 120+ recommended)
- Sufficient VRAM for the chosen model (shown in the dropdown)

Verify WebGPU support at [webgpureport.org](https://webgpureport.org/).

## Model Sizes & Performance

The VRAM column in the dropdown reflects the `vram_required_MB` value from the WebLLM model registry. Models are downloaded once and cached in the browser; subsequent loads are instant.

---

## How It Works

1. **Open the app** – Pure HTML/CSS/JS served from the `docs/` folder
2. **Pick a model** – Choose from WebLLM's prebuilt model list
3. **Load & cache** – Downloads the model weights on first use; they persist in your browser
4. **Chat locally** – All inference runs on your GPU via WebGPU; no network requests during chat
5. **Download stays local** – Model weights are cached in browser storage for instant reuse

---

## Privacy & Data Sovereignty

Your conversations are yours - always.

This app runs inference **100% on your own hardware** inside your browser. There is no backend, no cloud API, and no telemetry of any kind.

| What happens | Detail |
|---|---|
| **Model weights** | Downloaded once from Hugging Face; cached locally in your browser |
| **Your prompts** | Never transmitted anywhere - processed entirely on-device |
| **Responses** | Generated locally by your GPU via WebGPU |
| **Conversation history** | Stored in browser's localStorage; persists across sessions, you control deletion |
| **Third-party servers** | Zero involvement after the initial model download |

Because the model runs on your device, you remain in full control of your data. This makes Chat webCLI suitable for sensitive or personal conversations where cloud-based AI assistants are not appropriate.

---

## Chat Management

All conversations are saved locally in your browser and persist across sessions:

- **Create Chats** – Click **New Chat** to start a new conversation anytime
- **Organize Chats** – Edit chat titles by double-clicking them in the sidebar
- **Track Models** – Each chat displays which model was used for that conversation
- **Full History** – All messages in each chat are automatically preserved
- **Delete Chats** – Click the trash icon to remove any conversation (permanent within your device)
- **No Cloud Sync** – Chats remain on your device only; not synced anywhere

Your chat data is stored in your browser's `localStorage` under the key `chat-webCLI-chats`. You can view, export, or delete it anytime via your browser's developer tools.

---

## Running Locally

```bash
git clone https://github.com/tejaswigowda/chat-webCLI.git
cd chat-webCLI

# Serve with any static server:
npx serve docs
# or
python3 -m http.server --directory docs
```

Then open `http://localhost:3000` (or the port shown by your server).

---

## Tech Stack

- [WebLLM](https://github.com/mlc-ai/web-llm) via CDN (`https://esm.run/@mlc-ai/web-llm`)
- [WebGPU](https://www.w3.org/TR/webgpu/) for GPU acceleration
- Pure HTML/CSS/JS — no build step, no dependencies

---

## Acknowledgments

Part of the webCLI family of zero-egress browser tools:
- [ffmpeg-webCLI](https://github.com/tejaswigowda/ffmpeg-webCLI) – Video & audio processing
- [whisper-webCLI](https://github.com/tejaswigowda/whisper-webCLI) – Speech-to-text transcription

- [WebLLM](https://github.com/mlc-ai/web-llm) — ML compilation & WebGPU runtime
- [OpenAI](https://openai.com/) — Model architectures and best practices

---

## License

GPL-3.0 — see [LICENSE](LICENSE) for details.
