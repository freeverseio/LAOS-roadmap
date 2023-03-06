## **LAOS Roadmap**

### **Goals and Objectives**

The LAOS Parachain aims to provide a secure and decentralized platform for the creation, ownership, and evolution of unique digital assets. The platform will utilize the Substrate framework and enable users to easily mint, trade, and evolve their assets. In addition, the LAOS Parachain will implement a robust governance system that will enable token holders to propose and vote on changes to the protocol.

---
### **Milestone 1 [0-3 months]**

The first milestone of the project aims to establish the basic infrastructure required for the development of 
the LAOS blockchain network within the next three months. The primary goals are to create the LAOS ownership 
chain as a parachain of Rococo and create the first LAOS evolution chain. A bidirection trustless bridge will 
be installed to enable cross chain communication allowing the ownership chain govern the evolution chain.


We will release:
- LAOS ownership chain node
- LAOS evolution chain node
- LAOS bidirectional bridge

#### **Deliverable 1**: 
The primary objective of the first deliverable is to bootstrap the project by creating and automating a test 
infrastructure focused on local testing, continuous integration, and continuous delivery. The goal is to 
establish the fundamental infrastructure upon which we will build the project's subsequent deliverables. 
To achieve this goal, we will release the LAOS ownership parachain node and the LAOS evolution chain node. 
Once we have completed the first deliverable, the LAOS ownership chain will be operational and connected to 
Rococo as a parachain, and the first evolution will be up and running as a solochain.

![](./relay_ownership_evolution.drawio.svg)
- [ownChain] release of LAOS ownership parachain node based on substrate based on [substrate parachain template](https://github.com/substrate-developer-hub/substrate-parachain-template)
- [ownChain] LAOS ownership chain is alive
- [ownChain] LAOS ownership chain connected to [Rococo](https://substrate.io/developers/rococo-network) as a parachain
- [evoChain] release of LAOS evolution chain node based on [substrate node template](https://github.com/substrate-developer-hub/substrate-node-template)
- [evoChain] LAOS evolution chain is alive 

#### **Deliverable 2**: 
The second deliverable is focused entirely on creating a trustless bridge between the LAOS evolution chain 
and the ownership chain. To achieve this, we will install an evolution chain light client in the ownership 
chain and initiate a bridge service between the two chains. Additionally, we will open the Grandpa-XCM 
channel from the evolution chain to the ownership chain.

![](./relay_ownership_evolution_bridge.drawio.svg)

- [ownChain] integrate the [solochain-parachain bridge](https://github.com/paritytech/solo-para-bridge-poc)
- [bridge] release of LAOS bridge
- [bridge] evolution -> ownership bridge up and running

#### **Deliverable 3**: 
The third deliverable will focus on enabling bidirectional communication of the LAOS chain through trustless 
bridges, allowing governance of the evolution chain from the ownership chain. To achieve this, we will remove 
the governance of the evolution chain and instead allow it to be governed by the ownership chain. 

![](./relay_ownership_evolution_duplexbridge.drawio.svg)

- [evoChain] integrate the [solochain-parachain bridge](https://github.com/paritytech/solo-para-bridge-poc)
- [evoChain] governance removed
- [ownChain] govern the evolution chains by XCM
- [bridge] ownership -> evolution bridge up and running

---
### **Milestone 2 [3-6 months]**
During Milestone 2 we will concentrate on implementing all aspects of livingassets. Our primary goals will include enabling LAOS to create collections, transfer livingassets, evolve the assets' metadata, generate proof, and verify assets metadata by Merkle proof. Furthermore, we will develop a layer of compatibility with the ERC721 standard.

#### **Deliverable 4**:
The forth deliverable focuses on the business logic for creating collections and their evolution.

To achieve this, we will develop a **living asset ownership pallet** based on the [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts)  and integrate it into the ownership chain. Additionally, we will develop a **living asset evolution pallet** and integrate it into the evolution chain. This will allow us to create and evolve collections.

- development of livingasset ownership pallet based on [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts) 
- [ownChain] integration living asset ownership pallet  
- development of livingasset evolution pallet
- [evoChain] integration of living asset evolution pallet
#### **Deliverable 5**:
In order to achieve compatibility with the ERC721 standard, we will develop the necessary services on our fifth deliverable. This will involve introducing the [LAOS ERC721 node](./erc721Capabilities/README.md), which will provide an Ethereum JSON-RPC api. As a result, Ethereum wallets such as Metamask will be able to interact with the living assets.

![](./erc721Capabilities/nodes-infrastructure.drawio.svg)

- release ERC721 node 
#### **Deliverable 6**:
This deliverable will be focused on the generation of proof of existence of the metadata of the assets. Evolution chain will be able to generate the proof and the ownership chain will be in charge of verify it.

- [evoChain] generate proof of existence of assets metadata
- [ownChain] verify proof of existence of assets metadata

---
### **Milestone 3 [6-9 months]**
During the final stage of development, we will prioritize cross-chain communication with sibling parachains, conduct a thorough code audit, and make preparations for the stable release of the code. We will also create a dynamic asset marketplace to demonstrate the system's capabilities. Finally, we will enable staking and eliminate the sudo pallet.

#### **Deliverable 7**:
In order to open the economy of the LAOS token we will implement XC-20 protocol for reserve transfer. We also activate the XCMv3 primitives to control the livingassets from sybling parachain. Additionally we will create the second LAOS evolution chain and will integrate a way to move a collection from the first evolution chain to the new one.

- [ownChain] XC-20 protocol
- [ownChain] remote transfer of living assets

#### **Deliverable 8**:
- [frontend] creation of living asset marketplace based on [substrate frontend template](https://github.com/substrate-developer-hub/substrate-front-end-template)
- [ownChain] staking enabled
- audit of the code
#### **Deliverable 9**:
In the final deliverable we will release the first stable version of the software and we'll remove the sudo pallet from the ownership chain.

- [ownChain] remove sudo pallet
- stable release of LAOS ownership node
- stable release of LAOS evolution node
- stable release of ERC721 node
- stable release of the bridge
---
### Notes

- The LAOS team follows Scrum methodology, conducting sprint cycles lasting two weeks. Regular updates on sprint progress are shared with the Substrate Builders Program team during sprint review meetings.
- The Substrate Builders Program team is invited to participate in these meetings to offer feedback and guidance on project development.
- A new release of the LAOS Parachain will be proposed at the end of each sprint, subject to stakeholder approval. 
- All software developed as part of the LAOS Parachain project will be released as open-source under an appropriate license.