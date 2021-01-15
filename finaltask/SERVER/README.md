# Server AWS

- Buat VPC baru

![](assets/01.png)

- Buat subnet private dan public

![](assets/02.png)
![](assets/03.png)

- Buat NAT gateway

![](assets/04.png)

- Buat internet gateway dan attach ke VPC

![](assets/05.png)
![](assets/05-1.png)

- Buat route table untuk public dan private subnet

![](assets/06.png)

- yang ini untuk subnet public

![](assets/07.png)

- yang ini untuk subnet private

![](assets/08.png)

- Buat security group untuk public dan private

![](assets/09.png)
![](assets/10.png)

- Ini ketika semua telah dibuat

![](assets/11.png)

- Assosiate public ip ke nginx

![](assets/12.png)