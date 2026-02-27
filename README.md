# Blockchain-Based Voting System

A district-based blockchain voting simulation built on a three-tier architecture, designed to assess scalability and fairness in large-scale electoral scenarios. A hierarchical smart contract architecture is implemented
comprising an election orchestrator and autonomous district contracts, operating through a structured five-phase lifecycle from
election setup to result verification.

This system simulates score voting, a method that allows voters to assign numerical scores to candidates, enabling more nuanced and equitable outcomes compared to traditional voting mechanisms. Virtual voting agents model diverse voter behavior across configurable districts and population sizes.

Inspired by https://skemman.is/bitstream/1946/31161/1/Research-Paper-BBEVS.pdf.


## System Architecture

The system implementation follows a three-tier architecture comprising
a frontend user interface, a Python-based simulation server and
smart contracts deployed on blockchain infrastructure.

The Python
backend integrates virtual voting agents that simulate diverse voter
behavior. These agents operate within score voting scenarios, the
most promising voting method that allows for more fair and versatile outcomes by enabling voters to assign numerical scores to
candidates.

The system utilizes Solidity for smart contract development,
Hardhat for blockchain development and testing, Python with
Web3.py for blockchain interaction and agent orchestration, and
standard web technologies for the user interface. Smart contracts
implement the core voting logic, while the Python server coordinates agent behavior and blockchain communication.

The frontend interface allows users to configure simulation parameters, enabling systematic testing scenarios. The system measures scalability performance through gas consumption analysis
and execution time evaluation across different voter population
sizes and number of districts. This architecture enables the assessment of how district-based blockchain voting systems perform
under varying load conditions and voter behaviors, providing insights into practical deployment scalability for large-scale electoral
scenarios.


## Prerequisites

- **Python 3.10+**
- **Node.js (v18+)**
- **npm (Node Package Manager)**

## Setup & Run Instructions

**1. Clone the Repository**

```sh
git clone https://github.com/zachathanasiadis/blockchain-voting-system.git
cd blockchain-voting-system
```

**2. Python Environment Setup**

- Install Python dependencies

```sh
pip install -r requirements.txt
```



**3. Node.js & Hardhat Setup**

- Install Hardhat and compile the smart contracts

```sh
npm install --save-dev hardhat
npm install
npx hardhat compile
```

- Start a local Hardhat node

```sh
npx hardhat node
```

**4. FastAPI Backend Setup**

- Run the FastAPI server

```sh
cd app
uvicorn server:app --reload
```

The API of the app will be available at: [http://127.0.0.1:8000](http://127.0.0.1:8000).

**5. Running Experiments**

- Open [`index.html`](app/index.html) or [http://127.0.0.1:8000](http://127.0.0.1:8000) for the UI.
- Use the `/election` endpoint to run election simulations.

**To run the simulation used for the evaluation execute:**
```
npx hardhat test test/scaling-experiments-par.js
```