# Gradua2s – Espejo mágico

Estructura: `public/index.html` (espejo), `public/v.html` (página del celular), `api/upload.js` (sube la foto a Vercel Blob).

## Despliegue (≈10 min)
1. Crea cuenta gratis en github.com y sube esta carpeta a un repositorio nuevo.
2. En vercel.com → Add New → Project → importa el repositorio (Framework: "Other"). Deploy.
3. En el proyecto: pestaña Storage → Create → Blob → conéctalo al proyecto (crea solo la variable BLOB_READ_WRITE_TOKEN). Haz Redeploy.
4. Abre `https://TU-PROYECTO.vercel.app` en Chrome, permite la cámara y prueba.

Alternativa sin GitHub: `npm i -g vercel`, luego `vercel` y `vercel --prod` dentro de la carpeta.

## DSLR
Chrome solo ve la cámara como webcam. Conecta la DSLR por HDMI con una capturadora USB, o con Canon EOS Webcam Utility / Sony Imaging Edge Webcam / Nikon Webcam Utility. Luego elígela en el selector de abajo a la derecha.

## Modificar
Todo se configura en el bloque `CFG` de `public/index.html` (segundos, marco PNG, calidad). Para un marco PNG propio: ponlo en `public/marco.png` y usa `framePng:'/marco.png'`.

## Notas
- Las fotos no se borran solas; límite gratuito de Blob: revisa tu plan y borra periódicamente desde Storage.
- Foto máxima ~4 MB (límite de las funciones de Vercel); se comprime automáticamente.
