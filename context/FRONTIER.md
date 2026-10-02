---
generated: true
generator: opencat-research
projectId: cmp170hx-unlock-inference
objectiveId: cmp170hx-unlock-inference
acceptedRevision: 4
doNotEdit: true
---
# Frontier

Active unfinished questions, ordered by accepted priority.

## cmp170hx-unlock-inference-question-1

What exact kernel source patches and firmware bypass mechanisms are applied during the build step?

Inspect driver/build.sh and patch diffs to verify the exact mechanism by which GSP/SEC2 firmware or memory controller register checks are bypassed and assess safety risks prior to hardware execution.
- Work status: ready; priority: 1
- Definition of done: Source patch diffs in driver/build.sh are cataloged and risk-assessed.
- Next action: Inspect driver/build.sh and kernel patches in amoghmunikote/cmpunlocker.
- Inputs: none
- Evidence basis: [cmp170hx-unlock-prerequisites-finding](context/EVIDENCE.md#cmp170hx-unlock-prerequisites-finding)

## cmp170hx-unlock-inference-question-2

What inference throughput and memory capacity are achieved on unlocked CMP 170HX hardware across standard model architectures?

Once an unlocked CMP 170HX testbed is available, measure memory throughput, compute scaling, and standard LLM inference tokens per second.
- Work status: blocked; priority: 2
- Definition of done: Inference benchmark results and memory utilization metrics are collected and compared against baseline GPU specifications.
- Next action: Deploy standard inference benchmarks on the unlocked card and record latency, throughput, and error rates.
- Inputs: [cmp170hx-unlock-inference-need-1](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)
- Evidence basis: [cmp170hx-unlock-inference-initial-context](context/EVIDENCE.md#cmp170hx-unlock-inference-initial-context), [cmp170hx-unlock-inference-need-1](context/EVIDENCE.md#cmp170hx-unlock-inference-need-1)
