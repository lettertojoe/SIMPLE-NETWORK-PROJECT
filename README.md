<h1>SIMPLE-NETWORK-PROJECT</h1>
<h2>DESCRIPTION</h2>
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
<h3>Topology</h3>
<div>
  <img src="images\Simple.png" alt="Topology">
</div>
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
>




