# Local ckUSDC Ledger 

This is a demo config repo for deploying a local icrc_1 token locally such as ckUSDC locally for demo pursposes. Remember to change the minter, initial balance and owner pricipals with your defualts in the `dfx.json` file before proceeding.

## Usage

1. Edit init_args and use your principal

```bash
dfx identity get-principal
# use this
```

2. Start local replica if you haven't already

```bash
dfx start --clean --background
```

3. Deploy ckUSDC

```bash
dfx deploy
# you can now call icrc_1 methods such as balance_of and transfer
 dfx canister call <DEPLOYED_CKUSDC_CANISTER_ID> icrc1_balance_of "(record { owner = principal \"<YOUR_PRINCIPAL>\"; })"
(1_000_000 : nat)

dfx canister call <DEPLOYED_CKUSDC_CANISTER_ID> icrc1_transfer '(
  record {
    to = record { owner = principal "<RECIPIENT_PRINCIPAL>"; };
    amount = 10_000;
  }
)'
```
