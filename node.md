# Node js

- Node.js® es un entorno de ejecución para JavaScript construido con V8, motor de JavaScript de Chrome.

- Node.js es un entorno en tiempo de ejecución multiplataforma, de código abierto, para la capa del servidor (pero no limitándose a ello) basado en el lenguaje de programación JavaScript.

- Al contrario que la mayoría del código JavaScript, **no se ejecuta en un navegador** (¿se podrá ejecutar entonces fetch api?).

- Ideado como un entorno de ejecución de JavaScript orientado a eventos asíncronos, Node.js está diseñado para crear aplicaciones network escalables.

- HTTP es un elemento destacado en Node.js. Esto hace que Node.js sea muy adecuado para la base de una librería o un framework web.

- En términos simples node no bloquea las operaciones, no queda a la espera de por ejemplo una solicitud a la base de datos, dejando la cpu trabajando en ello, node reanudará las operaciones cuando vuelva la respuesta. Esto permite que Node.js maneje miles de conexiones simultáneas con un solo servidor sin introducir la carga de administrar la concurrencia de subprocesos, lo que podría ser una fuente importante de errores.

- En Node.js, los nuevos estándares de ECMAScript se pueden usar sin problemas, ya que no tiene que esperar a que todos sus usuarios actualicen sus navegadores. versión de node y EcmaScript(opens new window)
  NPM: Cuenta con más de 1 millón de paquetes, módulos o bibliotecas disponibles para su utilización.

**TIP**

V8 es el entorno de ejecución para JavaScript creado para Google Chrome. Es software libre desde 2008, está escrito en C++ y compila el código fuente JavaScript en código de máquina en lugar de interpretarlo en tiempo real.

ver versión de de node

comando para la consola:

node -v

## Probar

Para probar archivos podemos ejecutar:

**node app.js**

para probar un index.js que esta en la raiz, no necesitamos
especificar su nombre ejecutamos:

**node .**

el fetch no lo podemos ocupar dentro de node porque el fetch trabaja con una API externa y donde se ejecuta fetch API en el navegador, como nosotros no estamos trabajando con el navegador no podemos utilizar fetch, lo mismo para el DOM y LocalStorage

## Modulos

- Node tiene un sistema de módulos incorporado.
- Un archivo Node.js puede importar la funcionalidad expuesta por otros archivos Node.js.
- module.exports > estos son los modulos nativos que tiene node js

En este caso estoy exportando 2 const y lo estoy llevando a un objeto

```js
const frutas = ["🥝", "🍎", "🍌", "🍓"];
const precios = [100, 200];

module.exports = {
  frutas,
  precios,
};
```

Desde ahora hablaremos mucho sobre los módulos (puede que los nombre como paquete, paquetito, biblioteca, dependencia, etc).
Además de utilizar módulos externos con NPM, también node cuenta con una gama de ellos incorporado, los puedes revisar aquí [node](https://nodejs.org/dist/latest-v16.x/docs/api/)

Node tiene un montón de modulos que vienen incorporado en el, que nosotros podemos utilizar, pero además la gracia es que nosotros
podemos utilizar estos paquetes como dependencias externas como axios, express, sql etc.

## NPM

- npmjs.com [npm](https://)
- Es el administrador de paquetes o dependencias estándar para Node.js.
- Repositorio de código de un solo idioma más grande de la Tierra.
  axios, express, jsonwebtoken, sequelize, son algunos paquetes, dependencias (códigos) que solucionan problemas, es tu elección utilizarlos (A menos que quieras reinventar la rueda).
- yarn [npm](https://) es una alternativa al cli de npm.

Cómo voy saber yo en qué versión estoy En que versión específica estoy trabajando
para eso existe el **package.json**

Para eso cada vez que inicie un proyecto tienes que hacer tu package.json

Vemos la versión
npm -v
6.14.15

vamos a iniciar con el package.json con el siguiente comando:

**npm init**

Esto inicializa nuestro package.json, con un cli. Un cli quiere decir que tiene más características

- Se nos creará un archivo el cual tendrá información sobre nuestro proyecto, lo más relevante en estos momentos serán sus dependencias y scripts
- npm y yarn almacena los nombres y versiones de todos los paquetes instalados.

## package-lock.json

- En la versión 5, npm introdujo el archivo package-lock.json.
- El objetivo del package-lock.json es realizar un seguimiento de la versión exacta de cada paquete que se instala, para que un producto sea 100% reproducible de la misma manera incluso si los paquetes son actualizados por sus encargados.
- El package-lock.json establece su versión actualmente instalada de cada paquete en piedra.

## npm update

npm 7 actualización(opens new window)
Desde npm versión 7 en adelante, al ejecutar npm update no cambiará el archivo package.json sino que package-lock.json llevará el control de la versión más reciente a utilizar.
Ejecute npm list para saber la versión actual o bien abra el archivo package-lock.json.
versionlens (opens new window)te ayuda a visualizar los paquetes actualmente utilizados.

**👀 si me da un monton de peresa crear ese archivo puedo aplicar**

**npm init -y**

## instalar paquetes

vamos a instalar esta lib para trabajar con fechas

(moment js)[https://momentjs.com/]

npm i moment

si quieres instalar una versión específica debes escribir:

@2.19.1

**npm i moment@2.19.1**

la carpeta **node_modules** no se comparte no se sube

**package-lock.json** muestra las versiones de paquetes que hemos instalados, vamos a llevar un registro

por lo tanto con esta banderita **^** nosotros vamos actualizar todo después del 2 o sea va instalar la 19, la 20
la 21 y 22 pero sin pasar 3.0.0 por que los últimos numeros que nosotros vemos son los parches, son la vulnerabilidades,
son las pequeñas correciones.

## Versiones

npm-update#description(opens new window)
semantic-versioning-using-npm(opens new window)
~1.2.3 Actualiza las versiones parches, por ende actualizará menor > 1.3.0
^1.2.3 Actualiza versiones menores incluyendo parches, por ende actualizará menor > 2.0.0
Instalar versión específica:

package/moment

```language-text
npm i moment@2.19.1
```

Cambia el package.json

```language-text
"dependencies": {
"moment": "~2.19.1"
}
```

Ejecuta:

```language-text
npm update
npm list
```

Cómo puedes ver solo se actualizó hasta la versión 2.19.4
Desinstalar e instalar nuevamente:

```language-text
npm uninstall moment
npm i moment@2.19.1
npm update
npm list
```

- Ahora se actualizó a la versión 2.29.1 (al 3 enero 2021, puede que tu veas otra versión más reciente)

- Volvamos a desinstalar e instalaremos sin una versión específica:

```language-text
npm uninstall moment
npm i moment
Se instala la última versión disponible 2.29.1 (al 3 enero 2021, puede que tu veas otra versión más reciente)
```

## Locales vs Globales
