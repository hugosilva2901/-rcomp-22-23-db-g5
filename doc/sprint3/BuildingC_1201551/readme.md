## RCOMP 2022/2023 - SPRINT 3 EDIFÍCIO C - 1201551 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta as simulações do edifício C, referentes ao sprint 3.

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

* Servidor DNS do Edificio C:
  * IP: 10.80.117.226
  * Nome: ns.building-C.rcomp-22-23-db-g5

**note**: Estes dados foram introduzidos posteriormente na configuração DHCP do router do edificio C.

* Servidor DNS do Edificio A:
  * IP: 10.80.113.2
  * Nome: rcomp-22-23-db-g5


* A base de dados DNS encontra-se descrita na seguinte imagem:

![DNS_database.png](config%2Fdns_database_C.png)

* A página HTML do servidor HTTP encontra-se descrita na seguinte imagem:

![HTTP_page.png](config%2Fhttp_server_html_page.png)

------------------------------------------------------------------------------------------------------------------------------------------------------------

## 2. DHCP implementação ##
Para estabelecer o DHCP, foram executadas as seguintes configurações no router do building C:

```

ip dhcp excluded-address 10.80.117.1 ( exluded the router's IP - Wifi vlan)
ip dhcp excluded-address 10.80.117.65 ( exluded the router's IP - Floor 1 vlan)
ip dhcp excluded-address 10.80.117.129  ( exluded the router's IP - Floor 0 vlan)
ip dhcp excluded-address 10.80.117.193 ( exluded the router's IP - VoIP vlan)
```

```    
ip dhcp pool NET-396
 network 10.80.117.0 255.255.255.192
 default-router 10.80.117.1

ip dhcp pool NET-397
 network 10.80.117.64 255.255.255.192
 default-router 10.80.117.65


ip dhcp pool NET-398
 network 10.80.117.128 255.255.255.192
 default-router 10.80.117.129

ip dhcp pool NET-399
 network 10.80.117.192 255.255.255.224
 default-router 10.80.117.193
 option 150 ip 10.80.117.193


```

## 3. OSPF implementação ##
Para estabelecer o OSPF no building C, foi apenas necessário definir a área de backbone e a área do próprio edifício:

```
router ospf 1
 network 10.80.115.0 0.0.0.127 area 0
 network 10.80.117.0 0.0.0.255 area 3
```

## 4. VOIP implementação ##
Para criar o serviço VOIP, foi primeiro necessário estabelecer as ligações entre edifícios

```
dial-peer voice 10 voip
 destination-pattern 1
 session target ipv4:10.80.115.1 (IP do router do edificio A)
!
dial-peer voice 20 voip
 destination-pattern 2
 session target ipv4:10.80.115.2 (IP do router do edificio B)
!
dial-peer voice 30 voip
 destination-pattern 3
 session target ipv4:10.80.115.3 (IP do router do edificio C)
!
dial-peer voice 40 voip
 destination-pattern 4
 session target ipv4:10.80.115.4 (IP do router do edificio D)
!
```

e posteriormente configurar os próprios telefones:

```
telephony-service
 max-ephones 10
 max-dn 10
 ip source-address 10.80.117.193 port 2000
 auto assign 1 to 2
!
ephone-dn 1
 number 3000
!
ephone-dn 2
 number 3001
!
 ```

## 5. Implementação teórica do NAT ##
Uma vez que no packet tracer haviam problemas na implementação do NAT, derivados da própria simulação, aqui fica a implementação teórica do NAT:
Primeiro, seria necessário definir as interfaces inside e outside:

```
ip nat inside source 10.80.117.225 (interface DMZ)
ip nat outside source 10.80.115.3 (interface Backbone)
```

Posteriormente, seria necessário definir as rotas estáticas:

```

syntax: ip nat inside source static <prtocol> <inside local IP> <inside local port> <outside global IP> <outside global port>

ip nat inside source static tcp 10.80.117.227 443 10.80.115.3 443
ip nat inside source static tcp 10.80.117.227 80 10.80.115.3 80
ip nat inside source static tcp 10.80.117.226 53 10.80.115.3 53
ip nat inside source static udp 10.80.117.226 53 10.80.115.3 53

Servidor HTTP: 10.80.117.227

Servidor DNS: 10.80.117.226

Sub-interface backbone: 10.80.115.3
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


Para a sub-interface wifi, a access list foi aplicada da seguinte forma:

```
access-list 101 deny ip any host 10.80.117.1
access-list 101 deny ip any host 10.80.117.65
access-list 101 deny ip any host 10.80.117.129
access-list 101 deny ip any host 10.80.117.193
access-list 101 deny ip any host 10.80.117.225
access-list 101 permit icmp any 10.80.117.224 0.0.0.31 echo-reply
access-list 101 permit tcp any 10.80.117.224 0.0.0.31 eq www
access-list 101 permit tcp any 10.80.117.224 0.0.0.31 eq 443
access-list 101 permit tcp any 10.80.117.224 0.0.0.31 eq domain
access-list 101 permit udp any 10.80.117.224 0.0.0.31 eq domain
access-list 101 deny ip any 10.80.117.224 0.0.0.31
access-list 101 permit ip 10.80.117.0 0.0.0.63 any
access-list 101 permit udp any eq bootpc any eq bootps

```

Para a sub-interface floor 1, a access list foi aplicada da seguinte forma:

```
access-list 102 deny ip any host 10.80.117.65
access-list 102 deny ip any host 10.80.117.1
access-list 102 deny ip any host 10.80.117.129
access-list 102 deny ip any host 10.80.117.193
access-list 102 deny ip any host 10.80.117.225
access-list 102 permit icmp any 10.80.117.224 0.0.0.31 echo-reply
access-list 102 permit tcp any 10.80.117.224 0.0.0.31 eq www
access-list 102 permit tcp any 10.80.117.224 0.0.0.31 eq 443
access-list 102 permit tcp any 10.80.117.224 0.0.0.31 eq domain
access-list 102 permit udp any 10.80.117.224 0.0.0.31 eq domain
access-list 102 deny ip any 10.80.117.224 0.0.0.31
access-list 102 permit ip 10.80.117.64 0.0.0.63 any
access-list 102 permit udp any eq bootpc any eq bootps
```

Para a sub-interface floor 0, a access list foi aplicada da seguinte forma:

```
access-list 103 deny ip any host 10.80.117.1
access-list 103 deny ip any host 10.80.117.65
access-list 103 deny ip any host 10.80.117.129
access-list 103 deny ip any host 10.80.117.193
access-list 103 deny ip any host 10.80.117.225
access-list 103 permit icmp any 10.80.117.224 0.0.0.31 echo-reply
access-list 103 permit tcp any 10.80.117.224 0.0.0.31 eq www
access-list 103 permit tcp any 10.80.117.224 0.0.0.31 eq 443
access-list 103 permit tcp any 10.80.117.224 0.0.0.31 eq domain
access-list 103 permit udp any 10.80.117.224 0.0.0.31 eq domain
access-list 103 deny ip any 10.80.117.224 0.0.0.31
access-list 103 permit ip 10.80.117.128 0.0.0.63 any
access-list 103 permit udp any eq bootpc any eq bootps
```

Para a sub-interface voip, a access list foi aplicada da seguinte forma:

```
access-list 104 deny ip any host 10.80.117.1
access-list 104 deny ip any host 10.80.117.65
access-list 104 deny ip any host 10.80.117.129
access-list 104 deny ip any host 10.80.117.225
access-list 104 permit icmp any 10.80.117.224 0.0.0.31 echo-reply
access-list 104 permit tcp any 10.80.117.224 0.0.0.31 eq www
access-list 104 permit tcp any 10.80.117.224 0.0.0.31 eq 443
access-list 104 permit tcp any 10.80.117.224 0.0.0.31 eq domain
access-list 104 permit udp any 10.80.117.224 0.0.0.31 eq domain
access-list 104 deny ip any 10.80.117.224 0.0.0.31
access-list 104 permit ip 10.80.117.192 0.0.0.31 any
access-list 104 permit udp any eq bootpc any eq bootps
```

Para bloquear spoofing externo, a access list foi aplicada da seguinte forma:

```
access-list 100 deny ip 10.80.117.224 0.0.0.31 any
access-list 100 permit tcp any 10.80.117.224 0.0.0.31 eq www
access-list 100 permit tcp any 10.80.117.224 0.0.0.31 eq 443
access-list 100 permit tcp any 10.80.117.224 0.0.0.31 eq domain
access-list 100 permit udp any 10.80.117.224 0.0.0.31 eq domain
access-list 100 deny ip 10.80.117.0 0.0.0.63 any
access-list 100 deny ip any host 10.80.117.1
access-list 100 permit ip any 10.80.117.0 0.0.0.63
access-list 100 deny ip 10.80.117.64 0.0.0.63 any
access-list 100 deny ip any host 10.80.117.65
access-list 100 permit ip any 10.80.117.64 0.0.0.63
access-list 100 deny ip 10.80.117.128 0.0.0.63 any
access-list 100 deny ip any host 10.80.117.129
access-list 100 permit ip any 10.80.117.128 0.0.0.63
access-list 100 deny ip 10.80.117.192 0.0.0.31 any
access-list 100 deny ip any host 10.80.117.193
access-list 100 permit ip any 10.80.117.192 0.0.0.31
access-list 100 deny ip any host 10.80.117.225
access-list 100 permit icmp any 10.80.117.224 0.0.0.31 echo-reply
access-list 100 permit ospf any any
```

Posteriormente, as access lists foram aplicadas nas sub-interfaces:

    ```
    interface FastEthernet0/0.x
    ip access-group x in
    ```

Para a sub-interface wifi:

    ```
    interface FastEthernet0/0.1
    ip access-group 101 in
    ```

Para a sub-interface floor 1:

    ```
    interface FastEthernet0/0.2
    ip access-group 102 in
    ```
Para a sub-interface floor 0:

    ```
    interface FastEthernet0/0.3
    ip access-group 103 in
    ```

Para a sub-interface voip:

    ```
    interface FastEthernet0/0.4
    ip access-group 104 in
    ```
Para bloquear spoofing externo:

    ```
    interface FastEthernet0/0.6
    ip access-group 100 in
    ```






## RCOMP SPRINT 3 checklist ##
* [x] OSPF
* [x] DHCP
* [x] VOIP
* [x] Adding a second server to each DMZ network to run the HTTP service.
* [x] Configuring DNS servers to establish a DNS domain tree
* [x] NAT
* [x] Firewall