# vue-firstProject

Para este proyecto de prueba la configuración fue la siguiente:

- Para este **NO** se escogió:
    - TypeScript
    - Soporte JSX 
    - Vitest
    - Cypress
- **Si** se escogió que se agregara:
    - Vue Router
    - Pinia
    - ESLint
    - Prettier


- Para iniciar la creación de la estructura de Carpetas y configuraciones inciales usar `npm init vue@latest`.
- Después de lo anterior entonces es necesario descargar las dependencias con `npm install`, se debe estar dentro del directorio del proyecto.
- Instaladas las dependencias entonces se inicia el servidor en modo dev con `npm run dev`.
- Para sacar las cosas para producción `npm run build` y lo que se supone debo subir al servidor es lo que queda en el folder **dist**.
> - cosas para tener en cuenta, cuando lo suba a un servidor WEB como es un aplicativo single page, almenos en este caso, es necesario en el servidor crear regla de redireccion y reescritura, en este ejemplo lo que se hizo fue crear una regla con ***source = /\**** y ***destination = /index.html***, de tal forma que si se llegará a copiar y pegar una dirección del sitio en otra pestaña o navegador siempre la va a redirigir al ***index.html*** que es el contenedor de toda la aplicación.
> - Ahora, para este aplicativo, dado que no se está controlando la parte de *página no encontrada* entonces si se llega a copiar y pegar cualquier URL del sitio en otro navegador o pestaña entonces lo que va a pasar es que se queda en blanco y muestra en la consola de Javascript una advertencia que no encuentra ese componente.