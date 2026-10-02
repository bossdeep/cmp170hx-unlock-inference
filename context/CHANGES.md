---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 4
doNotEdit: true
---
# Accepted changes

Git history is the complete publication history. This projection lists current public records under the accepted revision that last changed them.

## Revision 4

Applied 2026-10-02T04:58:14.125Z.

- Accepted Entry: `cmp170hx-failure-mode-xid154-finding` — Unlocked CMP 170HX cards face potential unrecoverable hardware failure (Xid 154, GFW_BOOT progress 0x1) under multi-card heavy PyTorch workloads unless power capped.
- Accepted Entry: `cmp170hx-glm-multicard-inference-finding` — A 4-card unlocked CMP 170HX setup achieves over 100 tok/s serving GLM5.3-Flash at >200k context.
- Accepted Entry: `cmp170hx-vbios-hard-fuse-validation-finding` — CMP 170HX validates VBIOS device IDs against physical hard fuses, causing boot firmware load failures if non-native VBIOS images are flashed.

## Revision 3

Applied 2026-10-01T23:51:08.250Z.

- State: current State revised

## Revision 2

Applied 2026-09-29T13:55:00.388Z.

- Accepted Entry: `cmp170hx-vllm-inference-benchmark-finding` — Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.
- Source added: `cmpunlocker-pr58-field-report` — docs: field report — dual CMP 170HX at 74 SM (PR #55) with production vLLM throughput by isenlink · Pull Request #58 · amoghmunikote/cmpunlocker · GitHub

## Revision 1

Applied 2026-09-29T09:12:12.181Z.

- Updated Entry: `cmp170hx-unlock-inference-question-1` — What exact kernel source patches and firmware bypass mechanisms are applied during the build step?
- Accepted Entry: `cmp170hx-unlock-prerequisites-finding` — cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.
- Source added: `cmpunlocker-install-sh-source` — install.sh
- Source added: `cmpunlocker-readme-source` — GitHub - amoghmunikote/cmpunlocker: A tool to unlobotomize your NVIDIA card! · GitHub
