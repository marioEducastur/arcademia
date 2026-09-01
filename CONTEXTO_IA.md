# Contexto compartido para cualquier IA

Última actualización: **2026-09-01**

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
| El Grimorio de las Transformaciones | 1.º Bach. | Ecuaciones (unidad 2, Álgebra) | `GrimorioInteractivo`, `gmConstruirSala`, `GM_PARAMETROS`, `GM_NOMBRES`, `gmMas`, `gmTerminoX`, CSS `.gm-` | **Publicado** |
| Órbita Gauss: el observatorio de los tres planos | 1.º Bach. | Sistemas de ecuaciones (unidad 2, Álgebra) | `OrbitaGaussInteractivo`, funciones `og*`, CSS `.og-` | **Publicado** |
| Los Guardianes de ℝ | 1.º Bach. | Números reales (unidad 1) | `GuardianesRealesInteractivo`, generadores `grGen*`, CSS `.gr-` | **Publicado** |
| La Torre de los Enteros | 1.º ESO | Números enteros | Aportado por el profesor (no procede de mat1) | **Publicado** |
| f(x) SKATE | 4.º ESO y 1.º Bach. | Funciones (familias, gráficas, pendiente) | Aportado por el profesor (no procede de mat1) | **Publicado** |
| Parabólica | 4.º ESO | Función cuadrática (tres formas) | Aportado por el profesor (no procede de mat1) | **Publicado** |

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

1. En sesiones de `mat1`, cuando el profesor lo ordene: retirar los juegos
   de `shell.html` y enlazar las unidades con tarjetas-cartucho. **Desde
   Arcademia, `mat1` no se toca.**
2. Decidir con el profesor si el **modo libre de Parabólica** permite
   lanzar con a > 0: hoy su pista invita a «poner a positiva y mirar
   hacia dónde se va el búho», pero `valida()` lo bloquea con un aviso y
   el búho nunca vuela (cambio pequeño si lo quiere).
3. «Aprende esto en…»: añadirlo a la Torre, f(x) SKATE y Parabólica cuando
   se publiquen las unidades de apuntes correspondientes; el pie del
   Grimorio pasará del portal a `unidad_02_algebra.html` cuando exista.
4. Respaldo en Drive: la última instantánea es del 6 de agosto de 2026;
   hacer una nueva cuando el profesor lo ordene.

## Registro breve

- **2026-09-01 (publicación de Funciones):** por orden expresa del
  profesor («ok, haz commit/push»): **commit `aa10655`** con las tres
  tandas pendientes (portada por áreas con filtro por curso, f(x) SKATE
  y Parabólica) y push a `origin/main`; `pages-build-deployment` en
  verde y las **siete páginas con 200 en producción** (portada y seis
  juegos), con «Parabólica» comprobado en la portada publicada. Como en
  el precedente del 6 de agosto, la publicación da por buena de facto la
  revisión visual pendiente; cualquier retoque posterior seguirá el
  ciclo normal. Sin instantánea nueva en Drive (no se ha ordenado; queda
  en Pendientes). Este registro entra en un segundo commit inmediato
  para que el repo quede al día.

- **2026-09-01 (Parabólica, 4.º ESO; SIN COMMIT, pendiente de orden):**
  tercer juego aportado por el profesor (canvas y WebAudio nativos, cero
  dependencias, coma decimal ya de serie), integrado en
  `juegos/eso-4/parabolica.html`. Es un «Angry Birds» donde el tirachinas
  se sustituye por **escribir la parábola**: cada forma tiene su misión
  (factorizada → la raíz cae sobre el enemigo; vértice → altura justa
  entre muro y techo; general → sistema 2×2 desde dos aros) y la «regla
  de oro» y(0) = 0 ata un parámetro y obliga a despejar. **Nivel: 4.º ESO
  con chip único** (su propio pie ya lo decía); los tres primeros niveles
  serían asequibles en 3.º, pero vértice, general y el sistema son de
  4.º. Sin «Aprende esto en…» (la unidad de funciones no está publicada).
  Retoques del precedente Torre/SKATE: cabecera con curso/tema/origen,
  `lang="es-ES"`, viewport sin bloqueo de zoom, botón «← Arcademia» como
  cuarto icobtn (con `flex-wrap` en la barra superior: a 375 px la
  botonera envuelve bajo el título) más enlace en el pie del panel de
  niveles, ARIA (`aria-live` en el aviso, labels en icobtns,
  `role="dialog"` + `aria-labelledby` en paneles) y sacudida de cámara
  quieta con `prefers-reduced-motion`. **Cuatro arreglos reales**:
  (1) los atajos globales Enter/Espacio robaban la activación de botones
  y enlaces (Enter sobre «Boceto» lanzaba el búho) — ahora se excluyen
  BUTTON y A; (2) el «Ajustar» de la forma de vértice con h = 0 proponía
  a = −k/10⁻⁹ (absurdo y sin salida) — ahora propone k = 0; (3) un búho
  con impulso negativo «curaba» bloques (daño negativo) — recortado a 0;
  (4) **la plataforma del nivel 8 pasa de `fila()` a `techo()`**: 3 de
  sus 6 tablas nacían sin apoyo según la regla de soporte del motor y el
  castillo se derrumbaba solo al primer disparo, invalidando la pista del
  vértice que el propio nivel enseña; fija, el nivel se comporta como su
  enunciado. Verificación en dos capas: **barrido jsc de 91.277
  comprobaciones, 0 fallos** (equivalencia de las tres formas contra un
  evaluador independiente en 50.000 puntos; tabla de verdad de `valida()`
  en 11.271 casos con re-comprobación de cada «Ajustar»; coherencia de
  las 8 pistas con geometría propia — el umbral 0,09 del muro cuadra al
  milímetro contando el radio del búho; partidas motorizadas de los 8
  niveles con estrellas 1/2/3, regla de mejora del récord y derrota; y
  2.400 vuelos aleatorios de modo libre que siempre terminan; el doblete
  de 3 estrellas del asedio existe con a ∈ [−0,087; −0,109], p. ej.
  −0,1) y **partida por DOM** (niveles 1, 4 y 6 tecleando comas
  decimales, victorias 3★ con récord en `localStorage`, aros marcados,
  avisos de a > 0 y de h = 0 con su «Ajustar», exclusión de teclado
  comprobada, boceto/sonido/ejes, consola limpia y 375 px sin
  desbordes). Cuidado aprendido del conductor: al reinyectar el juego con
  `requestAnimationFrame` intervenido para avanzar la física a mano, la
  instancia vieja también cae en la bomba y sigue escribiendo sus
  contadores en el DOM — hay que vaciar la cola de callbacks y clonar el
  subárbol para desarmarla. Portada: cartucho «Parabólica» (chip 4.º ESO,
  tema Función cuadrática) delante de f(x) SKATE en Funciones; filtros
  reverificados (4.º ESO → 2, 1.º Bach. → 4, 3.º ESO → 0, Todos → 6) y
  los seis «Jugar» con 200. Nota para el profesor: en modo libre la pista
  invita a «poner a positiva y mirar hacia dónde se va el búho», pero
  `valida()` lo bloquea con un aviso y el búho nunca vuela; decidir si en
  libre se permite lanzar cualquier parábola. **Pendiente: revisión
  visual del profesor y orden expresa de commit/push.**

- **2026-09-01 (f(x) SKATE, 4.º ESO y 1.º Bach.; SIN COMMIT, pendiente de
  orden):** segundo juego aportado por el profesor (prototipo «v7», canvas
  y WebAudio nativos, sin React ni KaTeX), integrado en
  `juegos/eso-4/fx-skate.html` siguiendo el precedente de la Torre.
  **Análisis de nivel**: el modo fácil (fórmula + gráfica, rectas y
  parábolas de inicio) es jugable desde 4.º ESO; los senos A·sen(Bx) a los
  120 m, las cúbicas a los 250 m, el modo PRO (imaginar la gráfica desde
  los coeficientes) y la lectura de la pendiente instantánea del HUD son
  contenido pleno de 1.º de Bachillerato — de ahí los chips multinivel
  «4.º ESO» + «1.º Bach.» en su cartucho de la estantería Funciones (sin
  «Aprende esto en…»: la unidad de funciones de mat1 no está publicada).
  Retoques respecto al prototipo: cabecera con curso/tema/origen,
  `lang="es-ES"`, botón «← Arcademia» en su propio estilo, **webfonts de
  Google sustituidas por pilas del sistema** (regla 2; si el profesor
  quiere Bungee/Space Grotesk exactas se incrustarían como data URI, como
  la Baloo 2 de la Torre), viewport sin bloqueo de zoom, ARIA
  (`aria-live` en avisos, cartas `role="button"` + Espacio, diálogo de
  lección con foco al abrir, vidas con `aria-label`), y **un arreglo
  real: centrado seguro de `.screen`** (con `justify-content:center` el
  título quedaba inalcanzable en 375 px; ahora márgenes automáticos en
  los extremos). Verificación en dos capas: **barrido jsc de 3,39
  millones de comprobaciones, 0 fallos** (25 200 segmentos + 9720 cartas;
  un parser independiente reconstruye la f desde la fórmula MOSTRADA y
  la contrasta con la pista — el contrato «lo que lees es lo que
  patinas» — más derivadas por diferencias finitas, monedas en extremos
  verdaderos, desbloqueos por familia, y «siempre una carta viable»:
  3240/3240 atravesables con un integrador propio incluso entrando a
  0,75·v; documentado que las parábolas pueden entrar con pendiente
  hasta ±2,2 por diseño — la viabilidad se filtra por energía) y
  **partida por DOM** con conductor honesto que lee solo fórmulas y
  velocidad del DOM: 1333 m, 2 muertes legítimas con lección
  matemáticamente coherente (v²/2g cuadra), desbloqueos clavados a 120 y
  250 m, marcador exacto (base y PRO ×1,5), 3 fallos → FIN con récord,
  consola limpia y 375 px sin desbordes (menú, cartas 2+1 y lección).
  Cuidados aprendidos: con el panel del navegador **oculto** el
  `requestAnimationFrame` se congela — para seguir verificando se avanza
  la física a mano en bloques síncronos (`physics(1/60)` en bucle) y se
  mide después; y los clics por coordenadas del panel oculto se atascan
  (usar `.click()` sintético). Filtros de la portada reverificados
  (4.º ESO → 1, 1.º Bach. → 4, Todos restaura) y los seis enlaces con
  200. **Pendiente: revisión visual del profesor y orden expresa de
  commit/push.**

- **2026-08-06 (portada por áreas; SIN COMMIT, pendiente de orden):**
  decisión del profesor tras debatirlo: la portada se organiza por
  **áreas matemáticas** en vez de por curso — cinco estanterías
  (Números, Álgebra, Geometría, Funciones, Estadística y probabilidad),
  cada una con su color de franja (`--area-*`) — y los cartuchos llevan
  **chips de curso múltiples** para juegos multinivel (la Torre luce
  «1.º ESO» y «2.º ESO»; familias `es-eso` verde / `es-bach` violeta) y
  `data-cursos` para el filtro. Nueva **botonera «Nivel»** sobre las
  estanterías (Todos + 6 cursos, `aria-pressed`, estilo recreativa):
  al elegir curso se atenúan los cartuchos que no encajan (sin
  ocultarlos, para que se vea lo que espera más adelante) y una línea
  `role="status"` canta el resultado («3 juegos para 1.º de
  Bachillerato», «0 juegos para 3.º ESO (de momento)»). Dentro de cada
  área, los juegos van de curso menor a mayor. Los archivos de
  `juegos/<nivel>/` no se mueven: solo cambia el salón. También se
  registró que el profesor activó el **Control remoto desde la propia
  interfaz de la app de escritorio** (conmutador con URL; el comando
  `/remote-control` escrito en el chat no abre panel ahí). Verificado:
  filtros correctos en los cuatro casos (1.º ESO → 1, 1.º Bach. → 3,
  3.º ESO → 0, Todos restaura), enlaces 200, escritorio y 375 px sin
  desbordes. **Pendiente de la orden expresa de commit/push.**

- **2026-08-06 (publicación de las mejoras del Grimorio):** por orden
  expresa del profesor («Hac commit y push después de corregir eso»),
  tras el último retoque: **la columna del mazo reserva solo la altura
  que necesita** (mín. 14,2 rem con la pila vacía y `minHeight` en línea
  que suma 1,7 rem por carta apilada extra), con lo que el marcador
  luminoso sube y desaparece el hueco muerto que señaló el profesor
  (tablero: de ~298 px a 227 px con el mazo vacío; verificado también el
  crecimiento a 2 cartas, 0 errores KaTeX y 375 px sin desbordes). Con
  este commit viajan las **cuatro tandas pendientes** de las entradas
  anteriores: naipes con arte, mesa de destilación + marcador, juego a
  ciegas + mazo, y clic directo + manos barajadas + pozo de trampas +
  exponente real. Las entradas siguientes marcadas «SIN COMMIT» quedan
  publicadas con este empuje.

- **2026-08-06 (clic directo, manos barajadas y mazo a tamaño real; SIN
  COMMIT, pendiente de orden):** cuarta tanda de peticiones del profesor
  sobre el Grimorio, la primera que toca jugabilidad de verdad:
  (1) **jugar al pulsar** — desaparece el panel de confirmación
  («Jugar la carta»/«Devolverla»); `jugarCarta(carta, indice)` se llama
  desde el clic del naipe, si acierta avanza y si no, tropiezo con su
  lección; (2) **manos siempre de 3 cartas y barajadas** — nuevo pozo
  `GM_TRAMPAS_COMUNES` (5 errores clásicos universalmente ilegales, con
  lección propia y arte: tachar la x, cambiar el signo a un lado, quitar
  paréntesis sin multiplicar, sustituir x por 0, derivar) que rellena
  las manos cortas vía `gmEnriquecerSala` + `gmBarajarCartas` aplicado
  en `cargarSala` y en el estado inicial: ya no hay manos de 1 carta ni
  posiciones fijas que delaten; (3) **primera ecuación aleatoria** — el
  estado inicial elige variante al azar (antes siempre `x(x+1)=6`);
  (4) **naipes del mazo al mismo tamaño y ratio que los de la mano**
  (160×195 de contenido); (5) **«Cambio z = 3^x» se muestra con
  exponente real** vía `GmNombreCarta` (el dato interno no cambia).
  Verificación: barrido jsc nuevo de manos enriquecidas (38.000 salas,
  610.001 comprobaciones, 0 fallos: 3 cartas únicas por mano, una sola
  que avanza, extras siempre trampa con lección, y el barajado varía la
  primera carta en las 19 variantes) y partida a ciegas completa
  (10/10 juicios, 76 puntos, primera ecuación distinta de la fija,
  exponente renderizado, 0 errores KaTeX, 375 px sin desbordes).
  Cuidado aprendido: con el panel del navegador **oculto**
  (`visibilityState: hidden`) las animaciones CSS se congelan en su
  fotograma inicial y `getBoundingClientRect` mide el vuelo, no el
  reposo: para medir geometría, desactivar la animación o dar por bueno
  el estado sin animación. **Sigue pendiente la orden expresa de
  commit/push** (naipes + mesa/marcador + mazo a ciegas + esta tanda).

- **2026-08-06 (juego a ciegas y mazo; SIN COMMIT, pendiente de orden):**
  tercera petición del profesor sobre el Grimorio, y esta sí cambia la
  experiencia de juego (no la matemática): (1) **el panel de selección
  ya no delata nada** — antes las trampas mostraban «no parece encajar»
  y solo las cartas buenas enseñaban previsualización, una doble pista;
  ahora todas las cartas muestran el mismo texto neutro y **no hay
  previsualización antes de jugar**: se juega a ciegas, el tropiezo
  ocurre, y la explicación de por qué no encajaba llega después con el
  «La carta rebota: …» de siempre; (2) **mazo de jugadas** a la derecha
  de la mano (`.gm-tablero` = mano + `.gm-mazo`): las cartas jugadas
  vuelan con una animación de vuelo y giro y quedan apiladas ladeadas
  con su arte y su nombre, con hueco punteado cuando está vacío.
  Truco de implementación: el mazo se **deriva sin estado nuevo**
  (`cartasJugadas` a partir de `pasoIdx`), porque el barrido jsc
  garantizó que el camino de cada cámara es único y consecutivo; la
  animación de entrada la dispara el montaje de cada carta nueva.
  Verificado con una **partida honesta a ciegas** (probando cartas como
  un alumno, sin leer pistas del DOM): 10/10 juicios, 98 puntos con
  1 tropiezo, mazo llegando a 3 cartas, lección visible tras el
  tropiezo, contador rojo subiendo en vivo, récord anterior (100)
  conservado, 0 errores KaTeX y 375 px sin desbordes. Nota: el conductor
  de partidas antiguo identificaba trampas por el texto del panel; ya no
  existe — los conductores futuros deben jugar a ciegas o leer la fibra.
  **Sigue pendiente la orden expresa de commit/push** (naipes + mesa y
  marcador + esto).

- **2026-08-06 (mesa y marcador del Grimorio; SIN COMMIT, pendiente de
  orden):** segunda petición estética del profesor sobre el Grimorio,
  también solo capa de vista: (1) la ecuación en curso vive ahora en la
  **«Mesa de destilación»** (`.gm-mesa`): atril con borde degradado de
  neón violeta-cian-ámbar animado y pulso de halo (quietos con
  `prefers-reduced-motion` por la regla global), rótulo en píldora y la
  fórmula en grande sobre pantalla encendida; (2) la nota de texto de
  jugadas se sustituye por un **marcador luminoso** (`.gm-marcador`) de
  tres celdas LED — jugadas·par en ámbar, tropiezos en rojo, espectros
  en violeta, ceros barrados monoespaciados — cuyas cifras dan un
  destello al cambiar (remontaje por `key` + animación). El resumen de
  la cámara sellada conserva su texto original. Verificado: partida
  completa 10/10 (98 puntos) con el contador de tropiezos visto pasar de
  0/0/0 a 0/1/0 en vivo, 0 errores KaTeX, 375 px sin desbordes.
  **Sigue pendiente la orden expresa de commit/push** (junto con los
  naipes de la entrada anterior).

- **2026-08-06 (naipes del Grimorio; SIN COMMIT, pendiente de orden):** a
  petición del profesor, las cartas del Grimorio son ahora naipes de
  verdad: cuerpo de carta con marco interior dorado y esquinas ✦,
  ventana de arte con un **pictograma matemático por transformación**
  (mapa `GM_ARTE` + `gmArteDeCarta`, dibujado con KaTeX y `aria-hidden`;
  depende SOLO del nombre para no delatar las trampas), banda inferior
  con el nombre, abanico sutil en la mano (se endereza con foco o
  selección) y las peligrosas selladas con **⚠ además del borde rojo**
  (el color deja de ser la única señal; la instrucción del juego se
  actualizó igual). Cambios solo de vista: constructores y lógica
  intactos. Los parches se aplicaron in situ sobre el HTML ensamblado
  (los intermedios del scratchpad no sobreviven entre sesiones; el
  archivo del proyecto es la fuente de verdad). Incidencia y lección: un
  `cat` con las piezas ya inexistentes truncó el HTML por la
  redirección; se restauró íntegro con `git checkout --` — primer
  rescate gracias al repo. Verificado: partida completa 10/10 con 100
  puntos, 33 artes dibujadas, 3 peligrosas con sello, 0 errores KaTeX y
  375 px sin desbordes. **Falta la orden expresa de commit/push para
  llevarlo a producción.**

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
