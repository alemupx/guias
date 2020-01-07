#########################################
Crear proyecto
#########################################

  ng new <nombre del proyecto>


#########################################
Iniciar proyecto
#########################################

  npm start
  
#########################################
Crear Componente
#########################################

  ng generate component <nombre componente>
  
#########################################
Instalar bootstrap
#########################################  

  Instala dependecias necesarias para usar boostrap en Angular
  
  npm i bootstrap jquery popper.js ngx-spinner -s
  

#########################################
Firebase Deploy
#########################################

  Ejecutamos Firebase:
  
  firebase init
  
  
  Luego de haber seleccionado las funciones que deseamos, nos preguntará acerca de donde deberia buscar los archivos de producción y le dire que en el carpeta dist. 
  Habiendo acabado las configuraciones y validaciones nos habrá creado una carpeta dist y en ella un archivo que por default crea el gestor de configuraciones el cual deberemos eliminar para alojar la versión de produción. 
  
  
  Ejecutamos el gestor de la versión de producción con el siguiente comando: 
  
  ng build --prod
  
  Subimos el versión producida por Angular 
  
  firebase deploy
  
  
  
  
  
  
  
  
 
