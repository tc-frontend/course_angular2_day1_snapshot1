

Angular 2: Getting Started - SnapShot 1
===================


----------


### 1 - Objetivos del Curso


----------


 - Aprender los principales conceptos de Angular2
 - Aplicar los conceptos a través de ejercicios guiados y basados en un curso de PluralSight
 - [Angular2: GettingStarted](https://app.pluralsight.com/library/courses/angular-2-getting-started-update/table-of-contents)

![enter image description here](https://i.imgur.com/S50z7av.png)	


----------


### 2 - Introducción


----------


#### Enlaces del curso


 - [Introduction](https://app.pluralsight.com/player?course=angular-2-getting-started-update&author=deborah-kurata&name=angular-2-getting-started-update-m1&clip=0&mode=live)


 - [First Things First](https://app.pluralsight.com/player?course=angular-2-getting-started-update&author=deborah-kurata&name=angular-2-getting-started-update-m2&clip=0&mode=live)


 - [Introduction to Components](https://app.pluralsight.com/player?course=angular-2-getting-started-update&author=deborah-kurata&name=angular-2-getting-started-update-m3&clip=0&mode=live)
 
 
**Definición**: "*Es un framework de javascript para crear aplicaciones cliente utilizando HTML, CSS y Javascript*"


**Características**
 - HTML claro (If’s, foreach’s…)
 - Databinding (OneWay, TwoWay, eventos…)
 - Basado en Módulos (desacoplamiento y reutilización)
 - Soporte nativo de comunicación con el servidor. HttpModule


**Mejoras en la versión 2**
 - Más rápido (renderizado, eventos y binding)
 - Actualizado a los últimos estándares de JS
 - API simplificada y orientado a productividad


----------


### 3 - Arquitectura


----------


Una aplicacion Angular 2 está compuesta por un conjunto de componentes


![enter image description here](https://i.imgur.com/Nzr6btH.jpg)


Cada componente se compone de:
 - Una Template HTML
 - Código javascript del componente
 - Metadatos asociados al componente


![enter image description here](https://i.imgur.com/po32QHz.jpg)


Una aplicación Angular 2 contiene un módulo principal o módulo Root pero se pueden añadir más módulos para agrupar las diversas funcionalidades de una aplicación compleja.


 ![enter image description here](https://i.imgur.com/V28Dzc3.jpg)





----------


### 4 - First Things First


----------


#### Escojer el lenguaje


Angular 2 soporta gran variedad de lenguajes. Para el curso utilizaremos TypeScript como lenguaje de desarrollo.


 - ES5
 - ES6
 - **TypeScript** : Aporta grandes funcionalidades como strong typing, orientación a clases y objetos y facilidad de interpretación de los editores y IDE's para ofrecer intellisense, navegación a definiciones y refactoring.
 - Dart



####Escojer el editor


Al desarrollar principalmente en JS y TypeScript podemos utilizar tanto editores como IDE's para el desarrollo de nuestras aplicaciones: Atom, Eclipse, VS. En este curso utilizaremos:
 - Visual Studio Code (Windows, Mac y Linux)




#### Creamos y ejecutamos nuestra primera aplicación

Hay muchas opciones para crear una solucion Angular 2. Podemos crearla desde 0 según:

https://angular.io/docs/ts/latest/quickstart.html

Apoyarnos en una solucion hecha por Angular que incluye por ejemplo Webpack y navegacion

https://github.com/angular/angular2-seed

O bien utilizar generadores como Angular CLI

https://cli.angular.io/



----------


### 5 - Introduction To Components


----------


#### Estructura de un Componente


Los componentes en angular tienen:


 - View: Es la template del componente. El código HTML.


 - Componente: Código TypeScript con la lógica de presentación (métodos, propiedades)


 - Metadatos: Un **Decorator** que se encargará de hacer público nuestro componente como directiva HTML y asociar la View y el código del componente. 


 ![enter image description here](https://i.imgur.com/BCR27MK.png)






#### Desarrollo de un componente


Como podemos observar en este caso se ha creado un componente con una **Template HTML Inline**, una clase que define la lógica del componente y un Decorator, **@Component** , que es el que se encarga de exportar los metadatos del componente.  


![enter image description here](https://i.imgur.com/j2FoQFG.png)






#### Carga de módulos de Angular


En la sección anterior hemos podido observar como se hace un imports de un módulo en Angular. En el caso del componente, para poder utilizar el Decorator **@Component** se ha importado el módulo **"core"** de angular.
Angular expone otros módulos separados para otras tareas como por ejemplo:


 - **router**: Para la navegación


 - **http**: para la comunicación con el backend


 - **animate**: para facilitar el uso de UI's enriquecidas


![enter image description here](https://i.imgur.com/r6tcVpc.png)






#### Orden en la carga de los módulos en nuestra práctica:

Existen muchas formas de implementar una aplicación Angular. Esto dependera en tre otras cosas de la estructura que acordemos y del cargador de modulos elegido.
En nuestro caso se va a utiizar SystemJS por lo que le orden quedaría:



 **1. index.html:** System.import se encarga de cargar el paquete de la aplicación.
 
 
 **2. Systemjs.config.js:** Se encarga de definir cuál es el módulo principal de bootstrapping de la aplicación : **main.js**.
 
 
 **3. main.ts:** Se encarga de referenciar al módulo principal e iniciar la aplicación llamando al bootstrap.
 
 
 **4. app.module.ts:** Es el módulo principal y tiene importados todos los componentes que se van a utilizar declarando con el decorador **@ngModule** que el componente que se va a utilizar para el bootstrap es "**AppComponent"**.
 
 
 **5. app.component.ts:** Finalmente el componente define en su Decorator que su "tag" html será "`<pm-app></pm-app>`" y que la template definida solo cargará un div con un título. El título es una propiedad del componente con un valor definido.
 





![enter image description here](https://i.imgur.com/A6rSYMa.png)






----------


### 6 - Práctica


----------


El objetivo es construir una aplicación Angular 2 con un componente simple. 
Para ellos clonamos des del repositorio una aplicación con una estructura básica y un componente básico.


#### Descargamos el código, restauramos las dependencias y abrimos el proyecto


    git clone https://github.com/tc-frontend/course_angular2_day1_snapshot1.git
    cd course_angular2_day1_snapshot1
    git checkout tags/init
    npm install
    code .
  

#### Descripción de los pasos


 - npm install  -> Instala toda las dependencias 
 

![](https://i.imgur.com/YdRTnGy.jpg)


 - code . -> Abre el proyecto en Visual Studio Code

 
#### Compilamos y ejecutamos la aplicación


    npm start


 - npm start -> Transpila el código TypeScript, levanta un servidor y lanza la aplicación en un browser.


![](https://i.imgur.com/meUZzzD.jpg) 


Una vez transpilado el código tenemos que para cada componente TypeScript ***.ts** se generan ficheros ***.js** y ***.map**.


![enter image description here](https://i.imgur.com/jxjWNLs.png)





#### ¿Cómo se carga el módulo principal de Angular? 


 - Se navega a **index.html**


 - En la página se realiza la carga principal del módulo root de Angular que está dentro del folder **"app"**


 - Finalmente se ejecuta el código de **main.js**


![enter image description here](https://i.imgur.com/4KMWtt7.png)






## Acceder a la versión final 


Si queremos ver la solucion final 

    git checkout master
    npm install
    npm start

Los pasos detallados los podemos vr en:

    https://github.com/tc-frontend/tc-frontend-angular2_day1_snapshot1/commits/master