==============
Rails by Null
==============

Guía escrita para recordar aspectos elementales de la gema de Ruby, Rails. 

==============
Instalación Ruby & Rails
==============

  Link: https://rubyinstaller.org/downloads/
  
Seleccionamos la versión más estable y reciente del Ruby+Devkit. 
 
Verificamos que Ruby éste correctamente instalado usando desde la consola la función:
  
  ruby -v
 
-----------
Rails
-----------
Una vez instalado Ruby, podemos instalar Rails usando: 

  gem i rails
  
Ahora verificamos que Rails éste correctamente instalado usando desde la consola la función:
  
  rails -v
  
==============
Crear una App y Ejecutarla
==============

Para crear una aplicación web usando Rails solo basta usar el comando:

  rails new NombreAplicación
  
Para ejecutar nuestra aplicación, accedemos al directorio de esta y usamos el comando:
  
  rails s
  
==============
Añade Componentes a tu App
==============
Con el comando:

  rails g scaffold NombreComponente

Rails creara automaticamente:

• Un controlador

• Un modelo

• Vistas para cada acción de controlador estándar (índice, editar, mostrar, nuevo)

• Una nueva ruta.

Y sí no te gusta el nombre del componente puedes usar el comando:
  
  rails d scaffold NombreComponente

Y así deshacerte de el.

Al crear un Componente debemos ejecutar las migraciones con la base de datos. Para esto usamos el comando: 

  rake db:migrate
  
  
  


