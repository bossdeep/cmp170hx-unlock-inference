---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 4
doNotEdit: true
---
# Evidence

Every accepted Entry, including inactive history. Claims carry an evidence badge; questions and decisions do not. Public citations retain the exact bounded support note used by the corpus.

## cmp170hx-unlock-inference-initial-context

**Investigating methods and community tools to unlock restricted hardware features and memory capacity on NVIDIA CMP 170HX cards for AI inference workloads.**

The owner seeks continuous tracking and evaluation of techniques to unlock compute throughput and addressable VRAM on CMP 170HX cards, using community repositories and discussion channels as initial reference points.

- Kind: Claim
- Status: active
- Evidence: Unverified
- Area: hardware
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card
- Topics: cmp170hx, hardware-unlock, ai-inference, vram-expansion
- Basis Entries: none
- Omitted private support records: 1

### Citations

No public citation retained.

## cmp170hx-unlock-inference-need-1

**Access to a CMP 170HX test host with prerequisite driver build environment.**

A physical host system containing a CMP 170HX GPU running a compatible Linux distribution with kernel headers and Secure Boot disabled.

- Kind: Question
- Status: active
- Area: hardware
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card
- Topics: cmp170hx, testbed, drivers
- Basis Entries: `cmp170hx-unlock-inference-initial-context`
- Omitted private support records: 1

### Citations

No public citation retained.

## cmp170hx-unlock-inference-question-1

**What exact kernel source patches and firmware bypass mechanisms are applied during the build step?**

Inspect driver/build.sh and patch diffs to verify the exact mechanism by which GSP/SEC2 firmware or memory controller register checks are bypassed and assess safety risks prior to hardware execution.

- Kind: Question
- Status: active
- Area: software-stack
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card; model: CMP 170HX
- Topics: driver-patching, kernel-modules, security
- Basis Entries: `cmp170hx-unlock-prerequisites-finding`
- Omitted private support records: 0

### Citations

- **GitHub - amoghmunikote/cmpunlocker: A tool to unlobotomize your NVIDIA card! · GitHub** (`cmpunlocker-readme-source`)
  - Locator: https://github.com/amoghmunikote/cmpunlocker
  - Support: Kernel build and patch scripts in amoghmunikote/cmpunlocker

## cmp170hx-unlock-inference-question-2

**What inference throughput and memory capacity are achieved on unlocked CMP 170HX hardware across standard model architectures?**

Once an unlocked CMP 170HX testbed is available, measure memory throughput, compute scaling, and standard LLM inference tokens per second.

- Kind: Question
- Status: active
- Area: performance
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card
- Topics: llm-inference, throughput, benchmarks
- Basis Entries: `cmp170hx-unlock-inference-initial-context`, `cmp170hx-unlock-inference-need-1`
- Omitted private support records: 1

### Citations

No public citation retained.

## cmp170hx-unlock-prerequisites-finding

**cmpunlocker requires nvidia-open 610+, disabled Secure Boot, IOMMU passthrough, and patched open-gpu-kernel-modules targeting PCI IDs 10de:20c2 and 10de:2082.**

Analysis of cmpunlocker install.sh and documentation indicates prerequisites: Linux x86_64, nvidia-open 610.xx.xx+, matching kernel headers, Secure Boot disabled, and IOMMU set to passthrough (intel_iommu=on iommu=pt). Target PCI device IDs are 10de:20c2 (8GB unlocks to 64GB) and 10de:2082 (10GB unlocks to 40GB). Unlocking involves patching open-gpu-kernel-modules to override memory geometry, restore SM throughput (SS0/SS1), configure PCIe Gen2 link retries, and set up VFIO passthrough. DKMS modules are removed, creating kernel upgrade fragility.

- Kind: Claim
- Status: active
- Evidence: Documented
- Area: software-stack
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card; model: CMP 170HX
- Topics: cmpunlocker, kernel-modules, prerequisites, driver-patching
- Basis Entries: `cmp170hx-unlock-inference-question-1`
- Omitted private support records: 0

### Citations

- **GitHub - amoghmunikote/cmpunlocker: A tool to unlobotomize your NVIDIA card! · GitHub** (`cmpunlocker-readme-source`)
  - Locator: https://github.com/amoghmunikote/cmpunlocker
  - Support: README and install.sh requirements for cmpunlocker
- **install.sh** (`cmpunlocker-install-sh-source`)
  - Locator: https://raw.githubusercontent.com/amoghmunikote/cmpunlocker/master/install.sh
  - Support: install.sh driver version checks and PCI ID handling

## cmp170hx-vllm-inference-benchmark-finding

**Unlocked CMP 170HX (64GB, 74 SMs, PCIe Gen2) achieves ~79 tok/s warm median decode in vLLM on Qwen3.8-27B-FP8; vLLM torch.compile caches require clearing upon SM count changes.**

On a dual CMP 170HX (10de:20c2 8GB unlocked to 64GB) system with driver 610.43.02 and PCIe Gen2, upgrading patch revision enabled 74 SMs (up from 70 SMs). Running vLLM 0.28.0 with MTP(5) and Qwen3.8-27B-FP8 (TP=1, seqs=4, 262k context) yielded 512-token decode throughput of 15.9 to 92.0 tok/s with a warm median of ~79 tok/s. Peak HBM bandwidth reached 1,599 GB/s idle and ~928 GB/s under resident model load. Changing SM counts invalidates vLLM torch.compile caches (keyed to SM count), requiring purging /root/.cache/vllm to avoid crash loops.

- Kind: Claim
- Status: active
- Evidence: Documented
- Area: serving
- Document date: 2026-09-29
- Retrieved: 2026-09-29
- Scope: topology: single-card; model: Qwen3.8-27B-FP8; precision: FP8
- Topics: cmp170hx, ai-inference, vllm, benchmarks, sm-unlock
- Basis Entries: `cmp170hx-unlock-prerequisites-finding`
- Omitted private support records: 0

### Citations

- **docs: field report — dual CMP 170HX at 74 SM (PR #55) with production vLLM throughput by isenlink · Pull Request #58 · amoghmunikote/cmpunlocker · GitHub** (`cmpunlocker-pr58-field-report`)
  - Locator: https://github.com/amoghmunikote/cmpunlocker/pull/58
  - Support: Dual CMP 170HX 64GB setup running vLLM 0.28.0 Qwen3.8-27B-FP8 at 74 SMs achieving ~79 tok/s warm median decode.

## cmp170hx-failure-mode-xid154-finding

**Unlocked CMP 170HX cards face potential unrecoverable hardware failure (Xid 154, GFW_BOOT progress 0x1) under multi-card heavy PyTorch workloads unless power capped.**

A 4-card CMP 170HX setup unlocked to 64GB encountered an unrecoverable failure during concurrent PyTorch execution across all four cards, triggering an Xid 154 error. Subsequent reboots hang at GFW_BOOT progress 0x1 with RmInitAdapter failure 0x62:0x55:2130, despite the device remaining visible in lspci and VBIOS dump matching functional cards. Community analysis attributes this to power delivery rail (pexvdd) breakdown or HBM interconnect failure under unthrottled load, highlighting the need for conservative power capping (e.g. 200W).

- Kind: Claim
- Status: active
- Evidence: Unverified
- Area: reliability
- Document date: 2026-09-30
- Retrieved: 2026-10-02
- Scope: topology: not-stated; model: CMP 170HX
- Topics: cmp170hx, hardware-failure, xid-errors, reliability, power-limits
- Basis Entries: `cmp170hx-unlock-prerequisites-finding`
- Omitted private support records: 1

### Citations

No public citation retained.

## cmp170hx-vbios-hard-fuse-validation-finding

**CMP 170HX validates VBIOS device IDs against physical hard fuses, causing boot firmware load failures if non-native VBIOS images are flashed.**

Testing with external hardware flashers and modified nvflash utilities confirmed that CMP 170HX hardware validates VBIOS device IDs against hard-burned efuses. Flashing mismatched firmware or attempting to bypass board ID certificate checks results in the GPU failing to load firmware at boot, demonstrating that device personality cannot be changed purely via SPI VBIOS flashing without software driver-level interception.

- Kind: Claim
- Status: active
- Evidence: Unverified
- Area: hardware
- Document date: 2026-09-30
- Retrieved: 2026-10-02
- Scope: topology: single-card; model: CMP 170HX
- Topics: cmp170hx, vbios, efuse, firmware, nvflash
- Basis Entries: `cmp170hx-unlock-prerequisites-finding`
- Omitted private support records: 1

### Citations

No public citation retained.

## cmp170hx-glm-multicard-inference-finding

**A 4-card unlocked CMP 170HX setup achieves over 100 tok/s serving GLM5.3-Flash at >200k context.**

A community field report describes a 4-card CMP 170HX rig running GLM5.3-Flash, delivering >100 tok/s inference throughput at >200k context length. This demonstrates multi-card serving feasibility across large context windows on unlocked CMP 170HX hardware.

- Kind: Claim
- Status: active
- Evidence: Unverified
- Area: serving
- Document date: 2026-09-30
- Retrieved: 2026-10-02
- Scope: topology: eight-card; model: GLM5.3-Flash
- Topics: cmp170hx, multi-card, inference, glm5.3-flash, long-context
- Basis Entries: `cmp170hx-vllm-inference-benchmark-finding`
- Omitted private support records: 1

### Citations

No public citation retained.
