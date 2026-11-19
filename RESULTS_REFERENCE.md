# Results: 428 vLLM Inference Throughput & Latency

**Main goal:** Measure vLLM serving throughput and latency  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_148 · recorded 2026-11-19). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · Intel(R) Xeon(R) Platinum 8452Y · Ubuntu 26.04.1 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-19T16:13:28Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 05:53 · benchmark 00:02 · whole run 06:15
- **Source:** run 428_20261119_161328
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Output token throughput (output_token_throughput_tokens_sec) | 283.7216829568709 |
| 2 | Time To First Token, ms (ttft_p50_msec) | 24.827918998198584 |
| 3 | Time Per Output Token, ms (time_per_output_token_tpot_p50_msec) | 5.373212999741857 |
| 4 | Inter-token latency, ms (inter_token_latency_itl_p50_msec) | 5.247902998235077 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 106.56131798168644 |
<!-- /profile:smoke -->
