# Las reglas del juego — versión piloto Firebase

## Contenido
- `index.html`: portal responsive, facilitador y estudiantes.
- `firebase-config.js`: ya incluye la configuración de tu proyecto `simuladores-juegos`.
- `firestore.rules`: reglas de seguridad para **la colección nueva `reglas_salas`**.

## Instalación
1. Abre la consola de Firebase y selecciona tu proyecto (puede ser `simuladores-juegos`).
2. En **Authentication > Sign-in method**, habilita **Anónimo**.
3. En **Firestore Database**, crea la base de datos si aún no existe.
4. La configuración web de `simuladores-juegos` ya está incorporada en `firebase-config.js`.
5. **IMPORTANTE:** si tu Firestore ya contiene otros simuladores, NO sustituyas sus reglas completas por este archivo. Integra el bloque `match /reglas_salas/{room}` en las reglas existentes y conserva las otras colecciones.
6. Publica los archivos juntos en un servidor HTTPS, Firebase Hosting o GitHub Pages. La autenticación anónima necesita un dominio autorizado en Authentication > Settings > Authorized domains.
7. Prueba con un navegador como facilitador y otros dos navegadores/perfiles como estudiantes. Un perfil de navegador equivale a una identidad anónima Firebase.

## Secuencia
1. Facilitador crea sala de 6 caracteres.
2. Estudiantes entran con nombre y código. Facilitador empareja; cada proponente ofrece y cada receptor acepta/rechaza. Facilitador revela resultados nominales en su panel.
3. Facilitador abre Empresa en crisis. Un representante por equipo se registra.
4. Ronda 1: máximo 4 estrategias; resultados de productividad y riesgo simulado.
5. Ronda 2: máximo 3 medidas, presupuesto de 50 créditos y canvas de política.
6. Facilitador califica políticas (0–20), muestra ranking final y exporta CSV.

## Limitaciones honestas de este piloto
- **No se ha probado con estudiantes conectados simultáneamente ni se ha desplegado en tu Firebase.**
- El puntaje de bienestar/productividad es una simulación pedagógica, no un cálculo jurídico o económico.
- El indicador de 'riesgo pendiente' es un proxy: una acción correctiva puede mitigar un hallazgo pero no extingue automáticamente obligaciones legales, sanciones o daños.
- La regla Firestore permite leer documentos de sala a usuarios anónimos autenticados. Para uso institucional con información identificable, conviene migrar a autenticación de facilitadores, membresía validada por sala y separar resultados privados de los públicos.
- La puntuación final del presupuesto usa una regla simple; ajusta pesos tras pilotaje.
- El sistema no usa temporizador automático: el facilitador controla manualmente los cambios de ronda.
- En caso de número impar, un participante queda en espera; no se fuerza un emparejamiento falso.
- Las normas citadas en las tarjetas son referencias didácticas y deben revisarse antes de usar en una evaluación formal.

## Validación mínima antes de clase
Prueba emparejamiento, aceptación/rechazo, reconexión, exportación CSV, selección máxima de estrategias, presupuesto, políticas y actualización de notas en al menos tres dispositivos.
