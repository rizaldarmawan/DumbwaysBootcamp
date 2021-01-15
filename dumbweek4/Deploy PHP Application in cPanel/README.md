# Deploy PHP in CPANEL

- Untuk CMS saya menggunakan joomla
- Untuk CPANEL menggunakan InfinityFree
- Untuk SSL Menggunakan GoGetSSL
- Untuk FTP menggunakan FileZilla


- Download Joomla dan extract lalu pindahkan ke server dengan FTP

![](assets/01.PNG)
![](assets/02.PNG)

- Buka Domain dan setup Joomla

![](assets/03.PNG)

- Setelah selesai setup joomla, masuk ke menu utama infinityfree dan minta ssl untuk domain yang ada. Setelah itu salin private key dan certificate di menu ssl pada cpanel

![](assets/06.PNG)

- setelah itu redirect semua request http ke https dengan htaccess

![](assets/08.PNG)

- selesai

![](assets/09.PNG)