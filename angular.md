Angular by Null 👁️
=

Pequeña guía escrita para recordar aspectos básicos de como llevar un proyecto de inicio a fin usando el grandioso framework "Angular". 

Are you ready?! 😈


Instalación Angular ⚙️
--
**1. Una vez instalado node ejecutamos el comando:**

    npm install -g @angular/cli
 

Crear una aplicación con Angular 
--

**1. Ejecutamos el comando:**

    ng new <NombreAplicación>


**2. Una vez creada la app, podemos empezara a modificarla. Para ello usamos el comando:**

    ng serve


Crear elementos de la aplicación con Angular CLI
--
**Paginas**

    ng g m pages/<NombrePagina> --routing=true && ng g c pages/<NombrePagina> --type=page -m <NombrePagina>

_Recuerda agregar esta linea en el routing-module de cada pagina_
    
    import { <NombrePagina> } from './<NombrePagina>.page';

    const routes: Routes = [
      {
        path: '',
        component: <NombrePagina>
      }
    ];
    
    
_Y por ultimo agregar la pgina creada al app-routing-module_

    const routes: Routes = [
    {
        path: '<NombrePorElCualSeMuestraLaPaginaEnLaURL>',
        loadChildren: () => import('<RutaDelModuloDeLaPagina>').then(m => m.<NombreDelMoudlo>.module)
    },

   
Actualizar Proyecto Angular
--

Sí se necesita pasar de la V.13 a la V.14 consulta este link

    https://update.angular.io/?v=13.0-14.0




Sí se clonó el proyecto y las versiones de angular están des actualizadas, puede que por ejemplo aparezca un error similar a éste:

(This version of CLI is only compatible with Angular versions ^9.0.0-beta || >=9.0.0 <10.0.0, but Angular version 8.2.14 was found instead.)  
    
    
Para actualizar la versión de Angular de la aplicación ejecutamos los siguientes comandos:

**A. Revisamos la versión actual de la aplicación.**
    
    ng --version
    
**B. Instalamos la ultima versión del cliente de Angular.**

    npm install --save-dev @angular/cli@latest
  
**E. Procedemos a actualizarlo.**

    ng update
    
**D. Actualizamos el "Core" de la aplicación.**

    ng update @angular/cli @angular/core
    
**Recomendación. En caso de que toque usar la fuerza bruta se usa este comando ;)**

    ng update @angular/cli @angular/core --allow-dirty --force

**E. Revisamos que todo este actualizado**

    ng --version
  
  
 
AOS Animations
--

Para poder usar Aos y sus animaciones debemos primero descargar las librerías en nuestra aplicación:

**A. Aos**

    npm install aos --save
  
**B. Jquery**

    npm install jquery --save

**2. Después modificamos el archivo angular.json y agregamos las librerías a nuestro proyecto:**

    "styles": ["node_modules/aos/dist/aos.css"],

Luego en los scripts:    

    "scripts": ["node_modules/aos/dist/aos.js","node_modules/jquery/dist/jquery.min.js"]

**3. Una vez hayamos realizado la modificación del archivo angular.json vamos al archivo app.component y agregamos las siguientes lineas de código:**
    
    import * as AOS from 'aos';

    export class AppComponent {  
      ngOnInit():void{
        AOS.init();
        AOS.refresh();
      }
    }





Firebase
--

**IMPORTANTE

    https://www.youtube.com/watch?v=TVwa2x-jz-Y


**1. Primero instalamos todos los archivos de firebase necesarios en la aplicación.**

    npm install -g firebase-tools
    
Luego:

    npm install firebase @angular/fire
 


**2. Incluir en la variable de entorno las configuraciones de firabase. (src/enviroments/enviroment.ts)**

  Dicho archivo debería quedar algo parecido a esto:  
  
      export const environment = {
        production: false,
        firebaseConfig : {
          apiKey: "null",
          authDomain: "",
          databaseURL: "",
          projectId: "",
          storageBucket: "",
          messagingSenderId: "",
          appId: "",
          measurementId: ""
        }
      };


  https://firebase.google.com/docs/web/setup?authuser=0#desde-las-url-de-hosting



**3. Importamos los modulos de firebase y la variable de entorno. (src/app/app.module.ts)**


    import { AngularFireModule } from '@angular/fire';
    import { AngularFirestoreModule } from '@angular/fire/firestore';
    import { AngularFireStorageModule } from '@angular/fire/storage';
    import { AngularFireAuthModule } from '@angular/fire/auth';
    import { environment } from '../environments/environment';


    @NgModule({
      declarations: [
        AppComponent,
        LoginComponent
      ],
      imports: [
        BrowserModule,
        AppRoutingModule,
        BrowserAnimationsModule,
        AngularFireModule.initializeApp(environment.firebaseConfig),
        AngularFirestoreModule,
        AngularFireStorageModule,
        AngularFireAuthModule,
      ],
      providers: [],  
      bootstrap: [AppComponent]
    })

Firebase Deploy
---
**1.** Ejecutamos Firebase
    
    
    firebase init
    
    
**2.** Firebase nos preguntará con que funciones deseamos trabajar y nos preguntará acerca de donde deberia buscar los archivos de producción y le diremos que en la carpeta dist.

**3.** Habiendo acabado las configuraciones y validaciones nos habrá creado una carpeta dist y en ella un archivo prederterminado el cual deberemos eliminar para alojar la versión de produción.
  
**4.** Generamos una aplicación en modo de producción:

    ng b --build-optimizer
  
**5.** Subimos la versión de producción generada.
  
    firebase deploy
 
