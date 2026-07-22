# youtube-transcript-cli skill

Fetch and display YouTube video transcripts/subtitles as plain text from a URL or video ID — no API key required, no browser automation.

Works with 🦞 [OpenClaw](https://www.clawhub.ai/therohitdas/youtube-full) (ClawdBot/Moltbot), <img src="assets/hermes.png" alt="" height="14"> [Hermes Agent](https://hermes-agent.nousresearch.com), Claude Code, Cursor, Antigravity, PI, Opencode and any agent that supports the [Agent Skills](https://skills.sh) format.

## What it does

Agents can fetch YouTube transcripts on demand — given a video URL or ID — and return clean text with optional timestamps, language selection, and chunked output for long videos.

## Installation

### npx skills

```sh
npx skills add https://github.com/onigetoc/youtube-transcript-cli-skill
```

### CLI (optional, for direct use)

```sh
npm install -g youtube-transcript-cli
```

## How it works

The skill uses [`youtube-transcript-cli`](https://github.com/onigetoc/youtube-transcript-cli) under the hood. Once installed, the agent runs it directly (or via `npx` for one-shot use).

### Trigger examples

```
Give me the transcript of https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

```
Extract transcript in French with timestamps for dQw4w9WgXcQ
```

```
Get the English and French transcript in 6000-char chunks
```

## Options

| Flag | Description |
|------|-------------|
| `--lang=en,fr` | Language priority list (comma-separated) |
| `--timestamps` | Include `[mm:ss]` timestamps |
| `--max=N` | Split output into chunks of N characters |
| `--srt` | Output in SRT subtitle format |

**Always quote URLs** — shell operators like `&` will break unquoted URLs.

## Output

- Plain text transcript (default) or SRT subtitles (`--srt`)
- Timestamps in `[mm:ss]` or `[hh:mm:ss]` format
- Automatic chunking when `--max` is set

## File structure

```
.agents/skills/youtube-transcript-cli/
├── SKILL.md      # Skill instructions for the agent
└── README.md     # This file
```

## About

A skill for the [Agent Skills](https://skills.sh) ecosystem. Uses the open-source [`youtube-transcript-cli`](https://github.com/onigetoc/youtube-transcript-cli) — no YouTube API key needed.
