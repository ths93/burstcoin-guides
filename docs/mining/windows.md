## Introduction

In order to mine Burst, you first have to plot the disk space you want to use. This is the only time and energy-consuming manipulation but it only has to be done once.

This tutorial will teach you how to plot your drives with [XPlotter](https://github.com/Blagodarenko/XPlotter/releases).

!!! info
    With Qbundle, the software is already included: just click "Tools" -> "Plotter". A guide is also present in the plotter page - it is recommended to follow the instructions detailed there.

If you want to use the software as a standalone, follow the instructions here.

The disk space you dedicate to Burst can't be used otherwise once plotted (unless you delete the plot files) so make sure you can truly afford the space dedicated to mining Burst.

HDD disk space will be occupied by **plot files**. Plot files are like bingo cards that contain pre-solved responses to the cryptographic problem that the blockchain poses to miners each and every round.

!!! tip
    Find out how much you can make with the capacity at your disposal using a [mining calculator](https://explore.burst.cryptoguru.org/tool/calculate).

Plotting the disk space you wish to dedicate to mining Burst can be accomplished multiple ways but in this tutorial we will be using XPlotter, a CPU based plotter (in contrast to GPU based plotting software) that automatically create optimized plot files. This means your plot files will be of the highest possible quality and efficiency.

---

## Plotting

### Prerequisites

* [XPlotter](https://github.com/Blagodarenko/XPlotter/releases)

### Configuration

!!! info "Plot files"
    There are a few things you have to understand to get a general overview of the nature of plot files.

    Plot files consist of **nonces** which contain the cryptographic solutions you will be mining with.

    * **1 nonce = 262144 bytes**

    Plot file size is measured in nonces so you will have to convert the size of your dedicated disk space to nonces. Nonce calculators exist to make this process easier.

    Nonces are ordered **linearly** in **sequential order**. the number they're assigned to is arbitrary but they should **never overlap** (overlapping reduces plot efficiency and triggers an error in most mining software).

    With Xplotter, that is all the technical knowledge you need to operate the software and to create an optimized plot file.


To execute Xplotter, it is necessary to create a run script - `run.bat`. This batch contains the parameters for Xplotter, e.g. where and how much to plot and the resources to consume to do so.

1. Go into the Xplotter directory and create a new file called `run.bat` with your preferred text editor (Notepad / Notepad++). Copy & Paste the following command into the file:

```
@setlocal
@cd /d %~dp0
XPlotter_avx.exe -id <your numeric account ID> -sn <starting nonce> -n <total nonces> -t <threads to use> -path <path>Z:\plots -mem <amount of RAM to use>
```

Replace the parameters according to your needs.

+ `-id <your numeric account ID>`

    This can be found by clicking your account's name in your wallet and copying the numeric account ID.

+ `-sn <starting nonce>`

    If this is your first time ever plotting it is recommended to start your nonce with 0 (ZERO).

+ `-n <total nonces>`

+ `-t <threads to use>`

    This refers to your machine's CPU architecture: if your CPU has multiple cores you can use them, otherwise put '1' here.

+ `-P <path>`

    where you want to store your plot files (for example 'D:/Burst/Plots', but any path will suffice).

+ `-mem <amount of RAM to use>`

    The amount of RAM in gigabytes you wish to utilize during this process.

!!! warning
    Never exceed recommended RAM usage! Always leave around 20% remaining RAM for remedial tasks.

!!! tip "Example"
    Your file content should look similiar to the following lines.
    ```
    @setlocal
    @cd /d %~dp0
    XPlotter_avx.exe -id 17559140197979902351 -sn 0 -n 20000 -t 4 -path F:\burst\plots -mem 5G
    ```

### Start Plotting

Once you have filled out the `run.bat` file, Xplotter is ready to plot your available hard disk space within the resources you wish to allocate. You can now save the file as `run.bat` in the Xplotter directory.

To maximize Xplotter's plotting power you're going to want to right click `run.bat` and select 'run as an administrator'.

You should see something similar to this:

![plottinginterface](https://steemitimages.com/0x0/https://steemitimages.com/DQmZk7KmZ1WMMfCbY61kEf23rRJaXSzKSbi31Ux4KYejZF6/xplotter1.png)

The plotting process will consume a great deal of resources if done correctly. You want to plot as fast as possible so raise the RAM and thread count as much as you reasonably can.

This may take a while depending on the size of your plot but you can run multiple instances of Xplotter if you have multi threading!


!!! Tip "Tips"
    - Add one to the last nonce to get the starting nonce of your next plot file. remember sequential is good, overlapping is bad.
    - Keep a record of your command line(s) that you're currently using so that if you need to pause Xplotter you can re-initiate the same plot by executing the EXACT same command!
    - Repeat these steps if you'd like to create multiple plot files. We recommend you make your plot files large but not bigger than a few TB as encountering an error after hours or days of plotting can be very frustrating.

---

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
