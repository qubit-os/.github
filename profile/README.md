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

## Current Release: v0.3.0

- Multi-qubit GRAPE optimization (n ≤ 5 qubits)
- Pulse scheduling with constraint system and crosstalk avoidance
- Parametric gates: fSim (Google), cross-resonance (IBM)
- Symplectic Clifford tableaux for multi-qubit randomized benchmarking
- Error budgets with cumulative fidelity prediction
- 947 tests · 91% coverage · Apache 2.0

---

📖 **[Documentation](https://qubit-os.github.io/qubit-os-core/)** · 🌐 **[Website](https://qubit-os.github.io)** · 📋 **[Contributing](https://github.com/qubit-os/qubit-os-core/blob/main/CONTRIBUTING.md)**
