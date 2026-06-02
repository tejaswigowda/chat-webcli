# WebLLM Chat

A simple single-page chat app that runs large language models **entirely in the browser** using [WebLLM](https://webllm.mlc.ai/) and WebGPU — no server, no API keys, no data leaves your device.

---

## 🔒 Privacy & Data Sovereignty

> **Your conversations are yours — always.**

This app runs inference **100% on your own hardware**, inside your browser. There is no backend, no cloud API, and no telemetry of any kind.

| What happens | Detail |
|---|---|
| **Model weights** | Downloaded once from Hugging Face, then cached locally in your browser |
| **Your prompts** | Never transmitted anywhere — processed entirely on-device |
| **Responses** | Generated locally by your GPU via WebGPU |
| **Conversation history** | Stored only in memory for the current session; cleared on reload |
| **Third-party servers** | Zero involvement after the initial model download |

Because the model runs on your device, you remain in full control of your data. This makes WebLLM Chat suitable for sensitive or personal conversations where cloud-based AI assistants are not appropriate.

---

## Features

- Dropdown of all WebLLM-supported models with VRAM requirements
- One-click model loading with a live progress bar
- Streaming chat responses (token-by-token)
- Full conversation history per session
- `Enter` to send, `Shift+Enter` for a new line

## Requirements

- A browser with **WebGPU support** (Chrome 113+ recommended)
- Sufficient VRAM for the chosen model (shown in the dropdown)

Verify WebGPU support at [webgpureport.org](https://webgpureport.org/).

## Usage

Open `docs/index.html` directly in a WebGPU-capable browser, or serve it with any static file server:

```bash
npx serve docs
# or
python3 -m http.server --directory docs
```

Then:
1. Pick a model from the dropdown (smaller models load faster)
2. Click **Load Model** — the model is downloaded and cached on first use
3. Start chatting

## Model sizes

The VRAM column in the dropdown reflects the `vram_required_MB` value from the WebLLM model registry. Models are downloaded once and cached in the browser; subsequent loads are instant.

## Tech

- [WebLLM](https://github.com/mlc-ai/web-llm) via CDN (`https://esm.run/@mlc-ai/web-llm`)
- Pure HTML/CSS/JS — no build step
