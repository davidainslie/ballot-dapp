# Dapp for a Ballot

Once we have our top-level structure, we can go through the "setup":

```shell
mkdir ballot-Dapp
cd ballot-Dapp
mkdir ballot-app
mkdir ballot-contract
```

```shell
|--- ballot-dapp
          |
          |--- ballot-app
          |
          |--- ballot-contract
```

## Setup

```shell
# ballot-dapp/ballot-contract
truffle init   

Starting init...
================

> Copying project files to /Users/davidainslie/workspace/blockchain/ballot-dapp/ballot-contract

Init successful, sweet!

Try our scaffold commands to get started:
  $ truffle create contract YourContractName # scaffold a contract
  $ truffle create test YourTestName         # scaffold a test
```

```shell
ls -las
total 16
 0 drwxr-xr-x  6 davidainslie  staff   192 27 Oct 22:11 .
 0 drwxr-xr-x  8 davidainslie  staff   256 27 Oct 17:57 ..
 0 drwxr-xr-x  3 davidainslie  staff    96 27 Oct 22:11 contracts
 0 drwxr-xr-x  3 davidainslie  staff    96 27 Oct 22:11 migrations
 0 drwxr-xr-x  3 davidainslie  staff    96 27 Oct 22:11 test
16 -rw-r--r--  1 davidainslie  staff  4900 27 Oct 22:11 truffle-config.js
```

## Contract Ballot.sol

We have a contract under `ballot-contract/contracts/`.
Within the `ballot-contract` directory we can request `truffle` to compile all contracts (see JSON built files under `ballot-contract/build/contracts`):

```shell
# ballot-dapp/ballot-contract
truffle compile

Compiling your contracts...
===========================
✔ Fetching solc version list from solc-bin. Attempt #1
✔ Downloading compiler. Attempt #1.
> Compiling ./contracts/Ballot.sol
> Compiling ./contracts/Migrations.sol
> Artifacts written to /Users/davidainslie/workspace/blockchain/ballot-dapp/ballot-contract/build/contracts
> Compiled successfully using:
   - solc: 0.8.9+commit.e5eed63a.Emscripten.clang
```

The `build/contracts` directory contains JSON files for the contracts that are used for (JSON-RPC) communication between the web client and blockchain server.

The JSON file of the smart contract is called the application binary interface (ABI) of the smart contract code. This file is the interface that will be used by calls from the web application to smart contracts and also for data transfer between these modules.