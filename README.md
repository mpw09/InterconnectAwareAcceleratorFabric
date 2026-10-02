# Interconnect-Aware Heterogeneous Accelerator Fabric Architecture

## Status

**Planned systems research. Implementation, profiling and validation are not yet claimed.**

## Research problem

A better physical link matters only when communication lies on a workload critical path. This project will translate P02 physical-link service and P03 digital-endpoint behaviour into system-level consequences for a bounded heterogeneous accelerator workload.

The current research question is:

> When do improvements in link and endpoint behaviour improve distributed autoregressive inference, and when do compute, memory, injection bandwidth, placement or congestion dominate instead?

## Planned Core architecture

The intended Core is a bounded C++20 discrete-event/resource model containing:

- a workload dependency graph;
- compute and memory service;
- communication events;
- finite queues;
- initially fixed routing;
- P02 link-service inputs;
- P03 endpoint behaviour;
- causal readiness/completion;
- occupancy;
- offered, admitted and completed traffic; and
- latency, throughput, utilisation and tail metrics.

The leading workload direction is pipeline-parallel dense autoregressive inference / token generation. A small collective comparator remains conditional rather than adopted Core.

## Tooling

Core tooling is expected to include C++20, CMake, Linux, Python, analytical oracles, profile ingestion, uncertainty analysis and tests.

CUDA, Nsight Systems, Nsight Compute, NCCL and ASTRA-sim are conditional evidence paths. Their presence in the research plan is not a claim that GPU profiling, multi-GPU calibration or ASTRA-sim comparison has been executed.

## Claim boundaries

This repository does not claim a validated OLIX or NVIDIA system, measured optical workload results, a cycle-accurate GPU model, or a proprietary architecture replica.

P04 owns workload message serialization exactly once, dynamic queueing/backpressure, congestion, workload dependencies and system-level metrics. Empty directories represent planned work only.
