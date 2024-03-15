# Základy počítačových sítí
## Koncová zařízení a druhy sítí
- koncová zařízení = koncová zařízení = zařízení, mezi kterými probíhá síťová komunikace (např. PC,
server apod.)

- LAN = místní (lokální) síť
- WAN = propojení více sítí
- Internet = všechny sítě na světě propojené dohromady

## Fyzická média
- Přenáší se pomocí nich data ve formě bitů (0 a 1)
  
- měděný kabel
  - přenáší bity pomocí elektronických signálů
  - UTP vs STP
    - UTP (Unshielded Twisted Pair) – více náchylný proti různým typům rušení
    - STP (Shielded Twisted Pair) – součástí je stínění proti rušení a elektrickému šumu
    - příklady:

    ![měďěný kabel](https://www.kenable.co.uk/204631-large_default/ethernet-network-cable-cat6-gigabit-rj45-copper-internet-patch-lead-10m-blue.jpg)

- optický kabel
  - používá optická vlákna k přenosu světla pomocí něhož jsou přenášny bity
  - vlákna tenká a křehká
  - příklady:

    ![optický kabel](https://rfindustries.com/wp-content/uploads/2020/06/fiber-optic-cable-types.jpg)

- koaxiální kabel
  - dnes již zastaralý
  - příklad:

    ![koaxiální kabel](https://cdn.ttgtmedia.com/rms/onlineImages/networking-coaixal_cable_01_mobile.jpg)

## Zprostředkující zařízení
- switch - propojuje zařízení v počítačové síti
- router – umožňuje routovat (směrovat) požadavky mimo LAN

## Server-client vs peer-to-peer
- server – poskytuje nějaké služby klientům
- klient – dotazuje se na server a přijímá služby

- peer-to-peer = není zde žádný centralizovaný server, zařízení si navzájem poskytují zdroje a služby

# Adresace

## IP adresa
- identifikační adresa zařízení v rámci sítě nebo Internetu
- IPv4 vs IPv6
  - IPv4 je 32-bitová → je pouze cca 4,3 miliard adres
  - to vedlo ke vzniku 128-bitové IPv6 adresy (340 undecillionů – undecillion má 36 nul)
  - ačkoliv se ještě hojně používá IPv4, tak už mnozí přecházejí na IPv6
- IPv4 adresa rozdělena na 4 oktety (ty jsou od sebe odděleny tečkami)
- privátní IPv4 adresy:

  | From        | To              |
  |:------------|:----------------|
  | 10.0.0.0    | 10.255.255.255  |
  | 172.16.0.0  | 172.31.255.255  |
  | 192.168.0.0 | 192.168.255.255 |

- loopback – zařízení posílá data samo sobě, localhost, nejčastější IP adresa 127.0.0.1 (je pro něj vyhrazen rozsah 127.0.0.0 do 127.255.255.255)
- další vyhrazené IPv4 adresy, například pro multicast (IP adresa pro více zařízení v síti, nikoliv však všechna)

## MAC adresa
- fyzická adresa síťové karty
- musí být unikátní
- má dvě části: první identifikuje výrobce, druhá samotnou kartu
- 48-bitová a zapsaná v hexadecimálním formátu
- příklad: 00:0a:95:9d:67:16
- podrobnosti o MAC adrese: https://maclookup.app
  
## Maska sítě
- určuje kolik je možno použít IP adres pro danou síť
- počet adres pro hosty získáme odečtením 2 od počtu všech použitelných IP adres (tyto 2 adresy jsou pro adresu sítě, z které se vše počítá, a pro broadcast, který reprezentuje všechny zařízení v síti – když pošlete něco na broadcast, posíláte to všem zařízením v síti)
- přehled masek sítě (cheatsheet)

![subnet mask cheatsheet](https://static.docsity.com/documents_first_pages/2019/09/02/7486fd161a127c39d507cb5034e13972.png)

## Výchozí brána
- adresa routeru, přes který jde síťový provoz mimo LAN (síťový provoz do dalších sítí)

## Statická vs dynamická analýza
- statická adresace
  - manuálně všem zařízením přiřadit IP adresu a masku sítě
  - náročné až nemožné ve velkých firmách a institucích
- dynamická adresace
  - adresace vykonána pomocí DHCP serveru (ten nejčastěji běží na routeru)

## DNS (domain name service)

- překlad doménových názvů na IP adresy
- domény jsou různého řádu, viz následující příklad:

>https://<span style="color:red">kb</span>.<span style="color:yellow">stuckinvim</span>.<span style="color:green">com</span>

- <span style="color:red">červeně</span> – doména 1. řádu
- <span style="color:yellow">žlutě</span> – doména 2. řádu
- <span style="color:green">zeleně</span> – doména 3. řádu


# Síťové vrstvy a protokoly
- protokol - sada pravidel, jimiž se řídí síťová komunikace

## Síťové vrstvy
- spíše pro zajímavost
- na každé vrstvé jsou nějaké protokoly, síťové prvky, datové jednotky

![]()

## Protokoly aplikační vrstvy
- HTTP (port 80) a HTTPS (port 443)
  - Používají se pro přenos webových stránek
  - HTTP nezabezpečené (komunikace v plain textu)
  - HTTPS šifrované

- Telnet (port 23) vs SSH (port 22)
  - používány pro vzdálené připojení k zařízení (CLI)
  - stejně jako HTTP je Telnet bezpečnostním rizikem a měl by být na zařízeních vypnutý
  - SSH (Secure shell) – šifrovaný nástupce Telnetu

- Přehled dalších četně používáných protokolů:
  - FTP
  - SFTP
  - FTPS
  - TFTP
  - SMTP
  - IMAP
  - POP3
  - DNS 
  - DHCP

## Protokoly transportní vrstvy
- TCP – kontroluje případné ztráty dat, je pomalejší než UDP
- UDP – celistvost dat nekontroluje, je rychlejší TCP

## ARP protokol
- protokol sloužící k získání MAC adresy jiného zařízení, pokud známe
pouze jen jeho IP adresu (v rámci síťové komunikace je nutné, aby znalo
zařízení, z kterého posíláme data, MAC adresu zařízení, které má data
přijmout)

# Příkazy

- ```ping```
  - zjistí spojení s daným zařízením
  - využívá protokol ICMP

  ```
  debian@debian:~$ ping -c 4 1.1.1.1
  PING 1.1.1.1 (1.1.1.1) 56(84) bytes of data.
  64 bytes from 1.1.1.1: icmp_seq=1 ttl=60 time=33.6 ms
  64 bytes from 1.1.1.1: icmp_seq=2 ttl=60 time=33.8 ms
  64 bytes from 1.1.1.1: icmp_seq=3 ttl=60 time=29.7 ms
  64 bytes from 1.1.1.1: icmp_seq=4 ttl=60 time=29.4 ms

  --- 1.1.1.1 ping statistics ---
  4 packets transmitted, 4 received, 0% packet loss, time 3006ms
  rtt min/avg/max/mdev = 29.388/31.611/33.795/2.078 ms
  debian@debian:~$
  ```

  ```
  debian@debian:~$ ping -c 4 archlinux.org
  PING archlinux.org (2a01:4f9:c010:6b1f::1) 56 data bytes
  64 bytes from archlinux.org (2a01:4f9:c010:6b1f::1): icmp_seq=1 ttl=48 time=43.3 ms
  64 bytes from archlinux.org (2a01:4f9:c010:6b1f::1): icmp_seq=2 ttl=48 time=61.9 ms
  64 bytes from archlinux.org (2a01:4f9:c010:6b1f::1): icmp_seq=3 ttl=48 time=39.2 ms
  64 bytes from archlinux.org (2a01:4f9:c010:6b1f::1): icmp_seq=4 ttl=48 time=59.9 ms

  --- archlinux.org ping statistics ---
  4 packets transmitted, 4 received, 0% packet loss, time 3005ms
  rtt min/avg/max/mdev = 39.190/51.056/61.854/9.944 ms
  debian@debian:~$
  ```
- ```traceroute```
  - zobrazuje celou cestu k danému zařízení
  - na Windows ```tracert```

  ```
  debian@debian:~$ traceroute archlinux.org
  traceroute to archlinux.org (95.217.163.246), 30 hops max, 60 byte packets
  1  compalhub.home (192.168.0.1)  5.790 ms  6.748 ms  8.238 ms
  2  * * *
  3  * * *
  4  ae10-0.prg10.core-backbone.com (5.56.18.205)  42.166 ms  42.143 ms  42.923 ms
  5  ae1-2081.sth10.core-backbone.com (80.255.14.194)  62.333 ms  62.309 ms  65.650 ms
  6  core-backbone.hetzner.com (80.255.15.126)  65.611 ms  40.562 ms  47.205 ms
  7  core52.sto.hetzner.com (213.239.252.65)  47.173 ms  49.175 ms  48.135 ms
  8  core31.hel1.hetzner.com (213.239.254.61)  62.113 ms core32.hel1.hetzner.com (213.239.254.69)  62.084 ms  62.056 ms
  9  * * *
  10  spine4.cloud1.hel1.hetzner.com (213.239.228.58)  187.749 ms spine3.cloud1.hel1.hetzner.com (213.239.228.54)  48.565 ms  51.638 ms
  11  * * *
  12  20996.your-cloud.host (65.108.115.145)  172.611 ms  138.926 ms  134.970 ms
  13  archlinux.org (95.217.163.246)  43.949 ms !X  49.199 ms !X  48.502 ms !X
  debian@debian:~$
  ```

- ```nslookup```
  - zjistí doménový překlad překlad pro doménu nebo IP adresu

- ```ip a``` (na Linuxu) nebo ```ipconfig``` (na Windows)
  - získání informací o konfiguraci sítě a síťových adaptérech