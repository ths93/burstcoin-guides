<div class="row sqs-row">
<div class="col sqs-col-3 span-3">
<div id="block-e871ba1bdafeeb570416" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<h2>Why Run a Full Node?</h2>
</div>
</div>
</div>
<div class="col sqs-col-9 span-9">
<div id="block-1ac097324b450625dcfc" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">

Running a full node is one of the most important ways to help support the Burst network. This allows other peers to connect to your wallet and synchronize the blockchain if they are not using an imported DB. When light clients are released, Full Nodes maintain a copy of the blockchain, in the decentralized manner that crypto currencies are designed to run, while light clients will not. Below are the steps for setting up a full node.

</div>
</div>
</div>
</div>
<div class="row sqs-row">
<div class="col sqs-col-12 span-12">
<div id="block-yui_3_17_2_3_1514524378123_7207" class="sqs-block horizontalrule-block sqs-block-horizontalrule" data-block-type="47">
<div class="sqs-block-content">

<hr />

</div>
</div>
</div>
</div>
<h2>Steps</h2>
<div class="row sqs-row">
<div class="col sqs-col-12 span-12">
<div id="block-yui_3_17_2_3_1514762412807_15661" class="sqs-block html-block sqs-block-html sqs-col-9 span-9 float float-right" data-block-type="2">
<div class="sqs-block-content">
<ol>
 	<li>Once you have a local wallet installed and running you need to forward port 8123 to allow other peers to connect to your wallet.</li>
 	<li>Now you will set the machine to have a static IP address. This is so that if the machine restarts, it will not change IP addresses and negate the port forwarding rule we will set up later.
<ul>
 	<li>Open "System Preferences"</li>
 	<li>Select "Network"</li>
 	<li>Select "Advanced"</li>
 	<li>Select "TCP/IP"</li>
 	<li>Note down your "IPv4 Address"</li>
 	<li>Note down the "Router" address, this is your default gateway.</li>
 	<li>Leave "Configure IPv6" set to "Automatic".</li>
 	<li>Change "Configure IPv4" to "Manual".</li>
 	<li>Now in the "IPv4 Address" field, enter the IPv4 address you copied down before switching to manual.</li>
 	<li>Make sure "Subnet Mask" is still
255.255.255.0</li>
 	<li>Make sure "Router" still matches the router number you copied down before switching to manual.</li>
 	<li>Click "Ok"</li>
 	<li>Click "Apply"</li>
 	<li>Close system preferences</li>
</ul>
</li>
 	<li>Now open your network router settings by entering your default gateway IP in the URL field of your browser.</li>
 	<li>Login to your router.
<ul>
 	<li>If you have never used these settings before, most ISPs have default username/password combinations. A quick google search will help you find it.</li>
 	<li>If you do not remember your username/password combo, you will need to factory reset your router. Be mindful, this will force you to re-setup your entire network.</li>
</ul>
</li>
 	<li>Find the "Port Forwarding" option. Note, "Port Forwarding" and "Port Triggering" are <strong>NOT</strong> the same. "Port Forwarding" is generally under the "Advanced" tab.</li>
 	<li>Select "Add Service", "Add Rule", or anything along those lines.</li>
 	<li>Set "Common Service" as "Other".</li>
 	<li>Set service name to "Burstcoin".</li>
 	<li>Set "Service Type" to "TCP/UDP".</li>
 	<li>Set IPv4 Address to your machines address which is the address you just made static.</li>
 	<li>Disregard the IPv6 Address field.</li>
 	<li>Set your "Start Port" and "End Port" to "8123".</li>
 	<li>Save the new service.</li>
</ol>
The local wallet must remain running for your full node to be accessible to the network.

After a few hours to a few days the <a href="https://explore.burst.cryptoguru.org/tool/observe" target="_blank" rel="noopener">network observer</a> will update and you can check that your set up worked. First find <a href="https://www.myexternalip.com/" target="_blank" rel="noopener">your external IP</a> address and then search your external IP address and port in the network observer (ex. 193.182.13.162:8123).

</div>
</div>
</div>
</div>
