# Empower Chain Testnet IBC Tasks
[Empower Testnet Explorer](https://empowerchain.exploreme.pro/dashboard)

## 1) IBC Transfer [EMPOWER-COSMOS] channel-2 <> channel-2765 
     
### install go v1.20
```
ver="1.20"
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
go version
```

### install Cosmos binaries
```
git clone https://github.com/cosmos/gaia cosmos
cd cosmos
git checkout v10.0.1
make install
```

### We create a Cosmos wallet (don't forget to register Mnemonics)
```
gaiad keys add walletname
```

### Let's move on to the tasks now :)
### We need some Atom for the mission. 
### Get osmo here.https://faucet.osmotest5.osmosis.zone/
### Swap some of it to atom from here
### https://frontier.osmosis.zone/?from=ATOM&to=OSMO
### Use the rest in the osmo mission
### Empower —> Cosmos transfer ($MPWR)
```
empowerd tx ibc-transfer transfer transfer channel-2 $COSMOS_WALLET_ADDRESS 100000umpwr --from=$WALLET --chain-id circulus-1 --packet-timeout-height 0-0 --fees 5000umpwr
```

### Cosmos —> Empower halfback transfer ($MPWR)
```
gaiad tx ibc-transfer transfer transfer channel-2765 <empower-wallet-address> 50000ibc/C3D75AA5082B8EEC8E6DE916F0CA9C1C71978A6BB0FA5AAE3E5ABE81BAF57B42 --from=$COSMOS_WALLET --fees 5000uatom --chain-id theta-testnet-001 --node https://rpc.state-sync-01.theta-testnet.polypore.xyz:443
```

### Cosmos —> Empower transfer ($ATOM)
```
gaiad tx ibc-transfer transfer transfer channel-2765 <empower-wallet-address> 100000uatom --from=$COSMOS_WALLET --fees 5000uatom --chain-id theta-testnet-001 --node https://rpc.state-sync-01.theta-testnet.polypore.xyz:443
```

[Cosmos Testnet Explorer](https://testnet.mintscan.io/cosmoshub-testnet)

---------------------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------------------

## 2) IBC Transfer [EMPOWER-STARGAZE] channel-1 <> channel-459
### install go v1.20
```
ver="1.20"
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
go version
```

### install Stargaze binaries
```
git clone https://github.com/public-awesome/stargaze stargaze
cd stargaze
git checkout v10.0.0-beta.1
make install
```

### We create a Stargaze wallet (don't forget to register Mnemonics)
```
starsd keys add walletname
```
### For stargaze tokens, you can go to the discord and request a testtoken from faucet.
### https://discord.com/channels/755548171941445642/940653213022031912

### Empower —> Stargaze transfer ($MPWR)
```
empowerd tx ibc-transfer transfer transfer channel-1 $STARGAZE_WALLET_ADDRESS 100000umpwr --from=$WALLET --chain-id circulus-1 --packet-timeout-height 0-0 --fees 200umpwr
```

### Stargaze —> Empower halfback transfer ($MPWR)
```
starsd tx ibc-transfer transfer transfer channel-459 <empower-wallet-address> 50000ibc/B077B9DE697E073055B12CEB81C0FBF259A2D418230FDF51EB348CDAD8D65FE8 --from=$STARGAZE_WALLET --fees 2000ustars --chain-id elgafar-1 --node https://stargaze-testnet-rpc.polkachu.com:443
```

### Stargaze —> Empower transfer ($STARS)
```
starsd tx ibc-transfer transfer transfer channel-459 <empower-wallet-address> 100000ustars --from=$STARGAZE_WALLET --fees 2000ustars --chain-id elgafar-1 --node https://stargaze-testnet-rpc.polkachu.com:443
```

[Stargaze Testnet Explorer](https://testnet-explorer.publicawesome.dev/stargaze)

---------------------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------------------

## 3) IBC Transfer [EMPOWER-OSMOSIS] channel-0 <> channel-155
### install go v1.19
```
ver="1.19"
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
go version
```

### install Osmosis binaries
```
git clone https://github.com/osmosis-labs/osmosis osmosis
cd osmosis
git checkout v15.1.0-testnet
make install
```

### We create a Osmo wallet (don't forget to register Mnemonics)
```
osmosisd keys add walletname

```

### Empower —> Osmosis transfer ($MPWR)
```
empowerd tx ibc-transfer transfer transfer channel-0 $OSMOSIS_WALLET_ADDRESS 100000umpwr --from=$WALLET --chain-id circulus-1 --packet-timeout-height 0-0 --fees 200umpwr
```

### Osmosis —> Empower halfback transfer ($MPWR)


```
tx ibc-transfer transfer transfer channel-155 <empower-wallet-address> 50000ibc/E0FDA81C892EEA14C2398519260AA706A068B36AE5BE8AE9FAD8EB1540A6E02E --from=$OSMOSIS_WALLET --fees 5000uosmo --chain-id osmo-test-5 --node https://rpc.osmotest5.osmosis.zone:443
```

### Osmosis —> Empower transfer ($aUSDC) (before to do this task, you must swap your $OSMO to $axUSDC in https://testnet.osmosis.zone/?from=OSMO&to=aUSDC)
```
osmosisd tx ibc-transfer transfer transfer channel-155 <empower-wallet-address> 100000ibc/6F34E1BD664C36CE49ACC28E60D62559A5F96C4F9A6CCE4FC5A67B2852E24CFE --from=$OSMOSIS_WALLET --fees 5000uosmo --chain-id osmo-test-5 --node https://rpc.osmotest5.osmosis.zone:443
```

### Osmosis —> Empower transfer ($OSMO)
```
osmosisd tx ibc-transfer transfer transfer channel-155 <empower-wallet-address> 100000uosmo --from=$OSMOSIS_WALLET --fees 5000uosmo --chain-id osmo-test-5 --node https://rpc.osmotest5.osmosis.zone:443
```

[Osmosis Testnet Explorer](https://testnet.mintscan.io/osmosis-testnet)


### That's all for all the tasks.... Do not forget to fill out the form after completing these procedures.

 https://forms.gle/JJDeX5AVaZnznvqv8

 ### EĞER REHBER İŞİNİZE YARADIYSA VE BEĞENDİYSENİZ FORKLAR VE YILDIZLARSANIZ SEVİNİRİM :))

