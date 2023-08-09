# How to compile your Vyper smart contracts in Remix?


If you are coming from Solidity background, you would have mostly started your Solidity journey with Remix online compiler. Its an amazing tool and fortunately Vyper too can be compiled and deployed with Remix. Here is how...

#### 1. Go to [https://remix.ethereum.org/](https://remix.ethereum.org/)
#### 2. Activate Vyper plugin
We need to activate a Vyper plugin to be able to work on Vyper smart contracts using Remix. For this, at the left bottom corner of the screen, click on the `Plugin Manager` and then scroll down to see the `activate` option on Vyper as shown in the screenshot. This will activate the Vyper compiler plugin. 

![Pasted image 20230809174709](https://github.com/El-Ku/VyperArticles/assets/46983244/8f2e79e3-3554-4140-ae7a-063ef745c83f)

#### 3. Create Vyper file
Next let's create a Vyper file for checking if this really works. Go to `File Explorer` and create a new vyper file, lets say `test.vy`. 

![Pasted image 20230809174859](https://github.com/El-Ku/VyperArticles/assets/46983244/6af262e2-dcfd-4907-9acb-d0e0f38d1658)

  You could copy the following code into it:
  
  ```python
  # @version 0.3.9
  
  @external
  def get_value() -> uint256:
      return 100
  ```

#### 4. Two ways to compile the contract
Next step is to try and compile this code. Click on the Vyper icon on the left panel, as marked by the red circle. You will get two options at this stage.

![Pasted image 20230809174914](https://github.com/El-Ku/VyperArticles/assets/46983244/da850f7c-046d-4513-ae1e-99f7efc2a8ad)

   1. The quick option is to use the remote compiler which can compile Vyper contracts upto version 0.2.16 (as of now). If you choose that option when trying to compile a higher vyper versioned contract you will get the following kind of error.

		```bash
		line 1:0 Version specification "0.3.9" is not compatible with compiler version "0.2.16"
		```

   2. If you insist on compiling at the latest version of Vyper, you have to use the `Local Compiler`. For this you need to install Vyper on your local machine and connect it with Remix. Lets see how to do that.
      1. Install Python 3.11 (the latest version at the moment) from [here](https://www.python.org/downloads/).
      2. Create a virtual environment using `venv`. This is where we will install the Vyper compiler. This is important, as installing many python packages might mess up the system configuration. Follow instructions from [here](https://docs.python.org/3/library/venv.html).
			For me (Ubuntu 22.04 on WSL2) the following commands does the job:
			
			```bash
			sudo python3 -m venv venv_name  # create a venv
			source venv_name/bin/activate   # activate the venv
			deactivate                      # deactivate or exit it
			```
      3. After activating the `venv`, install Vyper. Follow the commands from [here](https://docs.vyperlang.org/en/latest/installing-vyper.html#id1).
      4. Start the `server` for Vyper compiler by running the following command:
	
		```bash
		   vyper-serve
		```
      5. On Remix, click on `LOCAL COMPILER` option. Enter the `Local Compiler Url` as follows: 
	   `http://localhost:8000/compile`
      6. Click on compile. The contract should have compiled successfully now and the following kind of output is shown:
	
	   ![Pasted image 20230809184842](https://github.com/El-Ku/VyperArticles/assets/46983244/742598db-66ed-40bd-90be-08e1be0002f9)
#### 5. Deploying the contract
The contract could be deployed the same way you would deploy a solidity smart contract. Just go to the `DEPLOY & RUN TRANSACTIONS` tab and select the contract and click on `Deploy`.
