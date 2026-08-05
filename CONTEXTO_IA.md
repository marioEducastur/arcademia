# Contexto compartido para cualquier IA

Última actualización: **2026-08-05**

## Cómo retomar el proyecto

1. Leer completos `AGENTS.md` y este archivo.
2. Comprobar el estado real de los archivos antes de actuar.
3. No descartar ni sobrescribir cambios locales que no se hayan identificado.
4. Actualizar este archivo antes de cerrar cualquier trabajo relevante.

Las reglas permanentes están en `AGENTS.md`; aquí solo se mantienen el estado
vigente, las decisiones aún no convertidas en reglas y los pendientes.

## Estado del proyecto

- **Proyecto recién creado (2026-08-05)** por decisión del profesor,
  registrada también en el `CONTEXTO_IA.md` de `mat1`: los juegos de cierre
  de los apuntes se mudan a esta página aparte con estética de salón
  recreativo, organizados por nivel (ESO y Bachillerato). Motivo: cada
  unidad generada de `mat1` cargaba la plantilla completa con todos los
  juegos (~14.000 líneas y Babel compilando en el navegador); la separación
  aligera los apuntes y da libertad estética.
- **Frontera acordada**: los **juegos** (Guardianes, Grimorio, Órbita Gauss)
  se mudan; los **laboratorios didácticos** anclados a apartados se quedan
  en `mat1`.
- **Publicado el 6 de agosto de 2026** por orden expresa del profesor:
  repositorio <https://github.com/marioEducastur/arcademia> (rama `main`)
  y GitHub Pages en <https://marioeducastur.github.io/arcademia/>, con
  `.nojekyll` desde el primer commit (lección de mat1). Portada y los
  cuatro juegos verificados con 200 en producción.
- Respaldo en Drive (misma orden): `Mate/Arcademia/` en Mi unidad, con
  instantáneas fechadas que nunca se sobrescriben: `01_salon/` (web
  completa) y `99_respaldo/` (AGENTS, CONTEXTO_IA y ajustes locales),
  todas las copias verificadas byte a byte con `cmp`.
- El código de origen de los tres juegos migrados está commiteado en
  `mat1` (`plantilla/shell.html`), de modo que la mudanza no puede perder
  nada.

## Juegos y su origen en mat1

| Juego | Curso | Tema | Origen en `shell.html` | Estado |
|---|---|---|---|---|
| El Grimorio de las Transformaciones | 1.º Bach. | Ecuaciones (unidad 2, Álgebra) | `GrimorioInteractivo`, `gmConstruirSala`, `GM_PARAMETROS`, `GM_NOMBRES`, `gmMas`, `gmTerminoX`, CSS `.gm-` | **Migrado y verificado; pendiente de la aprobación del profesor** |
| Órbita Gauss: el observatorio de los tres planos | 1.º Bach. | Sistemas de ecuaciones (unidad 2, Álgebra) | `OrbitaGaussInteractivo`, funciones `og*`, CSS `.og-` | **Migrado y verificado; pendiente de la aprobación del profesor** |
| Los Guardianes de ℝ | 1.º Bach. | Números reales (unidad 1) | `GuardianesRealesInteractivo`, generadores `grGen*`, CSS `.gr-` | **Migrado y verificado; pendiente de la aprobación del profesor** |
| La Torre de los Enteros | 1.º ESO | Números enteros | Aportado por el profesor (no procede de mat1) | **Integrado y verificado; pendiente de la aprobación del profesor** |

Orden de migración: Grimorio (piloto) → **Guardianes** → Órbita Gauss
(cambiado por el profesor el 5 de agosto: quería el juego de la unidad 1
antes en la portada), **pidiendo confirmación entre juego y juego**.

Enlaces «Aprende esto en…» hacia los apuntes:

- Unidad 1 (números reales), publicada:
  <https://marioeducastur.github.io/mat1/unidad_01_numeros_reales.html>
- Unidad 2 (Álgebra): **aún sin página pública** en el portal de `mat1`
  (solo está publicada su fuente). Mientras no exista, decidir con el
  profesor si el enlace apunta al portal o queda preparado para
  `unidad_02_algebra.html`.

## Pendientes (lista única y vigente)

1. **Piloto migrado y verificado (2026-08-05), pendiente de la aprobación
   del profesor.** `juegos/bachillerato-1/grimorio-transformaciones.html`
   (1708 líneas, autocontenido, 5 cargas fijadas de jsDelivr, sin
   auto-render porque no hay fórmulas estáticas). Verificación en dos
   capas, como en `mat1`: barrido `jsc` de las 19 variantes
   (689 comprobaciones, 0 fallos: estructura y par de jugadas de cada
   camino, previsualizaciones que coinciden con el paso siguiente, TeX
   sin corrupción, veredicto de cada candidata contrastado con la
   evaluación numérica de la ecuación original reconstruida desde su TeX,
   coherencia controles-veredicto, y barrido de raíces por bisección que
   confirma que ninguna solución real queda fuera del Juicio) y partida
   completa por DOM en el navegador servido por HTTP (5 cámaras selladas,
   10/10 juicios certeros decididos por un evaluador numérico
   independiente que lee el TeX de las anotaciones MathML de KaTeX,
   tropiezo deliberado con su lección, 2 espectros en el frasco,
   98 puntos y récord en `localStorage`; consola limpia, 0 errores KaTeX,
   móvil de 375 px sin desbordes). Adaptaciones respecto a `shell.html`:
   la clase `og-misiones` que el juego tomaba prestada pasa a llamarse
   `gm-camaras` (mismo CSS, definido en el propio archivo) y el montaje
   es directo (sin registro de componentes ni respaldo Pandoc); el
   respaldo estático es un aviso de carga que desaparece al montar.
2. **Portada escrita y verificada (2026-08-05), con el plan aprobado por
   el profesor.** `index.html` (510 líneas, HTML y CSS puros: la portada no
   carga ninguna dependencia; los juegos cargan las suyas). Marquesina con
   el rótulo «ARCADEMIA» en pixel-art real (SVG de 154 rects generados
   desde matrices 5×7, `role="img"` y `aria-label`), halo neón por
   `drop-shadow` y orlas de bombillas con gradientes que alternan brillo
   (fijas con `prefers-reduced-motion`). Seis estanterías (1.º-4.º ESO,
   1.º-2.º Bachillerato) con rejilla `auto-fit minmax(16rem, 1fr)`; las
   vacías muestran la ranura «Próximamente». Cartucho del Grimorio con
   estrías, etiqueta clara con franja violeta del curso, chips de curso y
   tema, botón-enlace «Jugar» (ámbar con texto oscuro fijado y
   `aria-label` descriptivo) y «Aprende esto en…». Decisión del profesor:
   **solo se enlazan juegos migrados y verificados**. Verificado en
   navegador: landmarks presentes, `HEAD 200` del enlace relativo a
   Jugar, 375 px sin desbordes en portada y juego, capturas de escritorio
   y móvil revisadas. Pendiente: revisión visual del profesor.
3. Migrar «Órbita Gauss» y después «Los Guardianes de ℝ», con confirmación
   del profesor entre juego y juego.
4. Cuando Arcademia esté publicada (con autorización expresa: repo, commit,
   push y Pages), en sesiones de `mat1` se retirarán los juegos de
   `shell.html` y las unidades enlazarán con tarjetas-cartucho. **Desde
   Arcademia, `mat1` no se toca.**

## Registro breve

- **2026-08-06 00:43 CEST (publicación):** por orden expresa del profesor
  («haz push/commit… y la estructura en Drive»): repositorio
  `marioEducastur/arcademia` creado (público), **commit inicial
  `0025db4`** (9 archivos: portada, 4 juegos, AGENTS, CONTEXTO,
  `.gitignore` con `.claude/` y `.DS_Store`, y `.nojekyll`), push a
  `origin/main` y **GitHub Pages activado** (main, raíz):
  `pages-build-deployment` en verde y las cinco páginas con 200 en
  producción; la portada verificada en el navegador con el neón rotando
  y los cuatro «Jugar» funcionando bajo `/arcademia/`. La identidad de
  Git se configuró local al repo (copiada de mat1: no había global).
  **Drive**: creada `Mate/Arcademia/` con `01_salon/2026-08-06_0043/`
  (web completa) y `99_respaldo/2026-08-06_0043/` (AGENTS, CONTEXTO_IA
  y `settings.local.json`), copias en pasos simples y las ocho
  verificadas byte a byte con `cmp`. Antes de esta orden quedaba
  pendiente la revisión visual del profesor: la publicación la da por
  buena de facto; cualquier retoque posterior seguirá el ciclo normal
  (cambio → verificación → commit y push autorizados). Este registro
  entra en un segundo commit inmediato para que el repo quede al día.

- **2026-08-06 (La Torre de los Enteros, 1.º ESO):** primer juego de ESO,
  **aportado por el profesor** como archivo ya hecho (prototipo V3, no
  procede de mat1). Integrado en
  `juegos/eso-1/torre-de-los-enteros.html` con tres retoques mínimos:
  comentario de cabecera con curso/tema/origen, `lang="es-ES"` y un botón
  «← Arcademia» **en el propio estilo cartoon del juego** — decisión de
  diseño: este juego conserva su identidad visual de plataforma infantil
  (papel, sol, tubos verdes) y NO se re-tematiza en neón; cada cartucho
  puede ser su propio mundo. El juego es ejemplar en lo técnico:
  autocontenido de verdad (fuente Baloo 2 incrustada como data URI, cero
  peticiones externas, sin almacenamiento), lógica pura separada y
  testeable, `window.__torre` expuesto, `prefers-reduced-motion`,
  `aria-live`, modo proyector y «Reto del día» con semilla por fecha.
  Verificación en dos capas: **barrido jsc de 560.000 rondas
  (10,66 millones de comprobaciones, 0 fallos)** — batallas recontadas
  con un sumador independiente, tubos y plantas siempre dentro de la
  torre, bonus exactos (divisiones enteras no triviales) con 3 opciones
  sin repetidos ni dobles correctas, jefes bien formados, `scoreAnswer`/
  `scoreBonus` contrastados con 17 casos frontera a mano, niveles
  monótonos 1-6 y reto del día reproducible con la misma semilla y
  distinto entre fechas — y **partida completa por DOM** (5 rondas en
  52 s con animaciones desactivadas por su propia opción): medalla de
  oro, 13 puntos que cuadran con el desglose, «casi» deliberado con
  tolerancia, tubo averiado resuelto, jefe derrotado e insignias
  Fontanero/Mata-jefes/Partida redonda; móvil de 375 px sin desbordes.
  Cartucho en la estantería de 1.º ESO (color de curso verde, sin
  «Aprende esto en…»: no hay apuntes de ESO publicados). Los cuatro
  «Jugar» responden 200. Pendiente: revisión visual del profesor.

- **2026-08-05 (noche, neón animado y cartuchos):** dos peticiones más del
  profesor sobre la portada, aplicadas y verificadas (escritorio y
  375 px). (1) **El neón de ARCADEMIA ahora tiene efectos que rotan**: el
  SVG lleva un grupo `<g class="letra" style="--i: n">` por letra y un
  guion mínimo de JavaScript propio (sin dependencias; la cabecera de
  `index.html` lo documenta) alterna cada 9 s entre tres efectos CSS:
  `efecto-persecucion` (las letras se encienden en secuencia, con
  `animation-delay: calc(var(--i) * …)`), `efecto-destello` (parpadeos
  irregulares de tubo de neón) y `efecto-latido` (pulso suave). Con
  `prefers-reduced-motion` el letrero queda encendido fijo y el guion ni
  siquiera programa la rotación. (2) **Los cartuchos desentonaban con su
  etiqueta clara** (señalado por el profesor con captura): rediseñados en
  oscuro (etiqueta #131843 con franja superior del color del curso,
  título en ámbar monoespaciado en mayúsculas, chips translúcidos con
  neón del curso), **más compactos** (max-width 19rem) y **sin el enlace
  «Aprende esto en…»**, que ahora vive únicamente en el pie de cada
  juego. Los tres «Jugar» siguen respondiendo 200 y no queda ningún
  `.aprende-en` en la portada.

- **2026-08-05 (noche, tema retro de los juegos):** por orden del profesor,
  las tres páginas de juego visten ahora la estética del salón, en dos
  hojas ensambladas dentro de cada HTML: un **cromo compartido** (fondo
  nocturno con cielo estrellado de píxeles, orla de bombillas bajo la
  cabecera, aviso de carga y pie re-tematizados) para los tres juegos, y
  una **re-tematización del mueble** solo para Grimorio y Órbita Gauss
  (los Guardianes ya eran retro por diseño): panel oscuro con borde ámbar
  y título monoespaciado en ámbar —calcando `.guardianes-juego`—, botones
  estilo recreativa (plástico oscuro con rótulo ámbar que se enciende en
  ámbar con texto oscuro al pasar o enfocar, como el «Jugar» de la
  portada), fórmulas como pantallas encendidas (fondo #0a0e24, math casi
  blanco: KaTeX hereda `currentColor`), selects/inputs oscuros, chips en
  neón (verde/rojo para pasa/no-pasa) y cartas del Grimorio en plástico
  oscuro con selección violeta y peligrosas en rojo. Los **chips activos
  con estilo en línea** (cámaras del Grimorio y misiones de Órbita Gauss,
  herencia del arreglo de contraste de mat1 pensado para fondo claro) se
  reencienden con `!important` — solo tema, cero cambios de lógica.
  Verificado en los tres: montaje, 0 errores KaTeX, interacción básica
  (carta jugada y Juicio con chips legibles; panel de transformación con
  contrastes comprobados por estilo computado), 375 px sin desbordes.
  Cuidado aprendido: tras reescribir un HTML servido, el navegador del
  panel puede renderizar la versión en caché aunque `curl` sirva la
  nueva; se comprueba con `hayTemaRetro` en el DOM y se recarga con un
  parámetro rompe-caché (`?v=...`). **Pendiente de la revisión visual del
  profesor.**

- **2026-08-05 (noche, cierre):** dos encargos del profesor completados.
  (1) **Marquesina bicolor y mejoras retro** de la portada: «ARCADE» en
  cian neón (`--neon-cian`, #38e0f0) y «MIA» en ámbar, cada grupo del SVG
  con su propio halo, para que se aprecie el juego de palabras
  ARCADE+ACADEMIA; además, scanlines CRT sobre la marquesina
  (`.lineas-crt`), parpadeo clásico del «insert coin» (`steps`, apagado
  con `prefers-reduced-motion` por la regla global) y cielo estrellado de
  píxeles en `body::before`. Verificada de nuevo en escritorio y 375 px.
  (2) **Órbita Gauss migrado y verificado**
  (`juegos/bachillerato-1/orbita-gauss.html`, 1650 líneas): necesita dos
  ayudas compartidas más de `shell.html` (`monomioTex` y
  `filaEcuacionCeldasTex`, sin `$$`), y las clases comunes que ya traía
  la base del Grimorio. Verificación: **barrido jsc de 90.951
  comprobaciones, 0 fallos** (5000 recortes plano-cubo con convexidad
  del orden angular, 3000 pares de planos contrastados con una
  resolución paramétrica independiente, 1000 cámaras sin puntos tras el
  foco, 1687 haces conteniendo su bisagra, y las 4 misiones validadas
  por rangos con un Gauss propio, soluciones dentro del cubo);
  **partida completa por DOM de las cuatro misiones**: escalonado
  eligiendo coeficientes por fuerza bruta sobre los `<select>`
  permitidos, clasificación SCD/SCI/SI decidida por álgebra propia,
  puntos (1, −2, 3) y (2, 1, −1) tecleados y encendidos, clasificación
  errónea deliberada en la misión 4 con su aviso de reintento, récords
  de pasos (3 y 3, el mínimo) en `localStorage`, botones de cámara
  probados, 0 errores KaTeX y 375 px sin desbordes. Cartucho añadido:
  los tres «Jugar» de la portada responden 200. Cuidado aprendido: al
  leer estado por la fibra de React con `createRoot`, el contenedor
  puede apuntar al árbol viejo; el vigente es
  `contenedor[__reactContainer$].stateNode.current` (leer el alternate
  da estado obsoleto y desorienta al conductor). **Los tres juegos
  quedan pendientes de la aprobación del profesor.**

- **2026-08-05 (noche):** migrados y verificados **Los Guardianes de ℝ**
  (`juegos/bachillerato-1/guardianes-de-r.html`, 3901 líneas), adelantados
  a Órbita Gauss por decisión del profesor. Verificación en dos capas:
  **barrido jsc** de los 39 generadores (los 32 del torneo más los 7
  especiales del jefe): 974.000 preguntas, 1,21 millones de comparaciones
  numéricas con un intérprete de TeX independiente (con autoprueba) y
  **0 fallos**; el barrido reconoce como deliberadas las «trampas de
  forma» de los dos generadores de notación científica (distractor de
  igual valor con la mantisa fuera de [1, 10), que es justo lo que evalúa
  el enunciado; 50.393 admitidas y documentadas). **Partida completa por
  DOM**: victoria total (6 guardianes + Áleph, 5125 puntos, 23 aciertos,
  1 fallo deliberado con contraataque, mejor racha 20, récord en
  `localStorage`), duelo por equipos con turnos alternando y marcador,
  0 errores KaTeX, consola limpia y 375 px sin desbordes en portada del
  juego, mapa y combate. Cartucho añadido a la portada (delante del
  Grimorio, por orden de unidad; ambos «Jugar» responden 200).
  **Tres cuidados aprendidos de migración** (los dos primeros los cazó el
  barrido, el tercero Babel): (1) el juego usaba ayudas compartidas de
  intervalos (`notacionIntervalo`, `unionIntervalos`,
  `interseccionIntervalos`, `contieneExtremo`, `formatearExtremo`)
  definidas fuera de su bloque en `shell.html`: hay que llevarlas con cada
  juego que las use; (2) esas ayudas contienen `$$` (escape de Pandoc):
  al migrar a un HTML sin Pandoc se des-escapan a `$`, o los intervalos
  salen con dólares espurios; (3) al cortar por números de línea es fácil
  dejarse la llave de cierre del componente: compilar cada tramo con el
  Babel de la propia página localiza el tramo roto al instante.
  Pendiente: aprobación del profesor de los dos juegos migrados; después,
  Órbita Gauss.

- **2026-08-05 (tarde, portada):** el profesor **aprobó el plan de la
  portada** y delegó el destino del enlace de la unidad 2 («como tú mejor
  veas»): decisión aplicada, el enlace apunta al portal de `mat1` hasta que
  la unidad 2 tenga página pública (así nunca hay un 404); cuando se
  publique `unidad_02_algebra.html`, actualizar el cartucho del Grimorio y
  el pie del propio juego. `index.html` escrita y verificada (detalle en
  Pendientes 2). Capturas profundas del panel: también fallan aquí con
  desplazamiento largo; truco usado: ocultar temporalmente secciones por
  JavaScript de inspección para fotografiar lo de abajo y recargar después.
  Sigue pendiente la aprobación del piloto por el profesor antes de migrar
  «Órbita Gauss».

- **2026-08-05 (tarde):** piloto completado: el Grimorio migrado a su HTML
  autocontenido y verificado (jsc 19/19 con 0 fallos y partida completa en
  navegador con 10/10; detalle en Pendientes 1). Los enlaces «Aprende esto
  en…» de la unidad 2 apuntan de momento al portal de `mat1` porque esa
  unidad aún no tiene página pública; decidir destino definitivo con el
  profesor. Plan de la portada presentado al profesor; `index.html` no se
  escribe hasta su aprobación.

- **2026-08-05:** creación del proyecto: esqueleto de carpetas, `AGENTS.md`
  con las reglas adaptadas de `mat1` y este relevo. Comienza la migración
  del piloto (Grimorio).
