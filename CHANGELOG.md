# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [1.0.1] - 2026-09-15

### Changed

- User guides moved to `docs/user-guide.md` (English) and `docs/user-guide-fr.md` (French), with the screenshots in `docs/images/`
- README reorganized: features, formulas, usage example, getting started, repository structure and quality checks
- Contributing guide renamed `CONTRIBUTING.md`, with the process to propose a change to the template, the pull request process and the release process

### Added

- Code of conduct (Contributor Covenant 2.1), security policy, citation metadata, issue forms and pull request template
- CI: Markdown lint, check of the links, anchors and images, dependency review and CodeQL
- Dependabot for the GitHub Actions, with auto-merge of patch and minor updates once the required checks pass

### Fixed

- Wrong RPE chart value in the e1RM example of the user guides: 3 reps at RPE 8 is 86.3 %, so 110 kg gives an e1RM of 127.5 kg
- Belt load in the pull-up example of the user guides (27.5 kg, not 26.25 kg) and cell of the average bodyweight (A60)
- README usage example: 73.9 % of the e1RM matches 7 reps at RPE 7, not 8 reps
- Typos in the user guides
- Release date of version 1.0.0

## [1.0.0] - 2026-01-21

### Added

- 10-week structured tracking system
- Automatic e1RM calculation based on RPE
- Fatigue index with weekly averages
- Bodyweight integration for pull-ups and dips
- Weekly and multi-week charts
- Automatic load rounding (2.5 kg)
- Multi-sheet architecture (1 week = 1 sheet)
- README, user guides (French and English) and contribution guidelines

[Unreleased]: https://github.com/BnRomain/tracker-powerlifting/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/BnRomain/tracker-powerlifting/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/BnRomain/tracker-powerlifting/releases/tag/v1.0.0
