# pi-web-access

Web search, page fetching, source checks, PDF extraction, and video analysis for the Pi coding agent.

## Install

```sh
pi install git:github.com/vimhead/pi-web-access
```

Use current Pi and Node.js 24+, then run **`/reload`**. Enabled by default in [Vipi](https://github.com/vimhead/vipi).

## Use

Ask Pi to search, read a URL, or check a claim. The agent calls `load_web_search_tools` to activate `web_search`, `fetch_content`, `source_check`, and `get_search_content`.

- **`/websearch`** opens search and source review in a browser.
- **`/search`** browses stored results.
- **`/curator off`** returns results without browser review.

Search works without an API key through Exa MCP. Configure providers in `~/.pi/web-search.json`, or `web-search.json` under `PI_CODING_AGENT_DIR`. For example:

```json
{ "provider": "brave", "braveApiKey": "$BRAVE_API_KEY", "workflow": "none" }
```

PDFs support local text extraction; hosted extraction and video analysis may require provider credentials. Frame extraction requires `ffmpeg`, plus `yt-dlp` for YouTube.

Browser-cookie access is off by default. Queries and content sent to hosted providers are subject to those providers’ policies.

Disable in `/vipi` and sync, or run `pi remove git:github.com/vimhead/pi-web-access` and reload.
