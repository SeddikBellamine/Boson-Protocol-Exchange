# Boson-protocol-exchange

Boson Protocol is advancing the world of commerce by enabling enterprises, organisations, and customers to bridge the divide between digital decentralized technologies and the transfer and trade of physical goods. Our vision is for Boson to become the basic plumbing for dCommerce and its data on the emerging decentralized web, where the value captured is distributed equitably between token holders and protected from capture by a single centralized entity. Read more about us here: https://bosonprotocol.io/

# Design

The Idea is to create and deploy two smart contracts, the first is marketplaceagent that will handle listings(items), orders ... and the second will be about the escrow and will play the role of completing orders and holding funds until the buyer complete the order.
![alt text](https://i.ibb.co/z46Jt8S/diagrams.png)

# Tools used for the implementation of the MVP

- Web3 1.0: Provides a JavaScript API for Ethereum blockchains by implementing the Ethereum JSON RPC API; it allows frontend web applications to interact with blockchains.
- Ganache: Ethereum blockchain JavaScript implementation which runs in-memory; it removes the need for a local blockchain client
  for local testing and provides additional tools to aid in development of smart contracts.
- Truffle: Part of Ethereum development framework which provides a compilation, testing and deployment pipeline for Dapp developers.

- MetaMask: Extension for the Chrome web browser that enables interaction with the Ethereum blockchain, as required for the use
  of Dapps.
- NodeJS: Provides a development framework for Truffle and enables use of NPM, the NodeJS package manager, for the installation of JavaScript dependencies

# Test Setup

1. Run the Ganache desktop client
2. Inside the truffle-config.js, ensure that the development network settings are correctly pointing to the local IP and the port specified by Ganache, which is by default 7545.
3. From the command line inside the project folder, run “truffle compile” then “truffle migrate” To compile and migrate the solidity smart contracts to the running local in-memory blockchain provided by Ganache.
4. From the command line inside the project folder, run “npm run dev” Which will start the web server and automatically open a browser to the index page. if you face issues with node modules run npm install or install missing modules manually
5. Install Metamask and Open it.
6. If MetaMask is not already connected to the ganache instance Choose “Restore from seed phrase” and copy the Mnemonic from the Ganache client along with a password of your choosing.
7. If MetaMask does not already have the local network available in the drop down at the top left, then choose “Custom RPC” and enter a name of the network of your choice then enter http://localhost:#### replacing “####” with the correct port (which is by default 7545 for the desktop client) and enter the chain id as 1337 for ganache.
8. Ensure that you have 4 accounts available within MetaMask using the account selection menu to test with the problem input.
9. Refresh the browser page and then the web app will demand consent to use your metamask accounts, approve it and Ethereum Status panel should display the current account address, balance and the ID of the connected network.

# Uses cases done:

- As a user I can list items for sale with a name and price in Ether.
- As a user I can browse existing listings(items) for sale.
- As a user I can order an available listing.
- As a user I can fund an escrow for the purchase of a listing.
- As the buyer of a listing, I can complete the linked escrow and confirm the receipt of the item.
- As a seller, my Ethereum account is funded with the proceeds of a sale once the buyer has completed/finalised the linked escrow, once the listed goods have exchanged possession.
- As the buyer of a listing, I can complain the linked escrow should an issue with the exchange of physical goods occur.

# Input:

You can test the Dapp with this input:

Buyer 1 | Credit | 20
Buyer 2 | Credit | 40
Seller 1 | Offer | Coffee, 3
Seller 2 | Offer | T-Shirt, 5

Seller 1 | Offer | Tea, 2.5
Seller 1 | Offer | Cake, 3.5
Seller 2 | Offer | Shorts, 8
Seller 2 | Offer | Hoody, 12
Buyer 1 | Order | T-Shirt
Buyer 1 | Deposit | 10
Buyer 2 | Order | Hoody
Buyer 1 | Complete | T-Shirt
Buyer 1 | Order | Coffee
Buyer 1 | Order | Cake
Buyer 2 | Complain | Hoody
Buyer 2 | Order | Tea
Buyer 1 | Complete | Coffee

Ps: the system will not give the same output as in the problem statement because its a real Dapp and for each transaction there will be the cost of the transaction fees ...
