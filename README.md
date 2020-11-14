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
### membuat sebuah website utama dengan alamat http://semerut11.pw yang memiliki
- Buka MALANG dan update package lists dengan menjalankan command: ```apt-get update```
- Install aplikasi bind9 pada MALANG ```apt-get install bind9 -y```
- Pada MALANG lakukan perintah ```nano /etc/bind/named.conf.local```
- Konfigurasi domain semerub12.pw berisi:
```
zone "semerub12.pw" {
	type master;
	file "/etc/bind/jarkom/semerub12.pw";
};
```

- ![testestes](/ss/1-1.png)
   
- Buat folder ```jarkom``` pada directory ```/etc/bind``` : ```mkdir /etc/bind/jarkom```
- Salin file ```db.local``` pada ```/etc/bind``` ke dalam  folder jarkom dengan perintah: ```cp /etc/bind/db.local /etc/bind/jarkom/semerub12.pw```
- Buka dan edit file semerub12.pw dengan perintah ```nano /etc/bind/jarkom/semerub12.pw```
    ![testestes](/ss/1-2.png)
    
- Kemudian restart bind9 dengan perintah ```service bind9 restart```
- Pada client GRESIK dan SIDOARJO arahkan nameserver menuju IP MALANG dengan mengedit file resolve.conf dengan perintah ```nano /etc/resolv.conf```
```
nameserver 10.151.71.162     #IP MALANG
```
- ![testestes](/ss/1-3.png)
    
- Untuk mencoba koneksi DNS, lakukan ping domain semerub12.pw dengan melakukan perintah berikut pada client GRESIK dan SIDOARJO ```ping semerub12.pw```
</br></br></br>
