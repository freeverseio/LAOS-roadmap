# **LAOS Roadmap**

The LAOS Parachain aims to provide a secure, decentralized and highly scalable platform for the creation, ownership, and evolution of unique digital assets. From a high-level technical perspective, the platform will consist of a main Parachain that manages the ownership of the assets (the **ownChain**), connected via trustless bridges to multiple chains that manage the minting and evolution of the assets' attributes (the **evoChains**).

The platform will utilize the Substrate framework and enable users to easily mint, trade, and evolve their assets. In addition, the LAOS Parachain will implement a robust governance system that will enable token holders to propose and vote on changes to the protocol.

---
## Milestone 1 [months 0-3]

The first milestone of the project aims to establish the basic infrastructure required for the development of 
the LAOS blockchain network within the subsequent three months. The primary goals are to create the LAOS ownership 
chain (**ownChain**) as a parachain of Rococo, and create the first LAOS evolution chain (**evoChain**).A bi-directional trustless bridge will 
be installed to enable cross chain communication, allowing the ownership chain to govern the evolution chain.

At the end of this milestone, we shall have released:
- LAOS ownership chain node
- LAOS evolution chain node
- LAOS bidirectional bridge

The following are the 3 main deliverables of Milestone 1.

### Deliverable 1: 
The primary objective of the first deliverable is to bootstrap the project by creating and automating a test 
infrastructure focused on local testing, continuous integration, and continuous delivery. The goal is to 
establish the fundamental infrastructure upon which we will build the project's subsequent deliverables. 
To achieve this goal, we will release the LAOS ownership parachain node and the LAOS evolution chain node. 
After completion of this deliverable, the LAOS ownership chain will be operational and connected to 
Rococo as a parachain, and the first evoChain will be up and running as a solochain.

![](./relay_ownership_evolution.drawio.svg)
- [ownChain] release of LAOS ownership parachain node based on [substrate parachain template](https://github.com/substrate-developer-hub/substrate-parachain-template)
- [ownChain] LAOS ownership chain is alive
- [ownChain] LAOS ownership chain connected to [Rococo](https://substrate.io/developers/rococo-network) as a parachain
- [evoChain] release of LAOS evolution chain node based on the [substrate node template](https://github.com/substrate-developer-hub/substrate-node-template)
- [evoChain] LAOS evolution chain is alive 

### Deliverable 2: 
The second deliverable is focused entirely on creating a trustless bridge between the LAOS evolution chains
and the ownership chain. To achieve this, we will install an evolution chain light client in the ownership 
chain and initiate a bridge service between the two chains. Additionally, we will open the Grandpa-XCM 
channel from the evolution chain to the ownership chain.

![](./relay_ownership_evolution_bridge.drawio.svg)

- [ownChain] integrate the [solochain-parachain bridge](https://github.com/paritytech/solo-para-bridge-poc)
- [bridge] release of LAOS bridge
- [bridge] evolution -> ownership bridge up and running

### Deliverable 3: 
The third deliverable will focus on enabling bidirectional communication of the LAOS chain through trustless 
bridges, allowing governance of the evolution chain from the ownership chain. To achieve this, we will remove 
the governance of the evolution chain and instead allow it to be governed by the ownership chain. 

![](./relay_ownership_evolution_duplexbridge.drawio.svg)

- [evoChain] integrate the [solochain-parachain bridge](https://github.com/paritytech/solo-para-bridge-poc)
- [evoChain] governance removed
- [ownChain] govern the evolution chains by XCM
- [bridge] ownership -> evolution bridge up and running

---
## Milestone 2 [months 3-6]
During Milestone 2 we will concentrate on implementing the core features of Living Assets. Our primary goals will include enabling LAOS to create collections, transfer Living Assets, evolve the assets' metadata, generate proofs, and verify assets metadata via provision of Merkle proofs. THe compatibility layer with the ERC721 standard will also be integrated.

At the end of this milestone, we shall have released:
- LAOS ERC721 node

The following are the 3 main deliverables of Milestone 2.

### Deliverable 1:
This deliverable will focus on the business logic for creating collections and managing their evolution, in manners that can be verifiable from the ownership chain.

To achieve this, we will develop a **Living Assets ownership pallet** based on the [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts) and integrate it into the ownership chain. Additionally, we will develop a **Living Assets evolution pallet** and integrate it into the evolution chain. This will allow the creation and evolution of collections.

- development of Living Assets ownership pallet based on [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts) 
- [ownChain] integration Living Assets ownership pallet  
- development of Living Assets evolution pallet
- [evoChain] integration of Living Assets evolution pallet

### Deliverable 2:
This deliverable will focus on the development of the necessary services to provide compatibility with the ERC721 standard. This will involve introducing the [LAOS ERC721 node](./erc721Capabilities/README.md), which will provide an Ethereum JSON-RPC API. As a result, Ethereum wallets such as Metamask, as well as ayn DApp already familiarized with EVM-compatible blockchains, will be able to interact with Living Assets.

![](./erc721Capabilities/nodes-infrastructure.drawio.svg)

- release ERC721 node 

### Deliverable 3:
This deliverable will focus on the generation of proofs of existence for the metadata of the assets evolved in evoChains. Anyone with access to evoChain data will be able to generate such proofs and verify them on-chain in the ownership chain.

- [evoChain] generate proof of existence of assets metadata
- [ownChain] verify proof of existence of assets metadata

---
## Milestone 3 [months 6-9]

During the final stage of development, we will prioritize cross-chain communication with sibling parachains, conduct a thorough code audit, and make preparations for the stable release of the code. We will also create a dynamic asset marketplace to demonstrate the system's capabilities. Finally, we will enable staking and transition from sudo to a more decentralized governance system. 

At the end of this milestone, we shall have released:
- LivingAssets market

The following are the 3 main deliverables of Milestone 3.

### Deliverable 1:
In order to open the economy of the LAOS token we will implement XC-20 protocol for reserve transfer. We also activate the XCMv3 primitives to control Living Assets from sibling parachains. Additionally we will create the second LAOS evolution chain and integrate means to move collections among evoChains.

- [ownChain] XC-20 protocol
- [ownChain] remote transfer of Living Assets

### Deliverable 2:
- [frontend] creation of Living Assets marketplace based on [substrate frontend template](https://github.com/substrate-developer-hub/substrate-front-end-template)
- [ownChain] staking enabled
- code audit

### Deliverable 3:
In the final deliverable we will release the first stable version of the software and remove the sudo pallet from the ownership chain.

- [ownChain] remove sudo pallet
- stable release of LAOS ownership node
- stable release of LAOS evolution node
- stable release of ERC721 node
- stable release of the bridge

---

## Notes

- The LAOS team follows the Scrum methodology, conducting sprint cycles lasting two weeks. Regular updates on sprint progress can be shared with the Substrate Builders Program team during sprint review meetings.
  
- All software developed as part of the LAOS Parachain project will be released as open-source under an appropriate license.