# networking_in_linux
MPLS L3VPN on Linux


<b>IP addressing:</b>
<p>
Loopbacks ISP 10.255.1.0/24:</br>
RR Lo0: 10.255.1.1/32</br>
PE1 Lo0: 10.255.1.2/32</br>
PE2 Lo0: 10.255.1.3/32</br>
</p>
<p>
Loopbacks CE-A 10.100.255.0/24:</br>
CE01-A Lo0: 10.100.255.1/32</br>
CE02-A Lo0: 10.100.255.2/32</br>
</p>
<p>
RR - PE1: 10.12.1.0/24</br>
RR - PE2: 10.13.1.0/24</br>
PE1 - CE01A: 10.24.1.0/24</br>
PE2 - CE02A: 10.36.1.0/24</br>
</p>
<h3>Topology:</h3>

![Topology should be here](linux_networking_lab_v2.png "Topology overview")

<p>
  <b> Prerequisites </b>

Replace netplan with ifupdown (ifupdown2 if any vrf exist):

<pre>sudo apt install -y ifupdown && sudo apt purge -y netplan.io</pre>

Install FRR (will be acting as a routing daemon):

<pre>sudo apt install frr frr-pythontools</pre>

Turn system into a router:

<pre>Uncomment net.ipv4.ip_forward=1 in /etc/sysctl.conf</pre>
<pre>sysctl –p</pre>

Complete initial FRR setup:
Enable required daemons and add service to startup (Refer to FRR routing daemon initial setup)
</p>

<h3> Follow configuration steps describe in repo folders </h3>
