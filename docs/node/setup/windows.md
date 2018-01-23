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
<div id="block-d5e49ff1d1dd3e7491f7" class="sqs-block horizontalrule-block sqs-block-horizontalrule" data-block-type="47">
<div class="sqs-block-content">

<hr />

</div>
</div>
</div>
</div>
<div class="row sqs-row">
<div class="col sqs-col-3 span-3">
<div id="block-6466d18dd7278b035083" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<h2>Steps</h2>
</div>
</div>
</div>
<div class="col sqs-col-9 span-9">
<div id="block-3d6fbc74c9e267401943" class="sqs-block html-block sqs-block-html" data-block-type="2">
<div class="sqs-block-content">
<ol dir="ltr">
 	<li>Once you have a local wallet installed and running you need to forward port 8123 to allow other peers to connect to your wallet.</li>
 	<li>We now need to get some IP addresses.
<ul>
 	<li>Open "Command Prompt".</li>
 	<li>Type "ipconfig"</li>
 	<li>Find and record your "Default Gateway" and "IPv4 Address"</li>
</ul>
</li>
 	<li>Now you will set the machine to have a static IP address. This is so that if the machine restarts, it will not change IP addresses and negate the port forwarding rule we will set up later.
<ul>
 	<li>Open "Control Panel".</li>
 	<li>Open "Network and Internet".</li>
 	<li>Open "Network and Charing Center".</li>
 	<li>In the left menu, open "Change Adapter Settings".</li>
 	<li>Right click your preferred method of internet connection.</li>
 	<li>Select "Properties".</li>
 	<li>Uncheck "Internet Protocol Version 6 (TCP/IPv6)".</li>
 	<li>Click "Internet Protocol Version 4 (TCP/IPv4)".</li>
 	<li>Open "Properties"</li>
 	<li>Select "Use the following IP address"</li>
 	<li>In "IP address" type the IPv4 number that you got in Command Prompt.</li>
 	<li>In "Subnet Mask" type "255.255.255.0".</li>
 	<li>In "Default Gateway" type the default gateway address you got in Command Prompt.</li>
 	<li>Select "Use the following DNS server addresses"</li>
 	<li>In "Preferred DNS server" type
"8.8.8.8"</li>
 	<li>In "Alternate DNS server" type
"8.8.4.4"</li>
 	<li>Check "Validate settings upon exit"</li>
 	<li>Click "OK"</li>
 	<li>If you receive a warning about "Multiple default gateways..." select "Yes".</li>
 	<li>Click "Close"</li>
</ul>
</li>
 	<li>Now open your network router settings by entering your default gateway IP in the URL field of your browser.</li>
 	<li>Login to your router.
<ul>
 	<li>If you have never used these settings before, most ISPs have default username/password combinations. A quick google search will help you find it.</li>
 	<li>If you do not remember your username/password combo, you will need to factory reset your router. Be mindful, this will force you to re-setup your entire network.</li>
</ul>
</li>
 	<li>Find the "Port Forwarding" option. Note, "Port Forwarding" and "Port Triggering" are <strong>NOT</strong> the same. "Port Forwarding" is generally under the "Advanced" tab.
<ul>
 	<li>Select "Add Service", "Add Rule", or anything along those lines.</li>
 	<li>Set "Common Service" as "Other".</li>
 	<li>Set service name to "Burstcoin".</li>
 	<li>Set "Service Type" to "TCP/UDP".</li>
 	<li>Set IPv4 Address to your machines address which is the address you just made static.</li>
 	<li>Disregard the IPv6 Address field.</li>
 	<li>Set your "Start Port" and "End Port" to "8123".</li>
 	<li>Save the new service.</li>
</ul>
</li>
 	<li>Finally, you must reserve the IP address for your specific machine
<ul>
 	<li>Navigate to "Connected Devices" (or something of the like).</li>
 	<li>Find and click-on the machine you are running the node from.</li>
 	<li>Select "Edit"</li>
 	<li>Change configuration to "Reserved IP"</li>
 	<li>Verify the IP is the same one you set in port forwarding.</li>
 	<li>Select Save.</li>
</ul>
</li>
 	<li>You are now finished and can close out network settings.</li>
</ol>
The local wallet must remain running for your full node to be accessible to the network.

After a few hours to a few days the <a href="https://explore.burst.cryptoguru.org/tool/observe" target="_blank" rel="noopener">network observer</a> will update and you can check that your set up worked. First find <a href="https://www.myexternalip.com/" target="_blank" rel="noopener">your external IP</a> address and then search your external IP address and port in the network observer (ex. 193.182.13.162:8123).

</div>
</div>
</div>
</div>
