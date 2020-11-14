# Jarkom_Modul2_Lapres_T11

1. 05311840000007 - I Gde Made Bhaskara Jala Dhananjaya
2. 05311840000023 - Robby Irvine Surya
</br></br>

### Soal DNS
- [No. 1](#1)
- [No. 2](#2)
- [No. 3](#3)
- [No. 4](#4)
- [No. 5](#5)
- [No. 6](#6)
- [No. 7](#7)
### Soal Web Server
- [No. 8](#8)
- [No. 9](#9)
- [No. 10](#10)
- [No. 11](#11)
- [No. 12](#12)
- [No. 13](#13)
- [No. 14](#14)
- [No. 15](#15)
- [No. 16](#16)
- [No. 17](#17)
</br></br></br>

<a name="1"></a>
## No. 1
### Membuat website utama dengan alamat http://semerut11.pw
- Buka UML MALANG dan jalankan command: ```apt-get update```
- Lalu install aplikasi bind9 dengan command: ```apt-get install bind9 -y```
- Lalu ketik command:```nano /etc/bind/named.conf.local```
- Lalu bisa mengkonfigurasi domain semerut11.pw sebagai berikut:
```
zone "semerut11.pw" {
	type master;
	file "/etc/bind/jarkom/semerut11.pw";
};
```
- Buat folder ```jarkom``` pada directory ```/etc/bind``` , dengan command: ```mkdir /etc/bind/jarkom```
- Salin file ```db.local``` pada ```/etc/bind``` ke dalam  folder jarkom dengan command: ```cp /etc/bind/db.local /etc/bind/jarkom/semerut11.pw```
- Edit file tersebut dengan command: ```nano /etc/bind/jarkom/semerut11.pw```
- Kemudian restart bind9: ```service bind9 restart```
- Pada client GRESIK dan SIDOARJO arahkan nameserver menuju IP MALANG dengan mengedit file ```resolve.conf``` dengan command: ```nano /etc/resolv.conf```
```
nameserver 10.151.77.138     #IP MALANG
```
- Ping domain semerut11.pw dengan melakukan command: ```ping semerut11.pw```, pada client GRESIK dan SIDOARJO
</br></br></br>
