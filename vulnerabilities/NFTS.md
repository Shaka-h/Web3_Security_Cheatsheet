There has to be a limitation on NFT minting to maintaing the rarity feature
To address the issue, consider implementing one or more of the following:

1. **Mint Cap per Player**: Limit how many eggs each address can mint per game session.
2. **Global Supply Cap**: Set a hard cap on the total number of eggs that can exist.
3. **Cooldown Periods**: Enforce a delay (e.g. 30 seconds) between `searchForEgg()` calls per user.
4. **Dynamic Difficulty**: Reduce `eggFindThreshold` as more eggs are minted, to slow inflation.
5. **Require Payment or Staking**: Make users pay a small fee or stake tokens to search, deterring spam.


## _mint(to, tokenId) VS _safeMint(to, tokenId);

`_mint` function directly, which does not check for the safety of minting tokens to arbitrary addresses or addresses that may not be able to handle the NFT. 
The proper function to use is `safeMint`, which ensures that tokens are minted safely to addresses that can accept them.

**Impact**

* Token Loss: If an NFT is minted to a contract address that cannot handle the token (e.g., a contract that does not implement the IERC721Receiver interface), the minted token may be lost.

* Security Risks: The direct use of \_mint exposes the contract to potential issues with minting to malicious or invalid addresses, which could have unforeseen consequences.

* Reduced Interoperability: The absence of safe checks limits the contract's compatibility with other applications or contracts that expect NFTs to be safely transferable.


## `transferFrom` to transfer NFTs, VS `safeTransferFrom` 
`transferFrom` to transfer NFTs, which does not verify if the recipient can safely receive ERC721 tokens. This could result in NFTs being irreversibly locked in contracts that do not support ERC721, leading to asset loss.
`safeTransferFrom` instead adds a safety mechanism by implementing `onERC721Received`: it checks if the recipient (if a contract) correctly implements the ERC721 receiver interface. If not, the transaction reverts, preventing the transfer and loss of the NFT.

## Impact
