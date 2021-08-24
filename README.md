# SORA Network validator auto payout

Claim and distribute validator staking rewards for your stakers automagically in SORA Substrate blockchain.

Made with ❤️ from ColmenaLabs_SVQ! and adapted to SORA-XOR Network by Jimi Flowers

## Install

Needs nodejs (>= v10.20.1), check https://nodejs.org/en/download/ to install for your platform.

Clone the repository and install the needed dependencies:

```
git clone https://github.com/FlowerStake/sora-xor-validator-auto-payout.git
cd sora-xor-validator-auto-payout
yarn
```

Go to [Polkadot JS UI](https://polkadot.js.org/apps/#/accounts) and export the account you want to use to json format, then copy the json file/s in the `keystores` folder.

## Usage

Using parameters:

```
node autopayout.js -a keystores/account.json -p password -v validator_stash_address
```

Ask for password:

```
node autopayout.js -a keystores/account.json -v validator_stash_address
```

Or simply edit `config.js` with your data and run without any parameter (cron friendly):

```
node autopayout.js
```
Example output:

```
 Substrate auto payout

 - Check source at https://github.com/FlowerStake/sora-xor-validator-auto-payout
 - Made with love from ColmenaLabs_SVQ https://colmenalabs.org/ and adapted to SORA-XOR Network by Jimi Flowers

 -> Validator stash address is cnUDwD4nPorodyd3inwThA2yBt2dFuHTfnvKowH6dirk47Qqr
 -> Importing account cnTYVPiZahYwoc4nF9PuzQNERbZeADFYvwSMsTg72iT6ZFqFS
 -> Connecting to wss://kusama-rpc.polkadot.io
 -> Account cnTYVPiZahYwoc4nF9PuzQNERbZeADFYvwSMsTg72iT6ZFqFS free balance is 32.58 kXOR
 -> Current era is 330
 -> Unclaimed eras: [328,329]
 -> Claiming Era: 328
    Payout Success!
 -> Claiming Era: 329
    Payout Success!

```


NOTE: Set `config.js` file permissions to `600` for better security.

TODO: It doesn't take in account ongoing elections yet!

## Using multiple validators

Edit `validators` array in `config.js` to add the stash address of your validators, then:

```
node autopayout-validators.js
```
