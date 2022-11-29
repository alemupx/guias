Angular by Null...
==============

Pequeña guía escrita para recordar aspectos básicos de como llevar un proyecto de inicio a fin usando el grandioso framework "Angular". Are you ready?! c:


Instalación Angular
-------------
**#1. Una vez instalado node ejecutamos el comando:**

    npm install -g @angular/cli
 

Crear una aplicación con Angular
-------------

**#1. Ejecutamos el comando:**

    ng new <NombreAplicación>


**#2. Una vez creada la app, podemos empezara a modificarla. Para ello usamos el comando:**

    ng serve


Crear elementos de la aplicación con Angular CLI
-------------
**Paginas**

    ng g m pages/<NombrePagina> --routing=true && ng g c pages/<NombrePagina> --type=page -m <NombrePagina>

_Recuerda agregar esta linea en el routing-module de cada pagina_

    const routes: Routes = [
      {
        path: '',
        component: <NombrePagina>
      }
    ];
   
Actualizar Proyecto Angular
-------------
Sí se clonó el proyecto y las versiones de angular están des actualizadas, puede que por ejemplo aparezca un error similar a éste:

(This version of CLI is only compatible with Angular versions ^9.0.0-beta || >=9.0.0 <10.0.0, but Angular version 8.2.14 was found instead.)  
    
    
Para actualizar la versión de Angular de la aplicación ejecutamos los siguientes comandos:

**#A. Revisamos la versión actual de la aplicación.**
    
    ng --version
    
**#B. Instalamos la ultima versión del cliente de Angular.**

    npm install --save-dev @angular/cli@latest
  
**#E. Procedemos a actualizarlo.**

    ng update
    
**#D. Actualizamos el "Core" de la aplicación.**

    ng update @angular/cli @angular/core
    
**#Recomendación. En caso de que toque usar la fuerza bruta se usa este comando ;)**

    ng update @angular/cli @angular/core --allow-dirty --force

**#E. Revisamos que todo este actualizado**

    ng --version
  
  
 
Instalar AOS
-------------

Para poder usar Aos y sus animaciones debemos primero descargar las librerías en nuestra aplicación:

**#A. Aos**

    npm install aos --save
  
**#B. Jquery**

    npm install jquery --save

**#2. Después modificamos el archivo angular.json y agregamos las librerías a nuestro proyecto:**

    "styles": ["node_modules/aos/dist/aos.css"],

Luego en los scripts:    

    "scripts": ["node_modules/aos/dist/aos.js","node_modules/jquery/dist/jquery.min.js"]

**#3. Una vez hayamos realizado la modificación del archivo angular.json vamos al archivo app.component y agregamos las siguientes lineas de código:**
    
    import * as AOS from 'aos';

    export class AppComponent {  
      ngOnInit():void{
        AOS.init();
        AOS.refresh();
      }
    }

 
  
