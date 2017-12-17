# Creando la máquina virtual

<img src="https://upload.wikimedia.org/wikipedia/commons/d/d5/Virtualbox_logo.png" width="200" height="200" />

Para crear la máquina virtual en un equipo con Windows 7 usaremos la aplicación [VirtualBox](https://www.virtualbox.org/), así que lo primero es bajar la aplicación e instalarla (yo tengo instalada la Versión 5.1.10 r112026 (Qt5.6.2)).

Despues para ahorrar tiempo bajaremos una imagen de Ubuntu reparada para VirtualBox. En estos enlaces se pueden descargar diferentes versiones.

* [http://www.osboxes.org/ubuntu/](http://www.osboxes.org/ubuntu/)
* [https://virtualboxes.org/images/ubuntu-server/](https://virtualboxes.org/images/ubuntu-server/)

Yo voy a probar suerte con esta:  [Ubuntu_17.10-VB-64bit.7z (964M)](https://drive.google.com/file/d/0B_HAFnYs6Ur-ZFBGM3gwd0pEMms/view?usp=sharing)

Esta distribución es una de las que recomiendan en el propio manual de [LibreTime](http://libretime.org/manual/preparing-the-server/)
[Ubuntu_16.04.3-VB-32bit.7z (1.0G)](https://drive.google.com/file/d/0B_HAFnYs6Ur-N0d2MGMxWGI5Uzg/view?usp=sharing)

* Username: osboxes
* Password: osboxes.org

![](../img/libretime_y_virtualbox/01.png)

La máquina ha arrancado a la perfección. Una vez arrancada he instalado el cliente Git y Vagrant con:

```
$ sudo apt-get install git
$ sudo apt-get install virtualbox
$ sudo apt-get install vagrant
```

[Vagrant](https://www.vagrantup.com/) es es una herramienta para la creación y configuración de entornos de desarrollo virtualizados. 

# Instalación Libretime

A continuación clonamos el repositorio de Libretime y lanzamos el entorno virtualizado con Vagrant:

```
$ git clone https://github.com/libretime/libretime.git
$ cd libretime
$ vagrant up-trusty
```
En ni caso la primera vez no ha funcionado porque faltaba por instalar [NFS](https://help.ubuntu.com/community/SettingUpNFSHowTo)

```
$ apt-get install nfs-kernel-server
$ apt-get install nfs-common
```

Vagrant descarga una caja (los entornos virtualizados los llaman boxes) 

# Conclusiones

Podiamos haber lanzado la maquina virtual instalando Vagrant directamente sobre Windows 7 y clonando con Git el repositorio.

