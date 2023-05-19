## RCOMP 2022/2023 - SPRINT 3 EDIFÍCIO D - 1211016 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta as simulações do edifício D, referentes ao sprint 3.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###
1. **Base de dados DNS no servidor DNS**
2. **DHCP implementação**
3. **OSPF implementação**
4. **VOIP implementação**
5. **Implementação teórica do NAT**
6. **Implementação da Firewall**

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Base de dados DNS no servidor DNS ###

* Servidor DNS do Edificio D:
  * IP: 10.80.118.242
  * Nome: ns.building-D.rcomp-22-23-db-g5

**note**: Estes dados foram introduzidos posteriormente na configuração DHCP do router do edificio D.

* Servidor DNS do Edificio A:
  * IP: 10.80.113.2
  * Nome: rcomp-22-23-db-g5


* A base de dados DNS encontra-se descrita na seguinte imagem: 

![DNS_database.png](config-dump%2FDNS_database.png)

------------------------------------------------------------------------------------------------------------------------------------------------------------

## 2. DHCP implementação ##
Para estabelecer o DHCP, foram executadas as seguintes configurações no router do building D:

```

ip dhcp excluded-address 10.80.118.1   (excluded the router's IP - Wifi vlan)
ip dhcp excluded-address 10.80.118.129 (excluded the router's IP - Floor 1 vlan)
ip dhcp excluded-address 10.80.118.193 (excluded the router's IP - Floor 0 vlan)
ip dhcp excluded-address 10.80.118.225 (excluded the router's IP - VoIP vlan)
```

```    
ip dhcp pool NET-401
network 10.80.118.0 255.255.255.128
default-router 10.80.118.1

ip dhcp pool NET-402
network 10.80.118.128 255.255.255.192
default-router 10.80.118.129

ip dhcp pool NET-403
network 10.80.118.192 255.255.255.224
default-router 10.80.118.193

ip dhcp pool NET-404
network 10.80.118.224 255.255.255.240
default-router 10.80.118.225
option 150 ip 10.80.118.225

```

## 3. OSPF implementação ##
Para estabelecer o OSPF no building D, foi apenas necessário definir a área de backbone e a área do próprio edifício:

```
router ospf 1
network 10.80.115.0 0.0.0.127 area 0
network 10.80.118.0 0.0.0.255 area 4 
```

## 4. VOIP implementação ##
Para criar o serviço VOIP, foi primeiro necessário estabelecer as ligações entre edifícios

```
dial-peer voice 10 voip
destination-pattern 1
session target ipv4:10.80.115.1 (IP do router do edificio A)

dial-peer voice 20 voip
destination-pattern 2
session target ipv4:10.80.115.2 (IP do router do edificio B)

dial-peer voice 30 voip
destination-pattern 3
session target ipv4:10.80.115.3 (IP do router do edificio C)
```

e posteriormente configurar os próprios telefones:

```
telephony-service
 max-ephones 10
 max-dn 10
 ip source-address 10.80.118.225 port 2000
 auto assign 1 to 2

ephone-dn 1
 number 4000

ephone-dn 2
 number 4001
 ```

## 5. Implementação teórica do NAT ##
Uma vez que no packet tracer haviam problemas na implementação do NAT, derivados da própria simulação, aqui fica a implementação teórica do NAT:
Primeiro, seria necessário definir as interfaces inside e outside:

```
ip nat inside source 10.80.118.241 (interface DMZ)
ip nat outside source 10.80.115.4 (interface Backbone)
```

Posteriormente, seria necessário definir as rotas estáticas:

```
syntax: ip nat inside source static <prtocol> <inside local IP> <inside local port> <outside global IP> <outside global port>

ip nat inside source static tcp 10.80.118.243 443 10.80.115.4 443
ip nat inside source static tcp 10.80.118.243 80 10.80.115.4 80
ip nat inside source static tcp 10.80.118.242 53 10.80.115.4 53
ip nat inside source static udp 10.80.118.242 53 10.80.115.4 53

Servidor HTTP: 10.80.118.243

Servidor DNS: 10.80.118.242

Sub-interface backbone: 10.80.115.4
```

## 6. Implementação da Firewall ##
A implementação da firewall foi baseada em listas de acesso, que foram aplicadas nas sub-interfaces do router.

Access List para a sub-interface wifi: ACL 101
Access List para a sub-interface floor 1: ACL 102
Access List para a sub-interface floor 0: ACL 103
Access List para a sub-interface voip: ACL 104
Access List para bloquear spoofing externo: ACL 100


As access lists têm o seguinte aspeto genérico:

```
access-list x deny ip any host 10.80.118.1
access-list x deny ip any host 10.80.118.129
access-list x deny ip any host 10.80.118.193
access-list x deny ip any host 10.80.118.225
access-list x deny ip any host 10.80.118.241
access-list x permit icmp any 10.80.118.240 0.0.0.15 echo-reply
access-list x permit tcp any 10.80.118.240 0.0.0.15 eq www
access-list x permit tcp any 10.80.118.240 0.0.0.15 eq 443
access-list x permit tcp any 10.80.118.240 0.0.0.15 eq domain
access-list x permit udp any 10.80.118.240 0.0.0.15 eq domain
access-list x deny ip any 10.80.118.240 0.0.0.15
access-list x permit ip x.x.x.x 0.0.0.x any
access-list x permit udp any eq bootpc any eq bootps
```

Posteriormente, as access lists foram aplicadas nas sub-interfaces:
  
    ```
    interface FastEthernet0/0.x
    ip access-group x in
    ```



## RCOMP SPRINT 3 checklist ##
* [x] OSPF
* [x] DHCP
* [x] VOIP
* [x] Adding a second server to each DMZ network to run the HTTP service.
* [x] Configuring DNS servers to establish a DNS domain tree
* [x] NAT
* [x] Firewall