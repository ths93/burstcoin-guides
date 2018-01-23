### What You Need

- Most Recent Java Version.
  - Select the download ending in ".dmg".
    - [JRE](http://www.oracle.com/technetwork/java/javase/downloads/jre9-downloads-3848532.html)
- Homebrew
  - You will install this directly from the terminal.
  - This is a macOS package installer, for more information see [brew.sh](https://brew.sh/)
- MariaDB
  - You will also install this directly from the terminal.
- [Burst Wallet v1.3.6cg Release Files](https://github.com/PoC-Consortium/burstcoin/releases)</a>

---

### Local Wallet Install Steps

1. Download and install the latest Java version using the Java install wizard.
2. Open Terminal.
3. Install brew by pasting the following into Terminal and pressing enter.

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  - Before installing, it will tell you exactly what it will change, and asks for your confirmation of install.
  - Enter your computer's login password and press enter.
  - Allow the install to finish.
4. Now install MariaDB.
  - First check that Xcode is up to date by typing the following and pressing enter.

    xcode-select --install

 	- After installing xcode, install MariaDB by typing the following and pressing enter.

    brew install mariadb

5. Once MariaDB is finished installing, start MariaDB with the following.

    brew services start mariadb

6. Now you will create the database for the blockchain.
  - Log into MariaDB by typing the following in.
  
    mysql -u root -p -h localhost

  - The default password for MariaDB is blank. If it asks you for a password, simple press enter.
 	- Type the following, one line at a time, pressing enter between lines.

    CREATE USER 'burstwallet'@'localhost' IDENTIFIED BY 'password';

    - Make sure to replace "password" with a password of your choice.

    GRANT ALL PRIVILEGES ON burstwallet.* TO 'burstwallet'@'localhost';

    CREATE DATABASE burstwallet;

7. Press ctr + c to exit.
8. Find the folder you downloaded from github titled "burstcoin-1.3.6cg.zip" and double click it. Archive utility will now extract it to a new folder.
9. Rename the extracted folder to "burstcoin".
10. Open the folder.
11. Open the "conf" folder.
12. Right click the file "nxt-default.properties" and select "Open With --&gt; TextEdit".
13. Find the lines...
  - "nxt.dbUsername="
    - Enter "burstwallet" after the equals sign.
  - "nxt.dbPassword="
    - Enter the password you assigned to the MariaDB database (in step 6 part 2) after the equals sign.
14. Move that folder to your home folder. This may appear as your username.
15. Back in terminal, navigate to the burstcoin folder by typing the follwoing and pressing enter.

    cd ~/burstcoin

16. Set "burst.sh" as executable by typing the following and pressing enter.

    chmod +x burst.sh

17. Now execute "burst.sh" by typing the following and pressing enter. This is how you will start the wallet in the future. To execute this command you must be inside the burtscoin folder in the terminal (refer to step 15).

    ./burst.sh

18. The wallet should now be running. In any web browser type the following in the url field and press enter to access the wallet interface.

    http://localhost:8125/

At this point the installation is finished, but you must leave the terminal running for it to complete the synchronization of the blockchain. If you do not have a wallet already you can create one now, but you will not be able to send or receive any transactions until the blockchain is fully synchronized. If you are trying to make a time sensitive transaction, use an [online wallet](https://wallet.burst.cryptoguru.org:8125/index.html). The same wallet used online will be available to use on your local wallet after the blockchain is synchronized.
