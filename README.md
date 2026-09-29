---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 2
doNotEdit: true
---
# CMP 170HX Unlock and AI Inference Evaluation

Accepted research state published by [OpenCat Research](https://gaudi.clarion.run/projects/cmp170hx-unlock-inference). Revision **2** · generated 2026-09-29T13:55:00.388Z · [machine corpus](corpus/corpus.json) · [integrity manifest](MANIFEST.json).

## Objective

Establish a reproducible process to evaluate CMP 170HX unlock methods and quantify their AI inference performance and stability.

### Success criteria

- **prerequisites-documented:** Software environment prerequisites, kernel module requirements, and risk factors for unlock procedures are cataloged.
- **capacity-verified:** Reported memory capacity expansion and compute throughput are evaluated and recorded on hardware.
- **inference-benchmarked:** Baseline AI inference execution (latency and throughput) is measured on the target card.

## TLDR

- cmpunlocker prerequisites identified: nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, targeting 10de:20c2 (64GB) and 10de:2082 (40GB).
- Field reports document dual CMP 170HX 64GB cards running at 74 SMs achieving ~79 tok/s warm median decode on Qwen3.8-27B-FP8 under vLLM 0.28.0.

## Primary blocker

Local CMP 170HX hardware testbed remains unavailable for active validation.

## Next action

Inspect driver/build.sh, SEC2/PLM patch diffs, and HBM control PLMs in amoghmunikote/cmpunlocker.

## Current priorities

- **P1 · ready:** [What exact kernel source patches and firmware bypass mechanisms are applied during the build step?](context/FRONTIER.md#cmp170hx-unlock-inference-question-1)
  - Next: Inspect driver/build.sh and kernel patches in amoghmunikote/cmpunlocker.
- **P2 · blocked:** [What inference throughput and memory capacity are achieved on unlocked CMP 170HX hardware across standard model architectures?](context/FRONTIER.md#cmp170hx-unlock-inference-question-2)
  - Next: Deploy standard inference benchmarks on the unlocked card and record latency, throughput, and error rates.

## Known

- [cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.](context/EVIDENCE.md#cmp170hx-unlock-prerequisites-finding)
- [Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.](context/EVIDENCE.md#cmp170hx-vllm-inference-benchmark-finding)

## Uncertain

- [Access to a CMP 170HX test host with prerequisite driver build environment.](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)

## Continue this research

Point an agentic harness at this repository. It must begin with [AGENTS.md](AGENTS.md), which loads the current context, shared research policy, and typed submission protocol. Anyone may research and submit candidate evidence; only OpenCat Research can reconcile, Apply, and publish accepted corpus changes.
