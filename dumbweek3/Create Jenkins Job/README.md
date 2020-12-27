# Create Jenkins Job

- Masukan Plugin untuk SSH

![text](assets/01.PNG)

- Lalu buat kredensial untuk login git jalur SSH

![text](assets/02.PNG)

- Masukan server dengan plugin over SSH

![text](assets/03.PNG)

- Lalu buat job baru dengan freestyle, dan konfigurasi seperti gambar dibawah

![text](assets/04.PNG)
![text](assets/05.PNG)
![text](assets/06.PNG)

- Pada repo di github, kita akan buat webhook untuk trigger jenkins

![text](assets/07.PNG)

- Coba ubah repo github, pada jenkins akan otomatis build dari repo setiap ada push baru

![text](assets/08.PNG)
![text](assets/09.PNG)

- dan untuk bot notif, saya menggunakan Discord

![text](assets/10.PNG)






