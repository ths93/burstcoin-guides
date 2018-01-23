<div class="row sqs-row">
<div class="col sqs-col-4 span-4">
<div id="block-41e744f5f35da5df192a" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<h2>What You Need</h2>
</div>
</div>
</div>
<div class="col sqs-col-8 span-8">
<div id="block-98c1cc63f7491b15750e" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<ul>
 	<li>Most Recent Java Version.
<ul>
 	<li>Select the download ending in ".dmg".
<ul>
 	<li><a href="http://www.oracle.com/technetwork/java/javase/downloads/jre9-downloads-3848532.html" target="_blank" rel="noopener">JRE</a></li>
</ul>
</li>
</ul>
</li>
 	<li>Homebrew
<ul>
 	<li>You will install this directly from the terminal.</li>
 	<li>This is a macOS package installer, for more information see <a href="https://brew.sh/" target="_blank" rel="noopener">brew.sh</a>.</li>
</ul>
</li>
 	<li>MariaDB
<ul>
 	<li>You will also install this directly from the terminal.</li>
</ul>
</li>
 	<li><a href="https://github.com/PoC-Consortium/burstcoin/releases" target="_blank" rel="noopener">Burst Wallet v1.3.6cg Release Files</a></li>
</ul>
</div>
</div>
</div>
</div>
<div class="row sqs-row">
<div class="col sqs-col-12 span-12">
<div id="block-yui_3_17_2_4_1514586803480_15849" class="sqs-block horizontalrule-block sqs-block-horizontalrule" data-block-type="47">
<div class="sqs-block-content">

<hr />

</div>
</div>
</div>
</div>
<div class="row sqs-row">
<div class="col sqs-col-4 span-4">
<div id="block-8c2a1474ffebfac68c15" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<h2>Local Wallet Install Steps</h2>
</div>
</div>
</div>
<div class="col sqs-col-8 span-8">
<div id="block-bc6c0d11d01687d662b4" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<ol>
 	<li>Download and install the latest Java version using the Java install wizard.</li>
 	<li>Open Terminal.</li>
 	<li>Install brew by pasting the following into Terminal and pressing enter.
<ul>
 	<li>
<pre>/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"</pre>
</li>
 	<li>Before installing, it will tell you exactly what it will change, and asks for your confirmation of install.</li>
 	<li>Enter your computer's login password and press enter.</li>
 	<li>Allow the install to finish.</li>
</ul>
</li>
 	<li>Now install MariaDB.
<ul>
 	<li>First check that Xcode is up to date by typing the following and pressing enter.</li>
 	<li>
<pre>xcode-select --install</pre>
</li>
 	<li>After installing xcode, install MariaDB by typing the following and pressing enter.</li>
 	<li>
<pre>brew install mariadb</pre>
</li>
</ul>
</li>
 	<li>Once MariaDB is finished installing, start MariaDB with the following.
<ul>
 	<li>
<pre>brew services start mariadb</pre>
</li>
</ul>
</li>
 	<li>Now you will create the database for the blockchain.
<ul dir="ltr">
 	<li>Log into MariaDB by typing the following in.
<ul>
 	<li>
<pre>mysql -u root -p -h localhost</pre>
</li>
</ul>
</li>
 	<li>The default password for MariaDB is blank. If it asks you for a password, simple press enter.</li>
 	<li>Type the following, one line at a time, pressing enter between lines.
<ul>
 	<li>
<pre>CREATE USER 'burstwallet'@'localhost' IDENTIFIED BY 'password';</pre>
<ul>
 	<li>Make sure to replace "password" with a password of your choice.</li>
</ul>
</li>
 	<li>
<pre>GRANT ALL PRIVILEGES ON burstwallet.* TO 'burstwallet'@'localhost';</pre>
</li>
 	<li>
<pre>CREATE DATABASE burstwallet;</pre>
</li>
</ul>
</li>
</ul>
</li>
 	<li>Press ctr + c to exit.</li>
 	<li>Find the folder you downloaded from github titled "burstcoin-1.3.6cg.zip" and double click it. Archive utility will now extract it to a new folder.</li>
 	<li>Rename the extracted folder to "burstcoin".</li>
 	<li>Open the folder.</li>
 	<li>Open the "conf" folder.</li>
 	<li>Right click the file "nxt-default.properties" and select "Open With --&gt; TextEdit".</li>
 	<li>Find the lines...
<ul>
 	<li>"nxt.dbUsername="
<ul>
 	<li>Enter "burstwallet" after the equals sign.</li>
</ul>
</li>
 	<li>"nxt.dbPassword="
<ul>
 	<li>Enter the password you assigned to the MariaDB database (in step 6 part 2) after the equals sign.</li>
</ul>
</li>
</ul>
</li>
 	<li>Move that folder to your home folder. This may appear as your username.</li>
 	<li>Back in terminal, navigate to the burstcoin folder by typing the follwoing and pressing enter.
<ul>
 	<li>
<pre>cd ~/burstcoin</pre>
</li>
</ul>
</li>
 	<li>Set "burst.sh" as executable by typing the following and pressing enter.
<ul>
 	<li>
<pre>chmod +x burst.sh</pre>
</li>
</ul>
</li>
 	<li>Now execute "burst.sh" by typing the following and pressing enter. This is how you will start the wallet in the future. To execute this command you must be inside the burtscoin folder in the terminal (refer to step 15).
<ul>
 	<li>
<pre>./burst.sh</pre>
</li>
</ul>
</li>
 	<li>The wallet should now be running. In any web browser type the following in the url field and press enter to access the wallet interface.
<ul>
 	<li>
<pre>http://localhost:8125/</pre>
</li>
</ul>
</li>
</ol>
At this point the installation is finished, but you must leave the terminal running for it to complete the synchronization of the blockchain. If you do not have a wallet already you can create one now, but you will not be able to send or receive any transactions until the blockchain is fully synchronized. If you are trying to make a time sensitive transaction, use an <a href="https://wallet.burst.cryptoguru.org:8125/index.html" target="_blank" rel="noopener">online wallet</a>. The same wallet used online will be available to use on your local wallet after the blockchain is synchronized.

</div>
</div>
</div>
</div>
