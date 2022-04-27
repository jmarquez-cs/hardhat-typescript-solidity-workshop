# Produced By [John Marquez](https://github.com/ScooterHelmet) with the help of `npx hardhat`
This is another implementation of my previous [contract in Solidity that is similar to The Button on reddit (r/thebutton),](https://github.com/ScooterHelmet/musical-chairs) only this time using Typescript + Hardhat.
## Dependencies
1. A macbook pro running [macOS Monterey version 12.2.1](https://apps.apple.com/us/app/macos-monterey/id1576738294?mt=12)
2. VS Code installed for macOS 10.11+: [VSCode-darwin-universal](https://code.visualstudio.com/sha/download?build=stable&os=darwin-universal)
3. [‘Solidity+Hardhat’ VS Code extension](https://marketplace.visualstudio.com/items?itemName=NomicFoundation.hardhat-solidity) installed 
4. [Node.js version 16.15.0 LTS](https://nodejs.org/dist/v16.15.0/node-v16.15.0.pkg) installed for macOS

### Getting Started
1. Open a terminal and check node versions
```shell
node -v && npm -v && npx -v
```
**step 1 example output:**
```console
v16.15.0
8.5.5
8.5.5
```
-----
2. Change directory to `$HOME`, create a `workspace` directory, and change directory to `workspace`
```shell
cd ~ && mkdir workspace && cd $_
```
**step 2 example output:**
```shell
foobar-MBP:workspace foo.bar$
```
-----
3. Globally install the [hardhat-shorthand](https://hardhat.org/guides/shorthand.html#shorthand-hh-and-autocomplete) node package 
```shell
npm i -g hardhat-shorthand
```
**step 3 example output:**
```console
added 10 packages, and audited 11 packages in 2s

found 0 vulnerabilities
```
-----
4. Install hardhat as a developer dependency for the workspace
```shell
npm i —save-dev hardhat
```
**step 4 example output:**: 
```console
npm WARN EBADENGINE Unsupported engine {
npm WARN EBADENGINE   package: 'hardhat@2.9.3',
npm WARN EBADENGINE   required: { node: '^12.0.0 || ^14.0.0 || ^16.0.0' },
npm WARN EBADENGINE   current: { node: 'v18.0.0', npm: '8.6.0' }
npm WARN EBADENGINE }

added 299 packages, and audited 300 packages in 13s

53 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```
**step 4 creates two new files and a `node_modules` directory:**  
```console
    .
    ├── node modules                # Compiled files (alternatively `dist`)
    ├── package.lock.json           # Documentation files (alternatively `doc`)
    ├── package.json                # Source files (alternatively `lib` or `app`)
```
-----
5. Install [hardhat dependencies](https://hardhat.org/guides/typescript.html#installing-dependencies) `ts-node` and `typescript`
```shell
npm install --save-dev ts-node typescript
```
**step 5 example output:**
```console
npm WARN EBADENGINE Unsupported engine {
npm WARN EBADENGINE   package: 'hardhat@2.9.3',
npm WARN EBADENGINE   required: { node: '^12.0.0 || ^14.0.0 || ^16.0.0' },
npm WARN EBADENGINE   current: { node: 'v18.0.0', npm: '8.6.0' }
npm WARN EBADENGINE }

added 16 packages, and audited 316 packages in 2s

53 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```
-----
6. Install the `chai` assertion library and its typescript dependencies for [BDD](https://cucumber.io/docs/bdd/)/[TDD](https://www.guru99.com/test-driven-development.html)
```shell
npm install --save-dev chai @types/node @types/mocha @types/chai
```
**step 6 example output:**
```console
npm WARN EBADENGINE Unsupported engine {
npm WARN EBADENGINE   package: 'hardhat@2.9.3',
npm WARN EBADENGINE   required: { node: '^12.0.0 || ^14.0.0 || ^16.0.0' },
npm WARN EBADENGINE   current: { node: 'v18.0.0', npm: '8.6.0' }
npm WARN EBADENGINE }

added 10 packages, and audited 326 packages in 2s

53 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```
-----
### Creating a hardhat project that uses typescript
1. Starting from the the project's root directory, open a terminal and execute:
```shell
npx hardhat
```
**Select > Create an advanced sample project that uses Typescript:**
```console
(node:87379) ExperimentalWarning: The Fetch API is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
You are using a version of Node.js that is not supported by Hardhat, and it may work incorrectly, or not work at all.

Please, make sure you are using a supported version of Node.js.

To learn more about which versions of Node.js are supported go to https://hardhat.org/nodejs-versions
888    888                      888 888               888
888    888                      888 888               888
888    888                      888 888               888
8888888888  8888b.  888d888 .d88888 88888b.   8888b.  888888
888    888     "88b 888P"  d88" 888 888 "88b     "88b 888
888    888 .d888888 888    888  888 888  888 .d888888 888
888    888 888  888 888    Y88b 888 888  888 888  888 Y88b.
888    888 "Y888888 888     "Y88888 888  888 "Y888888  "Y888

👷 Welcome to Hardhat v2.9.3 👷‍

? What do you want to do? … 
  Create a basic sample project
  Create an advanced sample project
❯ Create an advanced sample project that uses TypeScript
  Create an empty hardhat.config.js
  Quit
```
-----
2. Complete the terminal prompts
```console
✔ What do you want to do? · Create an advanced sample project that uses TypeScript
? Hardhat project root: › /Users/foo.bar/workspace
? Do you want to add a .gitignore? (Y/n) › y
```
**expected output after terminal prompts**
```console
You need to install these dependencies to run the sample project:
  npm install --save-dev "hardhat@^2.9.3" "@nomiclabs/hardhat-waffle@^2.0.0" "ethereum-waffle@^3.0.0" "chai@^4.2.0" "@nomiclabs/hardhat-ethers@^2.0.0" "ethers@^5.0.0" "@nomiclabs/hardhat-etherscan@^3.0.0" "dotenv@^10.0.0" "eslint@^7.29.0" "eslint-config-prettier@^8.3.0" "eslint-config-standard@^16.0.3" "eslint-plugin-import@^2.23.4" "eslint-plugin-node@^11.1.0" "eslint-plugin-prettier@^3.4.0" "eslint-plugin-promise@^5.1.0" "hardhat-gas-reporter@^1.0.4" "prettier@^2.3.2" "prettier-plugin-solidity@^1.0.0-beta.13" "solhint@^3.3.6" "solidity-coverage@^0.7.16" "@typechain/ethers-v5@^7.0.1" "@typechain/hardhat@^2.3.0" "@typescript-eslint/eslint-plugin@^4.29.1" "@typescript-eslint/parser@^4.29.1" "@types/chai@^4.2.21" "@types/node@^12.0.0" "@types/mocha@^9.0.0" "ts-node@^10.1.0" "typechain@^5.1.2" "typescript@^4.5.2"

✨ Project created ✨
See the README.md file for some example tasks you can run.
```
-----
3. Given the project created successfully, install the terminal prompt dependencies listed
```shell
npm install --save-dev "hardhat@^2.9.3" "@nomiclabs/hardhat-waffle@^2.0.0" "ethereum-waffle@^3.0.0" "chai@^4.2.0" "@nomiclabs/hardhat-ethers@^2.0.0" "ethers@^5.0.0" "@nomiclabs/hardhat-etherscan@^3.0.0" "dotenv@^10.0.0" "eslint@^7.29.0" "eslint-config-prettier@^8.3.0" "eslint-config-standard@^16.0.3" "eslint-plugin-import@^2.23.4" "eslint-plugin-node@^11.1.0" "eslint-plugin-prettier@^3.4.0" "eslint-plugin-promise@^5.1.0" "hardhat-gas-reporter@^1.0.4" "prettier@^2.3.2" "prettier-plugin-solidity@^1.0.0-beta.13" "solhint@^3.3.6" "solidity-coverage@^0.7.16" "@typechain/ethers-v5@^7.0.1" "@typechain/hardhat@^2.3.0" "@typescript-eslint/eslint-plugin@^4.29.1" "@typescript-eslint/parser@^4.29.1" "@types/chai@^4.2.21" "@types/node@^12.0.0" "@types/mocha@^9.0.0" "ts-node@^10.1.0" "typechain@^5.1.2" "typescript@^4.5.2"
```
**expected output**
```console
added 1743 packages, changed 1 package, and audited 2072 packages in 47s

176 packages are looking for funding
  run `npm fund` for details

56 vulnerabilities (11 moderate, 44 high, 1 critical)

To address issues that do not require attention, run:
  npm audit fix

To address all issues possible (including breaking changes), run:
  npm audit fix --force

Some issues need review, and may require choosing
a different dependency.

Run `npm audit` for details.
```
-----
4. Verify that the project runs built-in tasks the accounts sample successfully
```shell
npx hardhat accounts
```
**If you are met with an `unexpected error` caused by breaking changes for openssl, this means you are not using the hardhat supported Node.js LTS version:**
```console
An unexpected error occurred:

Error: error:0308010C:digital envelope routines::unsupported
    at new Hash (node:internal/crypto/hash:67:19)
    at Object.createHash (node:crypto:133:10)
    at hash160 (/Users/john.marquez/work-space/oneof/node_modules/ethereum-cryptography/vendor/hdkey-without-crypto.js:249:21)
    at HDKey.set (/Users/john.marquez/work-space/oneof/node_modules/ethereum-cryptography/vendor/hdkey-without-crypto.js:50:24)
    at Function.HDKey.fromMasterSeed (/Users/john.marquez/work-space/oneof/node_modules/ethereum-cryptography/vendor/hdkey-without-crypto.js:194:20)
    at deriveKeyFromMnemonicAndPath (/Users/john.marquez/work-space/oneof/node_modules/hardhat/src/internal/util/keys-derivation.ts:22:27)
    at derivePrivateKeys (/Users/john.marquez/work-space/oneof/node_modules/hardhat/src/internal/core/providers/util.ts:30:52)
    at normalizeHardhatNetworkAccountsConfig (/Users/john.marquez/work-space/oneof/node_modules/hardhat/src/internal/core/providers/util.ts:58:10)
    at createProvider (/Users/john.marquez/work-space/oneof/node_modules/hardhat/src/internal/core/providers/construction.ts:79:59)
    at /Users/john.marquez/work-space/oneof/node_modules/hardhat/src/internal/core/runtime-environment.ts:82:28 {
  opensslErrorStack: [ 'error:03000086:digital envelope routines::initialization error' ],
  library: 'digital envelope routines',
  reason: 'unsupported',
  code: 'ERR_OSSL_EVP_UNSUPPORTED'
}
```
**to remedy openssl issues, `SET NODE_OPTIONS=--openssl-legacy-provider` and try starting a JSON-RPC server on top of Hardhat Network:**
```shell
export SET NODE_OPTIONS=--openssl-legacy-provider && npx hardhat node
```
**example output:**
```console
Accounts
========

WARNING: These accounts, and their private keys, are publicly known.
Any funds sent to them on Mainnet or any other live network WILL BE LOST.

Account #0: 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266 (10000 ETH)
Private Key: 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80

Account #1: 0x70997970c51812dc3a010c7d01b50e0d17dc79c8 (10000 ETH)
Private Key: 0x59c6995e998f97a5a0044966f0945389dc9e86dae88c7a8412f4603b6b78690d

Account #2: 0x3c44cdddb6a900fa2b585dd299e03d12fa4293bc (10000 ETH)
Private Key: 0x5de4111afa1a4b94908f83103eb1f1706367c2e68ca870fc3fb9a804cdab365a

Account #3: 0x90f79bf6eb2c4f870365e785982e1f101e93b906 (10000 ETH)
Private Key: 0x7c852118294e51e653712a81e05800f419141751be58f605c371e15141b007a6

Account #4: 0x15d34aaf54267db7d7c367839aaf71a00a2c6a65 (10000 ETH)
Private Key: 0x47e179ec197488593b187f80a00eb0da91f1b9d0b13f8733639f19c30a34926a

Account #5: 0x9965507d1a55bcc2695c58ba16fb37d819b0a4dc (10000 ETH)
Private Key: 0x8b3a350cf5c34c9194ca85829a2df0ec3153be0318b5e2d3348e872092edffba

Account #6: 0x976ea74026e726554db657fa54763abd0c3a0aa9 (10000 ETH)
Private Key: 0x92db14e403b83dfe3df233f83dfa3a0d7096f21ca9b0d6d6b8d88b2b4ec1564e

Account #7: 0x14dc79964da2c08b23698b3d3cc7ca32193d9955 (10000 ETH)
Private Key: 0x4bbbf85ce3377467afe5d46f804f221813b2bb87f24d81f60f1fcdbf7cbf4356

Account #8: 0x23618e81e3f5cdf7f54c3d65f7fbc0abf5b21e8f (10000 ETH)
Private Key: 0xdbda1821b80551c9d65939329250298aa3472ba22feea921c0cf5d620ea67b97

Account #9: 0xa0ee7a142d267c1f36714e4a8f75612f20a79720 (10000 ETH)
Private Key: 0x2a871d0798f97d79848a013d4936a73bf4cc922c825d33c1cf7073dff6d409c6

Account #10: 0xbcd4042de499d14e55001ccbb24a551f3b954096 (10000 ETH)
Private Key: 0xf214f2b2cd398c806f84e317254e0f0b801d0643303237d97a22a48e01628897

Account #11: 0x71be63f3384f5fb98995898a86b02fb2426c5788 (10000 ETH)
Private Key: 0x701b615bbdfb9de65240bc28bd21bbc0d996645a3dd57e7b12bc2bdf6f192c82

Account #12: 0xfabb0ac9d68b0b445fb7357272ff202c5651694a (10000 ETH)
Private Key: 0xa267530f49f8280200edf313ee7af6b827f2a8bce2897751d06a843f644967b1

Account #13: 0x1cbd3b2770909d4e10f157cabc84c7264073c9ec (10000 ETH)
Private Key: 0x47c99abed3324a2707c28affff1267e45918ec8c3f20b8aa892e8b065d2942dd

Account #14: 0xdf3e18d64bc6a983f673ab319ccae4f1a57c7097 (10000 ETH)
Private Key: 0xc526ee95bf44d8fc405a158bb884d9d1238d99f0612e9f33d006bb0789009aaa

Account #15: 0xcd3b766ccdd6ae721141f452c550ca635964ce71 (10000 ETH)
Private Key: 0x8166f546bab6da521a8369cab06c5d2b9e46670292d85c875ee9ec20e84ffb61

Account #16: 0x2546bcd3c84621e976d8185a91a922ae77ecec30 (10000 ETH)
Private Key: 0xea6c44ac03bff858b476bba40716402b03e41b8e97e276d1baec7c37d42484a0

Account #17: 0xbda5747bfd65f08deb54cb465eb87d40e51b197e (10000 ETH)
Private Key: 0x689af8efa8c651a91ad287602527f3af2fe9f6501a7ac4b061667b5a93e037fd

Account #18: 0xdd2fd4581271e230360230f9337d5c0430bf44c0 (10000 ETH)
Private Key: 0xde9be858da4a475276426320d5e9262ecfc3ba460bfac56360bfa6c4c28b4ee0

Account #19: 0x8626f6940e2eb28930efb4cef49b2d1f2c9c1199 (10000 ETH)
Private Key: 0xdf57089febbacf7ba0bc227dafbffa9fc08a93fdc68e1e42411a14efcf23656e

WARNING: These accounts, and their private keys, are publicly known.
Any funds sent to them on Mainnet or any other live network WILL BE LOST.
```
**Now simply run the built-in task, `accounts` using `hardhat-shorthand`:**
```shell
hh accounts
```
**example output:**
```console
0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266
0x70997970C51812dc3A010C7d01b50e0d17dc79C8
0x3C44CdDdB6a900fa2b585dd299e03d12FA4293BC
0x90F79bf6EB2c4f870365E785982E1f101E93b906
0x15d34AAf54267DB7D7c367839AAf71A00a2C6A65
0x9965507D1a55bcC2695C58ba16FB37d819B0A4dc
0x976EA74026E726554dB657fA54763abd0C3a0aa9
0x14dC79964da2C08b23698B3D3cc7Ca32193d9955
0x23618e81E3f5cdF7f54C3d65f7FBc0aBf5B21E8f
0xa0Ee7A142d267C1f36714E4a8F75612F20a79720
0xBcd4042DE499D14e55001CcbB24a551F3b954096
0x71bE63f3384f5fb98995898A86B02Fb2426c5788
0xFABB0ac9d68B0B445fB7357272Ff202C5651694a
0x1CBd3b2770909D4e10f157cABC84C7264073C9Ec
0xdF3e18d64BC6A983f673Ab319CCaE4f1a57C7097
0xcd3B766CCDd6AE721141F452C550Ca635964ce71
0x2546BcD3c84621e976D8185a91A922aE77ECEc30
0xbDA5747bFD65F08deb54cb465eB87D40e51B197E
0xdD2FD4581271e230360230F9337D5c0430Bf44C0
0x8626f6940E2eb28930eFb4CeF49B2d1F2C9C1199
```
-----
### Write a contract in Solidity that is similar to The Button on reddit (r/thebutton),
1. From the root directory, navigate to the `workspace/test/index.ts` file and describe a new test for a contract in Solidity, where participants pay a fixed amount of ether to call `press_button`, and then if 3 blocks pass without someone calling `press_button`, whoever pressed the button last can call `claim_treasure` and get the other participants’ deposits.

**Write a test case that should allow participant to claim_treasure while press_button has not been called for 3 blocks:**
```typescript
import { expect } from "chai";
import { ethers } from "hardhat";

describe("Button", () => {
  it("Should allow participant to claim_treasure while press_button has not been called for 3 blocks", async () => {
    const Button = await ethers.getContractFactory("Button");
    const button = await Button.deploy();
    await button.deployed();

    expect(await button.claim_button()).to.equal("press_button");

    const setButtonTx = await button.setButton("claim_treasure");
    /**
     * wait until the transactions is mined 3 times
     */
    await setButtonTx.wait();
    await setButtonTx.wait();
    await setButtonTx.wait();

    expect(await button.claim_button()).to.equal("claim_treasure");
  });
});
```
-----
2. Write a Solidity smart contract for the button in a new file `workspace/contracts/Button.sol`
```solidity
//SPDX-License-Identifier: Unlicense
pragma solidity ^0.8.0;

import "hardhat/console.sol";

contract Button {
    string private button;

    constructor(string memory _press_button) {
        console.log("Deploying a Button as press_button:", _press_button);
        button = _press_button;
    }

    function claim_button() public view returns (string memory) {
        return button;
    }

    function setButton(string memory _press_button) public {
        console.log("Changing press_button from '%s' to '%s'", button, _press_button);
        button = _press_button;
    }
}
```
-----
3. Within a terminal clean artifacts and compile the `workspace/contracts/Button.sol` contract to generate new artifacts
```shell
hh clean && hh compile
```
**step 3 example output:**
```console
Generating typings for: 3 artifacts in dir: typechain for target: ethers-v5
Successfully generated 7 typings!
Compiled 3 Solidity files successfully
```
-----
4. In the terminal, run the unit tests:
```shell
hh test
```
**step 4 example output:**
```console
No need to generate any newer typings.


  Greeter
Deploying a Greeter with greeting: Hello, world!
Changing greeting from 'Hello, world!' to 'Hola, mundo!'
    ✔ Should return the new greeting once it's changed (733ms)

  Button
Deploying a Button as press_button: press_button
Changing press_button from 'press_button' to 'claim_treasure'
    ✔ Should allow participant to claim_treasure while press_button has not been called for 3 blocks (73ms)


  2 passing (816ms)
```
-----
5. Deploy the smart contract using typechain via the hardhat script found in `workspace/scripts/deploy.ts`, adding logic to the `async function main() { ... }` after Line 22:
```typescript
   const Button = await ethers.getContractFactory("Button");
   const button = await Button.deploy("press_button");
   await button.deployed();

   console.log("Button deployed to:", button.address);
```
-----
### hh usage

```shell
hh accounts
hh compile
hh clean
hh test
hh node
hh help
REPORT_GAS=true hh test
hh coverage
hh run scripts/deploy.ts
```
### Lint usage
```shell
TS_NODE_FILES=true npx ts-node scripts/deploy.ts
npx eslint '**/*.{js,ts}'
npx eslint '**/*.{js,ts}' --fix
npx prettier '**/*.{json,sol,md}' --check
npx prettier '**/*.{json,sol,md}' --write
npx solhint 'contracts/**/*.sol'
npx solhint 'contracts/**/*.sol' --fix
```

# Etherscan verification

To try out Etherscan verification, you first need to deploy a contract to an Ethereum network that's supported by Etherscan, such as Ropsten.

In this project, copy the .env.example file to a file named .env, and then edit it to fill in the details. Enter your Etherscan API key, your Ropsten node URL (eg from Alchemy), and the private key of the account which will send the deployment transaction. With a valid .env file in place, first deploy your contract:

```shell
hardhat run --network ropsten scripts/deploy.ts
```

Then, copy the deployment address and paste it in to replace `DEPLOYED_CONTRACT_ADDRESS` in this command:

```shell
npx hardhat verify --network ropsten DEPLOYED_CONTRACT_ADDRESS "Hello, Hardhat!"
```

# Performance optimizations

For faster runs of your tests and scripts, consider skipping ts-node's type checking by setting the environment variable `TS_NODE_TRANSPILE_ONLY` to `1` in hardhat's environment. For more details see [the documentation](https://hardhat.org/guides/typescript.html#performance-optimizations).
