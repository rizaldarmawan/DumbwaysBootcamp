# SERVER FOR REVERSE PROXY

- Memilih OS yang akan digunakan untuk server, dalam hal ini Ubuntu server 18.04

![text](assets/01.PNG)

- Memilih spesifikasi server, tidak perlu terlalu besar karena hanya akan digunakan untuk mendeploy aplikasi sederhana

![text](assets/02.PNG)

- Konfigurasi koneksi yang akan digunakan oleh server, pastikan memilih opsi **Disable** pada `Auto-assign Public IP` agar ip menjadi static dan tidak akan berubah - ubah setelah server di restart

![text](assets/03.PNG)

- Memilih storage yang akan digunakan, disini yang saya ganti hanya bagian `Size` dari default 8GB menjadi 10GB.

![text](assets/04.PNG)

- Configurasi security group agar user hanya bisa mengakses beberapa port yang sudah di sediakan, dalam hal ini yang dibutuhkan adalah: 

	- SSH   : agar server bisa diakses lewat komputer lokal 
	- HTTP  : agar website bisa diakses public
	- HTTPS : agar website bisa dipasang SSL 

![text](assets/05.PNG)

- Buat key pair baru yang nantinya digunakan untuk login ke server menggunakan SSH

![text](assets/06.PNG)

- Setelah proses instalasi server selesai, server sebelumnya tidak memiliki public ip, jadi harus ditambahkan Elastic IP terlebih dahulu agar server bisa diakses dari komputer lokal

![text](assets/07.PNG)

- Tambahkan Elastic Ip yang sudah didapat ke server public
![text](assets/08.PNG)
![text](assets/09.PNG)

---

# SERVER FOR APPLICATION

Untuk konfigurasi server Private cara konfigurasinya kurang lebih sama, hanya pada `Configure Security Group` cukup menggunakan All trafic, kemudian Source diganti Ip Private milik Server Public. Server ini juga tidak memerlukan Elastic IP.

![text](assets/10.PNG)

Pada gambar diatas sementara saya masukan Ip dari komputer yang saya gunakan untuk menambahkan user baru agar tidak perlu menggunakan key-pair saat login dari server public.

---
# SSH KE SERVER 

Cara berikut saya lakukan pada kedua server untuk menghilangkan key-pair saat login:

- Login dari terminal lokal menggunakan perintah `ssh -1 key-pair ubuntu@ip-public` 

![text](assets/11.PNG)

- Tambahkan user baru dengan perintah `adduser nama-user` kemudian beri akses sudo menggunakan `usermod -aG sudo nama-user`

![text](assets/12.PNG)
![text](assets/13.PNG)

- Edit file yang ada dalam `/etc/ssh/sshd_config` dan ganti `PasswordAuthentication` dari No ke Yes 

![text](assets/14.PNG)

-Restart sshd dan coba login menggunakan user baru

![text](assets/15.PNG)