# Agent Boundary Check — contribution fork

**Synthetic-canary tooling for measuring an AI coding agent’s effective execution boundary.**

This repository is a fork of [Sylvester Kaczmarek’s Agent Boundary Check](https://github.com/sylvesterkaczmarek/agent-boundary-check). The upstream project and its original authorship remain credited to Sylvester Kaczmarek.

**Runtime:** Python 3.11+ · **CLI:** `agent-boundary` · **License:** MIT

## What it measures

A probe uses synthetic resources to check read, write, process-execution, and network capabilities in the agent’s execution environment. Results describe the tested path and configuration; they are not a universal guarantee of sandbox security.

Capability results distinguish `ALLOW`, `DENY`, `ERROR`, `SKIP`, `N/A`, and `UNKNOWN`. Policy violations and insufficient evidence are separate outcomes.

## Get started

```bash
git clone https://github.com/cstolting-collab/agent-boundary-check.git
cd agent-boundary-check
python3 -m pip install .
agent-boundary demo
```

The deterministic demo exercises the reporting path without an AI account. It does not measure a real agent’s sandbox.

To measure an installed, configured agent:

```bash
agent-boundary verify codex --json boundary.json
```

Other supported automatic runners include Claude Code and Gemini CLI. See [supported agents](docs/supported-agents.md) for setup and the manual flow.

## Documentation

| Read | Purpose |
| --- | --- |
| [How it works](docs/how-it-works.md) | Probe and reporting model |
| [Policies](docs/policies.md) | Interpret capabilities against a chosen policy |
| [Reproducibility](docs/reproducibility.md) | Compare runs and preserve evidence |
| [Threat model](docs/threat-model.md) | Limits and assumptions |
| [Security policy](SECURITY.md) | Reporting guidance |
| [Citation](CITATION.cff) | Upstream attribution |

## Development

```bash
python3 -m pip install -e '.[dev]'
pytest -q
```

No new runtime or test result is claimed by this documentation update. Contribution history and upstream review outcomes must be assessed from the relevant commits and pull requests.

## License and attribution

[MIT License](LICENSE). Copyright (c) 2026 Sylvester Kaczmarek.

[Upstream repository](https://github.com/sylvesterkaczmarek/agent-boundary-check) · [Estra Logics engineering record](https://github.com/cstolting-collab/CML-GitHub-Work-Record)
