# Cappture for Claude

Cappture is a camera and screen-capture app for the Mac. This plugin lets Claude search the screenshots, screen recordings and photos you take with Cappture, and read the text in them, the links they contain and the transcripts of recordings — so you can ask "what was the address in that screenshot from Tuesday?" and get an answer.

## What it runs and what it sends

- It runs one file, `server/cappture-mcp`, a short shell script that starts the Cappture app you already have installed (`/Applications/Cappture.app`) with `--mcp-stdio`.
- That bridge talks only to Cappture on your Mac, at `127.0.0.1`. Nothing is downloaded, and nothing is sent to any server by this plugin.
- The first time Claude asks, Cappture shows **Allow** / **Don't Allow**. Only after you allow it does Claude get a key, kept on your Mac.
- What Claude may read — screenshots, recordings, text, transcripts, camera photos — is chosen in Cappture › Settings › AI, and every request is listed there.

## On claude.ai, Claude Desktop and the Claude mobile apps

The plugin also connects to `https://clouddashboard.getcappture.com/mcp`, Cappture's remote connector. You sign in with your Cappture account and allow Claude once; each request is then carried to a Mac of yours that has **Answer Claude on the web** turned on (Cappture › Settings › AI), answered there, and only that answer comes back. Nothing is kept after the answer is delivered.

## Requirements

- A Mac with [Cappture](https://www.getcappture.com) installed.
- In Cappture, Settings › AI › **Let AI tools ask Cappture** turned on.

## Tools

| Tool | What it does |
| - | - |
| `search_captures` | Finds captures by the words in them, their kind or when they were taken |
| `get_capture` | One capture's details |
| `get_text` | The text read from a capture |
| `get_links` | Links found in a capture |
| `get_transcript` | A recording's transcript |
| `pinboards` | Albums, and adding captures to them |

The `find-captures` skill tells Claude when and how to use them.

## Privacy

Cappture's privacy policy: https://www.getcappture.com/legal/privacy
