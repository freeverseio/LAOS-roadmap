# ERC-721 compatibility
We will analyze the implementation of a complete [ERC-721 standard](https://eips.ethereum.org/EIPS/eip-721), including its extensions, by introducing the ERC-721 node. This node will be connected to a LAOS ownership node and a LAOS evolution node to retrieve the necessary data.

The infrastructure of the nodes is depicted in the following diagram:

![**](./nodes-infrastructure.drawio.svg)

The ERC-721 standard includes the Non-Fungible Token Standard, the Metadata extension, and the Enumeration extension.


## Non-Fungible Token Standard
The ERC-721 Non-Fungible Token Standard includes the following functions and events:

- [**ownership node**] `event Transfer(address indexed _from, address indexed _to, uint256 indexed _tokenId)`: emitted when ownership of any NFT changes by any mechanism.
- [**ownership node**] `event Approval(address indexed _owner, address indexed _approved, uint256 indexed _tokenId)`: emitted when the approved address for an NFT is changed or reaffirmed.
- [**ownership node**] `event ApprovalForAll(address indexed _owner, address indexed _operator, bool _approved)`: emitted when an operator is enabled or disabled for an owner.
- [**ERC721 node**] `function balanceOf(address _owner) external view returns (uint256)`: returns the number of NFTs owned by a given address.
- [**ownership node**] `function ownerOf(uint256 _tokenId) external view returns (address)`: returns the owner of a given NFT.
- [**ownership node**] `function safeTransferFrom(address _from, address _to, uint256 _tokenId, bytes data) external payable`: transfers the ownership of an NFT from one address to another address. This function checks if the receiver is a smart contract and calls onERC721Received on it.
- [**ownership node**] `function safeTransferFrom(address _from, address _to, uint256 _tokenId) external payable`: transfers the ownership of an NFT from one address to another address.
- [**ownership node**] `function transferFrom(address _from, address _to, uint256 _tokenId) external payable`: transfers the ownership of an NFT from one address to another address.
- [**ownership node**] `function approve(address _approved, uint256 _tokenId) external payable`: changes or reaffirms the approved address for an NFT.
- [**ownership node**] `function setApprovalForAll(address _operator, bool _approved) external`: enables or disables approval for a third party to manage all of an owner's assets.
- [**ownership node**] `function getApproved(uint256 _tokenId) external view returns (address)`: gets the approved address for a single NFT.
- [**ownership node**] `function isApprovedForAll(address _owner, address _operator) external view returns (bool)`: checks if an address is an authorized operator for another address.

## Metadata extension

The ERC-721 Metadata extension includes the following functions:
 
- [**ownership node**] `function name() external view returns (string _name)`: returns the name of the NFT collection.
- [**ownership node**] `function symbol() external view returns (string _symbol)`: returns the symbol of the NFT collection.
- `function tokenURI(uint256 _tokenId) external view returns (string)`: returns the URI of a given asset.
    * [**ownership node**] returns an universal location to the evolution chain
    * [**evolution node**] returns an URL to the same node
    * [**ERC721 node**] returns an URL to the same node


## Metadata extension

The ERC-721 Enumeration extension includes the following functions:

- [**ERC721 node**] `function totalSupply() external view returns (uint256)`: returns the total count of valid NFTs tracked by the contract.
- [**ERC721 node**] `function tokenByIndex(uint256 _index) external view returns (uint256)`: returns the identifier for the NFT at the given index of all NFTs assigned to the contract.
- [**ERC721 node**] `function tokenOfOwnerByIndex(address _owner, uint256 _index) external view returns (uint256)`: returns the identifier for the NFT at the given index of all NFTs assigned to the owner.
