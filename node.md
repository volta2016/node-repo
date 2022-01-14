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

ver version de de node

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

En este caso estoy exportando 2 cositas y lo estoy llevando a un objeto
