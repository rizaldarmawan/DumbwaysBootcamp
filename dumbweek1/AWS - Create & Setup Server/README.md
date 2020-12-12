# SERVER FOR REVERSE PROXY (Public)

- Memilih OS yang akan digunakan untuk server, dalam hal ini Ubuntu server 18.04

![text](assets/01.PNG)

- Pilih spesifikasi server

![text](assets/02.PNG)

- Pada configure instance details, matikan auto-assign ip

![text](assets/03.PNG)

- Ubah ukuran default dari 8GB ke 10GB

![text](assets/04.PNG)

- Pada configure security group tambahkan seperti gambar berikut

![text](assets/05.PNG)

- Lalu review dan launch server, jangan lupa keypairnya karena akan dipakai untuk login

![text](assets/06.PNG)

- Setelah itu allocate elastic ip agar ip publicnya statis

![text](assets/07.PNG)

- Lalu Associate ipnya dengan instance

![text](assets/08.PNG)
![text](assets/09.PNG)

# SERVER FOR APPLICATION (Private)

- Untuk setingannya sama dengan sebelumnya, namun dibedakan pada configure security group, dan tidak diberi elastic ip

![text](assets/10.PNG)

# SETTING USER, SSH, DAN HOSTNAME SERVER PUBLIC

- SSH Server Public dengan perintah `ssh -i keypair.pem ubuntu@ippublic`

![text](assets/12.PNG)

- Tambahkan user dengan perintah `sudo adduser namauser`, lalu isi password sesuai keinginan

![text](assets/13.PNG)

- Beri akses sudo untuk user baru tersebut dengan perintah `sudo usermod -G sudo namauser`

![text](assets/14.PNG)

- Ubah hostname dengan mengedit `/etc/hosts` dan `/etc/hostname` dengan hostname yang diinginkan lalu restart server dan remote lagi

![text](assets/15.PNG)

- Edit file `/etc/ssh/sshd_config` lalu rubah pada bagian `PasswordAuthentication no` menjadi `PasswordAuthentication yes`

![text](assets/16.PNG)

- Restart service sshd dan cek servicenya, lalu coba remote kembali dengan `ssh namauser@publicip`

![text](assets/17.PNG)
![text](assets/18.PNG)

# SETTING USER, SSH, DAN HOSTNAME SERVER PRIVATE

- Pertama remote terlebih dahulu server public, baru setelah itu kita remote server private, sisanya sama dengan setting server public

![text](assets/19.PNG)
![text](assets/20.PNG)

# SETTING VPC

- Karena saya menggunakan VPC Default, saya hanya akan memberi nama subnet pada server private menjadi private dan public
menjadi public

![text](assets/31.PNG)

# SETTING NAT INSTANCE UNTUK SERVER PRIVATE

- Agar server private kita aman, kita tidak akan memberinya public ip yang dapat diakses langsung oleh internet, tetapi kita akan mengaksesnya lewat server public. tetapi, dengan ini server private kita tidak bisa mengakses internet, oleh karena itu kita akan setting nat instance agar private server dapat mengakses internet.

- Pertama kita bikin Instance baru, pilih AMI seperti gambar berikut

![text](assets/21.PNG)

- Pilih saja spesifikasi yang ringan

![text](assets/22.PNG)

- Disini Pilih Network dengan VPC yang diinginkan, pada subnet pilih yang public, dan nyalakan auto assign ip

![text](assets/23.PNG)

- Disini set dengan type all traffic, dan source ip dari network/subnet server private

![text](assets/24.PNG)

- Kita pindah ke list instance di aws, lalu pilih instance nat tadi dan klik action > networking > change source/destination check, dan ceklis stop

![text](assets/25.PNG)
![text](assets/26.PNG)

- Setelah itu kita bikin route table baru untuk server private

![text](assets/27.PNG)

- Lalu edit routenya dan tambahkan Nat instancenya

![text](assets/28.PNG)

- Lalu associate route table tadi dengan subnet private

![text](assets/29.PNG)

- Setelah itu cek koneksi private server

![text](assets/30.PNG)
