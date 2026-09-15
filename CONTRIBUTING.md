# Contributing

Thank you for your interest in PowerLift Tracker. It started as a personal tool to track my own powerlifting training, and bug reports, suggestions and pull requests are welcome.

By participating, you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## Ways to contribute

- **Report a bug**, such as a wrong calculation or a broken formula, or **suggest an improvement** with the [issue forms](https://github.com/BnRomain/PowerLiftingTracker/issues/new/choose).
- **Ask a question or share your results** in [GitHub Discussions](https://github.com/BnRomain/PowerLiftingTracker/discussions).
- **Report a security vulnerability** privately, as described in the [security policy](SECURITY.md). Please do not open a public issue for it.
- **Open a pull request** for the documentation: README, user guides, translations.

For a larger change, please open an issue first so that we can agree on the approach.

## Improving the Google Sheets template

The template lives in Google Drive, not in this repository, so it cannot be changed through a pull request. To propose a change:

1. Make a copy of the [template](https://docs.google.com/spreadsheets/d/1cMEQfgsgYV3C5RC8sq0Xvccz4UgO5aT8dhn19qVybdU/edit?usp=sharing) (File > Make a copy) and apply your change to the copy.
2. Test it on several weeks, including a missed session, weighted pull-ups or dips and accessory exercises (`ac`).
3. Open a [feature request](https://github.com/BnRomain/PowerLiftingTracker/issues/new?template=feature_request.yml) or a [bug report](https://github.com/BnRomain/PowerLiftingTracker/issues/new?template=bug_report.yml) with the cells and formulas you changed, and before and after screenshots. A read-only link to your copy makes the review easier.

Guidelines for formulas:

- Do not break existing calculations: the MAXs of a week come from the average e1RM of the previous week, and the "Suivi e1RM" sheet reads every week sheet by its name.
- Prefer simple and readable formulas, and explain any complex logic.
- Handle empty cells and missed sessions (`IFERROR`, `ISNUMBER`), like the existing formulas.
- Keep the planned loads rounded to the nearest 2.5 kg.

## Documentation setup

```bash
git clone https://github.com/BnRomain/PowerLiftingTracker.git
cd PowerLiftingTracker
```

| Path | Content |
| --- | --- |
| `README.md` | project presentation, features and getting started |
| `docs/user-guide.md` | user guide (English) |
| `docs/user-guide-fr.md` | user guide (French) |
| `docs/images/` | screenshots of the template |
| `CHANGELOG.md` | version history |

- Keep both user guides in sync: a change of usage must be applied to the English and the French guide.
- Store screenshots in `docs/images/`, with lowercase names separated by hyphens (for example `session-planned.png`).
- The [wiki](https://github.com/BnRomain/PowerLiftingTracker/wiki) explains how the tracker works and how the repository is automated: update it when the behavior changes.

Before opening a pull request, check the documentation the same way as the CI. markdownlint requires [Node.js](https://nodejs.org/), and [lychee](https://lychee.cli.rs/) is a single binary:

```bash
npx markdownlint-cli2                        # Markdown lint, configured in .markdownlint-cli2.yaml
lychee --offline --include-fragments .       # links to files, heading anchors and images
```

The repository provides an [`.editorconfig`](.editorconfig) file: most editors apply its indentation and whitespace settings automatically.

## Pull request process

1. Create a branch from `main` with a descriptive name, for example `docs/fatigue-index-example` or `fix/pull-up-guide`.
2. Keep commits focused, with a short summary in the imperative mood (for example "Explain the belt weight in the pull-up example").
3. Open a pull request against `main`, fill in the template and add a label (`bug`, `enhancement`, `documentation`...): labels sort the release notes.
4. The `main` branch is protected: a pull request can only be merged once the required checks (`docs` and `dependency-review`) pass and the branch is up to date with `main`. CodeQL also analyzes the workflows on every pull request.
5. Describe your change in [`CHANGELOG.md`](CHANGELOG.md), under "Unreleased".

## Versioning and releases

The project follows [Semantic Versioning](https://semver.org/):

- **MAJOR** (`2.0.0`): incompatible change of the template that requires starting from a new copy, for example a new layout that moves the input cells (MAXs, bodyweight, Reload, actual RPE);
- **MINOR** (`1.1.0`): new backward-compatible feature, such as a new chart, metric or exercise label;
- **PATCH** (`1.0.1`): backward-compatible fix of a formula or of the documentation.

Releases are published from `main` with a `vX.Y.Z` tag. GitHub generates their notes from the merged pull requests, grouped by label as configured in [`.github/release.yml`](.github/release.yml). [`CHANGELOG.md`](CHANGELOG.md) and the `version` field of [`CITATION.cff`](CITATION.cff) are updated at the same time.
