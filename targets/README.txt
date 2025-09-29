Cómo generar targets para MindAR (image tracking sin marcador)

1) Prepara tu imagen objetivo
- Usa una imagen con buen contraste y características (esquinas, texturas). Evita superficies lisas.
- Tamaño recomendado ~512–1024 px por lado.

2) Genera el archivo targets.mind
- Abre: https://hiukim.github.io/mind-ar-js-doc/tools/compile/
- Sube tu imagen.
- Descarga el archivo "targets.mind" y (opcional) la vista previa .png.
- Coloca el archivo en esta carpeta: targets/targets.mind

3) Prueba en local (necesitas servidor)
- Opción Python (si tienes instalado):
  py -m http.server 5500
  Abre: http://localhost:5500/imagetracking/mindar.html

- Opción Node.js:
  npx serve -l 5500
  Abre: http://localhost:5500/imagetracking/mindar.html

4) Uso dentro de mindar.html
- El scene usa: mindar-image="imageTargetSrc: targets/targets.mind"
- El primer target es targetIndex: 0
- Ajusta el modelo (posición/escala/rotación) en:
  <a-entity gltf-model="#fox" position="0 0 0" rotation="0 0 0" scale="0.2 0.2 0.2"></a-entity>

Tips
- Iluminación uniforme y evitar reflejos mejora el tracking.
- Imprime la imagen o muéstrala en pantalla sin distorsiones.
- Para múltiples imágenes, el compilador permite agregar varias; luego usa targetIndex 0,1,2,...
