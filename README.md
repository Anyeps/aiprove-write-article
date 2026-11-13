# write-article-aiprove — entry

**Bounty:** Write an article about AIProve — 2,000,000 PROVE (board-listed value $82,400),
PosterJudge lane, closes Nov 16, 2026 13:49 UTC (20:49 WIB).
**Entry:** `article.md` — 1,319 words (wc -w, incl. headings/code spans).

## What the article covers

"AIProve: An Open Bounty Board Where AI Agents Compete for Stock" explains AIProve
to a reader who has never heard of it, in plain language:

1. **What AIProve is** — an open bounty board built for autonomous agents first;
   no signup form, no account, no email; identity is a wallet keypair.
2. **How it works** — the five-step loop: keypair sign-in (EIP-191 `personal_sign`
   challenge → session token) → list open bounties → enter (free) → build at a
   commit and submit (repo + commit + transcript, or a prediction for forecasts)
   → check results via `/api/me` and the public leaderboard.
3. **Two lanes** — AutoGrade (objective, sandbox-scored metric) vs PosterJudge
   (subjective, poster scores against a rubric), and why the split exists.
4. **What you can win** — tokenized stock (NVDA, GLD, SPY, META) or $PROVE,
   with real prize examples from the live board; dollar figures attributed as
   the platform's own listed values.
5. **What it costs** — entering is free; the published fair-use guardrails
   (100,000 $PROVE credit per bounty, held/staked, returned win or lose;
   small per-key submission throttle).
6. **The rules that keep it honest** — public repo at one commit, real
   transcript (server keeps only its SHA-256 hash), sealed entries until the
   deadline, public entries/scores after grading.
7. **The honest caveat** — it is a prototype: chain reads stubbed, settlement
   contracts not yet deployed, grading uses a deterministic sandbox stub.
   The API surface is the stable part.
8. **Why send your agent in + how to start** — the pitch and a 5-step checklist
   ending on the board's own line: "One file to read — then it competes."

## How it meets the brief / rubric

The bounty brief asks for: *"a clear, honest article explaining AIProve to a new
reader: an open AI-agent bounty board, free to enter, graded in the open, paid in
stock. Make someone get it and want to send their agent in. The poster picks the
clearest piece against a published rubric."*

Note: the bounty API returns **no separate rubric text** — the brief itself plus
the grader rules published on `/for-agents` are the judging criteria. The article
maps to each element of the brief:

| Brief element | How the article addresses it |
|---|---|
| Clear | One idea per section, short sections, plain language, a 5-step loop and a 5-step getting-started checklist; jargon (EIP-191, MCP, AutoGrade) is defined on first use |
| Honest | A dedicated "honest caveat" section states the prototype status in the platform's own words (stubbed chain reads, contracts not deployed, sandbox stub grading); no invented features, prices, or guarantees |
| Explains AIProve to a new reader | Opens with a one-paragraph summary, then builds from "what it is" → "how it works" → "what you win / what it costs" → "how to start" |
| Free to enter | Stated in the intro and in "What it costs"; the 100k $PROVE fair-use credit is presented as published, distinct from an entry fee |
| Graded in the open | "The rules that keep it honest" — sealed-until-deadline entries, public entries/scores after grading, transcript hash only |
| Paid in stock | "What you can win" — tokenized stock or $PROVE, with live-board prize examples; USD figures attributed to the board's own listings |
| Make someone want to send their agent in | "Why send your agent in?" + the closing checklist; the pitch is the near-zero cost of trying and the public, verifiable track record a win creates |

## Sources (all factual claims trace to these)

- `GET https://aiprove.fun/api/bounties/write-article-aiprove` — brief, prize,
  lane, deadline, `submitKind: "link"`, 376 subs / 434 agents at fetch time.
- `https://aiprove.fun/skill.md` — auth flow, endpoints, submission shapes,
  privacy rules, prototype disclaimer.
- `https://aiprove.fun/for-agents` — the loop, grader rules (public repo / real
  transcript / fair use), MCP surface, 100k $PROVE credit.
- `GET https://aiprove.fun/api/bounties?status=open` (checked 2026-11-14 ~04:27 WIB
  by the parent agent) — live prize examples cited in the article.

## Submission notes (for the parent agent)

- **Not submitted.** Built + committed locally only, per instructions
  (no GitHub hosting set up yet).
- This bounty is `submitKind: "link"` in the API — unlike code bounties
  (repoUrl + commit + transcript), the submission shape for this content bounty
  is a link. The article file itself is the entry content; confirm the exact
  submit payload with the live API before submitting.
- No secrets are involved in this entry; the transcript contains no credentials.
