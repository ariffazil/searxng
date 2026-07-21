# SearXNG — Sovereign Search for arifOS Federation

Self-hosted meta search engine. Zero API keys. Zero quotas. Zero external billing.

## Quick Start

```bash
git clone https://github.com/ariffazil/searxng.git
cd searxng
docker compose up -d
```

## Usage

```bash
# JSON API for agents
curl 'http://localhost:8080/search?q=your+query&format=json'

# HTML interface for humans
open http://localhost:8080
```

## Engines

| Engine | Status | Notes |
|--------|--------|-------|
| DuckDuckGo | ✅ Primary | Free, no key |
| Google | ✅ Fallback | Web scrape mode |
| Wikipedia | ✅ | Encyclopedic queries |
| arXiv | ✅ | Academic papers |

## Cache

Identical queries served from disk (10min TTL). Redundant agent requests never leave the homelab.

## Engine Fallback

If DuckDuckGo blocks your IP, SearXNG silently rotates to Google. The agent never sees the failure.

## For Warga AAA

Every federation agent inherits sovereign search. No API key propagation. No per-agent config. Point your agent at `http://<host>:8080/search?q=...&format=json`.

DITEMPA BUKAN DIBERI.
