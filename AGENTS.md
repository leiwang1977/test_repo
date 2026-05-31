# AGENTS.md

Guidance for AI agents working in this repository.

## Repository overview

`test_repo` is a minimal Git integration / workflow test repository. It contains a short `README.md` and seven placeholder text files under `src/` (`file1.c` through `file7.c`). The `.c` extension is naming only; files are not valid C source and there is no `Makefile`, package manager, Docker setup, or CI configuration in-tree.

## Development commands

There are no install, lint, test, build, or dev-server scripts defined in this repo.

| Task | Command / note |
|------|----------------|
| Clone / update | Standard `git` operations against `origin` |
| Lint | Not applicable (no linter config) |
| Test | Not applicable (no test suite) |
| Build | Not applicable |
| Run app | Not applicable (no application process) |

To sanity-check the workspace after clone:

```bash
ls -1 src/*.c | wc -l   # expect 7
git status
git log --oneline -5
```

## Branching

Default branch is `develop`. Feature work for cloud agents should branch from `develop` using the `cursor/<name>-a608` naming convention when instructed by cloud task rules.

## Cursor Cloud specific instructions

- **No services to start.** Do not run `docker compose`, `npm run dev`, or similar unless new application code is added to the repository.
- **No dependency install step** beyond keeping the git checkout current. The VM update script is a no-op (`true`) because there are no language package lockfiles or vendored dependencies.
- **“Hello world” for this repo** means verifying git works and all seven `src/file*.c` files are present—not starting a server or UI.
- If a future branch adds real application code (e.g. `package.json`, `Makefile`, `docker-compose.yml`), revisit this section and the VM update script accordingly.
