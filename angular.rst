==============
Angular by Null...
==============

Pequeña guía escrita para recordar aspectos basicos de como lllevar un projecto de inicio a fin usando el grandiosisimo framework Angular. Are you ready?! c:

==============
Instalación Angular
==============

#1. Una vez instalado node ejecutamos el comando:
  npm install -g @angular/cli
 
==============
Crear una aplicación con Angular
==============

#1. Ejecutamos el comando: 
  ng new <NombreAplicación>


#2. Una vez creada la app, podemos empezara a modificarla. Para ello usamos el comando:
  ng serve
   

==============
Actualizar Proyecto Angular
==============
Sí se clonó el proyecto y las versiones de angular estan desactualizadas, por ejemplo:

Aparece este error. 
(This version of CLI is only compatible with Angular versions ^9.0.0-beta || >=9.0.0 <10.0.0, but Angular version 8.2.14 was found instead.)  
    
Para actualizar la versión de Angular de la aplicación ejecutamos los siguientes comandos:

#A. Revisamos la versión actual de la aplicación.
  ng --version
  
#B. Instalamos la ultima versión del cliente de Angular.
  npm install --save-dev @angular/cli@latest
  
#E. Procedemos a actualizarlo.
  ng update
    
#D. Actualizamos el "Core" de la aplicación.
  ng update @angular/cli @angular/core
    
#Recomandación. En caso de que toque usar la fuerza bruta se usa este comando ;)
  ng update @angular/cli @angular/core --allow-dirty --force

#E. Revisamos que todo este actualizado
  ng --version

  
  
##################################################################################
Schematichs para generar un componente con modulo y routing
##################################################################################
  

1# Reemplazar nombre
ng g m <nombrePagina> --routing=true && ng g c <nombrePagina> --skip-tests=true -m=<nombrePagina>



2# Routing Module

import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home.component';

const routes: Routes = [
  {
    path: '',
    component: HomeComponent,
  },
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule],
})
export class HomeRoutingModule {}



#3 app-routing.module

{
  path: 'about',
    loadChildren: () =>
      import('./pages/about/about.module').then((m) => m.AboutModule),
},



  
  
