# Proyecto Arcademia

Salón recreativo web con los juegos de matemáticas del profesor, organizados
por nivel educativo (1.º-4.º ESO y 1.º-2.º Bachillerato). Es el proyecto
hermano de los apuntes `mat1` (<https://github.com/marioEducastur/mat1>), del
que hereda la cultura de trabajo, y nace para sacar los juegos de cierre de la
plantilla de los apuntes: allí cada unidad cargaba todos los juegos aunque no
los usara.

## Entrada obligatoria para cualquier IA

Antes de actuar sobre el proyecto, cualquier IA debe leer completos
`AGENTS.md` y `CONTEXTO_IA.md`. Este archivo contiene las reglas permanentes;
`CONTEXTO_IA.md` es el cuaderno de relevo con el estado actual, las decisiones
vigentes y el siguiente paso pendiente. Si discrepan, se verificará primero el
estado real del proyecto y se consultará al profesor cuando la decisión no
pueda deducirse con seguridad.

## Reglas permanentes

1. **Cada juego vive en su propio HTML autocontenido.** Nada de acumular
   juegos en una plantilla o archivo común: esa es la lección aprendida en
   `mat1`, donde la plantilla llegó a las ~14.000 líneas y toda unidad la
   cargaba entera. Un juego = un archivo en `juegos/<nivel>/<juego>.html`
   con su CSS y su JavaScript dentro. El código común (por ejemplo, las
   piezas KaTeX `MatematicaEnLinea` y `FormulaViva`) se **duplica** en cada
   juego: la independencia de los archivos vale más que evitar la
   repetición.
2. Las únicas dependencias web permitidas se cargan desde
   `cdn.jsdelivr.net`, siempre con estas versiones exactas, idénticas a las
   de `mat1`: `react@18.3.1`, `react-dom@18.3.1`, `@babel/standalone@7.29.7`
   y `katex@0.16.8` (CSS y JS; el auto-render solo si la página tiene
   fórmulas estáticas que renderizar). Se prohíben otros CDN, otras
   bibliotecas, las webfonts externas y las URL sin versión. Todo lo demás
   —sprites, sonido, gráficos— se hace con SVG, CSS y las API nativas del
   navegador (WebAudio incluida).
3. **Accesibilidad obligatoria** en portada y juegos: manejo completo por
   teclado, roles y etiquetas ARIA en los controles y los SVG
   (`aria-label`, `aria-pressed`, `aria-live` en los veredictos), respeto a
   `prefers-reduced-motion` en toda animación, y el color nunca como única
   fuente de significado (siempre acompañado de texto, forma o posición).
4. **Todo botón o control con fondo claro debe fijar su `color`
   explícito.** Cuidado heredado de `mat1`: una regla global de `button`
   con texto blanco pinta de blanco cualquier botón claro que no declare su
   color, y el defecto es invisible hasta que se mira ese botón concreto.
5. Los números se escriben con la **coma decimal española** (en KaTeX,
   `0{,}75`); cuando un intervalo o par tiene extremos decimales, el
   separador es punto y coma.
6. La web debe funcionar en un **móvil de 375 px sin desbordes
   horizontales**. Las fórmulas largas se contienen con `overflow-x: auto`
   en su propio contenedor, nunca desbordando la página.
7. Todo el trabajo y la documentación se realizan en español.
8. Dentro de una tarea ya autorizada se pueden realizar diagnósticos,
   copias temporales, ediciones locales seguras y validaciones sin pedir un
   permiso por cada comando. Sigue siendo obligatorio pedir **autorización
   expresa** antes de instalar software, borrar material importante, hacer
   `commit` o `push`, crear repositorios remotos y efectuar cualquier otra
   acción externa o difícil de revertir. Si un comando falla, se muestra el
   error literal, se diagnostica y se propone el siguiente paso antes de
   realizar más cambios. Nunca se solicitan contraseñas ni tokens por el
   chat.
9. **El repositorio `mat1` no se toca desde Arcademia.** La retirada de los
   juegos de los apuntes y las tarjetas-cartucho de enlace se harán en
   sesiones propias de `mat1`, cuando el profesor lo ordene. Desde aquí,
   `mat1` es solo lectura (código de origen de las migraciones y destino de
   los enlaces «Aprende esto en…»).
10. `CONTEXTO_IA.md` se mantiene como registro compartido, conciso,
    independiente del proveedor de IA y apto para un repositorio público. Al
    terminar cualquier trabajo relevante, la IA debe actualizarlo antes de
    entregar el turno: fecha, estado vigente, decisiones aún no promovidas a
    estas reglas, archivos afectados, validaciones y tareas pendientes.
    Nunca se guardan contraseñas, tokens, credenciales, correos, rutas
    privadas ni información personal innecesaria.

## Estructura

```text
arcademia/
├── AGENTS.md               # Reglas permanentes (este archivo)
├── CONTEXTO_IA.md          # Estado y relevo común para cualquier IA
├── index.html              # Portada: el salón recreativo
└── juegos/
    ├── eso-1/ … eso-4/     # Estanterías de ESO (se crean al llegar juegos)
    ├── bachillerato-1/
    │   ├── grimorio-transformaciones.html
    │   ├── orbita-gauss.html
    │   └── guardianes-de-r.html
    └── bachillerato-2/
```

Cada juego declara en un comentario de cabecera su curso, su tema y la unidad
de apuntes a la que enlaza su «Aprende esto en…».

## Verificación obligatoria de cada juego

Heredada de cómo se validaron los juegos en `mat1`:

1. **Barrido fuera del navegador con `jsc`** (el motor JavaScriptCore que
   trae macOS en
   `/System/Library/Frameworks/JavaScriptCore.framework/Versions/A/Helpers/jsc`;
   no hay que instalar nada): se extrae la lógica del juego del HTML y se
   recorren todas sus variantes o un barrido amplio de partidas
   parametrizadas, contrastando los veredictos del juego con una evaluación
   matemática independiente (numérica) de la situación original. Ningún
   distractor puede valer lo mismo que la respuesta correcta y ningún
   veredicto puede contradecir la matemática.
2. **Partida completa en el navegador** sirviendo la página por HTTP
   (`python3 -m http.server`; las capturas profundas con `file://`
   fallaban): interacciones reales por DOM, consola limpia, 0 errores KaTeX
   y móvil de 375 px sin desbordes. Cuidado aprendido: al automatizar clics
   de React, un clic sobre un nodo capturado antes de un re-render se
   pierde en silencio; cada clic debe buscar su botón en el DOM vigente, y
   leer el DOM en el mismo bloque síncrono del clic muestra el estado
   anterior al re-render.
3. Revisión visual del profesor antes de cualquier publicación.

## Ciclo de trabajo

```text
migrar o crear el juego → verificar (jsc + navegador + móvil) →
validación del profesor → enlazarlo en la portada →
publicar solo con autorización expresa
```

## Publicación

El repositorio remoto y GitHub Pages **aún no existen**; crearlos exige la
autorización expresa del profesor. Cuando existan, los enlaces internos serán
relativos para funcionar bajo la ruta del proyecto en GitHub Pages, y los
enlaces a los apuntes apuntarán a las unidades publicadas en
<https://marioeducastur.github.io/mat1/>.
