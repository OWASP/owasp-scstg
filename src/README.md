# Scripts and Releases

## Overview

This folder contains scripts and assets needed to generate our deliverables.

Files:

- `pandocker/`: Directory containing the scripts and auxiliary files needed to run the pandocker image for the document generation.
- `scripts/`: Directory containing the scripts used for the generation of the SCS deliverables such as the PDF, the website, the checklists, etc.
- `contributors.py`: Python script to retrieve current contributors and group them into our different categories according to their additions.

## GitHub Actions

Our workflows for GitHub Actions are located in `.github/workflows`.

Usually we don't have to change anything here apart from upgrading the version of the included actions (e.g. `actions/checkout@v2`).

- **Document** (`.github/workflows/docgenerator.yml`) generates:
    - the SCSTG as PDF and ePub using `src/pandocker/pandoc_makedocs.sh`
    - the SCS Checklist using `src/scripts/yaml_to_excel.py`
- **Build Website** (`.github/workflows/build-website.yml`): builds the website and pushes the result to the `gh-pages` branch.
- **Markdown Linter** (`.github/workflows/markdown-linter.yml`): runs a markdown linter using our config `.markdownlint.json` (more about [configuration](https://github.com/igorshubovych/markdownlint-cli#configuration)).
- **URLs Checker** (`.github/workflows/url-checker.yml`, `.github/workflows/url-checker-pr.yml`): runs a URL checker using our config `.github/workflows/config/url-checker-config.json` (this workflow usually gives false positives that we have to exclude in the config).
- **Spell Checker** (`.github/workflows/spell-checker.yml`): runs a spell checker
- **CodeQL Security Scan** (`.github/workflows/codeql-analysis.yml`): to detect security issues in our Python code.
- **Labeler** (`.github/workflows/labeler.yml`): automatically labels PRs based on the files changed and the configuration in `.github/labeler.yml`.

## How to Release

See ["How to Release"]() (access restricted).