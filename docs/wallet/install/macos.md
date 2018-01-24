In order to run the wallet locally, we need a database to store the blochchain information. The following guide shows the setup of MariaDB as database and the installation of the Burst Reference Software on MacOS.

## Prerequisites

- [Java](http://www.oracle.com/technetwork/java/javase/downloads/jre9-downloads-3848532.html)
- [Homebrew](https://brew.sh/)

---

## Setup MariaDB

MariaDB is used as database to store the blockchain. The following steps will guide you through the installation of MariaDB on MacOS.

First check that Xcode is up to date by typing the following and pressing enter.
```
xcode-select --install
```
After installing Xcode, install MariaDB by typing the following and pressing enter.
```
brew install mariadb
```
Once MariaDB is finished installing, start MariaDB with the following.
```
brew services start mariadb
```
---
### Database configuration

As soon as MariaDB is successfully installed, we can log into the MariaDB interface.

```
mysql -u root -p -h localhost
```

!!! Info
    The default password for MariaDB is blank. If it asks you for a password, simple press enter.

Now we create the database `burstwallet` for the blockchain.

```
CREATE DATABASE burstwallet;
```

In addition, we create a user which is used by the wallet to access the database. Replace `<your password>` with a password of your choice.
```
CREATE USER 'burstwallet'@'localhost' IDENTIFIED BY '<your password>';
```

Finally we, grant this user all privileges for the database `burstwallet`.
```
GRANT ALL PRIVILEGES ON burstwallet.* TO 'burstwallet'@'localhost';
```

---

## Setup Wallet

1. Now, download the `burstcoin-1.3.6cg.zip` file from the [Github release section](https://github.com/PoC-Consortium/burstcoin/releases)
2. Find the folder you downloaded from github titled `burstcoin-1.3.6cg.zip` and double click it. Archive utility will now extract it to a new folder.
3. Rename the extracted folder to `burstcoin`.
4. Open the `conf` folder inside the extracted folder
5. Right click the file `nxt-default.properties` and select "Open With --> TextEdit".
6. Find the following lines and enter `burstwallet` as database user and your password (assigned beforehand) as database password
```
nxt.dbUsername=burstwallet
nxt.dbPassword=<your password>
```
7. Move that folder to your home folder. This may appear as your username.
8. Back in terminal, navigate to the `burstcoin` folder.
```
cd ~/burstcoin
```
16. Make `burst.sh` executable.
```
chmod +x burst.sh
```
17. Now execute `burst.sh`. This is how you will start the wallet in the future. To execute this command you must be inside the burtscoin folder in the terminal.
```
./burst.sh
```
18. The wallet should now be running. In your web browser navigate to http://localhost:8125/ to access the wallet interface.

!!! Info
    At this point the installation is finished, but you must leave the terminal running for it to complete the synchronization of the blockchain. If you do not have a wallet already you can create one now, but you will not be able to send or receive any transactions until the blockchain is fully synchronized. If you are trying to make a time sensitive transaction, use an [online wallet](https://wallet.burst.cryptoguru.org:8125/index.html). The same wallet used online will be available to use on your local wallet after the blockchain is synchronized.
