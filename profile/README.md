# QubitOS

**Open-Source Quantum Control Kernel**

Pulse optimization and hardware abstraction for quantum computing research.

QubitOS sits between your compiler output and the hardware — it optimizes control pulses against current calibration data, schedules them with constraint-aware parallelism, and tracks error budgets across sequences.

## Repositories

| Repository | Description | Language |
|:-----------|:------------|:---------|
| **[qubit-os-core](https://github.com/qubit-os/qubit-os-core)** | GRAPE pulse optimization, scheduling, calibration, benchmarking, CLI | Python |
| **[qubit-os-hardware](https://github.com/qubit-os/qubit-os-hardware)** | Hardware Abstraction Layer — gRPC interface to quantum backends | Rust |
| **[qubit-os-proto](https://github.com/qubit-os/qubit-os-proto)** | Protocol Buffer definitions for all IPC contracts | Protobuf |

## Quick Start

```bash
pip install qubitos
```

```python
from qubitos.pulsegen import generate_pulse

result = generate_pulse(gate="CZ", num_qubits=2, duration_ns=80, target_fidelity=0.999)
print(f"Fidelity: {result.fidelity:.4f}")  # → 0.9983
```

## Current Release: v0.4.0

**Active Calibration & GRAPE-in-Rust**

- Real-time drift monitoring with 5 severity levels
- Async recalibration loop: measure → detect → recalibrate → resume
- Rust GRAPE optimizer: **10.4x speedup** over Python
- Provenance Merkle tree records drift events and recalibrations
- Multi-qubit GRAPE, pulse scheduling, parametric gates, Clifford tableaux
- 982 Python tests · 233 Rust tests · 92% coverage · Apache 2.0

---

📖 **[Documentation](https://qubit-os.github.io/qubit-os-core/)** · 🌐 **[Website](https://qubit-os.github.io)** · 📋 **[Contributing](https://github.com/qubit-os/qubit-os-core/blob/main/CONTRIBUTING.md)**
