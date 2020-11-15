# Jarkom_Modul2_Lapres_T11
Repositori sebagai Laporan Resmi Soal Praktikum Modul 2 Praktikum Komunikasi Data dan Jaringan Komputer 2020\
Disusun oleh :
```
Kelompok    :   T11
Anggota     :   I Gde Made Bhaskara Jala Dhananjaya (05311840000007)
                Robby Irvine Surya                  (05311840000023)
Departemen  :   Teknologi Informasi
'''

### Soal DNS
- [No. 1](#1)
- [No. 2](#2)
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

INSERT PICTURE (1d/c)

</br></br></br>

<a name="2"></a>
## No. 2
### Membuat alias http://semerut11.pw
- Pada UML MALANG, konfigurasi file ```semerut11.pw``` dengan command: ```nano /etc/bind/jarkom/semerub12.pw```

INSERT PICTURE (2a) 

