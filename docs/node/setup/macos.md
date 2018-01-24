
## Run a Full Node

Running a full node is one of the most important ways to help support the Burst network. This allows other peers to connect to your wallet and synchronize the blockchain if they are not using an imported DB. When light clients are released, Full Nodes maintain a copy of the blockchain, in the decentralized manner that crypto currencies are designed to run, while light clients will not. Below are the steps for setting up a full node.

### Network Settings

- Once you have a local wallet installed and running you need to forward port 8123 to allow other peers to connect to your wallet.
- Now you will set the machine to have a static IP address. This is so that if the machine restarts, it will not change IP addresses and negate the port forwarding rule we will set up later.

---

1. Open "System Preferences"
2. Select "Network"
3. Select "Advanced"
4. Select "TCP/IP"
5. Note down your "IPv4 Address"
6. Note down the "Router" address, this is your default gateway.
7. Leave "Configure IPv6" set to "Automatic".
8. Change "Configure IPv4" to "Manual".
9. Now in the "IPv4 Address" field, enter the IPv4 address you copied down before switching to manual.
10. Make sure "Subnet Mask" is still 255.255.255.0
11. Make sure "Router" still matches the router number you copied down before switching to manual.
12. Click "Ok"
13. Click "Apply"
14. Close "System Preferences"

### Router Settings

Now open your network router settings by entering your default gateway IP in the URL field of your browser. Login to your router.

- If you have never used these settings before, most ISPs have default username/password combinations. A quick google search will help you find it.
- If you do not remember your username/password combo, you will need to factory reset your router. Be mindful, this will force you to re-setup your entire network.  

---

1. Find the "Port Forwarding" option. Note, "Port Forwarding" and "Port Triggering" are **NOT** the same. "Port Forwarding" is generally under the "Advanced" tab.
2. Select "Add Service", "Add Rule", or anything along those lines.
3. Set "Common Service" as "Other".
4. Set service name to "Burstcoin".
5. Set "Service Type" to "TCP/UDP".
6. Set IPv4 Address to your machines address which is the address you just made static.
7. Disregard the IPv6 Address field.
8. Set your "Start Port" and "End Port" to "8123".>
9. Save the new service.

The local wallet must remain running for your full node to be accessible to the network.

!!! Info
    After a few hours to a few days the [network observer](https://explore.burst.cryptoguru.org/tool/observe) will update and you can check that your set up worked. First find [your external IP](https://www.myexternalip.com/) address and then search your external IP address and port in the network observer (e.g. 193.182.13.162:8123).
