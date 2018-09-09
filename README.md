# Rawhide Registry

This project is the web user interface for minting non-fungible tokens on the ethereum blockchain based on the truffle box Etherplate https://github.com/chuckbergeron/etherplate created by Chuck and team.

### View Demo

![Rawhide Demo Gif](https://raw.githubusercontent.com/rawhideio/dapp/master/app/images/raw.gif)

[View Etherplate Demo on Netlify (Uses Ropsten testnet)](http://etherplate.netlify.com/)

# Setup

### Requires NPM & Direnv

Homebrew on Mac OSX:

`brew install node npm direnv`

Apt on Linux:

`apt-get install node npm direnv`

### Install truffle globally:

`npm install truffle -g`

### Install the local NPM packages:

`npm install`

### Environment Variables

1. `cp .envrc.example .envrc`

2. Enter your own twelve random words in the .envrc.

3. Also, we'll leverage Infura's Ethereum Ropsten testnet node, so make sure to set up an account and paste your private key in your .envrc.

4. Use `direnv allow` to export the env vars into your current terminal shell.

### Ganache (CLI)

Create a directory for ganache-cli to store it's database in:

`mkdir .ganache`

### Compile the Solidity code

`truffle compile`

### Migrate the Contracts

This will deploy the contract to the network (tip: use --network=ropsten to deploy to Ethereum's Ropsten Testnet)

`truffle migrate`

# Run the Project

Make sure the truffle contracts are compiled and migrated.

In one terminal window, run the ganache-cli (local Ethereum RPC test node) with:

`./ganache.sh`

Once Ganache is running, in another terminal start the Webpack dev server.

`npm run dev`

Your server should now be running at http://127.0.0.1:8080

### truffle.js & truffle-config.js

Why is there both a truffle and truffle-config file?

* On Windows, truffle-config.js is required. You can safely delete the one you don't need (ie on Mac/Linux you can delete truffle-config.js)

# Building the Project

`npm run build`

*Note: Currently we are manually migrating contracts against the Ropsten & Rinkeby testnets, and checking the build into the repo. This is less than ideal. It would be better to use a build script such as the [netlify-build.sh](https://github.com/chuckbergeron/etherplate/blob/master/netlify-build.sh) file and compile contracts on the server.*

# Running the Tests

For the Solidity contract's truffle test suite:

`truffle test`

To run the DApp test suite (React components, etc):

`npm test`

--------------------

## Toast Messages

Examples of a bunch of different looking toast messages to show on an error message, success, info, etc.:

```
  toastr.light('test', 'message', { icon: 'info', status: 'info' })
  toastr.light('test', 'message', { icon: 'success', status: 'success' })
  toastr.light('test', 'message', { icon: 'warning', status: 'warning' })

  toastr.success('test', 'message')
  toastr.info('test', 'message')
  toastr.warning('test', 'message')
  toastr.error('test', 'message')
```
