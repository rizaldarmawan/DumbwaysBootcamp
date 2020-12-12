# Reverse Proxy

- update dan server dengan perintah `apt-get update && apt-get upgrade`, Setelah itu install nginx dengan perintah `apt-get install nginx`

![text](assets/01.PNG)

- Lalu cek nginxnya dengan memasukan ip public server

![text](assets/02.PNG)

- Lalu buat file housy.conf di `/etc/nginx/sites-available/` dan isi dengan settingan seperti berikut

![text](assets/03.PNG)

- Lalu cek reverse proxynya dengan memasukan ip public di browser, jika muncul, berarti reverse proxynya sudah tersambung dengan server private

![text](assets/04.PNG)