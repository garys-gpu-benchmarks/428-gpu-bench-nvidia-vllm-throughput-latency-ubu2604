# Results: 428 vLLM Inference Throughput & Latency

**Main goal:** Measure vLLM serving throughput and latency  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_143 · recorded 2026-11-16). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 26.04.1 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-16T20:05:25Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 03:18 · benchmark 00:01 · whole run 03:33
- **Source:** run 428_20261116_200525
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Output token throughput (output_token_throughput_tokens_sec) | 302.54411528526015 |
| 2 | Time To First Token, ms (ttft_p50_msec) | 13.12965014949441 |
| 3 | Time Per Output Token, ms (time_per_output_token_tpot_p50_msec) | 5.67242627342542 |
| 4 | Inter-token latency, ms (inter_token_latency_itl_p50_msec) | 5.642144940793514 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 99.11969816312194 |
<!-- /profile:smoke -->
