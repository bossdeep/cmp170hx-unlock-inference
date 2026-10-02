---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 4
doNotEdit: true
---
# Sources

All public Sources retained by accepted revision 4. Private provenance is never projected into a public project repository.

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
