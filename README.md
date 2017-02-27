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


Prueba, ignorar
```sh
$ npm install mysql --save
```