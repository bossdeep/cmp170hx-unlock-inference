---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 5
doNotEdit: true
---
# Current State

Accepted revision 5.

Brief as of 2026-10-02.

### prerequisites-documented — Partial

Software environment prerequisites, kernel module requirements, and risk factors for unlock procedures are cataloged.

- cmpunlocker prerequisites identified: nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, targeting 10de:20c2 (64GB) and 10de:2082 (40GB).
  - Cites: [cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.](context/EVIDENCE.md#cmp170hx-unlock-prerequisites-finding)
- Multi-card setups across root complexes or PEX88096 switches require NCCL_P2P_LEVEL=SYS and vLLM --disable-custom-all-reduce to avoid custom IPC all-reduce crashes.
  - Cites: [CMP 170HX multi-GPU setups require NCCL_P2P_LEVEL=SYS and vLLM --disable-custom-all-reduce to enable functional BAR1 P2P and prevent IPC all-reduce crashes.](context/EVIDENCE.md#cmp170hx-p2p-multigpu-prerequisites-finding)

Uncertain: none.

### capacity-verified — Open

Reported memory capacity expansion and compute throughput are evaluated and recorded on hardware.

No current answer.

Uncertain: none.

### inference-benchmarked — Partial

Baseline AI inference execution (latency and throughput) is measured on the target card.

- Field reports document dual CMP 170HX 64GB cards running at 74 SMs achieving ~79 tok/s warm median decode on Qwen3.8-27B-FP8 under vLLM 0.28.0.
  - Cites: [Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.](context/EVIDENCE.md#cmp170hx-vllm-inference-benchmark-finding)
- 2x CMP 170HX TP2 with BAR1 P2P achieves 4,714 tok/s 8k prefill (1.9x vs host-staged) and ~120 tok/s decode on Qwen3.8-Flash-Next W4A16 in vLLM 0.30.0.
  - Cites: [Dual CMP 170HX in vLLM TP2 with BAR1 P2P achieves 4,714 tok/s 8k prefill (~1.9x gain over host-staged) and ~120 tok/s decode on Qwen3.8-Flash-Next W4A16.](context/EVIDENCE.md#cmp170hx-tp2-p2p-vllm-benchmark-finding)

Uncertain: none.

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
