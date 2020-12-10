# Jarkom_Modul4_Lapres_C04

### Anggota Kelompok C04 :
#### 05111840000029 - Khofifah Nurlaela
#### 05111840000053 - Yulia Niza
<br>

##### Tabel 1. Subnetting
![alt text](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/blob/modul-4/assets/1.png?raw=true)

## 1. Cisco Packet Tracer dengan Metode VLSM

### Persiapan
#### Langkah 1 
Mentukan jumlah subnet yang ada di dalam topologi

<img src="VLSM/Picture1.png" width="800">


Lalu menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan melakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan dengan melihat pada tabel subnet.
##### Tabel 2. Pembagian IP
<img src="VLSM/Picture3.png" width="600" >

Berdasarkan total IP dan netmask yang dibutuhkan, maka kita dapat menggunakan netmask /19 untuk memberikan pengalamatan IP pada subnet.

#### Langkah 2
Subnet besar yang dibentuk memiliki NID 192.168.0.0 dengan netmask /19. Lalu Hitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon seperti gambar di bawah dan lakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada.
<img src="VLSM/Picture5.png" >

Dari pohon dari pohon tersebut akan diperoleh pembagian IP sesuai pada **Tabel 2. Pembagian IP** diatas


### Praktik
#### Membuat Topologi
<img src="VLSM/Picture6.png" width="600" >

#### Subnetting

Mengatur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM diatas tadi
Interface dapat diatur pada menu Config > INTERFACE > “nama interface”.

#### Interface Router - Router
Misal pada **subnet A5** SURABAYA yang mengarah ke BATU dengan **eth1/1** lalu isi dengan data sesuai **Tabel 2. Pembagian IP** disini kita menggunakan NID+1 yaitu 192.168.0.5.

<img src="VLSM/Picture7.png" width="500" >

dan mengatur IP pada interface BATU yang mengarah ke SURABAYA, disini kita menggunakan NID+2 yakni 192.168.0.6

<img src="VLSM/Picture8.png" width="500" >

#### Interface Router - Client
Misal **subnet A8** Mengatur IP pada interface BATU yang mengarah ke client NGANJUK yakni 192.168.12.1
<img src="VLSM/Picture9.png" width="500" >

dan mengatur IP pada interfaces client NGANJUK yakni 192.168.12.2 dan IP Gateway yang mengarah ke BATU yakni 192.168.12.1
<img src="VLSM/Picture10.png" width="500" >

#### Interface Router - Server, 
konfigurasinya sama seperti Router - Client tetapi menggunakan IP DMZ masing-masing kelompok dan dibagi 2 karena server berada pada subnet yang berbeda.
IP DMZ kelompok kami adalah 10.151.77.40 sehingga untuk server MOJOKERTO dihasilkan IP dengan range antara 10.151.77.40-10.151.77.43 dan server MALANG 10.151.77.44-10.151.77.47.
Misal untuk interface SURABAYA yang mengarah ke MOJOKERTO, maka digunakan IP 10.151.77.41

<img src="VLSM/Picture11.png" width="500" >
dan pada interface MOJOKERTO digunakan IP 10.151.77.42 dengan IP Gateway yang mengarah ke SURABAYA yakni 10.151.77.41

<img src="VLSM/Picture12.png" width="500" >

Setelah melakukan konfigurasi alamat IP pada setiap interfaces, maka langkah selanjutnya adalah routing

<br>

#### Routing

<img src="VLSM/Picture4.png" width="500" >



## 2. UML dengan Metode CIDR
