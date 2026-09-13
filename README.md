# mobleyhelms.com — canonical reference copy

**Source of truth for deployment is `/Users/johnmobley/nginx/`, not this
directory.** The real Cloudflare Worker + assets live at:

- Worker: `/Users/johnmobley/nginx/workers/mobleyhelms.com/` (`src/worker.js`, `wrangler.toml`)
- Static assets it serves: `/Users/johnmobley/nginx/sites/mobleyhelms.com/`

This directory exists as the per-venture reference copy the rest of the
portfolio's convention expects at `/Users/johnmobley/<domain>/` (see
`AGENTS.md`'s "check `/Users/johnmobley/<name>` before asking" section) —
but it had drifted badly out of sync with production. As of 2026-09-13 a
depth audit found `index.html` here was a 722KB unrelated MASCOM-WebOS/
"fecundity index" dump (commit `20e8fe5`, "[MASCOM] Restore maximal
fecundity index"), not the real campaign page — the live site
(`https://mobleyhelms.com/`) has always served the clean 83,608-byte
campaign page from `nginx/sites/mobleyhelms.com/index.html`, confirmed
byte-identical via live `curl`. This directory's files have been
re-synced from that real source.

`blog.html`, `assets/`, and `versions/` in this directory are leftover
noise from the same contamination episode (fabricated "Fecundity Loom" /
"Autopoiesis Phase 4" copy, not real content, not linked from the live
site, not part of the deployed asset set) — left in place rather than
deleted, but don't treat them as real.

**If you're re-syncing this directory again later**: copy from
`nginx/sites/mobleyhelms.com/` (all files) and diff `index.html` against
a live `curl https://mobleyhelms.com/` before trusting either copy.
