# Virtualización ligera usando contenedores

---
## Ejercicio 1: *Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.*

~~~
apt-get install lxc
dpkg -s lxc
~~~

Comprobamos que nos ha instalado la versión 2.0.8

---

---

## Ejercicio 2: *Crear y ejecutar un contenedor basado en tu distribución y otro basado en otra distribución, tal como Fedora. Nota En general, crear un contenedor basado en tu distribución y otro basado en otra que no sea la tuya.*

Para instalar un contenedor basado en mi distribución (ubuntu):
~~~
sudo lxc-create -t ubuntu -n una-caja
sudo lxc-start -n una-caja
~~~

Para instalar un contenedor basado en ontra distribución en /usr/share/lxc/templates podemos ver los templates que tenemos disponibles y solo tenemos que elegir uno de ellos.
~~~
sudo lxc-create -t debian -n caja-debian
sudo lxc-stat -n caja-debian
~~~

---

---

## Ejercicio 3: *Instalar docker*

~~~
sudo apt-get update

sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual

sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install docker-ce

sudo docker run hello-world
~~~

---

---

## Ejercicio 4: *Instalar a partir de docker una imagen alternativa de Ubuntu y alguna adicional, por ejemplo de CentOS. Buscar e instalar una imagen que incluya MongoDB.*

~~~
sudo docker search ubuntu
sudo docker pull dorowu/ubuntu-desktop-lxde-vnc
sudo docker pull centos

sudo docker search mongodb
sudo docker pull mongo
~~~

---

---

## Ejercicio 5: *Crear un usuario propio e instalar alguna aplicación tal como nginx en el contenedor creado de esta forma, usando las órdenes propias del sistema operativo con el que se haya inicializado el contenedor.*

~~~
sudo docker run -i -t ubuntu /bin/bash
apt-get update
apt-get install nginx
~~~

## Ejercicio 6: *Crear a partir del contenedor anterior una imagen persistente con commit.*

Primero sacamos la ID del contenedor que queremos hacer persistente y luego hacemos commit ID nuevonombre.
~~~
docker ps
sudo docker commit c645daa75d9a ubuntu_persistente
~~~

## Ejercicio 7: *Crear un Dockerfile para el servicio web que se ha venido desarrollando en el proyecto de la asignatura.*

Este ejercicio será realizado como parte del hito 4.

---

---

## Ejercicio 8: *Desplegar un contenedor en alguno de estos servicios, de prueba gratuita o gratuitos.*

Este ejercicio será realizado como parte del hito 4.
