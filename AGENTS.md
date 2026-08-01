# AGENTS.md

## Cursor Cloud specific instructions

### What this repository is
This is a **GitHub profile README** repository (`Carlos-Crisostomo/Carlos-Crisostomo`). A repo whose name matches its owner's username is special: its `README.md` is rendered on the owner's GitHub profile page. There is no application code, no services, no package manager, no build system, and no automated tests.

### Product / "how to run"
The only artifact is `README.md`. The development workflow is:
1. Edit `README.md`.
2. Preview the GitHub-Flavored Markdown rendering locally.
3. Commit and push to `main`; GitHub renders it on the profile page.

There is no lint/test/build step. "Running the app" means previewing the rendered README.

### Local preview (dev server)
`grip` (GitHub Readme Instant Preview) renders the README exactly as GitHub does and serves it on a local port. It is installed in a virtualenv at `.venv` during environment setup.

- Start the preview server: `/workspace/.venv/bin/grip README.md 0.0.0.0:6419`
- Then open `http://localhost:6419`.

Notes / gotchas:
- `grip` renders via GitHub's Markdown API by default. Unauthenticated requests are rate-limited; if you hit a rate limit, pass a token with `grip --user <user> --pass <token>` or render offline with `grip --norender`.
- The `.venv` is not tracked by git and is recreated by the environment update script, so do not rely on it being committed.
