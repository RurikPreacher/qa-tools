# Agent Instructions — qa-tools

## Purpose and scope
`qa-tools` is a public collection of browser-based utilities for QA engineering, testing, and everyday tasks, published through GitHub Pages.

These instructions apply to the entire repository. Additional nested `AGENTS.md` files may define tool-specific rules, but do not create them unnecessarily.

## Existing architecture
- Static website deployed from the `main` branch, repository root.
- `index.html`: landing page and navigation to tools.
- `tools/<tool-slug>/index.html`: standalone tool page.
- `README.md`: public project documentation.
- No build step, framework, or external dependency is currently required.
- Keep relative links compatible with the GitHub Pages project path `/qa-tools/`.

Before changes, inspect the current repository: these details may evolve, and existing behavior takes precedence over stale descriptions.

## Development principles
1. Read relevant code, documentation, and any requirements before editing. Identify dependencies and the affected tools.
2. Prefer small, focused changes. Preserve existing functionality, public URLs, saved settings, UI behavior, and backward compatibility unless explicitly instructed otherwise.
3. Avoid duplication: reuse common patterns where justified, but do not introduce abstractions or dependencies merely for hypothetical future needs.
4. Keep tools usable without accounts or a backend unless a feature explicitly requires them. Do not add analytics, tracking, remote storage, or unnecessary network requests.
5. Build responsive, accessible interfaces with keyboard support, clear labels, meaningful errors, and light/dark themes consistent with the site.
6. Treat inputs as untrusted. Validate boundary conditions, escape rendered output, and avoid unsafe DOM injection, arbitrary code execution, and accidental destructive commands.
7. Keep public repository code, test data, screenshots, and docs free of credentials, private information, confidential business content, and internal-only URLs.
8. Do not claim a format is valid merely because a file has its extension; explicitly distinguish dummy files from properly formatted files.
9. Preserve local browser privacy: use `localStorage` only for appropriate non-secret user preferences; guard against unavailable or corrupted storage and avoid breaking existing keys without migration.

## Documentation and decisions
- Store agreed, public-facing functional specifications or architectural decisions under `docs/` when their complexity warrants separate files; do not create redundant documents for trivial changes.
- Keep `README.md` accurate as tools and their limitations change.
- Keep agent workflow rules here, and feature requirements in the relevant specification or tool documentation.
- Do not silently overwrite previously agreed requirements. When new requirements supersede existing behavior, update the canonical specification and implementation consistently.
- Treat chat discussion as proposals until requirements are confirmed. Distinguish assumptions from approved decisions.

## Implementation workflow
1. Inspect applicable instructions, existing files, relevant specifications, and the current git state.
2. Identify impacted code, user-facing behavior, persistence, edge cases, and regressions.
3. Implement the smallest coherent solution; avoid unrelated refactoring.
4. Validate positive, negative, and boundary cases, including invalid input, unusual paths/file names, mobile widths, and theme changes as applicable.
5. Run existing tests and static checks when available. If the environment allows, perform browser-based verification for UI changes. Never imply tests ran if they did not.
6. Review changed files for broken links, console/runtime issues, privacy exposure, and regressions.
7. Update documentation only where functionality, architecture, or instructions changed.
8. Provide a concise change summary, tests actually executed, limitations, and relevant commit or pull request links.

## Publishing and change safety
- The live site is served from `main`. Prefer a feature branch and pull request for substantial or potentially breaking work; small user-authorized changes may be committed directly when appropriate.
- Avoid force pushes, destructive resets, broad deletions, or changes to repository visibility without explicit approval.
- Do not modify unrelated files or public deployment settings unnecessarily.
- Do not introduce secrets into the repository, even temporarily: Git history can retain them.

## Current tool-specific considerations
For `tools/test-file-generator/`:
- It generates Windows CMD commands using `fsutil file createnew` for size-based dummy files; it does not generate valid structured document contents.
- Keep the optional `Create directory if missing` behavior, including persistence of the checkbox setting.
- Preserve explicit size limits, safe path/filename validation, copy behavior, and local preference persistence.
- Check CMD quoting and command metacharacters carefully; never produce an unsafe command through unchecked input.

## Cross-repository boundary
`RurikPreacher/personal-knowledge` is a separate private repository. Do not depend on its availability at runtime or copy private notes into this public repository. Request or use only explicitly approved, publishable requirements needed for this project.
