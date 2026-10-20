> **ucc2026 branch.** This fork of [cloud-ai-ufcg/ai-engine](https://github.com/cloud-ai-ufcg/ai-engine) holds the exact ai-engine
> used in the UCC 2026 paper "When a Better Prompt Is Just Noise in LLM-Driven Cloud Orchestration". It adds three commits on
> top of upstream `7aa416e` (tag `ucc2026-confirmatory`, the version of the confirmatory runs): `5cd98cd` logs why a
> recommendation cycle is skipped, `8b7b7e3` requests the analysis lookback window from the monitor (the fix for silently
> skipped cycles in the compressed scenario), and `a657919` versions the experiment prompts (tag `ucc2026-live`, the version
> of the live experiment). The experiment code and data are in [Androthorn/simulator-ucc](https://github.com/Androthorn/simulator-ucc),
> whose `ai-engine` submodule is pinned at `a657919`. Apache License 2.0, as upstream.

# ai-engine
This is a FastAPI and CLI AI Engine that uses machine learning and LLMs to analyze workloads and generate recommendations with explanations for efficient workload migration between private and public clouds.

## Installation

```bash
make setup
```

## Usage

### API

Run API
```bash
make api
```

Run Fake Monitor
```bash
make fake-monitor
```

Run Fake Actuator
```bash
make fake-actuator
```

Turn on recommendations
```bash
curl -X POST http://0.0.0.0:8083/start
```

Turn off recommendations
```bash
curl -X POST http://0.0.0.0:8083/stop
```

Analyze a single time
```bash
curl -X POST http://0.0.0.0:8083/analyze --data @monitor_outputs.json
```

### CLI

Run CLI Mode
```bash
make cli
```

### Docker

Build API
```bash
make build-docker-api
```

Build CLI
```bash
make build-docker-cli
```

Run API
```bash
make run-docker-api
```

Run CLI
```bash
make run-docker-cli
```

