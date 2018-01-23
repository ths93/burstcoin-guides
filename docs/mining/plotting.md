<h2>Introduction</h2>

In order to mine Burst, you first have to plot the disk space you want to use. This is the only energy-consuming manipulation and only has to be done once.

This tutorial will teach you how to plot your drives with XPlotter (CPU plotting) without using the AIO client.

The disk space you dedicate to Burst can't be used otherwise once plotted (unless you delete the plot files) so make sure you can truly afford the space dedicated to mining Burst.

HDD disk space will be occupied by <strong>Plot Files</strong>. Plot files are like bingo cards that contain pre-solved responses to the cryptographic problem that the blockchain poses to miners each and every round. Plot files require a great deal of time and processing power to create.

Plotting the disk space you wish to dedicate to mining Burst can be accomplished multiple ways but in this tutorial we will be using <strong>XPlotter</strong>, a CPU based plotter that automatically create optimized plot files. This means your plot files will be of the highest possible quality and efficiency.

<hr />

<h2>Instructions</h2>
<strong>If you are using Qbundle, the software is included: just click "Tools" -&gt; "Plotter". </strong>It will simplify the process and it offers an improved interface. A guide is included in the Plotter page of Qbundle - follow the instructions there.

Otherwise, download XPlotter<strong> </strong>and extract it to your desktop or a local directory of your choice.

<strong>=&gt;  <a href="https://github.com/Blagodarenko/XPlotter/releases" target="_blank" rel="nofollow noopener">Download on GitHub</a> &lt;=</strong>

Now let's talk about plot files so you can get the gist of the nature of these things :

Plot files consist of <strong>nonces</strong> which contain the cryptographic solutions you will be mining with.
<h4>1 nonce = 262144 bytes</h4>
Plot file size is measured in nonces so you'll have to convert the size of your dedicated disk space to nonces. Nonce calculators exist to make this process easier.

Also something very important to understand:

!!! info
    Nonces are ordered <strong>linearly</strong> in <strong>sequential order</strong>. the number they're assigned to is arbitrary but they should <b>never</b> overlap (overlapping reduces plot efficiency and triggers an error in most mining software).

With Xplotter that is all the technical knowledge you need to operate the software and to create an optimized plot file.

To execute Xplotter we will have to create a text document and save it as <strong>run.bat</strong>. this batch file will tell Xplotter where and how much to plot and the resources to consume to do so. Follow the next instructions closely :

-Go into the Xplotter directory and create a new text document and paste this command line into the notepad :
<blockquote>@setlocal
@cd /d %~dp0
XPlotter_avx.exe <strong>-id</strong> <em>XXXXXXXXXXXXXX</em> <strong>-sn</strong> <em>O</em> <strong>-n</strong> <em>P</em> <strong>-t</strong> <em>Q</em> <strong>-path</strong> <em>Z:\plots</em> <strong>-mem</strong> <em>y</em><strong>G</strong></blockquote>
<strong>And we will now fill in the blanks regarding the variables in italics.</strong>
<blockquote><strong>-id</strong> = your wallets numerical code. This can be found by clicking your account's name in your wallet and copying the numeric account ID.</blockquote>
<blockquote><strong>-sn</strong> = Starting Nonce (if this is your first time ever plotting I recommend you start your nonce with 0 [ZERO])</blockquote>
<blockquote><strong>-n</strong> = Total nonces</blockquote>
<blockquote><strong>-t </strong>= Threads (this refers to your machine's CPU architecture. you should see if it has multi threading otherwise put '1' here)</blockquote>
<blockquote><strong>-P </strong>= Path you wish to have your plot file. (mine look like this 'D:/Burst/Plots' any path will suffice really)</blockquote>
<blockquote><strong>-mem</strong>= Gigs of RAM you wish to consume during this process.</blockquote>
<strong>Never exceed recommended RAM usage! Always leave like 20% remaining RAM for remedial tasks.</strong>

Once you've filled out your text document to customize Xplotter to plot your available hard disk space and to limit the resources it will consume then <strong>SAVE AS</strong> '<em>run.bat</em>' in the Xplotter directory.

To maximize Xplotter's plotting power you're going to want to <em>right click</em> the <strong>run.bat</strong> and select '<em>run as an administrator</em>'.

<img src="https://steemitimages.com/0x0/https://steemitimages.com/DQmZk7KmZ1WMMfCbY61kEf23rRJaXSzKSbi31Ux4KYejZF6/xplotter1.png" alt="xplotter1.png" />

This process will consume a great deal of resources if done correctly. You want to plot as fast as possible so crank up the RAM and Thread count if you can.

This may take a while depending on the size of your plot but you can run multiple instances of Xplotter if you have multi threading!

-Add one to the last nonce to get the starting nonce of your next plot file. remember sequential is good, overlapping is bad.

-Keep a record of your command line(s) that you're currently using so that if you need to pause Xplotter you can re-initiate the same plot by executing the EXACT same command!

-Repeat these steps if you'd like to create multiple plot files. We recommend you make your plot files large but not bigger than a few TB as encountering an error after hours or days of plotting can be very frustrating.

You are now plotting!
