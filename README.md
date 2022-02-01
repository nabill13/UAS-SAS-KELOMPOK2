# FINAL PROJECT

### SISTEM ADMINISTRASI SERVER 

##### KELOMPOK 2

- NABILA NUR AMALIA_1202190013
- EVYRA RIZKI SAFITRI_1202190015
- M. PRADATA YUDA P_1202190061

Pertama-tama buat lxc, setting manual IP dan SSH, jangan lupa di autostart.

lxc yang akan dibuat :

- 6 lxc Ubuntu 20.04 PHP 7.4
- 2 lxc debian 10 PHP 5.6
- 1 LXC debian 10 mariadb server

```
sudo lxc-create -n lxc_php7_1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php7_2 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php7_3 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php7_4 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php7_5 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php7_6 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org
```

2 lxc debian 10
```
sudo lxc-create -n lxc_php5_1 -t download -- --dist debian --release buster --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org

sudo lxc-create -n lxc_php5_2 -t download -- --dist debian --release buster --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org
```

1 lxc untuk mariadb (debian 10)
```
sudo lxc-create -n lxc_mariadb -t download -- --dist debian --release buster --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org
```


<img width="657" alt="0" src="https://user-images.githubusercontent.com/92876637/152006200-1a568439-3245-40a1-a85d-371bfd4cf75e.PNG">

<img width="954" alt="1" src="https://user-images.githubusercontent.com/92876637/151707964-2eec3c05-7e6f-4ac6-a228-85b5bce20cc0.PNG">

<img width="238" alt="4" src="https://user-images.githubusercontent.com/92876637/151708030-739ad761-34d0-4d08-a562-721e05fd0f92.PNG">   <img width="215" alt="5" src="https://user-images.githubusercontent.com/92876637/151708092-b3dbf2f1-ffad-4ecc-bd11-b4f6ab280dac.PNG">


<img width="484" alt="3" src="https://user-images.githubusercontent.com/92876637/151708022-90774ddd-a35b-4022-bbc5-4d13e0aa9c32.PNG">

Pertama kita buat folder di direktori ansible sudo mkdir -p ~/ansible/uas untuk menampung semua script konfigurasi yang akan kita gunakan dalam tugas akhir ini.

Di direktori tubes, buat direktori untuk menampung semua skrip di setiap framework yang akan diinstal dalam proyek ini.

Buat direktori laravel di direktori sudo mkdir laravel untuk mengakomodasi skrip yang memungkinkan untuk menginstal laravel framewrok.

```
sudo mkdir -p laravel/tasks
sudo mkdir -p laravel/handlers
sudo mkdir -p laravel/templates
```

*picture*



kemudian, jalankan Ansible

*picture*



Install mariadb pada LXC_DB_SERVER dan CodeIgniter 3 pada LXC_CI dengan ansible

*link ansible*

*picture 1*

*picture 2*

*picture 3*

*picture 4*



Install laravel 8 pada LXC_LARAVEL dengan ansible

*link ansible*

*picture 1*

*picture 2*

*picture 3*

*picture 4*



Install latest wordpress pada LXC_WORDPRESS dengan ansible

*link ansible*

<img width="481" alt="install wp" src="https://user-images.githubusercontent.com/92876637/152006638-3915e03f-f952-4f16-b196-850b706f7375.PNG">


*picture 2*

*picture 3*

*picture 4*

*picture 5*



Install YII 2.0 on LXC_YII dengan ansible

*link ansible*

<img width="482" alt="install yii" src="https://user-images.githubusercontent.com/92876637/152006699-8189d217-4392-4634-9f2f-075096d891b8.PNG">

*picture 2*



copy LXC sebelumnya, seperti arsitektur 

*picture*



setelah itu tulis perintah berikut 
```
cd /roles/ci/tasks
nano main.yml
```

*picture 1*

setelah itu tulis perintah 
 ```
 cd ../templates
nano app.conf
```

*picture*

setelah itu tulis perintah 

```
cd ../handlers
nano main.yml
```

*picture*


 setelah ansible Code Igniter, maka kita ke cd task

```
cd ../../
cd php/tasks
nano main.yml
```
 *picture*
 
kemudian masuk ke main.yml dengan perintah

```
cd ../handlers
nano main.yml
```

*picture*

setelah ansible pada php selesai, selanjutnya setting laravel.
ketikkan perintah berikut 

```
cd ../../
cd lv/tasks
nano main.yml
```
*picture*


kemudian masuk ke env.template dengan perintah berikut :
```
cd ../templates
nano env.template
```

*picture*

