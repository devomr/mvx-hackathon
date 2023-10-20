# Code Structure

The code structure for xCoffee project is split in 3 different repositories:

- dApp: https://github.com/devomr/xcoffee-dapp
- Microservice: https://github.com/devomr/xcoffee-service
- Smart Contract: https://github.com/devomr/xcoffee-smart-contract

You will find the necessary details in each repostory.

## Overview of the application architecture

![Diagram](https://github.com/devomr/mvx-hackathon/blob/main/xcoffee-architecture.png)

## xCoffee dApp

The xCoffee dApp is based on the [mx-template-dapp](https://www.npmjs.com/package/@multiversx/mx-template-dapp) and is built using [React.js](https://reactjs.org/) and [Typescript](https://www.typescriptlang.org/).

The users can use the dApp to interact directly with the smart contract or with the backend microservice.

The interaction with the smart contract is by sending the transactions: donate, create_user_subscription and cancel_subscription

The interaction with the microservice is by getting the donate transactions for a creator,
get and save the creator profile details in off-chain database (MongoDB), get the most recent registered creators and get the subscription deadline for an user.

## xCoffee Microservice

The microservice component is mainly used to query the smart contract (plus storing in CacheService), MultiversX API (plus storing in CacheService) and getting and saving data in the MongoDB database.

For non-public endpoints, the authentication and authorization process is mandatory and is implemented via the NativeAuthGuard.

## xCoffee Smart Contract

The smart contract is used to perform the payable transactions:

- donate
- create_user_subscription
- renew_subscription

non-payable transaction:

- cancel_subscription

and the view:

- get_user_subscription_deadline

Storage mappers are used to keep track of the smart contract state to fulfill the requirements.

Complete integration tests for the smart contract (Coming soon)
