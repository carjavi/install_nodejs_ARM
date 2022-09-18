<p align="center"><img src="https://raw.githubusercontent.com/carjavi/install-nodejs-ARM/master/img/node_raspberry.png" height="250" alt="MarlinFirmware's logo" /></p>

<br>

<h1 align="center">Installation NODEJS & NPM for ARM</h1>

<img src="https://img.shields.io/badge/OS%20-Raspbian%20GNU%2FLinux%2011%20(bulleye)-yellowgreen">
<img src="https://img.shields.io/badge/OS%20-Raspbian%20GNU%2FLinux%2010%20(buster)-yellowgreen">

<img src="https://img.shields.io/badge/Hardware-Raspberry%20ver%204-red">
<img src="https://img.shields.io/badge/Hardware-Raspberry%20ver%203-red">
<img src="https://img.shields.io/badge/Hardware-Raspberry%20Zero-red">

<h4 align="right">Aug 22</h4>


<!--
***Option 0***
excellent for a file.sh node v17.9.0 /npm v8.5.5
```
sudo su
curl -fsSL https://deb.nodesource.com/setup_17.x | bash -
```
```
sudo apt install nodejs
npm install -g npm@8.19.2 // new
```
### Uninstall/ Remove NodeJS and NPM
```
sudo apt remove nodejs
```
-->

***Option 1***

# nvm (node version manager)

```
curl -sL https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh -o install_nvm.sh
```
```
bash install_nvm.sh
```

> :warning: Una vez instalado, cierra la terminal y abre otra.
```
source .bashrc
nvm install node
npm install -g npm@8.19.2 
```
Eso instalará la última versión disponible

### Probar instalación
```
$ node --version
$ npm --version
```
> :bulb: ```nvm --version``` para verificar la versión de nvm instalada. <br>

> :bulb: Si alguna vez necesitas cambiar de la versión de node, puedes simplemente ejecutar ```nvm use <número de versión>```, por ejemplo ```nvm use v12.18.1```. <br>

> :bulb: Para listar las diferentes versiones de node que tiene instaladas con nvm, ejecute ```nvm ls```.<br>

> :bulb: Me gusta nvm porque me permite usar diferentes versiones de node para diferentes proyectos. A veces, puedes estar colaborando en un proyecto con alguien que usa una versión diferente de node y necesitas cambiar las versiones de node a lo que el proyecto requiere. Para esto, nvm es la mejor herramienta.

---

### Desinstalar nodejs si está instalado

```
$ sudo apt remove nodejs
```

<br><br>



***Option 2***

# Repositorio NodeSource

```
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt-get install -y npm
```
> :memo: instalar otras versiones cambiar setup_xx.x
```
setup_current.x
setup_18.x
setup_16.x
setup_14.x
setup_lts.x // versión con soporte a largo plazo
```

<br><br>

***Option 3***

# Decargando el paguete de Nodejs de su sitio web 

```
sudo wget https://nodejs.org/dist/v16.16.0/node-v16.16.0-linux-armv7l.tar.xz
sudo apt install tar
sudo tar -xvf node-v16.16.0-linux-armv7l.tar.xz
sudo chmod -R 755 /usr/local
```
<br><br>

# NodeJS Install Steps for Pi Zero
Descargar
```
//wget <link to NodeJS ARMv61 from nodejs.org>
wget https://unofficial-builds.nodejs.org/download/release/v14.13.0/node-v14.13.0-linux-armv6l.tar.xz
```

Descomprimir
```
//tar xvfJ <file.tar.xz>
tar xvfJ node-v14.13.0-linux-armv6l.tar.xz
```

Copie el contenido del archivo extraído en el directorio usr/local de su Pi Zero.
```
//sudo cp -R <extracted tar folder>/* /usr/local
sudo cp -R node-v14.13.0-linux-armv6l/* /usr/local
```

Ahora puede limpiar eliminar el archivo que descargó y la carpeta extraída. Este comando eliminará cualquier archivo o carpeta que comience con ```nodo-``` en su directorio actual. Asegúrese de no tener ninguna carpeta importante que use este prefijo, ya que también se eliminarán.
```
rm -rf node-*
```

Ahora puede ejecutar el siguiente comando que verificará qué versión de NPM y NodeJS están instaladas actualmente en su Pi Zero.
```
node -v && npm -v
```

## Extra steps

Es posible que deba hacer lo siguiente si recibe un ```error de comando no encontrado```. Primero, abra el archivo .profile usando nano
```
sudo nano ~/.profile
```

Agregue la siguiente línea al final del archivo y presione Ctrl + X para guardar, y luego presione 'y' e ingrese para confirmar los cambios.
```
PATH=$PATH:/usr/local/bin
```

<br><br>

# Actualizar nodejs & npm

nodejs
```
sudo npm install -g n
sudo n stable
```

npm
```
sudo npm install -g npm@latest
```

## install build tools (instalar herramientas de desarrollo)
```
sudo apt install build-essential
```
<br><br>

# Uninstall nodejs Ubuntu & Debian packages
To completely remove Node.js installed from the deb.nodesource.com package methods above:

use `sudo` on Ubuntu or run this as root on debian
```
apt-get purge nodejs
rm -r /etc/apt/sources.list.d/nodesource.list
```



<br>

---
Copyright &copy; 2022 [carjavi](https://github.com/carjavi). <br>
```www.instintodigital.net``` <br>
carjavi@hotmail.com <br>
<p align="center">
    <a href="https://instintodigital.net/" target="_blank"><img src="https://raw.githubusercontent.com/carjavi/install-nodejs-ARM/master/img/developer.png" height="100" alt="www.instintodigital.net"></a>
</p>
