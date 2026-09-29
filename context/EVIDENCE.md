---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 1
doNotEdit: true
---
# Evidence

Every accepted Entry, including inactive history. Public citations retain the exact bounded support note used by the corpus.

## cmp170hx-unlock-inference-initial-context

**Investigating methods and community tools to unlock restricted hardware features and memory capacity on NVIDIA CMP 170HX cards for AI inference workloads.**

The owner seeks continuous tracking and evaluation of techniques to unlock compute throughput and addressable VRAM on CMP 170HX cards, using community repositories and discussion channels as initial reference points.

- Kind: context
- Status: active
- Evidence: unverified
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

- Kind: need
- Status: active
- Evidence: unverified
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

- Kind: question
- Status: active
- Evidence: documented
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

- Kind: question
- Status: active
- Evidence: unverified
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

- Kind: finding
- Status: active
- Evidence: documented
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
