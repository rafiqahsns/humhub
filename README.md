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
 $ sudo systemctl enable apache2
   ```
Jika anda sudah melakukan code tersebut, anda bisa langsung mengakses localhost di browser dan jika berhasil akan muncul halaman seperti ini:

#### Step 4 : Konfigurasi Database MySQL 

Dalam step ini, anda membuat sebuah database user untuk Humhub. Lakukan code berikut di terminal anda :

   ```
 $ sudo mysql -u root -p
   ```   
Jika anda hanya mau mencoba testing saja, cukup tekan enter untuk inisialisasi MySQL. Selain itu anda juga bisa membuat kata sandi root MySQL anda. Setelah anda sudah membuat kata sandi, MySQL akan terbuka ketika anda memasukkan code berikut:

   ```
	CREATE DATABASE `humhub` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
	GRANT ALL ON `humhub`.* TO '<your_username>'@'localhost' IDENTIFIED BY '<your_password>'; 
	FLUSH PRIVILEGES; 
	EXIT;
   ```   

#### Step 5 : Install HumHub 

Setelah anda sudah menyiapkan hal-hal diatas, anda sudah dapat menginstall Humhub. Versi humhub yang kami install adalah HumHub 1.3.1. Namun, anda bisa menginstall versi HumHub terbaru hanya dengan mengubah url pada baris pertama code dibawah ini. Anda bisa melihat url versi terbaru pada website HumHub.

Code dibawah akan menginstall HumHub versi 1.3.1 :

   ```
	wget https://www.humhub.org/en/download/package/humhub-1.3.1.tar.gz
	mv humhub-1.3.1.tar.gz /var/www/html
	cd /var/www/html
	tar -zxvf humhub-1.3.1.tar.gz
	chmod -R 777 humhub
   ```   

#### Step 6 : Install ekstensi HumHub yang diperlukan '

Sebelum anda mengkonfigurasi HumHub dan mulai menggunakannya, Anda perlu memastikan semua ekstensi yang diperlukan untuk menjalankan HumHub sudah terinstall semua. Anda perlu mengulangi tahap-tahap tersebut sampai semua ekstensi PHP terpenuhi.

1. jika semua sudah berjalan dengan baik, sekarang anda sudah bisa akses page konfigurasi HumHub di browser anda dengan mengakses localhost. Halaman konfigurasi terlihat seperti dibawah ini:

2. Setelah anda   


   
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
