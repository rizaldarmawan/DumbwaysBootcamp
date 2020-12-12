# Server Application

- Pertama kita update dan upgrade dengan perintah `apt-get update && apt-get upgrade`

![text](assets/01.PNG)

- lalu kita tambahkan repo nodejs dengan perintah `curl -sL https://deb.nodesource.com/setup_10.x | bash -`, dan setelah selesai kita install nodejsnya dengan perintah `apt-get install nodejs`

![text](assets/02.PNG)

- Setelah itu kita clone repo git aplikasi housy

![text](assets/03.PNG)

- lalu didalam folder housy, kita buat file `ecosystem.config.js`, dan isi seperti berikut

![text](assets/04.PNG)

- Setelah itu masukan perintah `npm install`, dan setelah selesai kita install pm2 dengan perintah `npm install -g pm2`

![text](assets/05.PNG)

- Terakhir jalankan aplikasi oleh pm2 dengan memasukan perintah `pm2 start ecosystem.config.js`

![text](assets/06.PNG)