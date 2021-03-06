## About the Bootstrap
The bootstrap file contains most of the current blockchain data in a downloadable zip file. You can use this data with your **Infinity Node** or **local wallet** to quickly sync. This method is much faster because you do not need to download every block over the p2p node network, which can take many hours or days depending on internet speed.

## Windows Bootstrap

To quickly re-sync your local Windows wallet follow the steps below:

- Download the latest bootstrap archive available:
https://github.com/SINOVATEblockchain/SIN-core/releases/latest/download/bootstrap.zip
- If open, close the wallet
- Go to your local SIN folder located at `%appdata%\SIN\`
	- (This defaults to `C:\Documents and Settings\YourUserName\Application data\SIN\` on Windows XP and to `C:\Users\YourUserName\Appdata\Roaming\SIN\` on Windows Vista, 7, 8, and 10.)
- Delete `blocks` and `chainstate` folders.
- Unzip the downloaded `bootstrap.zip` file
- Move the `blocks` and `chainstate` folders inside the SIN folder at `%appdata%\SIN\`
- Open the local wallet again.

## Linux CLI Bootstrap

In case you need to quickly sync the blockchain of your Infinity Node or linux wallet, follow the commented steps below:

```bash
# If running Infinity Node, stop it.
sudo systemctl stop sinovate.service

# install unzip package
sudo apt update && sudo apt install unzip

# remove old files and folders
rm -rf ~/.sin/{blocks,chainstate,debug.log,mnpayments.dat,mncache.dat,banlist.dat,peers.dat,netfulfilled.dat,governance.dat,fee_estimates.dat}

# download latest bootstrap archive
wget -O ~/bootstrap.zip https://github.com/SINOVATEblockchain/SIN-core/releases/latest/download/bootstrap.zip

# unzip the bootstrap archive
unzip ~/bootstrap.zip

# move bootstrap files
mv -t ~/.sin ~/bootstrap/blocks ~/bootstrap/chainstate

# remove unnecessary files
rm -rf ~/{bootstrap,bootstrap.zip}

# reboot infinitynode
sudo reboot
```