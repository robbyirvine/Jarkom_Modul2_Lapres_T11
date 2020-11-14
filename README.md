# Jarkom_Modul2_Lapres_T11

1. 05311840000007 - I Gde Made Bhaskara Jala Dhananjaya
2. 05311840000023 - Robby Irvine Surya


## Daftar Isi
### DNS
  1. [Nomor 1](#1)
  2. [Nomor 2](#2)
  3. [Nomor 3](#3)
  4. [Nomor 4](#4)
  5. [Nomor 5](#5)
  6. [Nomor 6](#6)
  7. [Nomor 7](#7)
### Web Server
  8. [Nomor 8](#8)
  9. [Nomor 9](#9)
  10. [Nomor 10](#10)
  11. [Nomor 11](#11)
  12. [Nomor 12](#12)
  13. [Nomor 13](#13)
  14. [Nomor 14](#14)
  15. [Nomor 15](#15)
  16. [Nomor 16](#16)
  17. [Nomor 17](#17)
  </br></br></br>


<a name="1"></a>
## SOAL NO 1
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
- Lakukan ping domain semerut11.pw dengan melakukan perintah berikut pada client GRESIK dan SIDOARJO ```ping semerut11.pw```
</br></br></br>
