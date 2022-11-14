# Guide to Create Your first Token on Stacks Blockchain



This Blog is a tutorial on "How to Create your First token on Stacks" . 
We will learn more about tokens on Stacks , Setting up a Dev Environment for creating the Smart Contract , Create a token , deploy them on Blockchain and even test them. 

So let's get right inn -->

## PreRequisites
- Introduction about Stacks Chain
- HIRO Wallet Setup 
- STX faucets
- Knowledge about Clarity 

I would highly recommend to go through this [Blog](https://www.stacks.sahilaujla.com/) by Sahil Aujla first , before starting this tutorial for a introduction to Stacks Ecosystem.


## What is Stack Blockchain

Stacks is a Layer-1 Blockchain that brings the power of Smart Contracts and dApps to Bitcoin  , they are integrated to the security of Bitcoin. STX is the native token for Stacks blockchain and is used to pay for the gas fees. [Clarity](https://clarity.tools/) is the language for Smart Contracts on Stack . We use [HIRO](https://wallet.hiro.so/) as the wallet for interacting with Stacks Chain .

For more Info on Stacks , check [here](https://docs.stacks.co/docs/intro)

## Tokens

A fundamental use of blockchain technology is the representation, store, and transfer of value between users of a blockchain. Cryptocurrency is a very common use of blockchain technology .

A blockchain token is a digital asset that can be verifiably owned by a user of a blockchain. Blockchain tokens are governed by a set of rules that are defined by either the blockchain itself (in the case of native tokens) or by a smart contract on a blockchain.

## Types of Tokens 

### Non - Fungible Tokens
Non-fungible tokens (NFTs) are a type of token that are not interchangeable. NFTs have unique traits (usually in the form of attached metadata) that restrict the abillity to replace them with identical tokens. An NFT is a token that is unique, such as a piece of art, or ownership rights to a real-world asset such as a house.

### Fungible Tokens 
A fungible token is a token that's mutually interchangable or capable of mutual substitution. In other words, one quantity or part of a fungible token can be replaced by an equal quantity or part of the same fungible token. Fungible tokens are often used to represent real-world fungible assets like currency.


## Setting up the Dev Environment

Clarity is the language which is used to write Smart Contracts on Stacks Chain . For an intro to Clarity check [this](https://docs.stacks.co/docs/write-smart-contracts/clarity-language/) . I am assuming , you already have basic knowledge of Clarity and that is what we need for this tutorial .

Please ensure , you have Hiro Wallet Setup , it will be used to interact with STAX blockchain and you have some funds . If not follow the tutorial [here](https://www.stacks.sahilaujla.com/docs/installing-hiro-wallet)

Luckily Clarity has inbuilt functions for both the types of token , so we are gonna use that. 

-  Head over to https://clarity.tools/ , this is where we will write Smart Contract in Clarity and Then deploy it to the testnet.

![Screenshot 2022-11-14 at 11.28.45 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668405529527/jXN26vmYT.png align="left")

- Connect Hiro Wallet by clicking on the gate icon in the top , A popup will appear , Select the account .


![Screenshot 2022-11-14 at 11.30.05 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668405714300/jhod18Zck.png align="left")

Once Connected  , the window will appear as : 
![Screenshot 2022-11-14 at 11.32.34 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668405758856/LYLZqAwXr.png align="left") 


- Clear up all the default Code , The window is divided into 2 parts , Code editor and Terminal that returns the output. Check Reference Image below

![Screenshot 2022-11-14 at 11.39.10 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668406341234/4xX8NRMEM.png align="left")


Ok So Now , we are good to go to create both types of token.

### NOTE
Before we move ahead , I have added both the codes in the github Repo [here](https://github.com/Dhruv-2003/StacksTokenContracts) , do check them out .

## Fungible Tokens Standard

The SIP-010 standard is the token Standard on Stacks for fungible types of tokens .
These are the default function for SIP-010 types of tokens :

- `mint`-  mint tokens to an Address
- `burn` - burn tokens from an Address
- `transfer` -  transfer a token amount from address1 to address2
- `get-name ` -  Name of the token created
- `get-symbol` - Symbol of the Token 
- `get-decimals` - No. of decimals for the token
- `get-total-supply` - Total Supply of the token 
- `get-balance-of` - Balance of token for an Address
- `get-token-uri` - Token URI associated with the token


1.  We create a token using `define-fungible-token token-name` and Boom !!, you just created a token , it's that easy.
![Screenshot 2022-11-14 at 11.57.46 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668407270005/67ltrwUnf.png align="left")

2. Now to test it , Functions for fungible token standard are already predefined in clarity .  Here is the code example with comments containing all the functions which are predefined : 
![Screenshot 2022-11-14 at 12.09.34 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668407996834/3fFWJ92Fo.png align="left")

3. To deploy the token contract , we will just keep `define-fungible-token token-name`  to create the token.
![Screenshot 2022-11-14 at 12.11.47 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668408111971/oVHCytm51.png align="left")

4. Head over to the tool box icon on the top and Select Deploy to tesnet. 
![Screenshot 2022-11-14 at 12.12.36 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668408161143/JNVDP-8xs.png align="left")

5. A Hiro Wallet Popup will be there to deploy the contract by confirming the tx .
![Screenshot 2022-11-14 at 12.14.48 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668408293173/PsT7npQQ3.png align="left")

6. You will get a Tx link of the explorer for the contract. It will be something like this : https://explorer.stacks.co/txid/0x8165aaf1cf4767ead78c4833e13b17b1ebb8620302748b35d9e326a2e3af47e9?chain=testnet

![Screenshot 2022-11-14 at 12.19.04 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668408549556/kOAv5vD7f.png align="left")

The contract is deployed to ST3MNTK3HEQ8GTSB6SNWQVN84VPKG4D5Q8TS5JD45.contract-68408193608 .

Woohoo !!  We just deployed a token contract to Stacks .
Let's head-over to NFT 

## Non Fungible Token Standard
The SIP-009 standard is the token standard for Non fungible type of tokens.
Default functions for this type 

- `mint` -  Mint a paritcular token to an Address
- `burn` - Burn a particular token from an Address 
- `transfer` -  Transfer the token from an Address
- `get-owner` -  Get the owner of a particular token


1. To Create the token use `define-non-fungible-token tokenName` , and this will create nftTokens for you . 
![Screenshot 2022-11-14 at 3.00.36 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668418240572/HGPgQ-ik_.png align="left")

2. Similar to Fungible token , Non-fungible token also have these functions predefined
![Screenshot 2022-11-14 at 3.03.08 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668418393554/8JReRNKeT.png align="left")

3. To deploy this contract , follow similar procedure from step 3 in Fungible token Tutorial .
You will get the txId after confirming the tx . Mine is deployed on : https://explorer.stacks.co/txid/0x8b0561a54ce1c69e7dfef1ad7a53fc18b82d41358a39da5114c0a2bb2f7bf62b?chain=testnet

4. For Testing , we will call similar functions and we can see the output in the sidebar
![Screenshot 2022-11-14 at 3.05.14 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668418517952/LVQegGO4c.png align="left")


So , We successfully completed NFT too . Great Job !!

## Bonus 

For all who have come to end of this tutorial , there is a bonus , which is transacting with STX token on Stacks blockchain with Contracts.

STX is the native token of STACKS chain. We have inbuilt clarity Commands as follows:

-  `stx-transfer` -  Transfer STX from account 1 to account 2 
-  `stx-get-balance` -  Balance of STX of the account
-  `stx-burn`-  Burn the amount STX from an account

We can use this inbuilt functions in other functions directly.

![Screenshot 2022-11-14 at 7.16.19 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668433583039/QCjBS7MkL.png align="left")

## Conclusion 
We learnt about what are tokens and It's types : Fungible and Non Fungible . How to write a Smart contract for creating tokens using Clarity , then to test them and eventually deploying them on the blockchain .

Finally , We have created our first Tokens ( Fungible and Non-Fungible ) on Stacks Blockchain . Kudos to you all who completed the tutorial.

If you like the blog , consider giving me on Twitter [@0xdhruva](https://twitter.com/0xdhruva) .
In case of further queries , connect on [Twitter](https://twitter.com/0xdhruva) . 

## Links and References

- https://docs.stacks.co/docs/intro
- https://github.com/Dhruv-2003/StacksTokenContracts
- https://www.stacks.sahilaujla.com/
- https://clarity.tools
- https://wallet.hiro.so/



