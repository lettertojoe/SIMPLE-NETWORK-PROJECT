<h1>SIMPLE-NETWORK-PROJECT</h1>
<h2>DESCRIPTION</h2>
<p>Design a network with two departments. Each department should contain at least two PCs.  The network address is 192.168.40.0. The PCs in each department should be able to ping the PCs in other deparment. <strong >Do not use VLAN</strong> .</p>
<h3>Topology</h3>
<div>
  <img src="C:\Users\lette\Desktop\Simple.png" alt="Topology">
</div>

<details>
  <summary>R1</summary>
  router ospf 1
   network 10.0.0.0 0.0.0.255 area 0
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
>

