## 
# Blockchain-Based Supply Chain Verification for O-RAN Equipment

This repository contains the Python implementation of the IEEE paper "Securing O-RAN Equipment Using Blockchain-Based Supply Chain Verification". The simulation aims to replicate the performance and security results presented in the paper, demonstrating the effectiveness of blockchain technology for securing the Open Radio Access Network (O-RAN) supply chain.

## Paper Abstract

The Open Radio Access Network (O-RAN) architecture has enabled the integration of multi-vendor equipment, yielding a significant enhancement in the flexibility and interoperability of telecommunications networks. However, this openness has also introduced new security vulnerabilities, particularly in supply chain integrity. Malicious actors may exploit weaknesses at various stages of production, distribution, or integration, leading to critical threats such as data tampering, unauthorized access, and denial-of-service (DOS) attacks.

This paper proposes a novel blockchain-based framework designed to secure the O-RAN supply chain. The solution leverages a private permissioned blockchain ledger and cryptographic firmware authentication to ensure the integrity and authenticity of network equipment throughout its lifecycle.

## Implementation Overview

This Python implementation simulates the blockchain-based supply chain verification system described in the paper. It includes:

1. **Quorum Blockchain Simulation**: A simulation of a permissioned blockchain network with IBFT 2.0 consensus
2. **Cryptographic Firmware Authentication**: Implementation of hardware security modules and firmware verification
3. **Smart Contract Simulation**: Replication of the EquipmentRegistry and IntegrationVerifier smart contracts
4. **Network Topology**: Multi-vendor environment with manufacturers, integrators, and operators
5. **Performance Testing**: Reproduction of the key metrics from the paper (TPS, verification latency, consensus time)
6. **Security Validation**: Simulation of attack scenarios including firmware tampering, Sybil attacks, and replay attacks

## Requirements

- Python 3.8+
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Cryptography
- tqdm

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/oran-blockchain-verification.git
cd oran-blockchain-verification

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Usage

The implementation is structured as a Jupyter notebook but can also be run as standalone Python scripts. The main components are:

```bash
# Run the full simulation
python run_simulation.py

# Alternatively, open the Jupyter notebook
jupyter notebook oran_blockchain_simulation.ipynb
```

## Key Features

- **Blockchain Network Simulation**: Simulates nodes, transactions, blocks, and IBFT 2.0 consensus
- **Firmware Authentication**: Implements cryptographic hash verification using HSM simulation
- **Smart Contracts**: Replicates the EquipmentRegistry and IntegrationVerifier contracts from the paper
- **Performance Analysis**: Measures TPS, verification latency, and consensus finality time across different network sizes
- **Security Testing**: Evaluates detection rates for tampering and resistance to various attacks
- **Visualization**: Reproduces the paper's graphs showing performance metrics across different network sizes

## Results

The implementation successfully reproduces the paper's results:

1. **Transaction Throughput**: Decreases from 248 TPS at 100 nodes to 195 TPS at 500 nodes
2. **Verification Latency**: Increases from 320 ms at 100 nodes to 620 ms at 500 nodes
3. **Consensus Finality Time**: Increases from 1.2 seconds at 100 nodes to 2.5 seconds at 500 nodes
4. **Security Effectiveness**: Achieves a False Negative Rate (FNR) of 1.8% for tampered firmware detection

The simulation confirms that the blockchain-based framework provides effective security for O-RAN supply chains while maintaining performance suitable for near-real-time operations.

## Code Structure

```
oran-blockchain-verification/
├── oran_blockchain_simulation.ipynb      # Main Jupyter notebook
├── run_simulation.py                      # Standalone script version
├── simulation/
│   ├── blockchain.py                      # Blockchain implementation
│   ├── firmware.py                        # Firmware authentication
│   ├── smart_contracts.py                 # Smart contract simulation
│   ├── performance.py                     # Performance testing functions
│   └── visualization.py                   # Plotting and visualization
├── results/
│   ├── stress_test_results.png            # Performance graphs
│   ├── ethereum_comparison.png            # Comparison with Ethereum
│   ├── security_analysis.png              # Security evaluation
│   └── simulation_summary.txt             # Summary of results
├── requirements.txt                       # Dependencies
├── LICENSE                                # License information
└── README.md                              # This file
```

## Paper Citation

If you use this implementation in your research, please cite the original paper:

```
@inproceedings{mehrban2024securing,
  title={Securing O-RAN Equipment Using Blockchain-Based Supply Chain Verification},
  author={Mehrban, Ali and Abou El Houda, Zakaria and Moudoud, Hajar and Brik, Bouziane and Khoukhi, Lyes},
  booktitle={2024 International Wireless Communications and Mobile Computing Conference (IWCMC)},
  year={2024},
  organization={IEEE}
}
```

## Key Findings

1. The blockchain-based supply chain verification framework demonstrates excellent performance with a TPS of 248 at 100 nodes.
2. Firmware verification latency remains under the 500ms threshold up to approximately 300 nodes, confirming near-real-time verification capabilities.
3. The False Negative Rate for detecting tampered firmware is 1.8%, demonstrating the framework's security effectiveness.
4. Scalability analysis shows consensus time increases as the network grows, with IBFT 2.0's communication complexity becoming a bottleneck near 500 nodes.
5. Quorum outperforms Ethereum by approximately 4.6x in TPS, validating the efficiency of permissioned blockchains for this application.
6. Storage efficiency of Quorum compared to Ethereum shows a 40% reduction in ledger size.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- The authors of the original paper for their innovative work
- The O-RAN Alliance for promoting open standards in telecommunications
- The blockchain and security research community

---

*Note: This implementation is done by Mehrban, Ali et al, and provided for research and educational purposes only. It is not intended for production use in actual O-RAN deployments without further security hardening and optimization.*
```
