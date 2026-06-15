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

✔ **Full Chat History** – Conversation persists for the session; cleared on reload

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

1. **Pick a Model** – Select from the dropdown (smaller models load faster)
2. **Load Model** – Click Load Model; the model downloads and caches on first use (subsequent loads are instant)
3. **Start Chatting** – Type your message and press `Enter` (or `Shift+Enter` for a new line)
4. **Stream Output** – Watch responses generate token-by-token

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
| **Conversation history** | Stored only in memory for the current session; cleared on reload |
| **Third-party servers** | Zero involvement after the initial model download |

Because the model runs on your device, you remain in full control of your data. This makes Chat webCLI suitable for sensitive or personal conversations where cloud-based AI assistants are not appropriate.

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
