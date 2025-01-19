# Networking
in this section some tools and techniques that are used widely,are described .keep in mind that win+x in windows os opens a menu bar that you can control so many other options too. like:

<ul>
<li>Python Port scanner</li>
<li>Active Directory one liners</li>
<li>Finding Forgotten Wifi Passwords</li>
<li>Network Interfaces in CMD</li>
<li>Managing users</li>
<li>Managing network connection</li>
<li>lists of Hosts in Windows</li>
<li>SSH reverse proxy</li>
<li>Basic Download Manager</li>
<li>CMD Networking commands </li>
</ul>



## powershell commands for network troubleshooting

Restart-NetAdapter

    Restart-NetAdapter -Name "Ethernet"

Get-NetFirewallProfile:check for firewall rules and status

    Get-NetFirewallProfile

Get-NetNeighbor

    Get-NetNeighbor

Test-Connection google.com

    Test-Connection google.com

Set-DnsClientServerAddress

    Set-DnsClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses "8.8.8.8"

Get-NetAdapter:basic information about network interfaces

    Get-NetAdapter

    Get-NetIPAddress

    Test-NetConnection google.com

## Scripts


| Port scanner | Python app that scan ports on localhost | <a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
| Forgotten Wifi Passwords | Show Forgotten Wifi Passwords IN CLEAR TEXT |<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
| Network Interfaces | Show Network Interfaces in detail in CMD |<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
| Managing users | add or delete users |<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
| Managing network connection | Show interfaces much more easier way |<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
| Hosts in Windows | Show localhosts and thier ips |<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a> |
|SSH Reverse Proxy|Ready to use scripts for reverse tunneling|<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a>|
|Basic Download Manager|cli app to manage downloads|<a href="https://github.com/pakoti/Awesome_Sysadmin/blob/main/Networking/readme.md" >See More</a>|





## Python Port scanner
if you can't scan your localhost for whatever reason use this script to scan your localhost.for running in your sysytem just execute this script:

<ul>
<li>1.for scanning ports of your systems just:

    python3 portscan.py

</li>
</ul>



## Finding Forgotten Wifi Passwords
To find passwords that were forgotten by using CMD and Powershell
<ul>
<li>1.To get wifi passwords that are stored in our system:

<p>to show past and present wifi you were connected to:</p>

    netsh show profile

<p>2.to find a wifi password that you know :</p>


    netsh wlan show profile WiFi Name key=clear

<p>i am working on linux version of this but this works foe windows right now.you can use powershell or cmd.</p>
</li>
<li>Firewall-Blocked ports:

    netsh firewall show state

</li>
</ul>


## Network Interfaces in CMD

<ul>
<li>/renew switch will renew DHCP address for all network cards:

    ipconfig /renew

</li>
<li>/displaydns switch will display the DNS client cache:

    ipconfig /displaydns

</li>
<li>/registerdns to trigger dynamic registration of the DNS names and IP addresses that are configured on the computer:

    ipconfig /registerdns

</li>
<li>/release to release DHCP addresses. This will release DCHP address on the network cards that are configured for DHCP:

    ipconfig /release

</li>
<li>/flushdns switch to clear the local DNS resolver cache:


    /flushdns switch to clear the local DNS resolver cache.

</li>
<li>To see what resources are mapped to our file system:

    net use

</li>
<li>to connect a printer to our system:

    net use \\srv-vm1\share

</li>
</ul>

## Managing users
simply type lusrmgr.msc  on run and a GUI will open.

    lusrmgr.msc

## Managing network connection
to see network connection,interfaces and also VPN connections just type this command in run:

    ncpa.cpl


## lists of Hosts in Windows

    type %WINDIR%\System32\drivers\etc\hosts

## SSH Reverse Proxy
<p>if you want to gain a shell behind firewalls and router that they do NAT (network address translation) and also PAT (Port address translation),and you have no static ip address you can execute this bash scripts to gain so called a reverse shell.it's good for when you want gain shell from outside to your home when you put personal Computer.</p>


## Basic Download Manager
basic automation task like downloading simple links from the web,save them in a directory and then shutdowns the instance.with wget and axel you can simply work with a download manager.you can use simply this tools:
<ul>
<li>1.Axel</li>
<li>2.Wget</li>
<li>3.Curl</li>
</ul>


## DNS

to show all dns records on the computer:

    ipconfig /displaydns

to flush all dns records on the computer:

    ipconfig /flushdns

show dns server cache

    show-DnsServerCache

clear dns server cache

    Clear-DnsServerCache






## Conditional DNS forwarding
Conditional DNS forwarding is a method to direct DNS queries related to a specific domain to another DNS server. This is done by creating conditional DNS forwarders or rules on the DNS server. This is a simple and reliable method to resolve DNS queries belonging to an external domain

<a href="https://vmc.techzone.vmware.com/resource/configure-conditional-dns-forwarding-between-oci-and-ad-domain">Resource</a>

## What is the difference between a forwarder and a conditional forwarder?

Conditional forwarders are created to enable your DNS servers to forward requests to a specific domain. A normal forwarder will forward all requests to one or more DNS servers; a conditional forwarder will only forward requests for the one domain

<a href="https://livebook.manning.com/concept/active-directory/conditional-forwarder">Resource</a>




## What is an example of a DNS conditional forwarder?

Conditional forwarding is when a condition is applied to which DNS requests are forwarding and which are not. DNS forwarding is the process of forwarding a DNS request from one DNS server to another. The most common example of this is when a company forwards its internal DNS server to its ISP's DNS server.

<a href="https://itfreetraining.com/lesson/forwarding_conditional/">Resource</a>


## CMD Networking commands


| Command | Description |
| --- | --- |
|1.ping |ommand works by sending out multiple data packets and seeing how many of them return|
|2.tracert | command outputs a line-by-line summary of each hop|
|3.pathping|is similar to "tracert," except it's more informative and takes a lot longer to execute|
|4.ipconfig|shows every network adapter on your system and how they resolve|
|5.netstat|s a tool for network statistics, diagnostics, and analysis |
|6.arp -a|to list all the devices on the network     |
|7.net view|see the computers and devices connected to my network|
|8.nslookup|for dns lookups     |
|9.Getmac|to get mac addresses    |


### net view 
The <code>net view</code> command works by querying the Server Message Block (SMB) protocol, which allows sharing of resources like files or printers over a network.
