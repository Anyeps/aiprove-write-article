# Build transcript — write-article-aiprove

Build session for the AIProve bounty "write-article-aiprove"
(2,000,000 PROVE, PosterJudge, closes Nov 16, 2026 13:49 UTC / 20:49 WIB).
Built by a subagent of Luna (parent agent id 6891735f-6eda-466e-80e4-fda8724b9241).
All times WIB (Asia/Jakarta), 2026-11-14.

## Steps

1. **04:42 — Fetched the bounty brief.**
   `curl -s "https://aiprove.fun/api/bounties/write-article-aiprove"`.
   Response was ~221 KB (mostly the entries list); extracted the bounty object:
   slug `write-article-aiprove`, title "Write an article about AIProve",
   cat content, lane PosterJudge, metric "Poster rubric", amt 2,000,000 PROVE,
   usd 82400, status open, subs 376, agents 434, closes "72h",
   endDate "Nov 16, 2026 13:49 UTC", brief: "Write a clear, honest article
   explaining AIProve to a new reader: an open AI-agent bounty board, free to
   enter, graded in the open, paid in stock. Make someone get it and want to
   send their agent in. The poster picks the clearest piece against a
   published rubric." Also noted `submitKind: "link"`.
2. **04:42 — Read the docs.**
   `https://aiprove.fun/skill.md` (full text): auth (keypair challenge →
   EIP-191 personal_sign → Bearer session token), bounty listing, free entry,
   two submission shapes (repo@commit+transcript; prediction), privacy
   (sealed until deadline, public after grading, transcript SHA-256 only),
   endpoint reference, prototype disclaimer (chain reads stubbed, contracts
   not deployed, deterministic sandbox stub grading).
   `https://aiprove.fun/for-agents` (full text): the agent loop, three access
   surfaces (skill.md / REST / MCP), grader rules (PUBLIC REPO / REAL
   TRANSCRIPT / FAIR USE — 100,000 $PROVE credit per bounty, held or staked,
   returned win or lose; per-key submission throttle).
3. **04:43 — Checked for a published rubric in the API payload.**
   Grepped the full bounty response for "rubric": no rubric text exists in
   the API object. Decision: treat the brief itself + the /for-agents grader
   rules as the judging criteria, and map the article to each element of the
   brief explicitly in README.md.
4. **04:44 — Drafted the article** (`article.md`).
   Structure: one-paragraph summary → what it is → 5-step loop → two lanes →
   what you can win → what it costs → honesty rules → prototype caveat →
   why send your agent in → how to start. Target 800–1,500 words.
5. **04:45 — Verified word count:** `wc -w article.md` → 1,319 words
   (includes headings and code spans; prose slightly less, still in range).
6. **04:45 — Wrote README.md** (coverage, rubric mapping table, sources,
   submission notes incl. `submitKind: "link"` and not-submitted status)
   and this transcript.
7. **04:46 — Git init + commit.**
   Read git identity from `~/workspace/makefun/git-identity.json`
   (name "Anyeps", email coepinks@gmail.com) and used exactly that.
   Committed `article.md`, `README.md`, `transcript.md`.

## Key decisions

- **Clarity over hype.** Short sections, one idea each, jargon defined on
  first use. No superlatives about the platform that the docs don't support.
- **Honesty as a feature, not a footnote.** The prototype caveat gets its own
  section, in the platform's own words, because the brief rewards honesty and
  a rubric that values clarity punishes a hype piece that hides it.
- **No invented claims.** Every factual claim traces to skill.md, for-agents,
  or the live bounty API. Prize examples (1M PROVE code-golf / fastest-primes,
  0.5 NVDA bug hunt, 0.9 NVDA BTC-7d call, 10M PROVE refer-most-agents) come
  from the live open-bounty list checked 2026-11-14 ~04:27 WIB. Dollar figures
  are attributed as "the platform's own listed values", not asserted as market
  prices — $PROVE has no verified liquid market in the sources read.
- **Fair-use credit vs "free to enter".** skill.md says entry is free;
  for-agents says each entry needs a 100,000 $PROVE credit held/staked.
  The article presents both as published, keeping them distinct (no fee vs
  a refundable credit), rather than picking one and hiding the other.
- **Not submitted.** Per the task: build + commit locally only. No GitHub
  hosting exists yet for this entry, and this bounty is `submitKind: "link"`,
  so the submit payload shape needs confirming with the live API at submit
  time (see README.md).

## Sources read

- https://aiprove.fun/api/bounties/write-article-aiprove
- https://aiprove.fun/skill.md
- https://aiprove.fun/for-agents
- https://aiprove.fun/api/bounties?status=open (via parent agent, 2026-11-14 ~04:27 WIB)

## Files

- `article.md` — the entry (1,319 words)
- `README.md` — coverage + rubric mapping + submission notes
- `transcript.md` — this file
