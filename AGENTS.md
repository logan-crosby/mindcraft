# Repository Guidelines

## Project Structure & Module Organization

Mindcraft is a Node.js ES-module application. `main.js` loads configuration and starts agents. Core behavior lives in `src/agent/`; model-provider adapters are in `src/models/`; server, dashboard, and Minecraft orchestration are in `src/mindcraft/`. Reusable configuration belongs in `profiles/`, evaluation and research workflows in `tasks/`, dependency fixes in `patches/`, and optional proxy support in `services/`. Docker entrypoints are defined by `Dockerfile`, `Tasks.Dockerfile`, and `docker-compose.yml`.

## Build, Test, and Development Commands

- `npm install` installs dependencies and applies `patch-package` patches.
- `npm start` or `node main.js` starts Mindcraft with profiles from `settings.js`.
- `node main.js --profiles ./profiles/gemini.json` runs a specific profile.
- `npx eslint .` checks JavaScript quality, including unhandled promises.
- `npm run reinstall` removes modules and the lockfile, then performs a clean install.
- `docker-compose up --build` builds and runs the containerized stack.

Use Node.js 18 or 20 LTS; newer releases may break native dependencies.

## Coding Style & Naming Conventions

Use four-space indentation, semicolons, ES-module imports, and `async`/`await` with every promise awaited or explicitly handled. Follow existing naming: `camelCase` for functions and variables, `PascalCase` for classes, and lowercase or snake_case filenames where established. Run ESLint before submitting changes. Keep provider-specific logic in `src/models/` and avoid unrelated refactors.

## Testing Guidelines

There is no unified automated test suite or coverage threshold. Every change must pass `npx eslint .` and receive focused validation. For agent or Minecraft behavior, run the affected profile against a local LAN world. For task changes, run the relevant script or fixture under `tasks/` and record the command and result in the pull request.

## Commit, Pull Request & Agent Workflow

Use focused Conventional Commit-style subjects such as `feat(dashboard): ...`, `fix: ...`, or `chore(docs): ...`. Pull requests should describe behavior, configuration impact, and validation; link the relevant issue and include screenshots for dashboard changes.

Track work with `bd`: claim an issue before implementation, keep its status current, and close it after verification. Use Lumen before broad code discovery and `rg` for exact strings. Preserve unrelated worktree changes and review the final diff before committing.

## Security & Configuration

Copy `keys.example.json` to ignored `keys.json`, or use environment variables; never commit credentials. Keep `allow_insecure_coding` disabled unless required. If enabled, use Docker and never connect the bot to public servers.
