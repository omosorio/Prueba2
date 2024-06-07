Despliegue de Nagios Core en Docker
Este repositorio contiene los archivos necesarios para desplegar Nagios Core en Docker utilizando un contenedor.


#Pasos para Desplegar Nagios Core en Docker


#Instalación de Docker:

sudo apt update
sudo apt install -y docker.io

#Descargar los Archivos de Nagios Core:

mkdir /opt/nagios-core-docker-v1
cd /opt/nagios-core-docker-v1/
wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.9.tar.gz
tar xzf nagios-4.4.9.tar.gz 
wget https://github.com/nagios-plugins/nagios-plugins/releases/download/release-2.4.2/nagios-plugins-2.4.2.tar.gz
tar xzf nagios-plugins-2.4.2.tar.gz 
wget https://github.com/NagiosEnterprises/nrpe/releases/download/nrpe-4.1.0/nrpe-4.1.0.tar.gz
tar xzf nrpe-4.1.0.tar.gz 

#Construir la Imagen Docker de Nagios Core:

docker build -t nagios-core:4.4.9 .

Ejecutar el Contenedor Docker:

docker run --name nagios-core-4.4.9 -dp 80:80 nagios-core:4.4.9


#Acceder a la Interfaz Web de Nagios Core:

Abre un navegador web.
Ingresa la dirección IP de tu máquina anfitriona y el puerto 80.


#Iniciar Sesión en Nagios Core:

Usuario: nagiosadmin
Contraseña: nagios

Problemas
Si encuentras algún problema o tienes alguna pregunta, por favor abre un issue en este repositorio.
