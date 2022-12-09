# Jarkom-Modul-5-B11-2022

### Kelompok B11

| **No** | **Nama**              | **NRP**    |
| ------ | --------------------- | ---------- |
| 1      | Cahyadi Surya Nugraha | 5025201184 |
| 2      | Sarah Alissa Putri    | 5025201272 |
| 3      | Ravin Pradhitya       | 5025201068 |

## List

1. [Soal A](#Question-A)
2. [Soal B](#Question-B)
3. [Soal C](#Question-C)
4. [Soal D](#Question-D)
5. [Soal 1](#Question-1)
6. [Soal 2](#Question-2)
7. [Soal 3](#Question-3)
8. [Soal 4](#Question-4)
9. [Soal 5](#Question-5)
10. [Soal 6](#Question-6)

## Konfigurasi

- **Strix**

    ```
    auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
hwaddress ether 6e:96:f5:fa:c5:4b

auto eth1
iface eth1 inet static
address 192.178.7.145
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.178.7.149
netmask 255.255.255.252
    ```

- **Ostania**

    ```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.178.7.150
netmask 255.255.255.252
gateway 192.178.7.149

auto eth1
iface eth1 inet static
address 192.178.7.137
netmask 255.255.255.248

auto eth2
iface eth2 inet static
address 192.178.4.1
netmask 255.255.254.0

auto eth3
iface eth3 inet static
address 192.178.6.1
netmask 255.255.255.0
    ```

- **Westalis**

    ```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.178.7.146
netmask 255.255.255.252
gateway 192.178.7.145

auto eth1
iface eth1 inet static
address 192.178.7.129
netmask 255.255.255.248

auto eth2
iface eth2 inet static
address 192.178.7.1
netmask 255.255.255.128

auto eth3
iface eth3 inet static
address 192.178.0.1
netmask 255.255.252.0
    ```

- **Eden**

    ```
auto eth0
iface eth0 inet static
address 192.178.7.130
netmask 255.255.255.248
gateway 192.178.7.129
    ```

- **Wise**

    ```
    auto eth0
    iface eth0 inet dhcp
    ```

- **Garden**

    ```
    auto eth0
    iface eth0 inet dhcp
    ```

- **SSS**

    ```
    auto eth0
    iface eth0 inet dhcp
    ```

- **Semua Client**

    ```
    auto eth0
    iface eth0 inet dhcp
    ```

## Question A

> Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Loid dibawah ini:
> Eden adalah DNS Server
> WISE adalah DHCP Server
> Garden dan SSS adalah Web Server
> Jumlah Host pada Forger adalah 62 host
> Jumlah Host pada Desmond adalah 700 host
> Jumlah Host pada Blackbell adalah 255 host
> Jumlah Host pada Briar adalah 200 host

### Answer

![image](https://i.ibb.co/NNdfYCX/Capture1.png)

## Question B

> Untuk menjaga perdamaian dunia, Loid ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM setelah melakukan subnetting.

### Answer
Teknik yang digunakkan adalah VLSM

![image](https://i.ibb.co/NNdfYCX/Capture.png)

![image](https://i.ibb.co/NNdfYCX/Capture2.png)

![image](https://i.ibb.co/NNdfYCX/Capture3.png)

## Question C

> Anya, putri pertama Loid, juga berpesan kepada anda agar melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.

### Script

PENJELASAN

> Script dibawah ini terdapat pada **root node Westalis**, untuk menjalankannya bisa langsung dengan melakukan command `bash no1.sh`

- **Westalis**
    ```
    echo "# Defaults for isc-dhcp-server initscript
    # sourced by /etc/init.d/isc-dhcp-server
    # installed at /etc/default/isc-dhcp-server by the maintainer scripts

    #
    # This is a POSIX shell fragment
    #

    # Path to dhcpd's config file (default: /etc/dhcp/dhcpd.conf).
    #DHCPD_CONF=/etc/dhcp/dhcpd.conf

    # Path to dhcpd's PID file (default: /var/run/dhcpd.pid).
    #DHCPD_PID=/var/run/dhcpd.pid

    # Additional options to start dhcpd with.
    #       Don't use options -cf or -pf here; use DHCPD_CONF/ DHCPD_PID instead
    #OPTIONS=\"\"

    # On what interfaces should the DHCP server (dhcpd) serve DHCP requests?
    #       Separate multiple interfaces with spaces, e.g. "eth0 eth1".
    INTERFACES=\"eth0\"" > /etc/default/isc-dhcp-server

    service isc-dhcp-server start
    ```

### Test
Teknik yang digunakkan adalah VLSM

![image](https://i.ibb.co/NNdfYCX/Capture.png)

## Question D

> Tugas berikutnya adalah memberikan ip pada subnet Forger, Desmond, Blackbell, dan Briar secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.

### Script

PENJELASAN

> Script dibawah ini terdapat pada **root node Westalis**, untuk menjalankannya bisa langsung dengan melakukan command `bash no1.sh`

- **Westalis**
    ```
    echo "# Defaults for isc-dhcp-server initscript
    # sourced by /etc/init.d/isc-dhcp-server
    # installed at /etc/default/isc-dhcp-server by the maintainer scripts

    #
    # This is a POSIX shell fragment
    #

    # Path to dhcpd's config file (default: /etc/dhcp/dhcpd.conf).
    #DHCPD_CONF=/etc/dhcp/dhcpd.conf

    # Path to dhcpd's PID file (default: /var/run/dhcpd.pid).
    #DHCPD_PID=/var/run/dhcpd.pid

    # Additional options to start dhcpd with.
    #       Don't use options -cf or -pf here; use DHCPD_CONF/ DHCPD_PID instead
    #OPTIONS=\"\"

    # On what interfaces should the DHCP server (dhcpd) serve DHCP requests?
    #       Separate multiple interfaces with spaces, e.g. "eth0 eth1".
    INTERFACES=\"eth0\"" > /etc/default/isc-dhcp-server

    service isc-dhcp-server start
    ```

### Test
Teknik yang digunakkan adalah VLSM

![image](https://i.ibb.co/NNdfYCX/Capture.png)