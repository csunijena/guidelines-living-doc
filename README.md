# Good Practices and Common Pitfalls in the Research and Development of New Electrolytes for Flow Batteries

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20277368.svg)](https://doi.org/10.5281/zenodo.20277368)
[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://rfb-data-hub.github.io/guidelines-living-doc/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://rfb-data-hub.github.io/guidelines-living-doc/manuscript.pdf)
[![GitHub Actions Status](https://github.com/rfb-data-hub/guidelines-living-doc/workflows/Manubot/badge.svg)](https://github.com/rfb-data-hub/guidelines-living-doc/actions)

**Read it:** [HTML](https://rfb-data-hub.github.io/guidelines-living-doc/) ·
[PDF](https://rfb-data-hub.github.io/guidelines-living-doc/manuscript.pdf) ·
[Cite it (DOI)](https://doi.org/10.5281/zenodo.20277368)

## What this is

This repository hosts the **living document** of the review article *"Good
Practices and Common Pitfalls in the Research and Development of New
Electrolytes for Flow Batteries"* (accepted for publication by *Chemical
Reviews*).

The article gives structured, practical guidance for researchers working with
novel redox flow battery electrolytes, organized around four core activities:

1. **Electrolyte formulation and physicochemical preparation**
2. **Electrolyte characterization** (electroanalytical screening, from dilute
   cyclic voltammetry to operationally relevant conditions)
3. **Cell hardware selection and flow cell assembly**
4. **Performance and lifetime testing protocols** (symmetric vs. full cell,
   potentiostatic cycling, reliable capacity-fade data)

Its essence is condensed into **ten practical recommendations** (Section 6).
A companion [reporting template](https://github.com/rfb-data-hub/guidelines-reporting-template)
proposes a checklist for reporting these details in publications' supporting
information.

## Why a living document?

The guidelines represent the view of a small group of researchers — but they
should evolve with the entire field. So instead of freezing them in a journal
PDF, the article continues here as an open, community-owned document:

- **Traceable:** every change is a git commit — who, what, when, and why.
- **Peer-reviewed in the open:** proposed changes are discussed publicly on
  pull requests, before (or instead of) becoming part of the document.
- **Self-building:** the [Manubot](https://manubot.org) workflow turns the
  markdown sources into a professionally typeset HTML/PDF/DOCX manuscript on
  every merged change — citations and references are managed automatically
  from DOIs.
- **Citable:** official versions are archived on Zenodo; the concept DOI
  [10.5281/zenodo.20277368](https://doi.org/10.5281/zenodo.20277368) always
  resolves to the latest version.

The goal: a community-wide consensus on how flow battery electrolytes should
be characterized, tested, and reported.

## Contributing

No write access needed — anyone can contribute from a free GitHub account.

### Just a thought, question, or criticism?

Open an [issue](https://github.com/rfb-data-hub/guidelines-living-doc/issues).
Suggestions, pointing out errors, and discussing existing recommendations are
all valuable and need no git skills.

### Proposing a concrete change (pull request)

```bash
# 1. Fork the repository via the "Fork" button (once)
# 2. Clone your fork and enter the repository
git clone https://github.com/<your-username>/guidelines-living-doc.git
cd guidelines-living-doc

# 3. Create a branch for one topic (keep changes focused)
git checkout -b clarify-electrolyte-concentration

# 4. Edit the relevant markdown file in content/ ... then commit and push
git add content/
git commit -m "Clarify recommended concentration range for CV screening"
git push origin clarify-electrolyte-concentration
```

GitHub will offer to open a **pull request** from the pushed branch — do that,
and describe the *why* of your change. A CI bot immediately builds the
manuscript with your change and reports success or failure (e.g., broken
citations) right on the pull request.

The community discusses and refines the proposal in the open on the pull
request. Once consensus is reached, a maintainer merges it: the live
manuscript is rebuilt automatically and the change becomes part of the
document — permanently attributed to you.

### Writing conventions (the 60-second version)

- One markdown file per manuscript section in [`content/`](content)
  (e.g., [`04.electrolyte-characterization.md`](content)), prefixed with their
  order in the document.
- New literature is cited inline as `[@doi:10.1021/example]`; Manubot fetches
  and formats the reference automatically. References without a DOI go into
  [`content/manual-references.json`](content/manual-references.json).
- Figures live in [`content/images/`](content/images), named
  `figN-short-title.png` with the caption and a `{#fig:name}` label in the
  markdown.
- Title, author list, and affiliations are set in
  [`content/metadata.yaml`](content/metadata.yaml).
- Math containing `{` must be spaced (`{ {math}}`) to avoid template
  conflicts.

More detail: [`USAGE.md`](USAGE.md) and the
[Manubot docs](https://manubot.readthedocs.io).

### Building locally (optional)

CI builds every pull request, so a local build is not required. If you want
one anyway:

```bash
conda env create --file build/environment.yml
conda activate manubot
bash build/build.sh   # outputs land in output/
```

## Releases and citations

- **Merged pull request** → live site and PDF update immediately; the full
  change history is visible via git.
- **Official release** (a GitHub release on this repository) → Zenodo
  automatically archives that state and mints a new version DOI under the
  concept DOI above. Releases are the official "published versions" of the
  living document, cut by the maintainers.

## Repository layout

+ [`content/`](content) — manuscript source: markdown sections, images,
  citations, metadata
+ [`output/`](output) and `gh-pages` branch — built manuscripts (generated,
  don't edit)
+ [`build/`](build) — build environment and pandoc configuration
+ [`.github/workflows/`](.github/workflows) — CI: build, checks, deployment
+ `.zenodo.json` — release metadata for Zenodo archival

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Except for code and data files (dual-licensed CC0, see the glob patterns in
[`LICENSE.md`](LICENSE.md)), the entirety of this repository is licensed under
CC BY 4.0. Please attribute by linking to
<https://github.com/rfb-data-hub/guidelines-living-doc>.

## Built with Manubot

This document is written and published with [Manubot](https://manubot.org),
a workflow for open, collaborative scholarly publishing on GitHub, based on
its [rootstock](https://github.com/manubot/rootstock) template. Manuscript
building, citation management, and versioning are documented in
[`USAGE.md`](USAGE.md).
