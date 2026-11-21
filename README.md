# Nebula AI Studio

Run local AI and every major cloud AI from one clean desktop app — built for cheap laptops and old PCs.

![version](https://img.shields.io/badge/version-2.2.0-7c5cff) ![platform](https://img.shields.io/badge/platform-Windows-blue) ![license](https://img.shields.io/badge/license-MIT-green)

Nebula AI Studio is an Electron desktop app that puts local AI and cloud AI side by side:

- **Chat** with OpenAI, Anthropic, Google Gemini, xAI Grok, DeepSeek, Mistral, Groq, Cerebras, Cohere, Perplexity, OpenRouter, GitHub Models, AirLLM, or your own OpenAI-compatible endpoint. Bring your own keys; they stay on your PC.
- **Agent mode** with a Claude-Code-style tool loop (read, write, edit, bash, glob, grep) and three permission levels: **Ask first**, **Allowed (folder)**, and **Bypass (full PC)** for when you truly mean it.
- **Local AI, zero terminal**: a portable Ollama runtime is built in. One click installs the engine, one click pulls a model (or imports any GGUF). If your PC can't run a model the normal way, the **AirLLM low-RAM backend** streams giant models (Kimi K3 2.8T, DeepSeek-V3 671B, Qwen3-235B) layer by layer so they fit in a few GB of RAM — honestly labeled 3-10× slower.
- **Model Gallery**: 33 curated open-source models across 7 categories, plus live OpenRouter cloud search.
- **Skills**: teach the AI new tricks with a no-code editor (or write the JSON yourself); active skills are injected into every chat and agent reply.
- **Web search**: toggle 🌐 Web and the app fetches current search results before the model answers.
- **Reasoning modes**: per-model thinking controls (Instant / low / medium / high) where the provider supports them.
- **Context tracker**: a live ring showing how much of the model's context window your conversation uses.
- **Image generation** with current image models, **chat export to Markdown**, data export/import, themes and accent colors.

## Download

Grab `NebulaStudio.exe` from the [latest release](https://github.com/Expstudiooficial/projectnebula/releases/latest), put it anywhere, run it. That is the whole install — the engine and models download on demand into your user folder.

Windows may show a SmartScreen prompt on first run (the exe is not code-signed yet). Click "More info" → "Run anyway".

## Build from source

```bat
git clone https://github.com/Expstudiooficial/projectnebula.git
cd projectnebula
npm install
npx electron .        :: run the app
npm run dist          :: build the portable exe
```

## Security notes

- API keys are stored in plain JSON in your user data folder (`%APPDATA%\nebula-ai-studio` when packaged). Nowhere else.
- Agent **Bypass** mode gives the model real shell access to the whole PC with no prompts. It is off by default and labeled in red. Use it like Claude Code's `--dangerously-skip-permissions`: only when you understand what the agent will do.
- The app phones home exactly once per launch, to GitHub, to check for a newer release. No telemetry.

## License

MIT — see [LICENSE](LICENSE).
