---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 3
doNotEdit: true
---
# CMP 170HX Unlock and AI Inference Evaluation

Accepted research state published by [OpenCat Research](https://gaudi.clarion.run/projects/cmp170hx-unlock-inference). Revision **3** · generated 2026-10-01T23:51:08.250Z · [machine corpus](corpus/corpus.json) · [integrity manifest](MANIFEST.json).

## Objective

## CMP 170HX Unlock and AI Inference Evaluation

Establish a reproducible process to evaluate CMP 170HX unlock methods and quantify their AI inference performance and stability.

### Success criteria

- **prerequisites-documented:** Software environment prerequisites, kernel module requirements, and risk factors for unlock procedures are cataloged.
- **capacity-verified:** Reported memory capacity expansion and compute throughput are evaluated and recorded on hardware.
- **inference-benchmarked:** Baseline AI inference execution (latency and throughput) is measured on the target card.

## Brief

Brief as of 2026-10-01.

### prerequisites-documented — Partial

Software environment prerequisites, kernel module requirements, and risk factors for unlock procedures are cataloged.

- cmpunlocker prerequisites identified: nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, targeting 10de:20c2 (64GB) and 10de:2082 (40GB).
  - Cites: [cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.](context/EVIDENCE.md#cmp170hx-unlock-prerequisites-finding)

Uncertain: none.

### capacity-verified — Open

Reported memory capacity expansion and compute throughput are evaluated and recorded on hardware.

No current answer.

Uncertain: none.

### inference-benchmarked — Partial

Baseline AI inference execution (latency and throughput) is measured on the target card.

- Field reports document dual CMP 170HX 64GB cards running at 74 SMs achieving ~79 tok/s warm median decode on Qwen3.8-27B-FP8 under vLLM 0.28.0.
  - Cites: [Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.](context/EVIDENCE.md#cmp170hx-vllm-inference-benchmark-finding)

Uncertain: none.

## Direction

## Next

**[What exact kernel source patches and firmware bypass mechanisms are applied during the build step?](context/EVIDENCE.md#cmp170hx-unlock-inference-question-1)**
- Work status: ready; priority: 1
- Definition of done: Source patch diffs in driver/build.sh are cataloged and risk-assessed.
- Next action: Inspect driver/build.sh and kernel patches in amoghmunikote/cmpunlocker.
- Inputs: none

## Blocker

[What inference throughput and memory capacity are achieved on unlocked CMP 170HX hardware across standard model architectures?](context/EVIDENCE.md#cmp170hx-unlock-inference-question-2)
Inputs: [Access to a CMP 170HX test host with prerequisite driver build environment.](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)

## Decisions

No steering decisions.

## Queue

- P1 · ready: [What exact kernel source patches and firmware bypass mechanisms are applied during the build step?](context/EVIDENCE.md#cmp170hx-unlock-inference-question-1)
- P2 · blocked: [What inference throughput and memory capacity are achieved on unlocked CMP 170HX hardware across standard model architectures?](context/EVIDENCE.md#cmp170hx-unlock-inference-question-2)

## Continue this research

Point an agentic harness at this repository. It must begin with [AGENTS.md](AGENTS.md), which loads the current context, shared research policy, and typed submission protocol. Anyone may research and submit candidate evidence; only OpenCat Research can reconcile, Apply, and publish accepted corpus changes.
