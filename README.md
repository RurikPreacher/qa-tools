# qa-tools

A collection of useful tools and utilities for QA engineering, testing, and everyday tasks.

## Tools

### QA Test File Generator

[Open generator](./tools/test-file-generator/) — generates Windows CMD commands for creating dummy files from 1 MiB up to 10 GiB (unit labels in the UI: MB and GB).

- File size: 1–10,240 MB or 1–10 GB (binary units)
- Built-in or custom file extension
- File name and destination directory
- Copyable commands using `mkdir` and `fsutil file createnew`
- Responsive layout and light/dark theme
- Settings persist locally in your browser using `localStorage`

**Note:** Created files contain zero bytes as their contents. A renamed dummy file is not a valid PDF, ZIP, XLSX, PNG, or other structured format. Windows CMD and `fsutil` are required.

## GitHub Pages

Open repository **Settings → Pages**, select **Deploy from a branch**, choose **main** and **/(root)**, then save.

After Pages is enabled:

- Home: https://rurikpreacher.github.io/qa-tools/
- Generator: https://rurikpreacher.github.io/qa-tools/tools/test-file-generator/

## Project structure

```text
qa-tools/
├── index.html
├── tools/
│   └── test-file-generator/
│       └── index.html
└── README.md
```

No build step, third-party dependencies, accounts, or server storage are needed. Add future tools as new directories under `tools/` and link them from the landing page.
