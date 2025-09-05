## Experiment No. 5

### 1. Aim:

Chaincode deployment in Hyperledger Fabric

### 2. Theory:

-   Hyperledger Fabric is an open source blockchain framework hosted by
    the Linux Foundation.\
-   It is designed for developing enterprise-level blockchain
    applications.

### Key Features:

1.  Permissioned network: Fabric supports networks where permissioned
    participants are known and must authenticate.\
2.  Modular architecture: It is highly modular allowing for
    customizability and plug & play components.\
3.  Smart Contracts: Fabric uses smart contracts called "chaincode"
    written in languages like Go or Node.js for flexibility and
    performance.\
4.  Access Control: Fabric provides building blockchains solutions.\
5.  Deployment of Hyperledger Fabric.

### Steps:

6.  Network setup: Define the network architecture including members of
    organizations, peers, and consensus mechanism.\
7.  Membership services: Certificate authority for each organization to
    manage identities.\
8.  Chaincode install: Install the chaincode on the organizations that
    will participate.\
9.  Chaincode development: Develop and package the chaincode in a proper
    format.

### Fabric Network Components:

-   **Peer nodes**: Execute chaincode, access ledger data, endorse
    transactions, and interface with applications.\
-   **Orderer nodes**: Ensure the consistency of the blockchain and
    deliver endorsed transactions to peers.\
-   **Membership Service Providers (MSPs)**: Implemented as Certificate
    Authorities, managing X.509 certificates for member authentication.

Hyperledger Fabric supports different consensus algorithms, with
Practical Byzantine Fault Tolerance (PBFT) being the most common.

### 4. Conclusion:

A blockchain-based voting system offers a potential solution to many of
the issues associated with traditional voting systems.
