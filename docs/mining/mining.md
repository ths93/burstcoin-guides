## Introduction

This is the continuation of the "Pt.1 - plotting" tutorial. In this instructional we're going to configure Blago's CPU Mining Software to mine the plots you already generated on your machine.

**If you are using Qbundle, the software is included: just click “Tools” -> “Miner”.**

Otherwise, download Blago's miner and extract it to your desktop or the local directory of your choice:

[**Download on GitHub**](https://github.com/Blagodarenko/miner-burst/releases)

---

## Instructions

### Edit the miner.conf Document

Open the miner.conf document located in the Blago's miner directory with notepad. What you see here is a reference chart for the mining software to utilize when initializing the mining program.

!!! note ""
    "Mode" = whether your mining software uploads **deadline hashes** to a *pool* or directly to the burst network in *solo* mode.

!!! tip
    Pool mining is recommended unless you are mining with a very sizeable capacity (hundreds of terabytes).

As it is the miner.conf document is automatically designated to a fictitious pool. You must update the file to direct the software to the proper **web address** / **IP** and **port**. You can usually find this information directly on each pool website.

You can find a pool overview [here](http://burstcoin.cc/pool). Remember that spreading the capacity accross multiple pools is healthier for the network, so you may want to avoid the most crowded ones.

!!! warning
    Remember to always check if the pool suits the size of your plot files.

<strong>You must acquire the pools web address and port and propagate this information throughout the miner.conf document</strong>.

Let's say you want to mine on the [0-100 cryptoguru pool](https://0-100-pool.burst.cryptoguru.org/) (maintained by the PoC Consortium developers). Once completed, your miner.conf document should look like that:

```
{
   "Mode" : "pool",
   "Server" : "0-100-pool.burst.cryptoguru.org",
   "Port": "8124",

   "UpdaterAddr" : "0-100-pool.burst.cryptoguru.org",
   "UpdaterPort": "8124",

   "InfoAddr" : "0-100-pool.burst.cryptoguru.org",
   "InfoPort": "8124",

   "EnableProxy": false,
   "ProxyPort": 8126,

   "Paths":["C:\\plots","D:\\plots","G:\\plots","H:\\plots","I:\\plots","J:\\plots","K:\\plots","L:\\plots","N:\\plots","P:\\plots","R:\\plots","S:\\plots","T:\\plots","U:\\plots"],
   "CacheSize" : 10000,

   "Debug": true,
   "UseHDDWakeUp": true,

   "TargetDeadline": 80000000,

   "SendInterval": 100,
   "UpdateInterval": 950,

   "UseLog" : true, 
   "ShowWinner" : false, 
   "UseBoost" : false,

   "WinSizeX": 76,
   "WinSizeY": 60
}                        
```

Furthermore, beside "Paths" you will need to refer to all of your completely plotted plot files while maintaining the syntax properly.

So if your plot files are along the paths "C:\BURST\Plots" and "E:\BURST\Plots" then this line should look like this:

```
"Paths": ["C:\BURST\Plots","E:\BURST\Plots"]
```

Now that you have your miner.conf document prepared properly, **save it**.

### Create a passphrases.txt document

Let's create a passphrases.txt document within the Blagos directory

1. Create a new text document within the Blagos Burst Miner directory.
2. Paste your wallet's passphrase into the document.
3. Save the document as passphrases.txt

### Set the Reward Assignment

*By now you should already have selected the pool you wish to mine with.*

Setting a reward assignment for your wallet will allow the pool to collect your earnings and redistribute them automatically.

1. Copy the wallet address of the pool you want to mine with onto your clipboard
2. Go to this page: [set reward assignment](http://127.0.0.1:8125/rewardassignment.html).

!!! note
    **If you are using Qbundle, just click “Tools” -> “Reward recipient” instead.**

3. Enter the pool's BURST address and your mining wallet's passphrase in the respective fields.

The pool address for 0-100-pool.burst.cryptoguru.org is **888561138747819634**. This pool uses a numeric address, but others use a standard account ID ("BURST-XXX-...).

4. Click "submit". If it is successful, you will now have to wait 4 Blocks (16-20 minutes on average) until your assignment takes effect!

Now when your pool of choice is dividing up the Burst rewards among the miners it will automatically send your burstcoins to your Burst wallet.

### Run the mining software

Blagos should look like this when you start it up:

![Blagosstartup](https://steemitimages.com/0x0/https://steemitimages.com/DQmdk7Gf5dQ4yvXmy75Ah3uidjo8CYw8QsHbLot2KKobAmG/blagosstartup.png)

---

## Optional: going solo

If you prefer to mine solo then change the miner.conf document to look like this:

```
{
   "Mode" : "solo",
   "Server" : "localhost",
   "Port": "8125",

   "UpdaterAddr" : "localhost",
   "UpdaterPort": "8125",

   "InfoAddr" : "localhost",
   "InfoPort": "8125",

   "EnableProxy": false,
   "ProxyPort": 8126,

   "Paths":["C:\\plots","D:\\plots","G:\\plots","H:\\plots","I:\\plots","J:\\plots","K:\\plots","L:\\plots","N:\\plots","P:\\plots","R:\\plots","S:\\plots","T:\\plots","U:\\plots"],
   "CacheSize" : 10000,

   "Debug": true,
   "UseHDDWakeUp": true,

   "TargetDeadline": 80000000,

   "SendInterval": 100,
   "UpdateInterval": 950,

   "UseLog" : true, 
   "ShowWinner" : false, 
   "UseBoost" : false,

   "WinSizeX": 76,
   "WinSizeY": 60
}                        
```

You also need to set the reward assignment to your **own Burst wallet address**. Enter your own wallet address under "reward recipient", and your wallet's passphrase under "your secret passphrase".

Wait 4 block and start Blago's miner, it should look the same as above.

**Congratulations! You are now mining Burst!**
