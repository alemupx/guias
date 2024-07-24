==============
Git para Dummies
==============

Pequeña guía escrita para recordar aspectos basicos de como manejar el sistema de versionamiento GIT.




==============
Configuraciones de Usuario
==============


-----------
Configurar nombre 
-----------

    git config --global user.name <usuario>

-----------
Configurar el usuario
-----------
    git config --global user.user <usuario>

-----------
Configurar correo electronico
-----------
    git config --global user.email <e-mail>

-----------
Función para eliminar la propiedad que se le exija. 
-----------
    git config --global --unset-all <user.name>



==============
Clone
==============

-----------
Para traer el repositorio remoto a nivel local
-----------
    git clone <url reporsitorio>

-----------
Una vez se haya clonado el repositorio deberíamos descargar todas las dependencias necesarias para poder ejecutar nuestro proyecto
-----------
    npm install


==============
Commit
==============

-----------
Añadir los archivos con los cambios hechos:
-----------
    git add -A // Almacenar todo los cambios hechos.

-----------
Pre publicar los archivos con un comentario detallado de los cambios hechos.  
-----------
    git commit -a -m "<Mensaje>" (IMPORTANTE!!! El mensaje va encerrado entre comillas)

-----------
Publicar cambios hechos. 
-----------
    git push // Subir los cambios confirmados al repositorio remoto.



==============
Branches
==============

-----------
¿Comó saber cuantas ramas tiene el repositorio?
-----------
    git branch --all

-----------
Manera de crear una rama remota: 
-----------
    git checkout -b <NombreDeLaRama>

-----------
Manera de cambiar entre ramas: 
-----------
    git checkout <NombreDeLaRama>




==============
Renombrar Branch
==============

-----------
Renombrar rama estando parado en ella: 
-----------

    git branch -m <NuevoNombre>

-----------
Eliminar la rama remota
-----------
    git push origin --delete <AntigüoNombreRama>


-----------
Publicar rama: 
-----------
    git push --set-upstream origin <NombreRamaLocal>


==============
Delete Branch
==============

-----------
Eliminar rama:
-----------
    git branch -D <NombreDeLaRama>

-----------
Refrescar luego de haber eliminado la rama (El espacio despues de origin es IMPORTANTISIMO): 
-----------

    git push origin :<NombreDeLaRama>


==============
Fetch
==============



-----------
Comando para buscar las ramas remotas actualizadas:
-----------

    git fetch --all --prune 

==============
Merge
==============


-----------
Una vez posicionado en la rama a la cual se le desea hacer la fusión:
-----------

    git merge <NombreDeLaRamaEnLaCualSeVaAFusionarEsta>

==============
Reset
==============


-----------
Una vez posicionados en la rama que queremos fusionar con el commit seleccionado 
-----------

    git checkout <Commit> . (El punto es necesario!)


==============
URL
==============


-----------
Obtener ruta url del repositorio
-----------

    git config --get remote.origin.url 

-----------
Cambiar la ruta URL de un repositorio.
-----------

#1. Eliminamos el origin con el URL antigüo

    git remote remove origin

#2. Creamos la nueva rama con la URL actualizada

    git remote add origin <url>

#3. Aseguramos que el nombre de la rama sea main
    git branch -M main

#4. Asociamos los "push" futuros a la rama origin main
    git push -u origin main





