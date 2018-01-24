## Introduction

In order to mine Burst, you first have to plot the disk space you want to use. This is the only time and energy-consuming manipulation but it only has to be done once.

This tutorial will teach you how to plot your drives with [XPlotter](https://github.com/Blagodarenko/XPlotter/releases).

!!! info
    With Qbundle, the software is already included: just click "Tools" -> "Plotter". A guide is also present in the plotter page - it is recommended to follow the instructions detailed there.

If you want to use the software as a standalone, follow the instructions here.

The disk space you dedicate to Burst can't be used otherwise once plotted (unless you delete the plot files) so make sure you can truly afford the space dedicated to mining Burst.

HDD disk space will be occupied by **plot Files**. Plot files are like bingo cards that contain pre-solved responses to the cryptographic problem that the blockchain poses to miners each and every round.

Plotting the disk space you wish to dedicate to mining Burst can be accomplished multiple ways but in this tutorial we will be using XPlotter, a CPU based plotter (in contrast to GPU based plotting software) that automatically create optimized plot files. This means your plot files will be of the highest possible quality and efficiency.

---

## Instructions

Download XPlotter and extract it to your desktop or a local directory of your choice.

[**Download on GitHub**](https://github.com/Blagodarenko/XPlotter/releases)

### What is a plot file?

There are a few things you have to understand to get a general overview of the nature of plot files.

Plot files consist of **nonces** which contain the cryptographic solutions you will be mining with.

!!! info
    **1 nonce = 262144 bytes**

Plot file size is measured in nonces so you will have to convert the size of your dedicated disk space to nonces. Nonce calculators exist to make this process easier.

!!! info
    Nonces are ordered **linearly** in **sequential order**. the number they're assigned to is arbitrary but they should **never overlap** (overlapping reduces plot efficiency and triggers an error in most mining software).

With Xplotter, that is all the technical knowledge you need to operate the software and to create an optimized plot file.

### Plotting your drive

To execute Xplotter we will have to create a text document and save it as **run.bat**. this batch file will tell Xplotter where and how much to plot and the resources to consume to do so. Follow the next instructions closely:

1. Go into the Xplotter directory and create a new text document and paste this command line into the notepad :

```
@setlocal
@cd /d %~dp0
XPlotter_avx.exe -id XXXXXXXXXXXXXX -sn O -n P -t Q -path Z:\plots -mem yG
```

We will now fill in the blanks regarding the variables in italics.

+ **-id** = your numeric account ID. This can be found by clicking your account's name in your wallet and copying the numeric account ID.
+ **-sn** = Starting Nonce. If this is your first time ever plotting it is recommended to start your nonce with 0 (ZERO).
+ **-n** = total nonces
+ **-t** = threads. This refers to your machine's CPU architecture: if your CPU has multiple cores you can use them, otherwise put '1' here.
+ **-P** = path: where you want to store your plot files (for example 'D:/Burst/Plots', but any path will suffice).
+ **-mem** = The amount of RAM in gigabytes you wish to utilize during this process.

!!! warning
    Never exceed recommended RAM usage! Always leave around 20% remaining RAM for remedial tasks.

Once you have filled out your text document, Xplotter is ready to plot your available hard disk space within the resources you wish to allocate. You can now **SAVE AS** run.bat in the Xplotter directory.

To maximize Xplotter's plotting power you're going to want to right click run.bat and select 'run as an administrator'.

You should see something similar to this:

![plottinginterface](https://steemitimages.com/0x0/https://steemitimages.com/DQmZk7KmZ1WMMfCbY61kEf23rRJaXSzKSbi31Ux4KYejZF6/xplotter1.png)

The plotting process will consume a great deal of resources if done correctly. You want to plot as fast as possible so raise the RAM and thread count as much as you reasonably can.

This may take a while depending on the size of your plot but you can run multiple instances of Xplotter if you have multi threading!

### Tips

-Add one to the last nonce to get the starting nonce of your next plot file. remember sequential is good, overlapping is bad.
-Keep a record of your command line(s) that you're currently using so that if you need to pause Xplotter you can re-initiate the same plot by executing the EXACT same command!
-Repeat these steps if you'd like to create multiple plot files. We recommend you make your plot files large but not bigger than a few TB as encountering an error after hours or days of plotting can be very frustrating.

Happy plotting!
