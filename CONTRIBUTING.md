# Contributing to Awesome Computer Vision Tools

Thank you for taking the time to contribute! This is a community-maintained list and all contributions are welcome.

---

## What Can I Contribute?

- Adding a new tool to an existing category
- Adding a new category (if justified by multiple tools)
- Fixing a broken link
- Updating outdated descriptions or statuses (e.g. marking a tool as discontinued or archived)
- Adding or correcting a format entry in the Data Serialization Formats or Media Quality Formats tables
- Fixing typos or formatting issues

---

## Before You Submit

Please check the following before opening a pull request:

1. The tool is relevant to Computer Vision development, training, inference, deployment, or MLOps
2. The tool is not already listed
3. The tool has a public website, GitHub repo, or documentation page
4. If the tool is archived or discontinued, it is marked accordingly (see badge reference below)

---

## Entry Format

All tool entries follow this format:

```markdown
* **Tool Name** ![license-badge] [![Stars](https://img.shields.io/github/stars/org/repo?style=flat&label=★)](https://github.com/org/repo): One-sentence description. [[Website](https://example.com)] | [[Github](https://github.com/org/repo)]
```

Add the recommended badge at the end if the tool is widely adopted or a clear best-in-class choice:

```markdown
* **Tool Name** ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) ![license-badge] [![Stars]...]: One-sentence description. [[Website](...)] | [[Github](...)]
```

### Badge Reference

| Badge | Markdown |
| --- | --- |
| ![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat) | `![open-source](https://img.shields.io/badge/open--source-brightgreen?style=flat)` |
| ![freemium](https://img.shields.io/badge/freemium-blue?style=flat) | `![freemium](https://img.shields.io/badge/freemium-blue?style=flat)` |
| ![paid](https://img.shields.io/badge/paid-red?style=flat) | `![paid](https://img.shields.io/badge/paid-red?style=flat)` |
| ![free](https://img.shields.io/badge/free-brightgreen?style=flat) | `![free](https://img.shields.io/badge/free-brightgreen?style=flat)` |
| ![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat) | `![recommended](https://img.shields.io/badge/★-recommended-gold?style=flat)` |
| ![discontinued](https://img.shields.io/badge/discontinued-lightgrey?style=flat) | `![discontinued](https://img.shields.io/badge/discontinued-lightgrey?style=flat)` |
| ![archived](https://img.shields.io/badge/archived-lightgrey?style=flat) | `![archived](https://img.shields.io/badge/archived_Mon_YYYY-lightgrey?style=flat)` |

### Rules

- Use `**bold**` for the tool name
- Place the ![recommended] badge immediately after `**Tool Name**` and before all other badges
- Write the description as a single sentence ending with a full stop
- Include at least one link (Website or Github)
- Add the Stars badge where a GitHub repo is available
- Add the entry in alphabetical order within its category

---

## Format Tables (Data Serialization & Media Quality)

The **Data Serialization Formats** and **Media Quality Formats** sections use Markdown tables, not bullet lists. To add or update a format entry, edit the relevant row directly in the table following the existing column structure.

For **Media Quality Formats** the columns are: `Format | Media | Quality | Notes`

- `Media` must be one of: `Image`, `Video`, `Figure`
- `Quality` should start with ⚠️ for lossy or ✅ for lossless

---

## How to Submit a Pull Request

1. Fork the repository
2. Create a new branch: `git checkout -b add-tool-name`
3. Make your changes to `README.md`
4. Verify all links work
5. Open a pull request with a short description of what you are adding and why

---

## Reporting Issues

If you find a broken link, an outdated entry, or a missing tool, please open a [GitHub Issue](../../issues) with:

- The name of the tool or section affected
- A brief description of the problem or suggestion

---

## Code of Conduct

Please be respectful and constructive in all interactions. Contributions that are promotional, spammy, or off-topic will not be accepted.