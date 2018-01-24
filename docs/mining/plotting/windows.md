
## Plotting

This tutorial will teach you how to plot your drives with [XPlotter](https://github.com/Blagodarenko/XPlotter/releases), a CPU plotter creating optimized plot files.

!!! info
    With Qbundle, the software is already included: just click "Tools" -> "Plotter". A guide is also present in the plotter page - it is recommended to follow the instructions detailed there.

If you want to use the software as a standalone, follow the instructions here.


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
