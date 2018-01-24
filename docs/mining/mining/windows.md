## Mining

In this section, Blago's CPU mining software is configured to mine the plots you already generated on your machine.

!!! Info
    If you are using Qbundle, the software is included: just click “Tools --> Miner”.

Otherwise, download Blago's miner and extract it to your desktop or the local directory of your choice:

### Prerequisites

* [Blago's Miner](https://github.com/Blagodarenko/miner-burst/releases)

---

Now you have to choose whether you are pool mining or solo mining.

!!! Info
    - A solo miner directly uploads his deadlines to the network - every time he forges a block, the entire block reward goes to him.
    - A pool miner redirects his earnings to a pool of miners; they are then redistributed following certain criterias to all miners in the pool. This way, you get rewarded even when you don't forge a block. On the other hand, you will receive less burstcoins when you forge a block yourself.

!!! tip
    Pool mining is recommended unless you are mining with a very sizeable capacity (hundreds of terabytes). There is no point in solo mining if you never forge any block!

---

### Pool mining

**Configuration**

Open the `miner.conf` file located in the Blago's miner directory with notepad. What you see here is a reference chart for the mining software to utilize when initializing the mining program.

By default, the `miner.conf` file points to a fictitious pool. You must replace the default values with respective values provided by a pool. Atleast the fields `Server`, `UpdaterAddr` and `InfoAddr` have to be adjusted accordingly.

!!! info
    You can find a pool overview [here](http://burstcoin.cc/pool). Remember that spreading the capacity across multiple pools is healthier for the network, so you may want to avoid the most crowded ones.

!!! warning
    Remember to always check if the pool suits the size of your plot files. Certain pools are better suited for small or large miners.

#### Example

Let's say you want to mine on the [0-100 cryptoguru pool](https://0-100-pool.burst.cryptoguru.org/) (a pool maintained by the PoC Consortium developers for miners of any size). Once completed, your `miner.conf` file should look like that:

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

Furthermore, with the `Paths` parameter, all directories containing plot files, which should be mined, have to be listed. E.g., if your plot files are along the paths `C:\BURST\Plots` and `E:\BURST\Plots` your configuration should look like this:

```
"Paths": ["C:\BURST\Plots","E:\BURST\Plots"]
```

#### Reward Assignment

*By now you should already have selected the pool you wish to mine with.*

Setting a reward assignment for your wallet will allow the pool to collect your earnings and redistribute them automatically.

1. Copy the wallet address of the pool you want to mine with onto your clipboard
2. Navigate to the wallet's reward assignment page: [Set reward assignment](http://127.0.0.1:8125/rewardassignment.html).

    !!! note
        **If you are using Qbundle, just click “Tools --> Reward recipient” instead.**

3. Enter the pool's BURST address and your mining wallet's passphrase in the respective fields.

The pool address for 0-100-pool.burst.cryptoguru.org is **888561138747819634**. This pool uses a numeric address, but others use a standard account ID ("BURST-XXX-...).

4. Click "submit". If it is successful, you will now have to wait 4 Blocks (16-20 minutes on average) until your assignment takes effect!

Now when your pool of choice is dividing up the Burst rewards among the miners it will automatically send your burstcoins to your Burst wallet.

#### Start Mining

Start Blago's miner. It should look like this when you start it up:

![Blagosstartup](https://steemitimages.com/0x0/https://steemitimages.com/DQmdk7Gf5dQ4yvXmy75Ah3uidjo8CYw8QsHbLot2KKobAmG/blagosstartup.png)

**Congratulations! You are now mining Burst!**

---

### Solo mining

Open the `miner.conf` file located in the Blago's miner directory with notepad. What you see here is a reference chart for the mining software to utilize when initializing the mining program.

If you want to mine solo, modify your `miner.conf` similiar to the following:

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

You also need to set the reward assignment to your **own Burst wallet address**.

Navigate to the wallet's reward assignment page: [Set reward assignment](http://127.0.0.1:8125/rewardassignment.html).

!!! note
    **If you are using Qbundle, just click “Tools --> Reward recipient” instead.**

Enter your own wallet address under "reward recipient", and your wallet's passphrase under "your secret passphrase". Click "submit".

Wait 4 block and start Blago's miner, it should look similar to the mining image above.

!!! info
    We recommend solo mining with an accumulated disk size with at least 200TB!

**Congratulations! You are now mining Burst!**
