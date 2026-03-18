# mise-example

Example repository showcasing [mise](https://mise.jdx.dev/) per-directory tool versioning, tasks, environment variables, and redactions.

## Structure

```
mise.toml          # Root config: global tools (uv, jq, shellcheck), env vars, tasks
node-18/           # Node.js 18
node-20/           # Node.js 20
node-22/           # Node.js 22
python-3.11/       # Python 3.11
python-3.12/       # Python 3.12
python-3.13/       # Python 3.13
```

Each subdirectory has its own `mise.toml` that pins a specific tool version, demonstrating how mise activates the correct version when you `cd` into a directory.

## Prerequisites

Install [mise](https://mise.jdx.dev/getting-started.html).

## Getting Started

```sh
# Install all tools (root + subdirectories)
mise run setup

# See installed tool versions
mise run info

# Run version checks across the project
mise run check
```

## Available Tasks

| Task    | Description                                      |
|---------|--------------------------------------------------|
| `setup` | Install all tools across root and subdirectories  |
| `info`  | Print current tool versions                       |
| `check` | Run shellcheck and version checks across project  |
| `fmt`   | Format Python files with ruff (via uv)            |
| `clean` | Clean `__pycache__` and `node_modules` directories|

Run any task with `mise run <task>`.
