# Smart Contract Auditing & Security Practice

This project is designed for auditing and improving the security of smart contracts using tools such as Slither and Echidna. It serves as a practice environment to identify vulnerabilities, such as reentrancy and oracle manipulation, in Solidity contracts.

## Overview

- **Auditing Tools:**  
  - **Slither:** A static analysis framework for Solidity to detect vulnerabilities.  
  - **Echidna:** A smart contract fuzzer for testing contract security and detecting issues such as brute-force attacks.

- **Project Contents:**  
  - **contracts/**: Contains sample Solidity contracts, some with intentional vulnerabilities for testing.  
  - **deploy/**: Deployment scripts for the contracts.  
  - **scripts/**: Contains additional scripts to interact with the contracts.

## Setup

### Download Docker Toolbox

Use the following command to download the Docker toolbox required for running tests:

   ```bash
   yarn toolbox
   ```

## Testing & Auditing

### Docker Fuzz Test

To run a fuzz test that searches for vulnerabilities (for example, contract passwords stored on-chain via brute-force attack), use:

   ```bash
   echidna /src/contracts/test/FuzzTest.sol --contract FuzzTest --config /src/contracts/test/config.yaml
   ```

### Running Slither

Before deploying any contracts, run Slither to perform a vulnerability test on the contracts in the `./contracts` directory:

   ```bash
   yarn slither
   ```

*Tip:* Ensure your Solidity compiler version matches the contracts. For example, to use version 0.8.7:

   ```bash
   solc-select use "0.8.7"
   ```

## Security Considerations

- **Common Attacks to Watch Out For:**  
  - **Reentrancy:** Ensure functions that send funds do not allow reentrant calls.  
  - **Oracle Manipulation:** Avoid centralized oracles for price information to prevent manipulation attacks.

- **Manual Auditing:**  
  In addition to automated tools, manually inspect contracts for vulnerabilities such as oracle manipulation or reentrancy patterns before deployment.

## Learning Outcomes

This project was developed as a practice exercise to:

- Gain hands-on experience with smart contract auditing tools like Slither and Echidna.
- Understand how to detect and mitigate common vulnerabilities in Solidity contracts.
- Learn best practices for secure smart contract development and deployment.

 

## Contact

For any questions or further discussion, please reach out via [alqeren1](https://github.com/alqeren1) or email [alqeren1@gmail.com](mailto:alqeren1@gmail.com).
