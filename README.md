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
	$ wget https://www.humhub.org/en/download/package/humhub-1.3.1.tar.gz
	$ sudo mv humhub-1.3.1.tar.gz /var/www/html
	$ cd /var/www/html
	$ sudo tar -zxvf humhub-1.3.1.tar.gz
	$ sudo chmod -R 777 humhub
   ```   

#### Step 6 : Install ekstensi HumHub yang diperlukan '

Sebelum anda mengkonfigurasi HumHub dan mulai menggunakannya, Anda perlu memastikan semua ekstensi yang diperlukan untuk menjalankan HumHub sudah terinstall semua. Anda perlu mengulangi tahap-tahap tersebut sampai semua ekstensi PHP terpenuhi.

1. jika semua sudah berjalan dengan baik, sekarang anda sudah bisa akses page konfigurasi HumHub di browser anda dengan mengakses localhost. Halaman konfigurasi terlihat seperti dibawah ini:

2. Setelah anda klik next, anda akan di arahkan kedalam sebuah page yang berisikan daftar keperluan untuk menjalankan HumHub.
3. Jika ada ekstensi yang hilang, anda perlu menginstall ekstensi yang hilang tersebut di server anda lewat termminal.
4. Restart Apache service, dan ulangi langkah ketiga sampai tidak ada ekstensi yang hilang.

Jika semua keperluan untuk menjalankan HumHub sudah terpenuhi semua, page akan menampilkan hasil seperti dibawah ini:


# Konfigurasi
[`^ kembali ke atas ^`](#)

Setelah anda sudah melakukan step-step instalasi dengan benar, maka anda sudah bisa melanjutkan kembali.

#### Konfigurasi Database

Setelah anda membuka localhost di browser anda, akan ada tampilan untuk *Database Configuration* yang perlu anda isi. Isikan informasi di dalam field sesuai ketentuan (username dan password yang sudah anda buat sebelumnya). Kami membuat nama Database "humhub". Tampilan page akan seperti dibawah ini:

#### Menentukan Nama untuk Social Network


#### Page selanjutnya hanya perlu memilih beberapa opsi, klik next sampai muncul page sepeRti ini:

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
	<h3 align="center"><img src="/etc/adduser6.png"></h3><br>
	
# Pembahasan
[`^ kembali ke atas ^`](#)

**Humhub** merupakan aplikasi sosial media open souce yang dapat bekerja pada server anda sendiri. Humhub memiliki beberapa kelebihan:
<ul>
	<li><i> open source software</i> </li>
  <li><i>user friendly</i></li> 
  <li> software yang fleksibel. Dengan adanya modul, humhub dapat diperluas dengan menggunakan alat dari pihak ketiga, menulis sendiri atau menghubungkan antar perangkat lunak yang ada. </li>
  <li> perangkat lunak yang aman karena Humhub bekerja pada server Anda, sehingga data yang diperoleh data Anda, dan aturannya adalah aturan yang dibuat sendiri. HumHub adalah solusi yang di-host sendiri dan berjalan di hampir setiap server. Humhub berada dalam kendali penuh atas data yang dimiliki.</li>
  <li> Setiap user dapat berkomunikasi melalui space (yang kerjanya seperti grup), Space memiliki wall sehingga setiap anggota dapat membaca yang apa yang ada di wall </li>
  <li> setiap <i>user</i> dapat <i>follow user</i> lain, agar setiap user menulis status dapat muncul di <i> dashboard </i> </li> 
</ul>

Kekurangan Humhub:
<ul>
  <li> tidak ada fitur chat antar user </li>
  <li> tidak dapat mengubah kata sandi </li>
</ul>



# Referensi
[`^ kembali ke atas ^`](#)

1. [About HumHub](https://humhub.org/) - HumHub
2. [Cara Instalasi HumHub](http://www.prabeshdhakal.com/2018/09/install-humhub-1-3-x-on-ubuntu-1804/) -prabeshdhakal
3. [Cara konfigurasi HumHub](http://www.prabeshdhakal.com/2018/10/configure-humhub-1-3-x-installed-on-ubuntu-1804/) -prabeshdhakal
