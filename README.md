# medipose

Análisis de movimiento corporal en tiempo real usando MediaPipe Pose, diseñado para fisioterapia y rehabilitación.

🔗 **Demo:** https://trucdefou.github.io/medipose

---

## Qué hace

- Detecta el esqueleto humano en tiempo real usando la cámara del dispositivo
- Calcula y visualiza ángulos articulares clave (codos, hombros, caderas, rodillas)
- Muestra métricas en vivo: FPS, confianza de detección, puntos visibles
- Graba sesiones de movimiento y las exporta como archivos `.json`
- Importa grabaciones para reproducirlas como animación

## Cómo usarlo

1. Abre la app y concede acceso a la cámara
2. Colócate frente a la cámara — el esqueleto se detecta automáticamente
3. Usa los botones de la barra inferior:
   - **Esqueleto** — activa/desactiva la visualización del esqueleto
   - **Ángulos** — activa/desactiva los ángulos articulares
   - **REC** — inicia y detiene la grabación (exporta `.json` al detener)
   - **Importar** — carga un `.json` grabado y lo reproduce como animación
   - **Cámara** — alterna entre cámara frontal y trasera
   - **Config** — ajustes de visualización y modo espejo

## Reproducción de movimientos

1. Graba una sesión con el botón **REC** → se descarga un archivo `fisio_<timestamp>.json`
2. Presiona **Importar** y selecciona ese archivo
3. La app reproduce el movimiento cuadro a cuadro con los controles:
   - `⏮ / ⏭` — saltar ±30 frames
   - `▶ / ⏸` — play / pausa
   - Scrubber para navegar libremente por la grabación
   - `✕` para cerrar y volver a la cámara en vivo

## Tecnologías

- [MediaPipe Pose](https://developers.google.com/mediapipe/solutions/vision/pose_landmarker) — detección de landmarks
- Canvas API — renderizado del esqueleto y ángulos
- PWA — instalable como app en móvil

## Uso local

```bash
python3 -m http.server 3000
```

Luego abre `http://localhost:3000` en el navegador.
