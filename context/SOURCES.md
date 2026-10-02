---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 5
doNotEdit: true
---
# Sources

All public Sources retained by accepted revision 5. Private provenance is never projected into a public project repository.

## cmpunlocker-readme-source

**[GitHub - amoghmunikote/cmpunlocker: A tool to unlobotomize your NVIDIA card! · GitHub](https://github.com/amoghmunikote/cmpunlocker)**

cmpunlocker repository README outlining unlock capabilities, hardware support, and installation requirements for NVIDIA CMP 170HX.

- Kind: reference-code
- Retrieved: 2026-09-29
- Primary: yes
- Selection rationale: Primary project documentation for the designated community unlock tool.

## cmpunlocker-install-sh-source

**[install.sh](https://raw.githubusercontent.com/amoghmunikote/cmpunlocker/master/install.sh)**

cmpunlocker installer script detailing PCI IDs, driver version checks, kernel arguments, and module patch procedures.

- Kind: reference-code
- Retrieved: 2026-09-29
- Primary: yes
- Selection rationale: Canonical installation implementation containing exact hardware detection and system configuration commands.

## cmpunlocker-pr58-field-report

**[docs: field report — dual CMP 170HX at 74 SM (PR #55) with production vLLM throughput by isenlink · Pull Request #58 · amoghmunikote/cmpunlocker · GitHub](https://github.com/amoghmunikote/cmpunlocker/pull/58)**

Field report pull request documenting dual CMP 170HX 64GB cards operating at 74 SMs running production vLLM Qwen3.8-27B-FP8, including throughput, HBM bandwidth measurements, and cache invalidation pitfalls.

- Kind: community-report
- Retrieved: 2026-09-29
- Primary: yes
- Selection rationale: Primary documented operational field report of vLLM LLM inference throughput and memory scaling on unlocked CMP 170HX hardware.

## level1techs-cmp170hx-thread-source

**[Couldn't resist grabbing a CMP 170HX, and now I'm in a sticky position - #41 by ropuls - Machine Learning, LLMs, & AI - Level1Techs Forums](https://forum.level1techs.com/t/couldnt-resist-grabbing-a-cmp-170hx-and-now-im-in-a-sticky-position/253947?page=3)**

Forum thread on Level1Techs documenting PCIe BAR1 P2P enablement, NCCL settings, and vLLM TP2 benchmark results on CMP 170HX across root complexes and PEX88096 switches.

- Kind: community-report
- Retrieved: 2026-10-02
- Primary: yes
- Selection rationale: Primary user-reported hardware benchmarks and driver/NCCL configuration for multi-card CMP 170HX with P2P.
