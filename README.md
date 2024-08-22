# Cartesi Wallet Template in JS/TS

This is a simple application that uses Deroll JS/TS framework to handle below functions:

1. Deposit Ether
2. Inspect balance
3. Withdraw Ether

## Steps to run

Pre-requisite: Cartesi CLI and Docker Desktop

Clone this repo in your local, open terminal inside the root of this project and hit:

```
cartesi build
```

after a successful build, you can run the node by:

```
cartesi run --epoch-duration 30
```

Above command will also keep epoch-duration as 30s to test voucher execution in a quicker way.

## Sending inputs

Now to deposit some ether inside your cartesi app, open another terminal tab and you can use `send` command. Follow the guided instructions to deposit a desired amount in eth:

```
cartesi send
```

To check your balance after the deposit, you can directly use curl request inside your terminal:

```
curl http://localhost:8080/inspect/balance/<eth-address-here>
```

To withdraw, use `cartesi send` with a generic input JSON string. For example to withdraw 2 eth, use:

```
{"method":"ether_withdraw", "amount":"2000000000000000000"}
```

After a successful withdraw request, look for the `voucher` created against your latest input in the local rollups explorer. Open below url in your browser.

```
http://localhost:8080/explorer
```

In the explorer, every voucher gives you an execute button to trigger on-chain action to finally transfer amount back to your base chain wallet.
