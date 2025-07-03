````markdown
# Securing O-RAN Equipment Using Blockchain-Based Supply Chain Verification

This repository contains the Python implementation of the **IEEE IWCMC 2025** paper  
**“Securing O-RAN Equipment Using Blockchain-Based Supply Chain Verification”**  
(<https://ieeexplore.ieee.org/document/11059692>). The simulation recreates the performance and security results presented in the paper, showing how blockchain technology can safeguard the Open Radio Access Network (O-RAN) supply chain.

---

## Paper Abstract
The Open Radio Access Network (O-RAN) architecture enables multi-vendor equipment integration, greatly improving flexibility and interoperability. Unfortunately, this openness also introduces supply-chain security vulnerabilities. Malicious actors might exploit weaknesses during production, distribution, or integration, causing data tampering, unauthorized access, or denial-of-service (DoS) attacks.

The paper proposes a **blockchain-based framework** that secures the O-RAN supply chain via a private permissioned blockchain ledger and cryptographic firmware authentication, guaranteeing equipment integrity and authenticity throughout the lifecycle.

---

## Implementation Overview
* **Quorum Blockchain Simulation** – permissioned network with IBFT 2.0 consensus  
* **Cryptographic Firmware Authentication** – hardware-security-module–style verification  
* **Smart Contract Simulation** – `EquipmentRegistry` & `IntegrationVerifier` contracts  
* **Network Topology** – manufacturers, integrators, and operators in a multi-vendor setting  
* **Performance Testing** – TPS, verification latency, consensus finality, etc.  
* **Security Validation** – firmware tampering, Sybil, and replay-attack scenarios  

---

## Requirements
* Python 3.8+  
* NumPy, Pandas, Matplotlib, Seaborn  
* Cryptography  
* tqdm  

---

## Installation & Usage
```bash
# Clone the repository
git clone https://github.com/yourusername/oran-blockchain-verification.git
cd oran-blockchain-verification

# (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the full simulation
python run_simulation.py

# Or explore via Jupyter Notebook
jupyter notebook oran_blockchain_simulation.ipynb
````

---

## Key Features

* **Blockchain Network Simulation** — nodes, transactions, blocks, IBFT 2.0
* **Firmware Authentication** — cryptographic hash verification (HSM simulation)
* **Smart Contracts** — `EquipmentRegistry` & `IntegrationVerifier` replicas
* **Performance Analysis** — TPS, latency, consensus-finality vs. network size
* **Security Testing** — tamper detection, Sybil resistance, replay-attack defense
* **Visualization** — reproduces graphs from the IWCMC 2025 paper

---

## Results

| Metric                     | 100 Nodes | 500 Nodes |
| -------------------------- | --------- | --------- |
| **Transaction Throughput** | 248 TPS   | 195 TPS   |
| **Verification Latency**   | 320 ms    | 620 ms    |
| **Consensus Finality**     | 1.2 s     | 2.5 s     |
| **Firmware-Tampering FNR** | 1.8 %     | —         |

These results confirm that the blockchain-based framework secures O-RAN supply chains while maintaining near-real-time performance.

---

## Code Structure

```
oran-blockchain-verification/
├── oran_blockchain_simulation.ipynb
├── run_simulation.py
├── simulation/
│   ├── blockchain.py
│   ├── firmware.py
│   ├── smart_contracts.py
│   ├── performance.py
│   └── visualization.py
├── results/
│   ├── stress_test_results.png
│   ├── ethereum_comparison.png
│   ├── security_analysis.png
│   └── simulation_summary.txt
├── requirements.txt
├── LICENSE
└── README.md
```

---

## Paper Citation

```bibtex
@INPROCEEDINGS{11059692,
  author    = {Mehrban, Ali and El Houda, Zakaria Abou and Moudoud, Hajar and Brik, Bouziane and Khoukhi, Lyes},
  title     = {Securing O-RAN Equipment Using Blockchain-Based Supply Chain Verification},
  booktitle = {2025 International Wireless Communications and Mobile Computing (IWCMC)},
  year      = {2025},
  pages     = {1570--1575},
  keywords  = {Wireless communication; Supply chains; Ecosystems; Authentication; Open RAN; Denial-of-service attack; Real-time systems; Blockchains; Telecommunications; Microprogramming; O-RAN; Supply Chain Verification; blockchain; firmware authentication; security},
  doi       = {10.1109/IWCMC65282.2025.11059692}
}
```

---

## Key Findings

1. **248 TPS** at 100 nodes demonstrates high throughput for permissioned chains.
2. Firmware-verification latency stays below **500 ms** up to \~300 nodes, enabling near-real-time validation.
3. Tampered-firmware detection achieves a **1.8 %** false-negative rate.
4. IBFT 2.0 consensus overhead becomes significant beyond \~500 nodes.
5. Quorum outperforms public Ethereum by **≈ 4.6× TPS** for this workload.
6. Quorum’s ledger is **≈ 40 % smaller** than Ethereum’s for equivalent data.

---

## License

Released under the **MIT License**. See the `LICENSE` file for details.

---

## Acknowledgments

* Authors of the IWCMC 2025 paper for their groundbreaking work
* O-RAN Alliance for promoting open standards
* Blockchain and security research community


