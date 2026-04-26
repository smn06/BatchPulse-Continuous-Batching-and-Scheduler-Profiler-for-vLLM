# BatchPulse

> Continuous batching and scheduler profiler for high-throughput vLLM inference

## 1. Project Overview

**BatchPulse** is a GitHub-ready project idea focused on **continuous batching, request scheduling, latency optimization, LLM serving**.

Serving performance depends heavily on scheduler choices, especially when requests vary widely in prompt length and concurrency. This project benchmarks continuous batching strategies and explains how scheduling decisions affect TTFT, throughput, and fairness.

**Target area:** CUDA / vLLM inference systems  
**Primary users:** ML platform teams, inference engineers, serving researchers


---

## 2. Why This Project Matters

This project shows the ability to think across:

- model design
- optimization and quantization or systems tuning
- runtime constraints
- reproducible benchmarking
- product-style engineering and evaluation



---

## 3. Core Features

- Workload generator for bursty, mixed-length, and steady traffic
- Scheduler tuning experiments around batch size and token budgets
- Latency breakdown into queueing, prefill, and decode stages
- Fairness analysis for short and long prompts
- Interactive benchmark report for throughput vs latency tradeoffs

---

## 4. Proposed System Architecture

1. Traffic generator emits configurable request patterns
2. Serving runner executes workloads with different scheduler configs
3. Metrics collector records queue time, TTFT, decode latency, and throughput
4. Analysis layer compares fairness and tail-latency effects
5. Results stored in reproducible benchmark tables

---

## 5. Recommended Tech Stack

- Python benchmark harness
- vLLM server or equivalent LLM inference engine
- Prometheus-style metrics or custom telemetry
- Pandas/matplotlib analysis notebooks
- Optional load-test container setup


---

## 6. Data / Workload Ideas

Synthetic prompts, summarization prompts, code prompts, and mixed user-session traces.

For a strong repository, keep one **small reproducible benchmark set** in the repo and document how the larger benchmark was prepared. That makes the project easier for others to run and review.

---

## 7. Milestone Plan

### Phase 1
Implement workload families and repeatable seeds

### Phase 2
Capture queueing and decode stage metrics

### Phase 3
Compare scheduler parameter regimes

### Phase 4
Document recommended settings for several workload classes

### Phase 5
Package results as benchmark report and dashboard

### Final Deliverable
A working demo, a benchmark report, and clear ablations showing what changed performance or accuracy.

---

## 8. Evaluation Metrics

- TTFT
- p50/p95/p99 latency
- Tokens/sec throughput
- GPU utilization
- Fairness ratio between short and long requests


A great final report should include:

- baseline vs optimized comparison
- error analysis
- failure cases
- hardware/runtime notes
- screenshots or short demo GIFs

---

## 9. Suggested Repository Structure

```text
batchpulse/
├── README.md
├── app/ or src/
├── models/
├── scripts/
├── configs/
├── notebooks/ or reports/
├── benchmarks/
├── assets/
└── docs/
```

---
