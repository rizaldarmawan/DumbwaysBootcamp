# PROSES INSTALASI SERVER NGINX DAN DEPLOY APLIKASI NODEJS
## Instalasi Nginx
1. Hal pertama yang harus dilakukan setelah instalasi server ubuntu ialah mengupdate dan upgrade paket yang sudah ada dengan perintah `apt update && apt upgrade` lakukan dengan root. 

![1](assets/01.PNG)

2. setelah proses update & upgrade selesai barulah install nginx dan cek servicenya setelah selesai.

![2.1](assets/02.PNG)
![2.2](assets/03.PNG)

3. uji coba mengakses server nginx pada komputer lokal dengan cara memasukkan ip server

![3](assets/04.PNG)

## Instalasi NodeJS dan deploy DW15WDTPH_housy

1. untuk melakukan instalasi nodejs versi 10.x, kita akan menginstall dari web nodejs dengan perintah `curl -sl https://deb.nodesource.com/setup_10.x | sudo -E bash`, dan setelah itu install menggunakan perintah `apt-get -y install nodejs`

![1](assets/05.PNG)
![1.2](assets/06.PNG)
![1.3](assets/07.PNG)

2. clone repository yang ada pada https://github.com/DumbwaysDotId/DW15WDTPH_housy.git ke server local untuk nantinya dideploy. Setelah itu cd ke DW15WDTPH_housy dan install semua paket dengan perintah npm install

![2](assets/08.PNG)

3. selanjutnya jika semua paket terinstall, jalankan perintah `npm start` agar aplikasi bisa diakses pada komputer local

![3](assets/09.PNG)

4. hasil setelah dijalankan pada komputer lokal

![4](assets/10.PNG)