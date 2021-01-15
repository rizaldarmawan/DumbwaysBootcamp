# CICD

- Jalankan jenkins dengan playbook berikut

![](assets/01.png)
![](assets/02.png)

- salin password default jenkins dari container

![](assets/03.png)
![](assets/04.png)

- Buat akun baru jenkins

![](assets/05.png)

## Github autentikasi

- Salin Private key sebelumnya dan salin untuk autentikasi server kita dan untuk github

![](assets/06.png)
![](assets/07.png)

## Install Plugin

- Install plugin `Publish Over SSH` dan `Discord Notifier`

![](assets/08.png)
![](assets/09.png)

## Tambah Server

- Tambahkan server frontend dan backend, untuk passnya gunakan private key

![](assets/10.png)

## Create Job

- Buat Job untuk Frontend dengan freestyle

![](assets/11.png)

- isi sesuai gambar-gambar dibawah

![](assets/12.png)
![](assets/13.png)
![](assets/14.png)

- Untuk Post Build masukan Discord Notifier dan salin webhook dari grup discord

![](assets/15.png)
![](assets/16.png)

- Buat Webhook di github

![](assets/17.png)

- Untuk yang backend settingnya sama, hanya beda pada build sedikit

## Test Automasi

- Coba push pada github, dan ini yang terjadi

![](assets/18.png)
![](assets/19.png)
![](assets/20.png)