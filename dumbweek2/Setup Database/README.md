# Setup Database

- Install mysql server dengan perintah `apt-get install mysql-server`

![text](assets/01.PNG)

- Sekarang kita akan mengubah password user root dengan perintah `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'passwordbaru`, tapi masuk ke mysql terlebih dahulu dengan perintah `sudo mysql -u root`

![text](assets/04.PNG)

- Setelah itu coba buat database housy dengan user root

![text](assets/02.PNG)
![text](assets/03.PNG)

- Sekarang kita akan buat user untuk login `server backend`, agar `server backend` dapat mengakses `server database`

```
create user 'namauser'@'ip-server-backend' identified by 'password'; 

grant all on *.* to 'namauser'@'ip-server-backend';

FLUSH PRIVILEGES;
```

![text](assets/05.PNG)

- Terakhir ubah bind-address mysql agar ipnya dapat diakses `server backend`

![text](assets/06.PNG)
