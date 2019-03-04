<h1 align="center"><img src="/etc/humhub.jpg"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**Humhub** merupakan perangkat lunak jaringan sosial dan *framework* yang dibuat untuk memudahkan komunikasi dan kolaborasi. 
Humhub merupakan software yang ringan, kuat dan dengan tampilan yang *user-friendly*. Kelebihan dari humhub antara lain merupakan *software* *open source*,
*flexibel*, aman, dan memiliki layanan profesional. 

# Instalasi
[`^ kembali ke atas ^`](#)

#### Server Requirements :
<li>Shell access (e.g. ssh) to server</li> 
<li>PHP 5.6 - 7.2.x (PHP 7.2+ is supported since HumHub 1.3)</li> 
<li>MySQL (5.5 or later) or MariaDB with utf8mb4 character set support and InnoDB storage engine installed</li> 
<li>A minimum 500 MB of free disk space</li> 
<li>A minimum 64 MB of memory allocated to PHP</li> 
<li>A minimum of 50 MB of database space</li> 

#### Langkah Instalasi:
#### Step 1 : Install LAMP Stack
Lamp merupakan singkatan dari **L**inux operating system, **A**pache HTTP Server, **M**ySQL relational database system, dan bahasa pemrograman **P**HP. Hal-hal tersebut digunakan oleh server untuk hosting suatu website atau aplikasi web.

Cara instalasi di terminal bisa dilakukan dengan: 

   ```
  $ sudo apt-get install lamp-server^ -y
   ```

#### Step 2 : Install PHP Extentensions
Ketika anda sudah menginstall LAMP, masih ada beberapa ekstensi PHP yang diperlukan untuk menjalankan Humhub.

Cara instalasi di terminal :

   ```
  $ sudo apt-get install php-curl php-gd php-mbstring -y
  $ sudo apt-get install php-intl php-zip -y
  $ sudo apt-get install php-ldap php-apcu php-sqlite3 -y
   ```
Jika anda masih menemukan error, mungkin anda perlu versi PHP yang sesuai. Hal ini kami menggunakan PHP versi 7.2. 

Contoh instalasi pada versi 7.2 :

  ```
  $ sudo apt-get install php7.2-curl php7.2-gd php7.2-mbstring -y
  $ sudo apt-get install php7.2-intl php7.2-zip -y
  $ sudo apt-get install php7.2-ldap php7.2-apcu php7.2-sqlite3 -y
   ```
Anda dapat menyesuaikan versi PHP yang anda butuhkan dengan hanya mengubah code diatas sesuai dengan versi PHP lainnya.

#### Step 3 : Restart dan Mengaktifkan Apache Service

Lakukan code berikut :

  ```
 $ sudo systemctl restart apache2
 $ systemctl enable apache2
   ```


# Konfigurasi
[`^ kembali ke atas ^`](#)


# Maintenance
[`^ kembali ke atas ^`](#)


# Otomatisasi
[`^ kembali ke atas ^`](#)

# Cara Pemakaian
[`^ kembali ke atas ^`](#)


# Pembahasan
[`^ kembali ke atas ^`](#)


# Referensi
[`^ kembali ke atas ^`](#)
