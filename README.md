# Jarkom-Modul-4-D06-2021

Anggota :

- Fitrah Mutiara 05111940000126
- Ahdan Amanullah Irfan Muzhaffar 05111940000197
- Dewi Mardani 05111940000225

## VLSM
### Menentukan subnet pada topologi

<img width="548" alt="image" src="https://user-images.githubusercontent.com/81247727/143670528-87516f75-9f8d-4ba9-b78a-362c601f6a6f.png">

### Menentukan jumlah IP dan netmask pada setiap subnet
Didapatkan 15 subnet dengan total jumlah IP sebanyak 5851 dengan netmask /19:

<img width="275" alt="image" src="https://user-images.githubusercontent.com/81247727/143671319-a4f48e22-3413-4e59-a7b0-913f8cf92b99.png">

### Menghitung NID
Kemudian dihitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon serta melakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada

![Untitled Diagram drawio](https://user-images.githubusercontent.com/73428220/143673974-70d007fe-ebb6-4ec6-b694-32beb5a977a9.png)


Akan didapatkan pembagian IP sebagai berikut:

<img width="502" alt="image" src="https://user-images.githubusercontent.com/81247727/143670183-681a3858-6aaf-40e2-8168-7a972076744f.png">

### Mengatur IP di GNS 3
- Edit configuration pada setiap interface
- Misal pada Water 7, diberikan konfigurasi sebagai berikut:
```
auto eth0
iface eth0 inet static
	address 10.24.27.150
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.24.27.153
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.24.16.1
	netmask 255.255.252.0
```
- Pada Cipher
```
auto eth0
iface eth0 inet static
	address 10.24.16.2
	netmask 255.255.252.0
```
- Pada Doriki
```
auto eth0
iface eth0 inet static
	address 10.24.27.162
	netmask 255.255.255.252
```
### Melakukan Routing
- Foosha
```
route add -net 10.24.16.0 netmask 255.255.252.0 gw 10.24.27.146
route add -net 10.24.27.148 netmask 255.255.255.252 gw 10.24.27.146
route add -net 10.24.27.0 netmask 255.255.255.128 gw 10.24.27.146
route add -net 10.24.0.0 netmask 255.255.248.0 gw 10.24.27.146

route add -net 10.24.24.0 netmask 255.255.254.0 gw 10.24.27.154
route add -net 10.24.20.0 netmask 255.255.252.0 gw 10.24.27.154
route add -net 10.24.27.128 netmask 255.255.255.240 gw 10.24.27.154
route add -net 10.24.27.156 netmask 255.255.255.252 gw 10.24.27.154
route add -net 10.24.26.0 netmask 255.255.255.0 gw 10.24.27.154
route add -net 10.24.12.0 netmask 255.255.252.0 gw 10.24.27.154
route add -net 10.24.27.164 netmask 255.255.255.252 gw 10.24.27.154
```
- Guanhao
```
route add -net 10.24.27.128 netmask 255.255.255.240 gw 10.24.24.3
route add -net 10.24.26.0 netmask 255.255.255.0 gw 10.24.27.158
route add -net 10.24.12.0 netmask 255.255.252.0 gw 10.24.27.158
route add -net 10.24.27.164 netmask 255.255.255.252 gw 10.24.27.158
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.27.153
```

- Alabasta
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.24.1
```

- OIMO
```
route add -net 10.24.12.0 netmask 255.255.252.0 gw 10.24.26.3
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.27.157
```

- Seastone
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.26.1
```

- Water7
```
route add -net 10.24.27.0 netmask 255.255.255.128 gw 10.24.27.150
route add -net 10.24.0.0 netmask 255.255.248.0 gw 10.24.27.150
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.27.145
```

- Pucci
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.24.27.149
```
## CIDR 

