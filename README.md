# Jarkom-Modul-5-T09-2021

Nama Anggota | NRP
------------------- | --------------		
Natasya Abygail N | 05111940000020
Muhammad Hilmi Ramadhan | 05311940000044
Sri Puspita Dewi | 05111940000045

## List of Contents :
- [Konfigurasi A](#konfigurasi-a)
- [Konfigurasi B](#konfigurasi-b)
- [Konfigurasi C](#konfigurasi-c)
- [Konfigurasi D](#konfigurasi-d)
- [Soal 1](#soal-1)
- [Soal 2](#soal-2)
- [Soal 3](#soal-3)
- [Soal 4](#soal-4)
- [Soal 5](#soal-5)
- [Soal 6](#soal-6)

## Catatan
---
1. CIDR dikerjakan di GNS3
2. Prefix IP menggunakan `10.46.0.0`

Detil soal dapat dilihat pada [tautan ini](https://docs.google.com/document/d/1Sc2jTlqmyM149yi4QzOGijyjPmSeEoy14Ajg9MnmkuY/edit)


## Konfigurasi A
---
![Foto](./img/config/topologi.jpg)
<br>

Diberikan sebuah topologi seperti diatas yang mana kami diminta untuk menyelesaikannya dalam `Subnetting`. Dalam hal ini dengan metode `CIDR`.

`Keterangan` :     
1. Doriki adalah DNS Server
2. Jipangu adalah DHCP Server
3. Maingate dan Jorge adalah Web Server
4. Jumlah Host pada Blueno adalah 100 host
5. Jumlah Host pada Cipher adalah 700 host
6. Jumlah Host pada Elena adalah 300 host
7. Jumlah Host pada Fukurou adalah 200 host

## Konfigurasi B
---

Selanjutnya kami melakukan pembagian subnetting seperti berikut:

1. Melakukan pembagian subnet terhadap topologi yang ada dengan Class A:
![Foto](./img/config/cidra.jpg)
<br>

2. Melakukan pembagian subnet terhadap topologi yang ada dengan Class B:
![Foto](./img/config/cidrab.jpg)
<br>
  
3. Melakukan pembagian subnet terhadap topologi yang ada dengan Class C:
![Foto](./img/config/cidrabc.jpg)
<br>
  
4. Melakukan pembagian subnet terhadap topologi yang ada dengan Class D:
![Foto](./img/config/cidrabcd.jpg)
<br>
  
5. Melakukan pembagian subnet terhadap topologi yang ada dengan Class E:
![Foto](./img/config/cidrabcde.jpg)
<br>
  
### Kemudian kami melakukan pembagian IP dan Tree seperti berikut:
---
1. Pertama-tama dari pembagian subnet Class A kami menghitung penggunaan IP sehingga didapatkan pembagiannya sebagai berikut:
![Foto](./img/config/tabelip1.jpg)
<br>

2. Selanjutnya kami mendetilkan pembagian IP berdasarkan hasil dari pembagian subnetting kelas B, C, D, dan E sebagai berikut:
![Foto](./img/config/tabelip2.jpg)
<br>

3. Lalu kami membuat tree berdasarkan pembagian subnetting dan Netmask metode CIDR guna mendapatkan NID yang spesifik dalam suatu subnett sebagai berikut:
![Foto](./img/config/treeip.jpg)
<br>

4. Setelah sudah maka didapatkan NID spesifik dalam suatu subnetting, maka kami menghitung broadcast address dan di tabelkan agar mudah dalam konfigurasi di GNS3 nantinya. Adapun tabel pembagian NID, Netmask, dan Broadcast Address sebagai berikut:
    - Contoh perhitungan mencari Broadcast dan Netmask dari sebuah NID:
    ![Foto](./img/config/perhitungan.jpg)
    - Tabel selengkapnya:
    ![Foto](./img/config/tabelnidlengkap.jpg)



### Lalu kami melakukan konfigurasi awal tepatnya pada `network configuration` di setiap node pada platform GNS3:
---

1. Pada node yang dijadikan Router sesuai dengan perhitungan `Subnetting` dengan metode `CIDR` maka kami mengkonfignya sebagai berikut:
    - Foosha sebagai berikut: \
      Pada awal ini kami menghubungkan router Foosha melalui `eth0` menuju `NAT` dengan `DHCP`. Ketika masuk di nomer 1 kami merubahnya menjadi `Static IP`
    ![Foto](./img/config/conffoosha.jpg)
    - Water7 sebagai berikut:
    ![Foto](./img/config/confwater7.jpg)
    - Guanhao sebagai berikut:
    ![Foto](./img/config/confguanhao.jpg)

2. Pada `Doriki` **(DNS Server)** dan `Jipangu` **(DHCP Server)** kami konfigurasi sebagai berikut:
    - Doriki sebagai berikut:
    ![Foto](./img/config/confdoriki.jpg)
    - Jipangu sebagai berikut:
    ![Foto](./img/config/confjipangu.jpg)

3. Pada `Client` kami konfigurasi sebagai berikut:
    - Blueno sebagai berikut:
    ![Foto](./img/config/confblueno.jpg)
    - Cipher sebagai berikut:
    ![Foto](./img/config/confcipher.jpg)
    - Elena sebagai berikut:
    ![Foto](./img/config/confelena.jpg)
    - Fukurou sebagai berikut:
    ![Foto](./img/config/conffukurou.jpg)

4. Pada `Web Server` kami konfigurasi sebagai berikut:
    - Jorge sebagai berikut:
    ![Foto](./img/config/confjorge.jpg)
    - MainGate sebagai berikut:
    ![Foto](./img/config/confmaingate.jpg)

## Konfigurasi C
---

Lalu pada hal ini kami diminta untuk melakukan Routing agar setiap perangkat pada jaringan tersebut terhubung.

