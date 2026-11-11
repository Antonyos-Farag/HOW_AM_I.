# Audit — `Antonyos-Farag/HOW_AM_I.`

**Date:** 2026-11-11
**Baseline:** `main` @ `d5210a2` (single commit, last merged 2026-10-15)
**Method:** every tracked file was read in full; all 16 public repositories were read through the
GitHub API; the TryHackMe profile was opened and read; heading anchors were recomputed with
GitHub's own slug algorithm.

---

## 1. Inventory

| File | Lines | Role | State |
| :--- | ---: | :--- | :--- |
| `README.md` | 402 | The profile itself: hero, badges, snapshot table, navigation table, ten numbered sections | Content complete, visually dated |
| `ABOUT_ME.md` | 223 | Plain-text mirror of the same ten sections | In sync with the README, including its errors |
| `AI_ASSISTANT_PROMPT.md` | 46 | Copy-paste context block for AI tools | In sync, including its errors |
| `docs/01-academic-background.md` | 48 | Coursework matrix | Fine |
| `docs/02-cybersecurity-profile.md` | 104 | Training, focus matrix, tools, SOC lab | Fine, one stale certification name |
| `docs/03-ai-robotics-and-intersection.md` | 61 | AI/ML foundations and the intersection | Fine |
| `docs/04-portfolio-and-documentation-standards.md` | 78 | Documentation philosophy, direction, learning style | Fine, one stale certification name |
| `templates/tryhackme-writeup-template.md` | 57 | Write-up template | Fine |
| `templates/soc-lab-experiment-template.md` | 67 | Lab experiment template | Fine |
| `index.html` | 660 | Interactive dashboard (sidebar, filters, search, modal) | Works, dark only, not served anywhere |
| `styles.css` | 754 | Dashboard styling | Dark palette hard-coded |
| `script.js` | 364 | Dashboard logic plus two **duplicated copies** of the markdown content | Copies drift from the real files |
| `assets/hero-banner.svg` | 105 | Terminal-style hero | Dark only, 38 px name at 1100 px width; emoji inside `<text>` |
| `assets/training-metrics-widget.svg` | 128 | Six training cards with progress bars | The bars are decorative percentages — looks like fake proficiency |
| `assets/soc-lab-widget.svg` | 134 | Lab architecture diagram | Fine, dark only |
| `assets/convergence-widget.svg` | 71 | Domain convergence diagram | Fine, dark only |

The repository has no `.github/`, no LICENSE, no `.gitignore`, no CI and no `favicon`.

## 2. What works

- Every relative link and image in every file points at a file that exists.
- All five project repositories and four write-up repositories exist, are public, and have content.
- `ChessBot` really is a fork of `XxPhotonguyxX/ChessBot`, and the fork carries two commits that the
  parent does not.
- The dashboard is self-contained: no CDN, no build step, no external requests. It opens and works
  from disk.
- The two templates are generic and contain no personal claims.

## 3. Broken

**Every table-of-contents and badge anchor in `README.md` is dead on GitHub.** GitHub keeps emoji in
the generated id, so the heading `## 1. 🎓 Academic Background` becomes `#1--academic-background`
(two dashes), while the file links to `#1-academic-background`. The same applies to all ten entries
of the table of contents, the four identity badges and the snapshot links. Six `TOC` anchors, four
`badge` anchors and three `snapshot` anchors all miss.

Nothing else is broken: no 404s, no missing images, no malformed markdown tables.

## 4. Outdated or contradicting the owner's own facts

| # | Where | Says | Should be |
| :-: | :--- | :--- | :--- |
| 1 | README, ABOUT_ME, AI prompt, docs/02, docs/04, `index.html`, `script.js`, both SVG widgets | **Huawei HCIA-Security V4.0** | **Huawei HCIA-AI V4.0** — confirmed by the owner. The description "firewall technologies, encryption" does not belong to an AI certification and was invented by an earlier draft |
| 2 | same files, six places | **TIPS Hindawi Cybersecurity Internship Program — Penetration Testing track** | **TIPS Hindawi: Red Teaming Training**, completed, two months, final project presented and passed |
| 3 | README, docs/02 | "Advanced Endpoint **Investigation**" | TryHackMe calls the path "Advanced Endpoint **Investigations**" |
| 4 | "HNU (Egypt)" everywhere | abbreviation never explained | the owner's university is **Helwan National University** |
| 5 | README §7, ABOUT_ME §7 | the portfolio "is intended to include" write-ups | four write-ups and five projects now exist and are not linked anywhere |
| 6 | README, ABOUT_ME, AI prompt | five TryHackMe paths → lists do not include **Pre Security**, **Cyber Security 101**, **SOC Level 1** | five paths are completed, and the profile carries a **Top 1%** global ranking |
| 7 | all training lists | missing the **DeepLearning.AI / Stanford Online** ML courses, the **Calculus for ML** course and **DataCamp Python** | they are completed |
| 8 | README §4 tool table | missing Snort, Zeek, Volatility, SQLMap, Hydra, Gobuster, Python, Java, C and Git | all are part of actual lab and project work |
| 9 | `docs/04` capability matrix | lists the TIPS entry as a "Penetration Testing Internship" | red teaming training |

## 5. Design findings

- **Hero:** dark only, so it turns into a black slab for anyone reading GitHub in light mode. Name is
  38 px in a 1100 px canvas: at 400 px wide on a phone it renders at ~14 px. Emoji inside SVG `<text>`
  render as platform-dependent glyphs, and they are inaccessible.
- **Badges:** 13 `for-the-badge` shields in ten different colors, including emoji in the label text.
  The colors carry no meaning and the row wraps into three lines on a laptop.
- **Progress bars:** `training-metrics-widget.svg` draws bars at 99.5 / 92 / 85 / 90 / 95 / 100 % of
  their track width. Nobody checks the arithmetic; everybody reads them as self-assigned scores.
  They contradict the "no invented metrics" rule and should go.
- **Length:** 402 lines, 12 tables, 10 sections. A recruiter reads the first screen and stops.
- **No links:** the profile links to no project, no write-up, no GitHub, no LinkedIn, no email, and no
  TryHackMe. The most credibly demonstrable work in the account is unreachable from the profile.
- **Dashboard:** `index.html` is GitHub-Pages-ready but Pages is disabled, so it is not served. It is
  still useful as a local artifact and is left in place.
- **Duplication:** `script.js` embeds a copy of `ABOUT_ME.md` and a second copy of the AI prompt.
  That is the reason the certification errors appear in nine files instead of four.

## 6. Decisions taken after asking the owner

1. **Huawei:** HCIA-AI V4.0 only; HCIA-Security is removed everywhere.
2. **TIPS Hindawi:** one program, renamed "TIPS Hindawi: Red Teaming Training" everywhere.
3. **Course projects:** `Bug_tracker_system`, the SRTF simulator and the Linux terminal app were team
   projects. Credit lines: services/backend layer (Bug tracker), scheduling algorithm (SRTF),
   documentation and build (Linux terminal app). `Elastic-SIEM-Network-Security-Monitoring-Lab` was a
   team of five that he led. `ChessBot` is a fork, worked on as a team; his part is alpha-beta pruning
   and the GUI.
4. **Display name:** Antonyos Farag Mansour in the hero; "Antonyos Farag" keeps being used where the
   handle or the university context already identifies him.

## 7. Unverified — deliberately left out, or left as-is

| Item | Why |
| :--- | :--- |
| Certificate verification links (Cisco, NTI, Huawei, DeepLearning.AI) | none are known; every "verify" cell is either a real link or absent. No placeholder URLs are added |
| HCIA-AI date, score, and credential id | not provided |
| DataCamp, DeepLearning.AI completion dates | not provided |
| `Snort--THM-Write-up` | the repository is empty (HTTP 409 on the tree, 404 on the README). Not linked |
| `jiml33t`, `demo`, `tony`, `Tony_Ghosr` | an unrelated fork and three empty repositories. Not linked |
| `Balanced-Recursive-Non_Recursive-AND-Domination-Recursive-Non_Recursive-Algorithms` | real work (Python, 190 tests, eight chapters) but not on the owner's list. Listed in this report only |
| Salary, availability dates, years of experience | not facts I have |
| Any Elo rating, benchmark number, or "5+ projects" style count | not measured; the ChessBot README itself calls its Elo labels "rough labels, not measurements" |

## 8. For the owner to do outside this repository

- The GitHub bio ends with "stay securet". It is a profile setting, not a repository file.
- The three empty repositories and the `jiml33t` fork could be deleted or archived.
- If Pages is ever enabled, `index.html` is ready to serve.
