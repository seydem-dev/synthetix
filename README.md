# WETH

**Wrapped ETH is, like the name says, Ether, but wrapped.** 

**Well, it's not literally wrapped in something, but you can imagine that if certain transactions want to be made with an ETH, you have to wrap it. Why? Because ETH is not an ERC20 and since ERC20 is the industry standard, you wrap ETH into an ERC20. ETH now acts as an ERC20 and you can successfully do what you initially wanted to. Unless there's a problem with the DAPP you're interacting with 😨**

```
Deposit
```
*Deposit event acts like a deposit state variable. But why is it an event then? Because events require less gas than storage variables. Events don't actually get stored in storage or else they wouldn't be cheaper. They aren't accessible to the smart contract, but they're basically mapped to the contract address and they're stored in LOGS. Events can really only do one thing, that's why you have to `emit` them.*

```
Withdraw
```
*Same as deposit, except you're doing the oppsoite, which is withdrawing.*

```
deposit()
```
*Function that allows users to deposit their ETH and mint WETH in return.*

```
withdraw()
```
*Function that allows users to withdraw their ETH, but burns their WETH.*

```
fallback()
```
*Fallback is called when users directly send ETH to the smart contract. Since fallback includes `deposit()`, users have the option to indirectly deposit their ETH, by sending ETH to the smart contract directly.*
