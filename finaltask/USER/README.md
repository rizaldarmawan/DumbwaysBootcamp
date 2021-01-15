# Create User

- Pertama remote server dan clone ansible-playbook yang telah dibuat

![](assets/01.png)

- setelah itu edit inventory sesuai server yang ada

![](assets/02.png)

- selanjutnya install ansible dengan perintah-perintah berikut

```
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

![](assets/03.png)

- cek playbook yang akan dijalankan

![](assets/04.png)

- cek ansible.cfg untuk user, jangan lupakan private key

![](assets/05.png)
![](assets/06.png)


- ping semua server agar meninggalkan fingerprint

![](assets/07.png)

- jalankan playbook untuk create user

![](assets/08.png)

- untuk bonus, saya akan mengubah hostname setiap server juga dengan playbook berikut

![](assets/09.png)

- Setelah itu coba masuk ke server tanpa key dari aws

![](assets/10.png)
![](assets/11.png)
