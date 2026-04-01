# README Header Template

Standardized README header for all Cascading Labs projects. Copy the relevant sections and replace the placeholders.

## Placeholders

| Placeholder | Description | Example |
|---|---|---|
| `{{PROJECT}}` | Display name | `Yosoi`, `VoidCrawl`, `QScrape` |
| `{{DOCS_URL}}` | Docs or site URL | `https://cascadinglabs.com/yosoi` |
| `{{DISCORD_INVITE}}` | Discord invite code | `YreV3CzxsE` |
| `{{LABEL_COLOR}}` | Brand `--XX-bg` hex (no `#`) | `2e3742` |
| `{{COLOR}}` | Brand `--XX-border` hex (no `#`) | `8fa3b3` |
| `{{GITHUB_ORG}}` | GitHub org | `CascadingLabs` |
| `{{GITHUB_REPO}}` | GitHub repo name | `Yosoi` |
| `{{CI_WORKFLOW}}` | CI workflow filename | `CI.yaml` |
| `{{PYPI_NAME}}` | PyPI package name | `yosoi`, `void-crawl` |
| `{{CODECOV_TOKEN}}` | Codecov upload token | `DFDI574EEA` |
| `{{DOI}}` | Zenodo DOI | `10.5281/zenodo.18713573` |

## Brand colors (from `global.css`)

| Project | `{{LABEL_COLOR}}` (`--XX-bg`) | `{{COLOR}}` (`--XX-border`) |
|---|---|---|
| Cascading Labs | `0c2340` | `3d7eb5` |
| QScrape | `1a0808` | `c94040` |
| Yosoi | `2e3742` | `8fa3b3` |
| VoidCrawl | `120a24` | `7c4dbd` |

## Template

### Logo (required — all projects)

```markdown
<p align="center">
  <a href="{{DOCS_URL}}">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="media/logo-dark.svg">
      <source media="(prefers-color-scheme: light)" srcset="media/logo-light.svg">
      <img src="media/logo-dark.svg" alt="{{PROJECT}}" width="200">
    </picture>
  </a>
</p>
```

Logo files: copy `Assets/{{project}}/{dark,light}/logo.svg` → `media/logo-{dark,light}.svg`.

### Badges (pick applicable rows)

Wrap all badges in a single centered block:

```markdown
<p align="center">
  <!-- Discord (all projects) -->
  <a href="https://discord.gg/{{DISCORD_INVITE}}"><img src="https://img.shields.io/badge/Discord-Join-{{COLOR}}?labelColor={{LABEL_COLOR}}&logo=discord&logoColor=white" alt="Discord"></a>
  <!-- License (all projects) -->
  <a href="https://opensource.org/licenses/Apache-2.0"><img src="https://img.shields.io/badge/License-Apache_2.0-{{COLOR}}?labelColor={{LABEL_COLOR}}" alt="License"></a>
  <!-- CI (if repo has CI workflow) -->
  <a href="https://github.com/{{GITHUB_ORG}}/{{GITHUB_REPO}}/actions"><img src="https://img.shields.io/github/actions/workflow/status/{{GITHUB_ORG}}/{{GITHUB_REPO}}/{{CI_WORKFLOW}}?label=CI&labelColor={{LABEL_COLOR}}&color={{COLOR}}" alt="CI"></a>
  <!-- PyPI version (if published to PyPI) -->
  <a href="https://pypi.python.org/pypi/{{PYPI_NAME}}"><img src="https://img.shields.io/pypi/v/{{PYPI_NAME}}?labelColor={{LABEL_COLOR}}&color={{COLOR}}" alt="PyPI"></a>
  <!-- Python versions (if Python package) -->
  <a href="https://pypi.python.org/pypi/{{PYPI_NAME}}"><img src="https://img.shields.io/pypi/pyversions/{{PYPI_NAME}}?labelColor={{LABEL_COLOR}}&color={{COLOR}}" alt="Python versions"></a>
  <!-- Codecov (if coverage is tracked) -->
  <a href="https://codecov.io/gh/{{GITHUB_ORG}}/{{GITHUB_REPO}}"><img src="https://img.shields.io/codecov/c/gh/{{GITHUB_ORG}}/{{GITHUB_REPO}}?token={{CODECOV_TOKEN}}&labelColor={{LABEL_COLOR}}&color={{COLOR}}" alt="codecov"></a>
  <!-- DOI (if citeable) -->
  <a href="https://doi.org/{{DOI}}"><img src="https://img.shields.io/badge/DOI-{{DOI_ESCAPED}}-{{COLOR}}?labelColor={{LABEL_COLOR}}" alt="DOI"></a>
  <!-- Docs (if dedicated docs site exists) -->
  <a href="{{DOCS_URL}}"><img src="https://img.shields.io/badge/docs-{{DOCS_URL_ESCAPED}}-{{COLOR}}?labelColor={{LABEL_COLOR}}" alt="docs"></a>
</p>
```

`{{DOI_ESCAPED}}` and `{{DOCS_URL_ESCAPED}}` — URL-encode slashes and special chars for shields.io (e.g. `/` → `%2F`).

### Alpha warning (if pre-stable)

```markdown
> [!WARNING]
> **{{PROJECT}} is currently in Alpha.** The API is expected to change significantly. We do not expect a stable API until we are out of Beta.
```

### Badge order

1. Discord
2. License
3. CI
4. PyPI version
5. Python versions
6. Codecov
7. DOI
8. Docs
