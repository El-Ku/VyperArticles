# How to Deploy your Vyper contract to testnet from Remix and Verify the source on Etherscan?

### 1. Get the code compiled
If this is your first time compiling a vyper contract in Remix, follow the steps from [here](https://github.com/El-Ku/VyperArticles/blob/main/compiling_vyper_contracts_in_remix.md) to compile the smart contract you want to deploy to testnet. 

### 2. Connect Metamask to your ethereum network

From `DEPLOY & RUN TRANSACTIONS`, select `Injected Provider-MetaMask`. Enter your password and choose the account you want to connect to Remix. 

![image](https://github.com/El-Ku/VyperArticles/assets/46983244/c80461c9-e8e6-4b2e-8262-e3f0c97dd318)


### 3. Deploy the contract as usual

Deploy the contract as usual. You can read and write the contract right from Metamask as well, just like you do when its deployed on a local network. 

### 4. Verify the contract on Etherscan

1. Paste the deployed contract address in etherscan website search bar. For me it was [0x71E0b7E9d8545212cb138Ba6794Ce5D659Ad025A](https://sepolia.etherscan.io/address/0x71E0b7E9d8545212cb138Ba6794Ce5D659Ad025A#code)
2. Go to the contract tab and click on `Verify & Publish Contract`. 
3. Select the compiler type to `Vyper(Experimental)`, compiler version to match the one in the source code and a license type of your choice. 
4. Click on `Continue` and paste the source code in the text box provided. 
5. On Remix window, under the Deploy section, there is a button called `Parameters`. Click that to copy the `Constructor arguments`. And paste it in the next text box provided in etherscan without the `0x` (very important).
6. Click on `Verify` and thats it. You can check how it looks from this [contract](https://sepolia.etherscan.io/address/0x71e0b7e9d8545212cb138ba6794ce5d659ad025a#code) I deployed. 
