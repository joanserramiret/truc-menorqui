# DISEÑO DEL JUEGO — Decisiones

## Dirección de arte: viñeta de prensa menorquina

Referencia de ambiente: el humor gráfico de Zaca (Es Diari) — inspiración de estilo, sin copiar dibujos concretos.

- **Tinta sobre papel**: fondo crema "papel de diari" con grano, línea negra a plumilla.
- **Trazo a mano**: filtro SVG de turbulencia (feTurbulence + feDisplacementMap) que hace temblar la línea.
- **Caricatura**: narices grandes y bulbosas, ojos de puntito, orejas salidas, tramas de rayitas para sombrear.
- **Personajes**: en Toni (socarrón: capell ample, mostacho, ceja espesa), en Biel (despistado: gorra, orejas grandes, ojos de plato), na Maria (que las mata callando: moño, sonrisa pícara, cruz de oro).
- **Bocadillos**: contorno irregular "a mano", texto en MAYÚSCULAS con exclamaciones.
- **Color selectivo**: paleta apagada de tinta (rojo teja, ocre, verde botella) sobre grises/sepias; las cartas se mantienen blancas y legibles.

## Baraja con imágenes reales (jun 2026)

- Las cartas usan recortes de la baraja clásica de **Wikimedia Commons** (autor: Basquetteur, licencia **CC BY-SA 3.0** — atribución visible en la pantalla de inicio). 30 cartas en webp embebidas en `cartas_data.js`, que debe estar junto al HTML.
- Si falta `cartas_data.js`, el juego usa como respaldo las cartas SVG dibujadas.
- La baraja Fournier que pasó Joan como referencia no se usa por copyright y baja resolución.

## Baraja española clásica SVG — respaldo (jun 2026)

- Cartas estilo Fournier: marco interior naranja, índice en las esquinas (número + pinta pequeña, también invertido abajo-derecha), pintas colocadas en disposición tradicional (el as grande, el 7 en 2-1-2-2...).
- Figuras dibujadas: **l'amo** = caballo de bastos (jinete con capell y basto en alto); **sa madona** = sota de oros (figura con cofia sosteniendo el oro). Banda roja inferior con el nombre de la pieza.
- Palos clásicos: oros (moneda dorada), copas (cáliz dorado/rojo), espadas (azuladas), bastos (verdes).

## Escenario: bar menorquín con vista a cala

- Fondo SVG a capas detrás de la mesa: vigas de madera, ventana en arco con la cala (sol, acantilados blancos con pinos, mar turquesa, llaüt con franja roja, gaviotas), estantería de botellas (gin, vino, hierbas), sobrasadas y queso colgados, guitarra apoyada, barril de vino.
- Personajes grandes (avatares ~110 px) asomando sobre la mesa.

## Mecánica de señas: "El Flash" ⚡

Sustituye a las señas presenciales del truc real (imposibles de simular en móvil).

**Decisión (jun 2026):**

- El **compañero decide** cuándo enseñar sus cartas, pulsando un botón **"Fer senya"**.
- Al pulsarlo, el otro jugador de la pareja ve las cartas del compañero como un **flash de ~400 ms** — visible pero sin tiempo de leerlo con calma ("coño, ¿qué he visto?").
- **Límite: 1 flash por mano** y por jugador.
- Las cartas en el flash deben renderizarse grandes y claras (el límite es el tiempo, no la legibilidad).

**Parámetros ajustables en testing:**

- Duración del flash (rango a probar: 300–500 ms).
- Posible variante futura: probabilidad de que los rivales "intercepten" la seña (aviso "los rivales sospechan"), para recuperar el riesgo del juego real. NO en v1.

## Configuración de partida

- Antes de iniciar: elegir **con doses o sin doses** (30 o 26 cartas). Ver REGLAS_TRUC_MENORQUI.md §2.
- Variantes locales (llevant/ponent, empates tras baza parda) como opciones configurables; por defecto, versión INJOVE.
