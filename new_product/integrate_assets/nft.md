<h1 align="center">Import NFT</h1>

In order to import NFT on Poly Bridge, please making sure that your source chain NFT contract can support `ERC721`, `ERC721Metadata` and `ERC721Enumerable` interfaces with the [ERC-721 standard](https://eips.ethereum.org/EIPS/eip-721).
Except for source chain NFT contract, you need to Develop and deploy the mapping NFT contracts on target chain . Here are the three steps to help you to complete the process. 

### Step1. Development for mapping NFT contract
- There ia a mapping the NFT contract [template](https://github.com/polynetwork/nft-contracts/tree/main/contracts/erc721_template) provided by Poly Network.
- The mapping contracts should support `ERC721`, `ERC721Metadata` and `ERC721Enumerable` interfaces with the [ERC-721 standard](https://eips.ethereum.org/EIPS/eip-721).
- The mapping contracts need to implement a minting interface. The method will be invoked by [NFTLockProxy](../../Core_Smart_Contract/Contract/NFTLockProxy.md) in Poly Network. Here is an example:

   ```solidity 
  function mintWithURI(address to, uint256 tokenId, string memory uri) external {
    require(!_exists(tokenId), "token id already exist");
    _safeMint(to, tokenId);
    _setTokenURI(tokenId, uri);
  }
  ```

  
### Step2. Information submission
- [Submit](https://docs.google.com/forms/d/e/1FAIpQLSfH1VcCAmdtjcQeCFjSXvYw7QS9MtsegzktyNmSvIPZzleSYg/viewform) your NFT information to the Poly Network team.
- Contact Poly Network via <a class="fab fa-discord" href= "https://discord.com/invite/y6MuEnq"></a>
- Waiting for feedback from Poly Network. We'll send you an email when everything is complete.

### Step3. Test 
- Click [here](https://bridge.poly.network/nft) and follow the [User Manual](../../Core_Smart_Contract/User_Manuals/NFT_Transaction.md) to test the NFT cross-chain transfer.
