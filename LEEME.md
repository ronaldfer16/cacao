# Mi Finca de Cacao: versión instalable (PWA)

Un solo servicio en internet hace dos cosas: entrega la app al celular y analiza las fotos con IA.
No necesita Play Store ni Android Studio. Necesita una computadora (o ayuda de alguien) solo una vez, unos 20 minutos.

## 1. Clave de la IA
- Entre a console.anthropic.com, cree una cuenta, agregue saldo pequeño y cree una "API key". Guárdela en privado.
- Ponga un límite de gasto mensual en esa misma cuenta.

## 2. Subir los archivos a GitHub
- Cree cuenta gratis en github.com y un repositorio nuevo (privado está bien).
- Suba TODO el contenido de esta carpeta (server.js, package.json, la carpeta public...) con "Add file > Upload files".

## 3. Publicar en Render (o Railway)
- En render.com: New > Web Service > conecte su repositorio de GitHub.
- Build Command: `npm install`   Start Command: `npm start`
- En Environment agregue: `ANTHROPIC_API_KEY` = su clave.
- Al terminar le dan una dirección como https://mi-cacao.onrender.com
- Nota: en el plan gratis el servicio "duerme" y la primera foto del día puede tardar casi un minuto.

## 3b. Opción sin GitHub (si prefiere): cualquier hosting con Node.js 18 o más que corra `npm install` y `npm start`.

## 4. Instalar en el celular
- Abra esa dirección en Chrome en el Android.
- Menú de los tres puntos > "Instalar app" o "Agregar a pantalla de inicio".
- Queda con su ícono y abre sin internet (la foto sí necesita señal).

## Para actualizar la app
Cambie `public/index.html`, suba el archivo, y suba el número VERSION en `public/sw.js` (cache-v1 a v2) para que los celulares se actualicen.

## Pendiente
- Los datos (registro de cosechas, finca) se guardan en cada celular. No se pasan de un celular a otro ni se respaldan todavía.
