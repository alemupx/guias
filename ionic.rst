Ionic para dummies
==============



Instalar Ionic CLI
==============


 npm install -g @ionic/cli


Crear aplicación
==============



#1. Crear aplicación y aplicar configuraciones.
------------------------------

 ionic start "nombreApp"


#2 Lanzar aplicación (Utilizar comando estando dentro de la carpeta de la app).
------------------------------

 ionic serve



Instalar Animate.css
==============



#1. Instalarlo
------------------------------

 npm install animate.css --save
 

#2. Añadirlo en el angular.json
------------------------------
 
 styles": ["node_modules/animate.css/animate.css"],

#3. Añadirlo en el global.scss
------------------------------

 @import "~animate.css/animate.min.css";

#4. Uso
------------------------------

 animate__animated animate__bounce



Hacer deploy a Firebase.
==============


#1. Instalar las dependencias
------------------------------

 npm install -g firebase-tools

#PD. Configurar la aplicación con el gestor de Firebase. 

#PD. Definir la carpeta WWW como carpeta de subida.


#2. Loguearse en Firebase
------------------------------

 firebase login

#3. Iniciarlizar Firebase
------------------------------

 firebase init
 
#PD. Configurar la aplicación con el gestor de Firebase. 


#4. Generar BUILD
------------------------------

 ionic generate build --prod
 
#5. Hacer Deploy
------------------------------

 firebase deploy




#REF.
==============


https://fireship.io/snippets/install-angularfire/






SOLUCIONAR BUG DE REDIRECCIÓN
==============


Ejemplo de como tiene que quedar el fireabse.json para evitar el error al recargar la app

{
  "firestore": {
    "rules": "firestore.rules",
    "indexes": "firestore.indexes.json"
  },
  "hosting": {
    "public": "./www",
    "ignore": ["firebase.json", "**/.*", "**/node_modules/**"],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}




Firestore limit
==============


getUpcomingEvents() {
    return this.firestore
      .collection('/events', (ref) => ref.limit(3))
      .snapshotChanges();
 }



REF: https://stackblitz.com/edit/firestore-filter?file=app%2Ffirebase.service.ts



GENERAR BUILD Y SUBIRLA A GIT PAGES
==============

#1 Tener instalado
------------------------------

 npm i angular-cli-ghpages --save

#2 Generar build con la url del proyecto
------------------------------

 ionic build --prod -- --base-href <url>

#3 este comando se encarga de crear una rama en donde estaran los archivos necesarios para que Git Pages despliegue la pag.
------------------------------

 npx angular-cli-ghpages --dir=www

#4 Configurar en Git Pages que la rama creada sea la rama en la cual encontrara los archivos que se mostrarán. 
------------------------------

# Opcional: 
npx angular-cli-ghpages --branch=BRANCH-NAME --dir=www




REF

https://stackoverflow.com/questions/53036381/how-to-deploy-ionic-4-app-to-github-pages

https://github.com/tschaub/gh-pages/issues/192




POSIBLE ERROR.

An error occurred when trying to deploy:
Failed to get remote.origin.url (task must either be run in a git repository with a configured origin remote or must be configured with the "repo" option).


SOLUCIÓN.
~~~~~~~~~~~~~~~~~~~~~~~~~

#1 Mira las ramas remotas que tienes añadidas

git remote -v

#2 Añade la rama origin como lo mencionan en problema y la url del repositorio.

git remote add origin <url>






 SUBJECT, OBSERVABLES, OBSERVER.
 https://desarrolloweb.com/articulos/practica-observables-angular.html









