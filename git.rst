#########################################
GIT
#########################################

###################
CONFIGURACIONES USUARIO
###################

    Configurar nombre 
        git config --global user.name <usuario>
	
    Configurar el usuario
        git config --global user.user <usuario>
	
    Configurar correo electronico
        git config --global user.email <e-mail>
	
    Función para eliminar la propiedad que se le exija. 
        git config --global --unset-all <user.name>

###################
CLON // CLONAR
###################
    
    Para traer el repositorio remoto a nivel local
        git clone <url reporsitorio>
    
    
    Una vez se hallá clonado el repositorio deberiamos descargar todas las dependencias necesarias para poder ejecutar nuestro proyecto
	npm install

###################
COMMIT // AÑADIR ARCHIVOS AL REPOSITORIO EN GITHUB
###################

    Añadir los archivos con los cambios hechos:
        git add -A // Almacenar todo los cambios hechos.

    Pre publicar los archivos con un comentario detallado de los cambios hechos.  
        git commit -a -m "<Mensaje>" (IMPORTANTE!!! El mensaje va encerrado entre comillas)
    
    Publicar cambios hechos. 
        git push // Subir los cambios confirmados al repositorio remoto. 

###################
BRANCHES // RAMAS
###################
		
    ¿Comó saber cuantas ramas tiene el repositorio?
	git branch --all
		
    Manera de crear una rama remota: 
        git checkout -b <NombreDeLaRama>

    Publicar rama que no este remotamente: 
        git push --set-upstream origin <NombreRamaLocal>
	
    Renombrar rama: 
    	git branch -m <NombreRamaLocal> <NuevoNombre>	
    
    Eliminar rama:
	git branch -D <NombreDeLaRama>
    	
    Refrescar luego de haber eliminado la rama (El espacio despues de origin es IMPORTANTISIMO): 
    	git push origin :<NombreDeLaRama>
	


###################
FETCH // BUSCAR
###################

    Comando para buscar las ramas remotas actualizadas:
        git fetch --all --prune 

###################
MERGE // FUSIÓN
###################

    Una vez posicionado en la rama a la cual se le desea hacer la fusión:
        git merge <NombreDeLaRamaEnLaCualSeVaAFusionarEsta>

###################
URLS
###################

    Obtener ruta url del repositorio
       git config --get remote.origin.url     
       
    Cambiar la ruta url de un repositorio.
       git remote set-url origin <url>
       
