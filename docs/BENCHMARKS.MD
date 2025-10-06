
# Performance Benchmarks
---
## Methodology
All benchmarks run on AWS c6i.8xlarge (32 vCPUs, 64GB RAM) with Rust 1.75. Results represent 1000 iterations with outliers removed.

## Cryptographic Operations

### Kyber (Post-Quantum Key Exchange)
| Operation | Time (μs) | Operations/sec |
| :--- | :--- | :--- |
| Key Generation | 14.30 ± 0.02 | ~69,930 |
| Encapsulation | 13.99 ± 0.01 | ~71,480 |
| Decapsulation | 14.57 ± 0.01 | ~68,630 |

![Kyber Benchmarks](./IMAGES/benchmark_plot_crypto_latency.png)

### Dilithium (Post-Quantum Signatures)
| Operation | Time (μs) | Operations/sec |
| :--- | :--- | :--- |
| Sign 1KB Data | 70.54 ± 0.04 | ~14,175 |

## Message Bus Performance

| Operation | Time | Rate |
| :--- | :--- | :--- |
| Send 10,000 messages | 7.53 ms | ~1.33 million msg/sec |
| Subscribe agent | 882 ns | ~1.13 million ops/sec |
| Priority queue operations | 67.0 μs | ~14,925 ops/sec |

![Message Bus Throughput](./IMAGES/benchmark_plot_message_throughput.png)

## Analysis

These results demonstrate:
1.  **Cryptographic readiness:** Post-quantum security adds minimal overhead (~0.01ms per operation)
2.  **Massive scalability:** Message bus handles >1 million messages/second
3.  **Real-time capability:** Sub-microsecond latency enables agent collaboration at human conversation speed
The architecture provides enterprise-grade performance while maintaining security and flexibility.

