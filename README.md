# docker-containers

`docker-containers` is a Codex skill for building, fixing, and hardening Docker setups for real apps. It is designed to help agents handle the repetitive parts of container work correctly on the first pass: `Dockerfile`, `.dockerignore`, Compose, startup commands, image size, caching, ports, volumes, and container debugging.

## What It Is For

Use this skill when you want Codex to:

- containerize a Node, Python, Go, or frontend app
- add Postgres, Redis, or another dependency with Compose
- fix a broken Docker build or startup failure
- reduce image size and improve build cache behavior
- make a container setup safer for production

## Why It Exists

Docker work is usually not hard, but it is easy to get subtly wrong. This skill keeps the process small, practical, and repeatable. It favors official base images, multi-stage builds, `.dockerignore`, service-name DNS in Compose, and clean runtime defaults.

## Install

Copy this once into your Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills" && git clone https://github.com/mdayan8/docker-containers.git "${CODEX_HOME:-$HOME/.codex}/skills/docker-containers"
```

If you already have the repo locally, copy the `docker-containers` folder into `${CODEX_HOME:-$HOME/.codex}/skills/`.

## Example Requests

Use the skill for requests like:

- `Containerize this Node app and add Compose for Postgres`
- `My Docker build is slow; make it smaller and faster`
- `Fix this container startup failure and tell me why it exits`
- `Add Redis to my Compose file and wire the app to it correctly`
- `Make this Docker setup production-safe without changing app behavior`

## What To Expect

The skill stays narrow on purpose:

- it does not invent Kubernetes unless the task needs Kubernetes
- it does not add extra layers or tools unless they solve a real problem
- it keeps changes reviewable and easy to undo
- it preserves the app's current run behavior unless the request says otherwise

## Skill Contents

- `SKILL.md` contains the trigger rules and workflow
- `references/examples.md` contains concrete Dockerfile and Compose starters
- `references/recipes.md` contains stack-specific patterns
- `references/troubleshooting.md` contains common failure modes and fixes

## Maintenance Rule

Keep the skill small, reliable, and easy to maintain. Add new guidance only when it helps Codex make a better decision repeatedly.
