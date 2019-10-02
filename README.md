# EcoTree
This repository serves to document EcoTree's blockchain integration.

![EcoTree Workflow](https://raw.githubusercontent.com/flyingcarpet-network/ecoTree/208b0ef5ad237d6004f54b3500662b0bf15e4518/ecotree-workflow.png)

The architecture is split into front-end and back-end. The back-end consists of EcoTree's existing SQL database which provides the raw data fields to the front-end, and a smart-contract layer for tracking each of EcoTree's forest "division" assets (each one tracked by a hash of its data). This smart-contract layers serves to provide both immutability and transparency to EcoTree's data management processes. Each individual "division" asset is stored as a ERC-721 Non-Fungible Token (or NFT), owned by the Asset Ownership Contract.

The front-end architecture functions to combine both the raw SQL data for display with the data-integrity reassurances provided by the smart-contract layer. The assets are displayed and created via two different React-based web3-enabled applications. These applications are in turn displayed via HTML iFrames inside EcoTree's existing web application. The asset explorer application is used to view "division" asset information (SQL data verified via the web3 integration). The asset creation application is used, on the other hand, to create new "division" assets. Data is entered, signed via MetaMask, and sent to the smart-contract for the creation of a new NFT. The new asset's NFT is only minted if the creator's address is marked as a whitelisted administrative address inside of the Asset Ownership Contract.

For a more detailed assessment of the planned database and smart contract architecture, see the [Database Structure file](https://github.com/flyingcarpet-network/ecoTree/blob/master/database-structure.md).
