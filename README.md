# DegenToken

DegenToken is a simple ERC-20 token contract with a decentralized marketplace functionality. It allows the owner to mint and burn tokens, and also provides a way for the owner to sell items to buyers who can purchase them using the token.

## Contract Details

- **Name:** DegenToken (DGN)
- **Standard:** ERC-20
- **Inherits from:** OpenZeppelin's ERC20 and Ownable contracts

## Functions

### mint

Allows the owner to mint new tokens and add them to a specified address.

function mint(address to, uint256 amount) public onlyOwner

### burn

Allows any address to burn a specified amount of their own tokens.

function burn(uint256 amount) public

### transfer

Overrides the standard ERC-20 transfer function to include custom logic.

function transfer(address to, uint256 amount) public override returns (bool)

### sellItem

Allows the owner to list items for sale with a specified price and quantity.

function sellItem(string memory itemName, uint256 price, uint256 quantity) public onlyOwner

### buyItem

Allows any address to purchase items listed by the owner using their tokens. The purchased tokens are burned.

function buyItem(string memory itemName, uint256 quantity) public

## Events

### ItemPurchased

Emitted when a buyer successfully purchases an item.

event ItemPurchased(address indexed buyer, string item, uint256 price, uint256 quantity);
