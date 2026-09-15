# Security Policy

## Supported Versions

Only the latest version is maintained: the Google Sheets template linked in the README and the `main` branch of this repository.

| Component | Location | Supported |
| --- | --- | --- |
| Google Sheets template | Google Drive, [template link](https://docs.google.com/spreadsheets/d/1cMEQfgsgYV3C5RC8sq0Xvccz4UgO5aT8dhn19qVybdU/edit?usp=sharing) | Yes |
| Documentation (README, user guides) | `README.md`, `docs/` | Yes |
| GitHub Actions workflows and Dependabot configuration | `.github/` | Yes |

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please do not disclose it publicly through a GitHub issue.

Instead, please report it privately to the project maintainer through GitHub's private vulnerability reporting: [report a vulnerability](https://github.com/BnRomain/PowerLiftingTracker/security/advisories/new).

When reporting a vulnerability, please provide:

* A short description of the vulnerability
* The affected sheet, cell, file or component
* The steps required to reproduce the issue
* Any relevant screenshots, logs or formulas

## Scope

This policy applies to the template and to the content of this repository, in particular:

* anything in the template that could expose the data of a copy, such as a formula or a link that loads or sends data to an external site, or wrong sharing settings of the template;
* links in the documentation that point to a malicious or hijacked page;
* the GitHub Actions workflows and the Dependabot configuration.

A wrong calculation is not a security issue: please report it with the [bug report form](https://github.com/BnRomain/PowerLiftingTracker/issues/new?template=bug_report.yml).

## Your Training Data

The template is shared read-only. You use the tracker by making your own copy (File > Make a copy): the copy belongs to your Google account, and the maintainer has no access to it or to the data you enter (bodyweight, loads, RPE).

## Security Measures

* **CodeQL** code scanning on the GitHub Actions workflows for every pull request and every push to `main`.
* **Dependabot** version updates for the GitHub Actions, plus Dependabot security updates. Patch and minor updates are merged automatically only once the required checks of `main` have passed.
* **Dependency review** blocks pull requests that introduce dependencies with known vulnerabilities of moderate severity or higher.
* **Secret scanning** with push protection.
* **Least privilege** in CI: the workflows get a read-only token, and only the Dependabot auto-merge workflow can write, for pull requests opened by Dependabot in this repository.

## Response

Security reports will be reviewed as soon as reasonably possible.

Depending on the nature and severity of the issue, appropriate corrective actions may include:

* Fixing the template or its sharing settings
* Updating dependencies
* Improving the documentation or the configuration
* Documenting the issue and its resolution
