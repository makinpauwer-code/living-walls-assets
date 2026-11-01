# GROK — INTEGRACIÓN DE LIVING WALLS DYNAMIC ASSET LIBRARY

Biblioteca pública: https://makinpauwer-code.github.io/living-walls-assets./
Repositorio: https://github.com/makinpauwer-code/living-walls-assets.

## Requisito principal
Esta biblioteca contiene 30 FONDOS ANIMADOS, no imágenes estáticas. Cada SVG tiene animaciones SVG embebidas (animate / animateTransform) que se reproducen en bucle en un navegador compatible. Debes conservar el carácter dinámico al integrarlos.

## Integración Android
- Usa Android WallpaperService y WallpaperService.Engine para que el fondo sea realmente el wallpaper del sistema.
- Opción práctica: renderizar cada SVG animado en un WebView controlado dentro del Engine, comprobando compatibilidad/rendimiento en el dispositivo. Alternativamente recrea sus capas y animaciones con Canvas/OpenGL nativo.
- No uses ImageView ni captures una imagen fija como resultado final.
- Pausa/reduce animación cuando el wallpaper no sea visible, al apagar pantalla o cuando el sistema lo solicite.
- Incluye perfiles de rendimiento, control de intensidad y modo ahorro.
- Prueba en dispositivo Android real que la animación sigue activa después de salir de la app.
- Si el renderer Android no soporta algún elemento SVG, implementa el efecto equivalente en el motor nativo; no lo sustituyas por un fotograma estático.
- La galería web reproduce los SVG animados para vista previa. En la app, no etiquetes un fondo como dinámico hasta que esté funcionando dentro de WallpaperService.

## Importación
1. Lee assets.json.
2. Descarga los 30 archivos assets/LW-xxx.svg.
3. Mantén ID, nombre, categoría y descripción.
4. Muestra vista previa animada.
5. Botón aplicar debe abrir el flujo oficial de Android para configurar live wallpaper.
6. Permite descargar/guardar recursos para uso offline.

## Derechos de uso
Todos los SVG de esta colección son obras vectoriales procedurales originales creadas desde cero para este proyecto. No se han usado fotografías, personajes de franquicias, logotipos, marcas ni recursos visuales de terceros. Se autoriza su uso, modificación e integración en Living Walls. No atribuyas los recursos a terceros ni afirmes que son personajes oficiales de franquicias.

## Criterios de aceptación
- Cada SVG se anima en la galería del navegador.
- El fondo continúa animándose cuando está aplicado en la pantalla de inicio Android.
- El sistema puede pausar/reanudar correctamente el render.
- El modo ahorro reduce la actividad gráfica.
- Ningún fondo animado se convierte silenciosamente en imagen fija.
