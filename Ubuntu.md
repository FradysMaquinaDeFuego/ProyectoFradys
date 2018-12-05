# PROYECTO UBUNTU
Para empezar con los pasos, necesitarémos MySQL, Apache y PHP ya instalados.
-Para hacerlo, inserte este código:

$ sudo apt install apache2 php mysql-server mysql

**-Para comprobar que todo esté corriendo en orden y sin errores, agregamos el código siguiente:**

$ sudo service apache2 start

$ sudo service mysql start

$ php ==version

**-Para extraer nuestra base de datos, debemos colocar el siguiente comando:**

$ cd /var/www/html

$ sudo git clone https://github.com/dgeti-cetis108/Programacion-M4S2-2018.git

**-Luego, modificarémos el nombre de la base de datos a "library.com":**

$ sudo mv Programacion-M4S2-2018 library.com

**-Agregarémos la base de datos a nuestro HTML:**

$ cd library.com/db

$ sudo -i

mysql>source /var/www/html/library.com/db/library.sql

**-Crearémos un Usuario y Contraseña:**

mysql>create user ´maquinadefuego´@´localhost´ identified by ´123´;

**-Después de crear ambos, le darémos permisos a la cuenta:**

mysql>grant all on library.* to ´maquinadefuego´@´localhost´;

**-Ahora, salimos de MySQL:**

mysql>exit

**-Comprobarémos la conexión de mysql con la cuenta que hemos creado posterirormente:**

$ mysql -u maquinadefuego -p

**-Luego, editamos "library.com":**

$ sudo nano /var/www/html/library.com/classes/conexion.php

$ sudo apt install php-mysql

$ sudo service apache2 restart

**-Después, debemos modificar nuesta IP para que al poner library.com en el buscador nos redireccione a la página:**

c:>windows\system32\drivers\etc\hosts

$ cd /etc/apache2/sities-available

$ sudo nano library.com.conf

<VirtualHost *:80>

​	ServerName "library.com"

​	ServerAlias "www.library.com"

​	Server Admin "brayan92_mp@hotmail.com"

​	DocumentRoot "/var/www/html/library.com"

​	ErrorLog "/var/log/library.com-error.log"

​	CustomLog "/var/log/library.com-access.log" common

""

**-Finalmente, insertarémos los siguientes códigos:**

$ sudo a2ensite library.com

$ sudo service apache2 restart
