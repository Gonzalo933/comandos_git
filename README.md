# comandos_git

* git ini <nombre_opcional>								-> Sin nombre, convierte el directorio en repo, con nombre, crea directorio y convierte

* git remote add origin https://github.com/Gonzalo933/..	-> Crea el repo online

* git clone git@github.com:Gonzalo933/nombre_repo.git 		-> Clonar repo privado

* git clone https://github.com/Gonzalo933/...

* git pull   												-> Descargar

* git add [NOMBRE_FICHERO o punto para todos]				-> añade ficheros para la lista de subirlos (soluciona el error nothing addded to commit but untracked ...)

* git commit -am "MENSAJE_COMMIT" 						-> actualizar lo que se subiria si haces push

* git push origin master 									-> Subir

* git config --global credential.helper cache				-> guardar credenciales temporalmente

* git mergetool											-> para conflictos


* git checkout -b "nombre_branch"							-> Crear Branch y cambiar al branch

* git branch "nombre"										-> Crear Branch

* git checkout "nombre"   								-> Cambiar al branch

* git merge "nombre"										-> añadir cambios del branch "" al branch actual (si antes has hecho git checkout master, estaras en master)


## OTROS

| Comando  | Accion |
| ------------- | ------------- |
| crontab -e | abrir crontab para añadir tareas a ejecutar |
| forever start | iniciar un proceso node para siempre (servidor), requiere npm install forever |
| sudo nano /etc/nginx/sites-available/default  | Nginx configuration  |
| sudo service nginx restart | Reiniciar nginx  |

## MYSQL

```sh
$ mysql -u [nombre de usuario] -p
$ CREATE USER 'nombre_usuario'@'localhost' IDENTIFIED BY 'tu_contrasena';
$ CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypass';  //Para remoto
$ GRANT ALL PRIVILEGES ON * . * TO 'nombre_usuario'@'localhost';
$ FLUSH PRIVILEGES;
```
Cuando el mysql se ponga tonto con full group
SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));

Configuracion de mysql
```sh
$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
$ sudo service mysql restart
```
[permiso]  = CREATE / DROP / DELETE / INSERT / SELECT

GRANT [permiso] ON [nombre de bases de datos].[nombre de tabla] TO ‘[nombre de usuario]’@'localhost’;

https://www.digitalocean.com/community/tutorials/crear-un-nuevo-usuario-y-otorgarle-permisos-en-mysql-es


## MAIL


`$ sudo vim /etc/postfix/generic`
Add: www-data gonzalo@gonzalohernandezmunoz.com

`$ sudo vim /etc/postfix/sender_canonical`
Add (I guess it's something like: user - email assigned):
gonzalo no-reply@gonzalohernandezmunoz.com
root no-reply@gonzalohernandezmunoz.com
www-data no-reply@gonzalohernandezmunoz.com

------
Check some settings on:
`$ sudo vim /etc/postfix/main.cf`

sender_canonical_maps = hash:/etc/postfix/sender_canonical
smtp_generic_maps = hash:/etc/postfix/generic
------
```sh
$ sudo postmap /etc/postfix/generic
$ sudo postmap /etc/postfix/sender_canonical
$ service postfix restart
(or)
$ /etc/init.d/postfix restart
```
To check if mail is working:
https://mxtoolbox.com/

Also check:
MailGun
