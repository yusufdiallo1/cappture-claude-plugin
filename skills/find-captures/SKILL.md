---
name: find-captures
description: Find something the user captured on their Mac with Cappture — a screenshot, screen recording or photo — by the words in it, and use its text, links or transcript. Use when the user mentions a screenshot, a recording, "that thing I captured", or asks what was on their screen.
---

# Finding captures with Cappture

Cappture's MCP server (this plugin's `cappture` server) answers on the user's Mac.

1. Call `search_captures` with the words the user remembers (`query`), and `kind` if they said screenshot, recording, photo or video. Leave `query` out to list the newest.
2. For the capture that matches, call `get_text` for the words read from it, `get_links` for its links, or `get_transcript` for a recording's speech.
3. Quote what you used and name the capture (its file name and when it was taken), so the user can find it in Cappture's Library.

If a call says Cappture isn't running or that access wasn't allowed, tell the user to open Cappture and allow Claude when it asks (Settings > AI > Let AI tools ask Cappture). Camera photos and videos are hidden unless the user turns them on there.
