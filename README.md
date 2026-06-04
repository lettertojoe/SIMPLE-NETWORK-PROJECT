<h1>SIMPLE-NETWORK-PROJECT</h1>
<h2>CASE STUDY</h2>
<p>Design a network with two departments. Each department should contain at least two PCs.  The network address is 192.168.40.0. The PCs in each department should be able to ping the PCs in other deparment. <strong >Do not use VLAN</strong> .</p>
<h3>Topology</h3>
<div>
  <img src="images\Simple.png" alt="Topology"> 
</div>

<details>
  <summary>R1</summary>
enable

conf t

interface Ethernet0/0

 ip address 192.168.40.129 255.255.255.128

no shutdown

exit
  
interface Ethernet0/1

 ip address 192.168.40.1 255.255.255.128

no shutdown

exit

line con 0

 exec-timeout 0 0

 logging synchronous

exit

no ip domain-lookup
</details> 
<details>
  <summary>Account</summary>  
  ip 192.168.40.2/25 192.168.40.1
</details>
<details>
  <summary>Account2</summary>  
  ip 192.168.40.3/25 192.168.40.1
</details>
<details>
  <summary>Delivery</summary>  
  ip 192.168.40.130/25 192.168.40.129
</details>
<details>
  <summary>Delivery2</summary>  
  ip 192.168.40.131/25 192.168.40.129
</details>
<!-- This comment other routers out
 <details> 
   <summary>R2</summary>
    router ospf 1
    network 20.0.0.0 0.0.0.255 area 0
 </details> 
 <details>
   <summary>R3</summary>
  router ospf 1
   network 30.0.0.0 0.0.0.255 area 0
 </details>
-->
<h3>Verification</h3>
<div>
  <img src="images\Delivery PC ping Account.png" alt="Confirmation">
</div>
<h3>In conclusion</h3>
<p>
192.168.40.0/24 has to be divided into 2 subnets because we need two departments.  
We need to borrow bits from the 4th octet to create a subnet. The formula is <strong>2<sup>n</sup>.</strong> N is the number of borrowed bit(s). In this case, we need to borrow 1 bit so <strong>2<sup>1</sup>.</strong> = 2.

  
<strong> 1 0 0 0 0 0 0 0 converts to binary gives 128. This is our subnet mask </strong>.
To calculate how many block size in a subnet, subtract number of borrowed bits converted to binary from 256.
<strong>256 - 128 = 128 blocks</strong>  
</p>
<h4>First Subnet</h4> 
<p>
  Start from 0 to 127. 
  
  <strong>Network Address</strong> 192.168.40.0
  
  <strong>Usable ip:</strong> 192.168.40.1  to ..40.126  
  
 <strong> Broadcast address:</strong> 192.168.40.127  
 
</p>
<h4>Second Subnet</h4> 
<p>
  Start from 128 to 255   
  
  <strong>Network Address</strong> 192.168.40.128  
  
 <strong> Usable ip:</strong> 192.168.40.129  to ..40.254  
  
  <strong>Broadcast address: </strong>192.168.40.255  
  
</p>




