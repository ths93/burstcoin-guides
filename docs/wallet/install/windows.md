Qbundle is a wrapper / launcher for the Burst Reference Software offering additional features such as plotting and mining tools, passphrase management and more. This tutorial is going to walk you through getting the Burst Core wallet completely set up using Qbundle on your Windows sytem.

## Prerequisites

- Most Recent Java Version
  - Select the download ending in “.exe”
    - [JRE](http://www.oracle.com/technetwork/java/javase/downloads/jre9-downloads-3848532.html)
- [Qbundle](https://github.com/PoC-Consortium/Qbundle/releases/)
  - Download “Qbundle_installer_[latest version].msi”

---

## Installation Steps

- Download all files listed above.
- Install Java JRE using the install wizards.
- Double click the Qbundle Installer file and follow the on screen instructions.
- A dialog box titled “Windows protected your PC” may pop up. This is typical with applications related to cryptocurrency.
  - Select “More info”.
  - Click “Run anyway”.
- Once the installer is finished, make sure the “Launch Qbundle” box is selected, and press “Finish”.
- If any of the necessary components are red, click “Download missing components”. Qbundle will find, download, and install all the programs you need.
- Once all components are green, click “Continue”
- A Windows firewall warning might popup. This happens with almost all cryptocurrency applications. Select “Allow Access”.
- At the top of the application window, select the menu item “Database”.
- Select “Change Database”.
- In the pop-up window select “Portable MariaDB”.
- Click “Next”.
- If a dialog box titled “Download MariaDB” pops up, select “Yes”.
- Allow the download to finish.
- In the window titled “Transition” select “No Copy”.
- Click “Save and close”.
- The wallet will now begin synchronizing the blockchain.

At this point the installation is finished, but you must leave the Qbundle running for it to complete the synchronization of the blockchain. If you do not have a wallet already you can create one now, but you will not be able to send or receive any transactions until the blockchain is fully synchronized. If you are trying to make a time sensitive transaction, use an online wallet. The same wallet used online will be available to use on your local wallet after the blockchain is synchronized.

## Qbundle Tips

- Checking for updates
  - File –> Check for updates
- “Account Manager” allows you to save your passphrase encrypted within the wallet for easy access.
  - Select “Manager” and enter the required information to add a new account to the wallet.
  - This feature is very useful, but should no be used for cold storage wallets.
  - To use saved accounts in the future, select “Login Account”, chose the target wallet, and enter the pin code to be automatically logged in.
- If you would like to keep the wallet running but do not want the wallet UI running, run Qbundle in “launcher” mode.
  - File –> Mode –> Launcher Mode## Burstcoin Core Wallet
