# Jarkom_Modul2_Lapres_T11
Repositori sebagai Laporan Resmi Soal Praktikum Modul 2 Praktikum Komunikasi Data dan Jaringan Komputer 2020\
Disusun oleh :
```
Kelompok    :   T11
Anggota     :   I Gde Made Bhaskara Jala Dhananjaya (05311840000007)
                Robby Irvine Surya                  (05311840000023)
Departemen  :   Teknologi Informasi
```

## Pendahuluan
- Kami melakukan konfigurasi terhadap file `topologi.sh` pada puTTy dan menambahkan server **PROBOLINGGO**, sebelum masuk lebih jauh ke soal.
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/topologi.sh.png)
- Server **PROBOLINGGO** juga ditambahkan ke file `bye.sh`. \
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/bye.sh.png)
- UML Surabaya menjadi router sesuai dengan Modul sebelumnya, IP Forwarding diaktifkan dengan command `/etc/sysctl.conf` dan `sysctl -p` untuk mengaktifkannya. \
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/SBY%202.png)
- Kemudian, IP setiap UML disetting dalam file `/etc/network/interfaces` dengan keterangan sebagai berikut :
### SURABAYA sebagai Router
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/SBY%201.png)
### MALANG sebagai DNS Master Server
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/MLG%201.png)
### MOJOKERTO sebagai DNS Salve Server
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/MJRT%201.png)
### PROBOLINGGO sebagai Web Server
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/PRB%201.png)
### GRESIK sebagai Client
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/GRS%201.png)
### SIDOARJO sebagai Client
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/SDJ%201.png)

- Kemudan seluruh IP diaktifkan dengan command `service networking restart`. Jalankan command `iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16` pada Router **SURABAYA** dengan tujuan agar dapat terkoneksi ke internet. Kemudian, masukan command di bawah ini untuk mengexport proxy pada UML :
```
export http_proxy="http://DPTSI-562455-7f4b5:e04f1@proxy.its.ac.id:8080"
export https_proxy="http://DPTSI-562455-7f4b5:e04f1@proxy.its.ac.id:8080"
export ftp_proxy="http://DPTSI-562455-7f4b5:e04f1@proxy.its.ac.id:8080"
```
- Kemudian, pada server **MALANG** dan **MOJOKERTO**, install aplikasi **bind9** dengan command :
`apt-get install bind9 -y`
- Terakhir, pada server **PROBOLINGGO**, install aplikasi apache2 dengan command :
`apt-get install apache2 -y`

### Soal DNS
- [No. 1](#1)
- [No. 2](#2)
</br></br></br>

<a name="1"></a>
## No. 1 
### Membuat website utama dengan alamat http://semerut11.pw
- Buka UML **MALANG**, kemudian jalankan command `apt-get update`.
- Kemudian install aplikasi bind9 dengan command `apt-get install bind9 -y`.
- Kemudian, ketik command `nano /etc/bind/named.conf.local` kemudian lakukan konfigurasi domain semerut11.pw sebagai berikut:
```
zone "semerut11.pw" {
	type master;
	file "/etc/bind/jarkom/semerut11.pw";
};
```
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/1A.png)

- Kemudian. buat folder `jarkom` pada directory `/etc/bind` , dengan command `mkdir /etc/bind/jarkom`.
- Lalu, salin file `db.local` pada `/etc/bind` ke dalam  folder jarkom dengan command `cp /etc/bind/db.local /etc/bind/jarkom/semerut11.pw`.
- Kemudian, edit file tersebut dengan command: `nano /etc/bind/jarkom/semerut11.pw`. Dengan rincian sebagai berikut :
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/1B.png)
- Kemudian restart bind9  ```service bind9 restart```
- Pada client GRESIK dan SIDOARJO arahkan nameserver menuju IP MALANG dengan mengedit file ```resolve.conf``` dengan command: ```nano /etc/resolv.conf```
```
nameserver 10.151.77.138     #IP MALANG
```
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/1C.png)

- Ping domain semerut11.pw dengan melakukan command: `ping semerut11.pw`, pada client **GRESIK** dan **SIDOARJO**.
### Dokumentasi Hasil
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/1D.png)
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/1E.png)

</br></br></br>

<a name="2"></a>
## No. 2
### Membuat alias http://semerut11.pw
- Pada UML MALANG, konfigurasi file `semerut11.pw` dengan command: `nano /etc/bind/jarkom/semerub12.pw`.
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/2A.png)

### Dokumentasi Hasil
![](https://github.com/robbyirvine/Jarkom_Modul2_Lapres_T11/blob/main/UML/Erorrr.png)

### Kami sudah mengalami eror ini selama 4 hari, dan sudah mencoba selalu namun tidak bisa diatasi

