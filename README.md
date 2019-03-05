<h1 align="center"><img src="/etc/logohumhub.jpg"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**Humhub** merupakan perangkat lunak jaringan sosial dan *framework* yang dibuat untuk memudahkan komunikasi dan kolaborasi. 
Humhub merupakan software yang ringan, kuat dan dengan tampilan yang *user-friendly*. Kelebihan dari humhub antara lain merupakan *software* *open source*,
*flexibel*, aman, dan memiliki layanan profesional. 

# Instalasi
[`^ kembali ke atas ^`](#)

#### Server Requirements :
<li>Shell access (e.g. ssh) ke server</li> 
<li>PHP 5.6 - 7.2.x (PHP 7.2+ mulai disupport pada HumHub 1.3)</li> 
<li>MySQL atau MariaDB dengan utf8mb4 character set support dan InnoDB storage engine yang sudah terinstall</li> 
<li>Minimal kapasitas disk: 500 MB</li> 
<li>Minimal alokasi memory untuk PHP: 64 MB</li> 
<li>Miniml kapasitas untuk database: 50 MB</li> 

#### Langkah Instalasi:
#### Langkah 1 : Install LAMP Stack
LAMP merupakan singkatan dari **L**inux operating system, **A**pache HTTP Server, **M**ySQL relational database system, dan bahasa pemrograman **P**HP. Hal-hal tersebut digunakan oleh server untuk hosting suatu website atau aplikasi web.

Cara instalasi di terminal bisa dilakukan dengan: 

   ```
  $ sudo apt-get install lamp-server^ -y
   ```
<img src="/etc/1.JPG" align=center>

#### Langkah 2 : Install PHP Extentensions
Ketika anda sudah menginstall LAMP, masih ada beberapa ekstensi PHP yang diperlukan untuk menjalankan Humhub.

Cara instalasi di terminal :

   ```
  $ sudo apt-get install php-curl php-gd php-mbstring -y
  $ sudo apt-get install php-intl php-zip -y
  $ sudo apt-get install php-ldap php-apcu php-sqlite3 -y
   ```
Gambar-gambar contoh instalasi :
<img src="/etc/5.JPG" align=center>

Jika menemukan error, gunakan versi PHP yang sesuai.

#### Langkah 3 : Restart dan Mengaktifkan Apache Service

Lakukan kode berikut :

  ```
 $ sudo systemctl restart apache2
 $ sudo systemctl enable apache2
   ```
<img src="/etc/3.JPG" align=center>

Setelah kode tersebut dijalankan, anda bisa langsung mengakses localhost di browser dan jika berhasil akan muncul halaman seperti ini:

<img src="/etc/apache.png" align=center>

#### Langkah 4 : Konfigurasi Database MySQL 

Humhub membutuhkan database untuk beroperasi. Dalam langkah ini, database tersebut akan dibuat. Lakukan kode berikut di terminal anda :

   ```
 $ sudo mysql -u root -p
   ```   
<img src="/etc/4.JPG" align=center>

Jika anda hanya mau mencoba testing saja, cukup tekan enter untuk inisialisasi MySQL. Selain itu anda juga bisa membuat kata sandi root MySQL anda. Setelah anda sudah membuat kata sandi, MySQL akan terbuka ketika anda memasukkan kode berikut:

   ```
	CREATE DATABASE `humhub` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
	GRANT ALL ON `humhub`.* TO '<username>'@'localhost' IDENTIFIED BY '<password>'; 
	FLUSH PRIVILEGES; 
	EXIT;
   ```   
   
 <img src="/etc/6.JPG" align=center>

#### Langkah 5 : Install HumHub 

Setelah anda sudah menyiapkan hal-hal diatas, anda sudah dapat menginstall Humhub. Versi humhub yang kami install adalah HumHub 1.3.1. Namun, anda bisa menginstall versi HumHub terbaru hanya dengan mengubah url pada baris pertama kode dibawah ini. Anda bisa melihat url versi terbaru pada website HumHub.

Kode dibawah akan menginstall HumHub versi 1.3.1 :

   ```
	$ wget https://www.humhub.org/en/download/package/humhub-1.3.1.tar.gz
	$ sudo mv humhub-1.3.1.tar.gz /var/www/html
	$ cd /var/www/html
	$ sudo tar -zxvf humhub-1.3.1.tar.gz
	$ sudo chmod -R 777 humhub
   ```   
<img src="/etc/9.JPG" align=center>

#### Langkah 6 : Install ekstensi HumHub yang diperlukan '

Sebelum anda mengkonfigurasi HumHub dan mulai menggunakannya, Anda perlu memastikan semua ekstensi yang diperlukan untuk menjalankan HumHub sudah terinstall semua. Anda perlu mengulangi tahap-tahap tersebut sampai semua ekstensi PHP terpenuhi.

1. Jika semua sudah berjalan dengan baik, sekarang anda sudah bisa akses page konfigurasi HumHub di browser anda dengan mengakses localhost. Halaman konfigurasi terlihat seperti dibawah ini:

<img src="/etc/10.JPG" align=center>

2. Setelah anda klik next, anda akan di arahkan kedalam sebuah page yang berisikan daftar keperluan untuk menjalankan HumHub.

<img src="/etc/11.JPG" align=center>

3. Jika ada ekstensi yang hilang, anda perlu menginstall ekstensi yang hilang tersebut di server anda lewat termminal.
4. Restart Apache service, dan ulangi langkah ketiga sampai tidak ada ekstensi yang hilang.

# Konfigurasi
[`^ kembali ke atas ^`](#)

Setelah anda sudah melakukan langkah-langkah instalasi dengan benar, maka anda sudah bisa melanjutkan kembali.

#### Konfigurasi Database

Setelah anda membuka localhost di browser anda, akan ada tampilan untuk *Database Configuration* yang perlu anda isi. Isikan informasi di dalam field sesuai ketentuan (username dan password yang sudah anda buat sebelumnya). Kami membuat nama Database "humhub". Tampilan page akan seperti dibawah ini:

<img src="/etc/12.JPG" align=center>

#### Menentukan Nama untuk Social Network

Tulis nama *social network* sesuai keinginan.

<img src="/etc/13.JPG" align=center>

#### Page selanjutnya hanya perlu memilih beberapa opsi, klik next sampai muncul page seperti ini:

<img src="/etc/14.JPG" align=center>

Disini, anda dapat membuat akun administratif. Lalu, anda dapat menggunakan username dan password untuk login dan mulai menggunakan HumHub.

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Beberapa hal yang dapat digunakan pada Humhub yaitu:

<h2><li><b> Sign in </b></li></h2><br>
	<h3 align="center"><img src="/etc/sign in.JPG"></h3>
	Pada sign in, user menuliskan password serta username agar bisa <i>Sign in</i> pada Humhub
	<h2><li><b> Membuat Space </b></li></h2><br>
	<h3 align="center"><img src="/etc/space.png"></h3>
	Tampilan space adalah seperti diatas. <br>
	<h3 align="center"><img src="/etc/space1.png"></h3>
	Pertama, klik My Space, kemudian klik create New Space. <br>
	<h3 align="center"><img src="/etc/space2.PNG"></h3>
	Lalu, tuliskan nama Space yang ingin dibuat serta deskripsi kemudian klik Next. Serta atur settingnya, seperti yang dibawah ini. <br>
	<h3 align="center"><img src="/etc/space3.png"></h3>
	<h3 align="center"><img src="/etc/space4.PNG"></h3>
	Kemudian, invite user yang ingin dimasukkan pada Space. <br>
	<h3 align="center"><img src="/etc/space5.PNG"></h3>
	Jika sudah, maka space telah selesai dibuat. seperti dibawah ini <br>
	<h3 align="center"><img src="/etc/space6.PNG"></h3>
<br>
	<h2><li><b>Dashboard HumHub</b></h2></li>
	<h3 align="center"><img src="/etc/dashboard.JPG"></h3>
<br>
	<h2><li><b> Follow </b></h2></li>
	Pada HumHub dapat mengikuti pengguna lain seperti yang terlihat pada gambar di bawah ini :
	<h3 align="center"><img src="/etc/follow.PNG"></h3>
<br>
	<h2><li><b> Membuat Status </b></h2></li><br>
	Untuk membuat status dapat dilakukan dengan tiga langkah yaitu : <br>
	1. Status dapat ditulis pada bagian yang ditunjukkan oleh gambar di bawah ini :
	<h3 align="center"><img src="/etc/status1.png"></h3>
<br>
	2. Pada bagian tersebut anda dapat menulis status yang anda inginkan dan klik "submit"
	<h3 align="center"><img src="/etc/status2.png"></h3>
<br>
	3. Dan status anda akan muncul pada timeline.
	<h3 align="center"><img src="/etc/status3.PNG"></h3>
<br>
	<h2><li><b> Add User </b></h2></li>
	Untuk melakukan add user pilih administration seperti gambar di bawah ini
	<h3 align="center"><img src="/etc/adduser1.png"></h3><br>
	Maka akan muncul window seperti gambar di bawah dan pilih "Add new user"
	<h3 align="center"><img src="/etc/adduser2.png"></h3><br>
	Selanjutnya isi data diri dan klik "create account"
	<h3 align="center"><img src="/etc/adduser3.PNG"></h3><br>
	Lalu lakukan seperti gambar di bawah
	<h3 align="center"><img src="/etc/adduser4.png"></h3><br>
	Maka akan muncul seperti gambar di bawah dan pilih "save"
	<h3 align="center"><img src="/etc/adduser5.png"></h3><br>
	Akun berhasil dibuat
	<h3 align="center"><img src="/etc/adduser6.png"></h3>
<br>
	<h2><li><b> Add Module </b></h2></li>
	Pada HumHub dapat menambahkan module dengan cara memilih module pada menu administrasi seperti pada gambar di bawah :
	<h3 align="center"><img src="/etc/modul1.png"></h3>
	Contohnya menambahkan module "Birthday Widget" selanjutnya pilih install
	<h3 align="center"><img src="/etc/modul2.png"></h3>
	Setelah berhasil di install maka akan terlihat pada gambar di bawah :
	<h3 align="center"><img src="/etc/modul3.png"></h3>
	Maka akan seperti pada gambar di bawah :
	<h3 align="center"><img src="/etc/modul4.png"></h3>
<br>
	
# Pembahasan
[`^ kembali ke atas ^`](#)

**Humhub** merupakan aplikasi sosial media open souce yang dapat bekerja pada server anda sendiri. Humhub memiliki beberapa kelebihan:
<ul>
	<li><i>Software open source</i> </li>
  <li><i>User Friendly</i></li> 
  <li> Fleksibel. Dengan adanya modul, humhub dapat diperluas dengan menggunakan alat dari pihak ketiga, menulis sendiri atau menghubungkan antar perangkat lunak yang ada. </li>
  <li> Aman. Humhub bekerja pada server Anda, sehingga data yang diperoleh data Anda, dan aturannya adalah aturan yang dibuat sendiri. HumHub adalah solusi yang di-host sendiri dan berjalan di hampir setiap server. Humhub berada dalam kendali penuh atas data yang dimiliki.</li>
  <li> Setiap user dapat berkomunikasi melalui space (yang kerjanya seperti grup), Space memiliki wall sehingga setiap anggota dapat membaca yang apa yang ada di wall </li>
  <li> setiap <i>user</i> dapat <i>follow user</i> lain, agar setiap user menulis status dapat muncul di <i> dashboard </i> </li> 
</ul>

Kekurangan Humhub:
<ul>
  <li>Tidak ada fitur chat antar user </li>
  <li>Beberapa fitur tidak tersedia secara gratis</li>
</ul>



# Referensi
[`^ kembali ke atas ^`](#)

1. [About HumHub](https://humhub.org/) - HumHub
2. [Cara Instalasi HumHub](http://www.prabeshdhakal.com/2018/09/install-humhub-1-3-x-on-ubuntu-1804/) -prabeshdhakal
3. [Cara konfigurasi HumHub](http://www.prabeshdhakal.com/2018/10/configure-humhub-1-3-x-installed-on-ubuntu-1804/) -prabeshdhakal