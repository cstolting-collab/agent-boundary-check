# Agent Boundary Check

**Problem:** You don't know what your AI coding agent can actually read, write, execute, and reach. Claims != capability.

**What breaks without it:** Agent reads credentials, writes outside repo, executes network calls in a supposedly sandboxed run.

**What this is:** Synthetic-canary tooling. Drops canary files, attempts read/write/exec/reach, records exact capability boundary.

**30 sec try:**
```bash
git clone https://github.com/cstolting-collab/agent-boundary-check
cd agent-boundary-check
python3 -m pip install .
agent-boundary demo
# For a real agent: agent-boundary verify codex --json boundary.json
```

**Evidence:**
- Patches live in `cml-github-work-record/patches/agent-boundary-check/README.md`
- Designed for: Cursor, Claude, Codex boundary verification
- Capability results distinguish ALLOW, DENY, ERROR, SKIP, N/A, and UNKNOWN; policy violations and insufficient evidence remain separate.

Upstream project: [Sylvester Kaczmarek / Agent Boundary Check](https://github.com/sylvesterkaczmarek/agent-boundary-check). This repository is a fork.

License: [MIT](LICENSE) · Copyright (c) 2026 Sylvester Kaczmarek · Topics: ai-agents, security, evaluation, canary, boundary-check, cml
