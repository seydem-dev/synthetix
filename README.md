# WETH

**Wrapped Ether is, like the name says, Ether, but wrapped.** 

**Well, it's not literally wrapped in something, but you can imagine that if certain transactions want to be made with ETH, you have to wrap it. Why? Because ETH is not an ERC20 and since ERC20 is the industry standard and pretty much supported by every protocol, you wrap ETH into an ERC20, hence the "Wrapped" before Ether. ETH now acts as an ERC20 and you can successfully do whatever you wanted to, unless there's a problem with the application you're interacting with 😵**

```
Deposit
```
*Deposit event acts like a deposit state variable. But why is it an event then? Because events require less gas than storage variables. Events don't actually get stored in storage, otherwise they wouldn't be cheaper. They aren't accessible to the smart contract, but they're basically pointing to the contract address. Events are stored in LOGS and they are restricted to their parameters, that's why you have to `emit` them.*

```
Withdraw
```
*Withdraw your deposited ETH, but burn all withdrawed WETH in return.*

```
deposit()
```
*Function that allows users to deposit their ETH and mint WETH in return.*

```
withdraw()
```
*Function that allows users to withdraw their ETH, but burn their current WETH.*

```
receive()
```
*Receive is called when users directly send ETH to the smart contract. Since receive implements `deposit()`, it enables users to deposit their ETH and receive WETH in return by sending ETH to the smart contract directly.*
