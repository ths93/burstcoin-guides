This is the continuation of the "plotting" tutorial. </br>
In this instructional we're going to configure <strong>Blago's CPU Mining Software</strong> to mine the plots you already generated on your machine.

<hr />

<h3>Let's get started!</h3>
<strong>If you are using Qbundle, the software is included: just click “Tools” -&gt; “Miner”.</strong>

Otherwise, download Blago's miner and extract it to your desktop or the local directory of your choice.

<strong>=&gt; <a href="https://github.com/Blagodarenko/miner-burst/releases" target="_blank" rel="nofollow noopener">Download on GitHub</a> &lt;=</strong>
<h2>Edit Miner.conf Document</h2>
-open the miner.conf document in the Blago's miner directory with notepad. What you see here is a reference chart for the mining software to utilize when initializing the mining program.

&nbsp;
<blockquote><strong>"Mode"</strong> = whether your mining software uploads <strong>deadline hashes</strong> to a <strong><em>"pool"</em></strong> or directly to the burst network in <strong><em>"solo"</em></strong> mode.</blockquote>
(it's up to you how you want to mine BURST but if you have less than 200TB of disk space plotted then I would recommend a pool)

As it is the miner.conf document is automatically designated to a fictitious pool which means you must update the file to direct the software to the proper <strong>web address</strong> or <strong>IP</strong> and <strong>port</strong>. You will need to know the pool of your choice's <strong>server address</strong> and <strong>port</strong> so you can update the miner.conf file.

-You can shop around for pools here : <a href="https://docs.google.com/spreadsheets/d/1KHu9BWwy_QXIYAx2m_Tzs9BqPoTYUDhEDbHihZEXGsE/edit#gid=327728699" target="_blank" rel="noopener">Pools spreadsheet</a>

-And you can see how each pool performs here : <a href="http://burstcoin.cc/pool" target="_blank" rel="nofollow noopener">burstcoin.cc/pool</a>

=&gt; Remember to always check if the pool suits the size of your plot files.

<strong>You must acquire the pools web address and port and propagate this information throughout the miner.conf document</strong>.

Let's say you are mining at <a href="http://burstmine.tk/" rel="nofollow noopener">burstmine.tk</a> (the <strong>Port</strong> there is :8080), here's how the completed miner.conf document would look:

<img src="https://steemitimages.com/0x0/https://steemitimages.com/DQmNjRLBzHpeHhosXr9kHyiJv91Nik7mjomPYLNzBGRbmcP/burstminetkconf.png" alt="burstminetkconf.png" />

<strong>Further more beside "Paths": in the miner.conf document you will need to refer to all of your completely plotted plot files while maintaining the syntax properly.</strong>

So if your plot files are along the paths "C:\BURST\Plots" and "E:\BURST\Plots" then this line should look like this:
<blockquote>"Paths": ["C:\BURST\Plots","E:\BURST\Plots"],**</blockquote>
Now that you have your miner.conf document prepared properly, <strong>save</strong> it.
<h2>Passphrases.txt</h2>
Let's <strong>create a passphrases.txt document</strong> within the Blagos directory

-Within the Blagos Burst Miner directory create a new text document.

-Paste your wallet's passphrase into the document

-Save the document as passphrases.txt
<h2>Setting the Reward Assignment!</h2>
<em>By this time you should already have selected the pool you wish to mine with. If not you can find a list of pool wallet addresses above in this tutorial.</em>

<strong>If you are using Qbundle, just click “Tools” -&gt; “Reward recipient”.</strong>

-Pick a pool and copy the wallet address onto your clipboard

-If you are using Qbundle, just click “Tools” -&gt; “Reward recipient”.<strong> </strong>Otherwise go to this page: <a href="http://127.0.0.1:8125/rewardassignment.html" target="_blank" rel="nofollow noopener">Set Reward Assignment</a>

-Enter the <strong>pool's BURST address</strong> and your <strong>mining wallet's passphrase</strong> in the respective fields.

<em>The pool address for <strong>burstmine.tk</strong> is <strong>BURST-H96D-FT7X-Q5WB-DX23A</strong></em>

<em>Now when your pool of choice is dividing up the Burst rewards among the miners it will automatically send your burstcoins to your Burst wallet.</em>
<h2>RUN BLAGOS!</h2>
Blagos should look like this when you start it up:

<img src="https://steemitimages.com/0x0/https://steemitimages.com/DQmdk7Gf5dQ4yvXmy75Ah3uidjo8CYw8QsHbLot2KKobAmG/blagosstartup.png" alt="blagosstartup.png" />
<h2>Optional : Going Solo</h2>
Conversely if you'd like to mine <em>solo</em> then change the miner.conf document to look like this:

<img src="https://steemitimages.com/0x0/https://steemitimages.com/DQmTdjAwvQZoeCHJSj7w46SqsAhx2CuxfEb2ZGjLmktxjzT/soloconf.png" alt="soloconf.png" />

Also, set the <strong>reward assignment</strong> to your <strong>own Burst wallet address</strong>.

<img src="https://steemitimages.com/0x0/https://steemitimages.com/DQmXofB5v8C8qC3f5EYAY3YGQuHkhQQqX83Bsr5r5CUYTrL/soloassignment.png" alt="soloassignment.png" />

<strong>Wait 4 block rounds</strong> and <strong>start up Blagos,</strong> it should look the same as above.
<h4>Congratulations! You are now mining Burst!</h4>
<p style="text-align: right;"><em>Credit : Gooplanets</em></p>
