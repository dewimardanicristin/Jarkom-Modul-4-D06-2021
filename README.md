# Jarkom-Modul-4-D06-2021

Anggota :

- Fitrah Mutiara 05111940000126
- Ahdan Amanullah Irfan Muzhaffar 05111940000197
- Dewi Mardani 05111940000225

## VLSM
### Menghitung NID

<img width="548" alt="image" src="https://user-images.githubusercontent.com/81247727/143670041-e0e4dfd0-4334-4f67-b353-f1c3e9261d6f.png">

Didapatkan 15 subnet dengan total jumlah IP sebanyak 5847 dengan netmask /19:

<img width="272" alt="image" src="https://user-images.githubusercontent.com/81247727/143670071-0d9f75c6-7d2f-4d75-859a-fad34f55b6f6.png">

Kemudian dihitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon serta melakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada

<img width="520" alt="image" src="https://user-images.githubusercontent.com/81247727/143670171-4c6f1f96-c3cc-41d7-b5af-80bc35caf7b7.png">

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
### Melakukan Routing

