# Supply-Chain-Management-
A supply Chain Management system for an auction setting and UI and metamask wallet, using Ethereum and Solidity.

## Technologies:
Web3.0, JS, React JS, Ganache, Ethereum, Solidity, Metamask, Truffle
<br/>
Editor: Visual Studio Code
## Supply-Chain Management using Solidity and Ethereum
Task: creating a transparent supply chain which
can be used by 5 clients and their customers.
The clients are either Suppliers, Manufacturers or Customers.
<br/>
1. Actors
Manufacturers: There are 2 clients (Tata and Maruti) who manufacture cars, and
sell them to the customers. For simplicity, we assume a car requires two
components: Wheels and Car-body.
Suppliers: There are 3 suppliers (Vedanta, MRF and CEAT). Each of them
supplies a single material.
- Vedanta has a market monopoly and supplies car-body to both Tata
and Maruti.
- MRF supplies wheels to Tata and CEAT supplies to Maruti.
- Each supplier has a limited supply of the material which they
produce (which can be set by calling a function) and this limit is
publicly known
Customers: Customers buy the product from the Manufacturers at the
retail-price.
2. Market Interaction
The market interaction goes as follows:
1. Suppliers set supply limit on their products
2. Manufacturers place their bids& (bids should be secret till all
manufacturers have placed their bid)
3. Smart contract performs resource optimal distribution$ of materials to
manufacturers
4. Manufacturer takes materials to create product and sets price for the
product
5. Customer buys the product from the manufacturer.
3. Goals
Goal 1: & = Bidding should be secret. We assume that all manufacturers will
place their bid in time. The bidding should be such that the following conditions is
met:
- No manufacturer should be able to find out another manufacturer’s bid
unless everyone has placed their bids.
This condition is enforced to ensure bids from each of the manufacturers which
reveal their true evaluation of the material.
Note that a bid contains price and quantity. Therefore, even though revealing the
bidding price for wheels will not give any advantage to either manufacturer
because the suppliers are different; revealing the quantity of wheels ordered
might allow the competition to infer the amount of car-bodies ordered. Therefore,
we want to keep all bids secret.
Goal 2: $ = Optimal supply means that the number of products put to use (not
lying on shelf) should be maximized.
For example: Consider 10 units of material A and B are required by E and 20
units of A and C are required by F.
The supply limits on A, B, C are 27, 15 and 15.
Bid by F on product A is higher than bid by E.
Profit maximizing distribution: Send 20 Units of A to F and 7 Units of A to E. Send
10 units of B to E and 15 Units of C to E.
Resource Optimal distribution: Send 10 Units of A to E and 17 units of A to F.
Send 10 units of B to E and 15 Units of C to E.
Definition [Resource Optimal Distribution]
A supply-chain follows optimal distribution of materials if the quantity of material
which is kept on the shelf is minimized, i.e. the amount of resource utilized is
maximized.
Our goal is to optimize the supply chain, therefore we will implement an resource
optimal distribution method.
Note that this is one of the many advantages of having a blockchain based
trustless and decentralized supply-chain that such globally optimal methods can
be implemented instead of selfish strategies opted by each party leading to
resource wastage and slowing down of supply-chain.
Goal 3: Validity of the product: This property requires:
- Each product is not duplicated (same UID is not sent to different users)
- Each product is authentic (suppliers create and distribute as much product
as specified by their supply limit, manufacturers create and distribute
products as much supply of materials they have).
- These two things should be verifiable by the buyer (he can make sure that
the materials are from said supplier and product is from said
manufacturer).
—--------------------------------------------------------------
Fig. A description of the supply chain
![Screenshot (369)](https://user-images.githubusercontent.com/31008590/202524211-ef0ce573-175c-4f29-81c9-d30f17f40403.png)

## UI using ReactJS and connection to Wallet service(Metamask):
Task:To create a frontend platform, accessible through a
web-browser, for the Supply-chain management which was created using
smart-contract on Ethereum blockchain. 
<br/>
Tools required:
● Metamask (for in browser wallet-management)
● web3.js package for calling smart-contract functions
We build a frontend solution for the contract developed
previously.
