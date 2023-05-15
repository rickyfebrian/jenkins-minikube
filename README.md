# jenkins-minikube

Berikut adalah langkah-langkah yang diperlukan untuk memdeploy service kubernetes localhost (minikube) 

![Screenshot from 2023-05-15 00-18-33](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/395da636-f1ed-4831-8034-4e8cc601cdb0)

1. Clone github https://github.com/savanihd/Laravel-8-CRUD

clone untuk mendapatkan source code service

2. Dockerfile

Buat Dockerfile yang dapat membuat image docker sesuai kebutuhan


=== Buat Jenkins pipeline build dan push ===

3. Pipeline build  

Jenkins pipeline akan menjalankan perintah >> akses ke vm docker kemudian build docker dengan Dockerfile

4. Pipeline push 

Jenkins pipeline akan menjalankan perintah >> akses ke vm docker kemudian push ke dockerhub https://hub.docker.com/u/rickyfebrian

![Screenshot from 2023-05-15 00-36-39](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/73f609fa-ec53-464c-ab93-905f93396b1d)

![Screenshot from 2023-05-15 00-21-13](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/6ec58053-9b47-445d-9eb0-54904904e4fe)

5. Kubernetes yaml dan domain

Buat kubernetes yaml untuk service mysql dan laravel serta sesuaikan host di vm minikube agar service dapat diakses menggunakan domain

![Screenshot from 2023-05-15 00-29-48](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/41aa3918-a9f6-413c-b567-2ee9fa0e12d5)

![Screenshot from 2023-05-15 00-30-23](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/54a74278-b6de-4ade-8c77-b5c54d110115)

=== Buat Jenkins pipeline pull dan deploy ===

6. pipeline pull  

Jenkins pipeline akan menjalankan perintah >>  akses ke vm minikube kemudian pull docker image dari dockerhub

7. pipeline deploy 

Jenkins pipeline akan menjalankan perintah >> akses ke vm minikube kemudian deploy docker image dengan kubernetes deploy, service dan ingress

![Screenshot from 2023-05-15 00-21-24](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/50e6bacd-6378-43d1-b0df-f46bb96a397c)

Akses service melalui domain oce.local

![Screenshot from 2023-05-15 00-34-27](https://github.com/rickyfebrian/jenkins-minikube/assets/46195764/4d47ca3b-9613-473d-91f6-6f02c1bf205b)
