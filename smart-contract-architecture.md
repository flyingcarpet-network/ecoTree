# EcoTree Smart Contract Architecture Workflow

This file serves to outline the smart contract workflow for EcoTree's architecture.

![EcoTree Workflow](https://www.lucidchart.com/publicSegments/view/ba75b7df-b00c-4ec9-93c9-d6e5a05fdb2d/image.png)

The Asset Ownership Smart Contract serves to own each of the unique division NFT (ERC-721) forestry assets as well as store all of the parcelles.

When a new parcelle is created, it's name (string) is added to the `parcelles` mapping. The `Division` struct serves to store each of the NFT assets and their corresponding parcelle ids. Before a new division NFT can be owed by the Ownership Smart Contract (by creating a new instance of the Division struct), its parcelle name must exist in the `parcelles` mapping.

Upon creation, each of the division NFT assets must contain a hash of the assocaited data division's data in the `dataHash` field.
