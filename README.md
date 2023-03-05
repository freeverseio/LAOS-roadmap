## **LAOS Roadmap**

### **Goals and Objectives**

The LAOS Parachain aims to provide a secure and decentralized platform for the creation, ownership, and evolution of unique digital assets. The platform will utilize the Substrate framework and enable users to easily mint, trade, and evolve their assets. In addition, the LAOS Parachain will implement a robust governance system that will enable token holders to propose and vote on changes to the protocol.
### **Milestone 1 [0-3 months]**

The focus of this milestone is to develop the LAOS ownership chain as a parachain, using the AURA protocol for block production. We will implement the business logic for creating collections and changing asset ownership, while establishing the necessary infrastructure for continuous integration/continuous deployment (CI/CD) and testing network. To ensure the reliability and functionality of the LAOS parachain, we will connect a testing network to the Rococo relay chain for further testing and development.


#### **Deliverable 1**: 
The primary objective of the first deliverable is to bootstrap the project by creating and automating a test infrastructure focused on local testing, continuous integration, and continuous delivery.

The goal is to establish the fundamental infrastructure upon which we will build the project's subsequent deliverables.

To achieve this goal, we will release the LAOS ownership parachain node and the LAOS evolution chain node. Once we have completed the first deliverable, the LAOS ownership chain will be operational and connected to Rococo as a parachain, and the first evolution will be up and running as a solochain.

![](./relay_ownership_evolution.drawio.svg)
- [ownChain] release of LAOS ownership parachain node based on substrate based on [substrate parachain template](https://github.com/substrate-developer-hub/substrate-parachain-template)
- [ownChain] LAOS ownership chain is alive
- [ownChain] LAOS ownership chain connected to [Rococo](https://substrate.io/developers/rococo-network) as a parachain
- [evoChain] release of LAOS evolution chain node based on [substrate node template](https://github.com/substrate-developer-hub/substrate-node-template)
- [evoChain] LAOS evolution chain is alive 

#### **Deliverable 2**: 
The second deliverable is focused entirely on creating a trustless bridge between the LAOS evolution chain and the ownership chain. To achieve this, we will install an evolution chain light client in the ownership chain and initiate a bridge service between the two chains. Additionally, we will open the Grandpa-XCM channel from the evolution chain to the ownership chain.

![](./relay_ownership_evolution_bridge.drawio.svg)

- [ownChain] integrate the [solochain-parachain bridge](https://github.com/paritytech/solo-para-bridge-poc)
- [bridge] up and running

#### **Deliverable 3**: 
The third deliverable focuses on the business logic for creating collections and their evolution. We will build on the already existent [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts)  provided by substrate to create a specific implementation. Additionally, we will integrate asset metadata evolution in the evolution chain.

To achieve this, we will develop a living asset ownership pallet based on the nfts pallet and integrate it into the ownership chain. Additionally, we will develop a living asset evolution pallet and integrate it into the evolution chain. This will allow us to create and evolve collections.

- development of livingasset ownership pallet based on [nfts pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts) 
- [ownChain] integration living asset ownership pallet  
- development of livingasset evolution pallet
- [evoChain] integration of living asset evolution pallet

### **Milestone 2 [3-6 months]**
The main objective of this milestone is to develop the LAOS Evolution Chain (EVOChain) node and integrate it with the existing Ownership Chain using a trustless bridge, thus creating the first LAOS evolution chain.

To achieve this goal, we will focus on implementing the necessary business logic to support asset evolution. By the end of this milestone, our aim is to have a fully functional and secure LAOS evolution chain integrated with the LAOS parachain in ROCOCO, which will allow for seamless asset evolution.

#### **Deliverable 4**:
#### **Deliverable 5**:
#### **Deliverable 6**:

### **Milestone 3 [6-9 months]**
This milestone aims to integrate the LAOS parachain with the ROCOCO relay chain. The XC-20 protocol will be integrated to facilitate transfer of the LAOS token to sibling parachains. Publication of the whitepaper.

![](./erc721Capabilities/nodes-infrastructure.drawio.svg)

#### **Deliverable 7**:
#### **Deliverable 8**:
#### **Deliverable 9**:
---
### Notes

- The LAOS team follows Scrum methodology, conducting sprint cycles lasting two weeks. Regular updates on sprint progress are shared with the Substrate Builders Program team during sprint review meetings.
- The Substrate Builders Program team is invited to participate in these meetings to offer feedback and guidance on project development.
- A new release of the LAOS Parachain will be proposed at the end of each sprint, subject to stakeholder approval. 
- All software developed as part of the LAOS Parachain project will be released as open-source under an appropriate license.