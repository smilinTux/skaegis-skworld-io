# AGENTS.md (skaegis-skworld-io)

Static GitHub Pages site for skaegis at https://skaegis.skworld.io. Read [README.md](./README.md) for the overview and
[SOP.md](./SOP.md) for operations. Standard: [AGENT_INSTRUCTIONS_STANDARD](https://github.com/smilinTux/sk-standards/blob/main/standards/AGENT_INSTRUCTIONS_STANDARD.md).

## Source of truth and invariants

- `index.html` and `styles.css` are canonical. Nothing is generated.
- `CNAME` contains exactly `skaegis.skworld.io`, no newline games, no other lines.
- The page says the product is in design. Do not remove that while it is true.
- No overclaims: never "unhackable", "100% secure", "quantum-proof" or similar.

## Commands

```bash
# install
none
# test (what CI runs)
python3 -m http.server 8000
# lint and format (what CI runs)
grep -rnP '[\x{2013}\x{2014}]' . --include='*.html' --include='*.md' --include='*.css'
# docs gate
python3 <path-to-sk-standards>/scripts/docs_check.py --repo .
```

## Start here

1. `index.html`: the whole page.
2. `styles.css`: theme tokens in `:root`.
3. `SOP.md`: deploy and troubleshooting.

## Rules

- **Writing style:** no em dashes (U+2014) and no en dashes (U+2013) anywhere: code,
  comments, docs, commits, PR bodies. Use commas, parentheses, colons or a new sentence.
  Hyphens are fine.
- **Branch and commit:** never commit to `main`. Branch, commit as soon as a fast check
  passes and before any long verification, then open a PR.
- **Attribution:** a `Co-Authored-By` trailer names the agent that actually did the work,
  or is left out.
- **Generated files:** none.
- Lead with "skaegis" as the product. The detection engine is named only in plain, factual FAQ context, never as the headline.
- No third-party scripts, trackers or fonts; keep the site self-contained.

## Privacy

Never put any of these in code, docs, tests, fixtures, commits or the site: host names,
LAN or tailnet IPs, estate names, personal names or data, credentials, and for this
repo: customer names, internal sizing or infrastructure details from the product plan. Enforced by: review only.

## Hazards

- Describing plans as shipped features: keep the "in design" status and the "plan" notes.
- Editing `CNAME` with a trailing newline or extra text: Pages can drop the custom domain. Keep it exact.

## See also

- [sk-standards](https://github.com/smilinTux/sk-standards): doc and disclosure standards.
- [SK_REPO_DOC_STANDARD](https://github.com/smilinTux/sk-standards/blob/main/standards/SK_REPO_DOC_STANDARD.md)
