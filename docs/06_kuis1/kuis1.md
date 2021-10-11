# Install Wordpress Pada PaaS

Cara untuk menginstall wordpress pada OCI dapat menggunakan langkah-langkah seperti berikut:

1. Mengakses instances yang dimiliki melalui ssh adalah dengan mengetik perintah sudo ssh -I <path private key> username@ip public. Contoh penggunaan perintah tersebut adalah 
adalah sebagai berikut:

![Screenshot Login ssh](img/Langkah1.PNG)

2.  Mengakses MySQL

Untuk mengkoneksikan mysql dengan perintah berikut mysql -u <database administrator> -p -h <ip private mysql oci /hostname>. Setelah ini database sudah siap untuk digunakan sesuai dengan kebutuhan anda

![Screenshot Langkah 2](img/Langkah2.PNG)

3. Membuat Database

Cara untuk membuat database pada mysql adalah dengan mengetik perintah di bawah ini.Perintah pertama untuk membuat database, perintah kedua untuk melihat apakah database kita sudah berhasil dibuat dan ketiga adalah memberikan previleges database pada user admin. Anda dapat membuat 
user baru dan mengatur previlegenya.

mysql> create database wordpress;
mysql> show databases;
mysql> grant all privileges on wordpress.* to admin;

![Screenshot Langkah 3](img/Langkah3.PNG)

2. Download Wordpress Pada Folder /var/www/html dengan perintah

wget https://wordpress.org/latest.tar.gz;

![Screenshot Langkah 4](img/Langkah4.PNG)

3. Mengetrak Wordpress Pada Folder /var/www/html dengan perintah

tar zxvf latest.tar.gz

![Screenshot Langkah 5](img/Langkah5.PNG)

Selanjutnya setelah estrak file hasil download dapat dihapus dengan menggunakan perintah

sudo rm rf latest.tar.gz

![Screenshot Langkah 6](img/Langkah6.PNG)

4. Selanjutnya menginstall extension mysql pada php dan mengaktifkannya pada php.ini

Berikut adalah perintah untuk menginstall extenstion mysql pada php

sudo apt-get install php-mysql

![Screenshot Langkah 7](img/Langkah7.PNG)

Sedangkan cara untuk mengaktifkan extension mysql pada php dapat diaktifkan pada php.ini. Path dari php.ini dapat dilihat pada phpinfo() seperti pada gambar berikut terletah pada /etc/php/7.4/apache2/php.ini

Pada php.ini aktifkan extension=php_mysqli.dll kemudian lakukan restart apache menggunakan perintah berikut.

![Screenshot intall php dan apache](img/installPhp.PNG)

sudo service apache2 restart
sudo chown www-data:www-data -R *

![Screenshot Langkah 8](img/Langkah8.PNG)

5. Selanjutnya Proses Intalasi Wordpress Melalui Browser

![Screenshot Langkah 9](img/Langkah9.PNG)

Masukkan data-data yang digunakan untuk membuat tabel

![Screenshot Langkah 10](img/Langkah10.PNG)

Copy teks dibawah ini

![Screenshot Langkah 11](img/Langkah11.PNG)

Buat file dengan nama wp-config.php

Paste teks yang sudah dicopy tadi dan klik run the installation pada browser

![Screenshot Langkah 12](img/Langkah12.PNG)

![Screenshot Langkah 13](img/Langkah13.PNG)

![Screenshot Langkah 14](img/Langkah14.PNG)

![Screenshot Langkah 15](img/Langkah15.PNG)

![Screenshot Langkah 16](img/Langkah16.PNG)

![Screenshot Langkah 17](img/Langkah17.PNG)

![Screenshot Langkah 18](img/Langkah18.PNG)