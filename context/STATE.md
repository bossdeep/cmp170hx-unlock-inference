---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 2
doNotEdit: true
---
# Current State

As of 2026-09-29; accepted revision 2.

## TLDR

1. cmpunlocker prerequisites identified: nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, targeting 10de:20c2 (64GB) and 10de:2082 (40GB).
   - Basis: `cmp170hx-unlock-prerequisites-finding`
2. Field reports document dual CMP 170HX 64GB cards running at 74 SMs achieving ~79 tok/s warm median decode on Qwen3.8-27B-FP8 under vLLM 0.28.0.
   - Basis: `cmp170hx-vllm-inference-benchmark-finding`

## Primary blocker

Local CMP 170HX hardware testbed remains unavailable for active validation.

- **[Access to a CMP 170HX test host with prerequisite driver build environment.](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)** — `cmp170hx-unlock-inference-need-1`

## Next action

Inspect driver/build.sh, SEC2/PLM patch diffs, and HBM control PLMs in amoghmunikote/cmpunlocker.

- **[What exact kernel source patches and firmware bypass mechanisms are applied during the build step?](context/EVIDENCE.md#cmp170hx-unlock-inference-question-1)** — `cmp170hx-unlock-inference-question-1`

## Known

- **[cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.](context/EVIDENCE.md#cmp170hx-unlock-prerequisites-finding)** — `cmp170hx-unlock-prerequisites-finding`
- **[Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.](context/EVIDENCE.md#cmp170hx-vllm-inference-benchmark-finding)** — `cmp170hx-vllm-inference-benchmark-finding`

## Uncertain

- **[Access to a CMP 170HX test host with prerequisite driver build environment.](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)** — `cmp170hx-unlock-inference-need-1`
