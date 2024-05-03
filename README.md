# TP2 de Programación de Video Juegos 2: UnitInvaders

## Metodología

Integrantes por equipo: 1

Se aprueba con:             6

### Objetivos

- Que se acostumbren a usar Unity
- Que aprendan a adaptar la lógica del juego para que se vea mas lindo en Unity
- Mejorar lo que ya saben de C#
- Diseñar un flujo de juego junto a sus ventanas

### Comentarios Adicionales

Tengan en cuenta que en varios de estos ejercicios espero que apliquen los conceptos que vimos en clase como encapsulamiento y polimorfismo. Puede que igual se los de por correctos a los ejercicios donde podrían haberlo usado y no lo hicieron, pero me van a tener que justificar porque no usaron esa solución y se fueron por otro lado.

Pueden asumir cosas que no están aclaradas explícitamente. Si igualmente tienen dudas, pregunten.

Recuerden que, por lo general, la solución más simple es la mejor.

----

## Entrega

### Código

Todo lo van a resolver en un repositorio de GitHub.

La fecha límite es el Jueves 23 de Mayo de 2024 a las 23:59 hs. Antes de ese horario me tienen que mandar el link del repo por mail a <me@diegofreijo.com>.

Tiene que haber una `tag` que se llame `tp2`. Ese commit es el que voy a corregir.

Si crearon branches por feature o por ejercicio, no los borren. Así puedo ver cómo estuvieron trabajando.

### Defensa

Les voy a estar mandando horarios para que cada uno se conecte y tengamos la devolución por Google Meet.

----

## UnitInvaders

Vamos a adaptar el juego del TP1 para que se vea con gráficos lindos usando Unity! Además vamos a agregar ventanas y un flujo de juego entero: desde que arranca el juego hasta que se cierra, dándole la posibilidad al jugador de jugar tantas partidas como quiera.

Recuerden que el 20% de los millones que ganen en Steam tiene que ir para el profe. Es para financiar los chocolates de Mendoza.

### 1. Adaptación desde Sharp Invaders (4 puntos)

Primero queremos adaptar lo que ya teníamos programado en C#. Esto incluye los 4 puntos del TP1. Algunas consideraciones:

#### Código existente

Van a ver que mucho código que maneja los datos y lógica del juego lo van a poder reutilizar. O al menos van a poder si hicieron un buen diseño como los que vimos en clase. En cambio, las funciones que se encargan de dibujar la vista o de escuchar input ya no nos sirven. Todo eso lo vamos a reemplazar por las funcionalidades que nos da Unity.

#### Sprites y Tiles

Son libres de usar los gráficos que quieran. Pueden dibujarlos ustedes mismos también si así lo desean. Aplica tanto para los gráficos del mapa, jugador y enemigos como para los de la interfaz grafica. 

Recuerden que en este TP solo evalúo la funcionalidad, así que prefiero un juego horrible que funcione antes que uno hermoso que no haga nada. 

Hay muchos packs gratuitos de gráficos 2D que les puede servir. No estoy poniendo ninguno de ejemplo a propósito, para que vayan a investigar por su cuenta. Recuerden que pueden googlear, usar ChatGPT o hasta comprar assets si así lo desean. Si están trabados, pregunten.

#### Mapa y Enemigos

Esta vez **no vamos a hacer el mapa dinámico**. Quiero que usen el editor de Unity para armar el nivel a mano. Así que el tamaño va a ser fijo. 

Los enemigos tampoco van a ser dinámicos. Va a haber una cantidad fija de enemigos desparramados en una cantidad fija de filas. O sea que van a arrancar en una posición inicial ya pre-establecida por ustedes en la escena que armen a mano. Traten igual de que respete mas o menos la distribución del TP1: que haya un espacio entre cada enemigo, que las filas estén desfazadas, etc. 

Son libres de elegir el tamaño del mapa y la cantidad de enemigos. Usen su intuición para elegir buenos números. Pero recuerden que tampoco estoy evaluando game design en este TP.

#### Jugador y Misiles

Claramente el jugador ya no se va a mover ni disparar como en el TP1 usando `Console.ReadKey`. Ahora van a tener que usar el Input System de Unity. Me da lo mismo si usan la notificación por mensajes o eventos, usen el que gusten.

### Misiles de enemigos (2 puntos)

Cada enemigo va a disparar un misil hacia abajo cada cierta cantidad de tiempo. Esa cantidad va a ser elegida al azar entre cada disparo. No hay friendly fire: los misiles de los enemigos deben atravesar a los demás enemigos.

Si un misil toca al jugador, el jugador pierde.

### GUI (4 puntos)

Vamos a agregarle interfaz grafica al juego. No se maten en el diseño de cada ventana, la mayoría van a ser solo unos botones desparramados por ahi. Recuerden que no evalúo que se vea lindo!

Los elementos de la UI que vamos a necesitar son:

- Ventana de inicio que tiene:
	- botón para empezar a jugar
	- botón para cerrar el juego
- Ventana de juego perdido que tiene:
	- botón para volver a jugar una partida
	- botón para volver al menú principal
- Ventaja de juego ganado que tiene:
	- botón para volver a jugar una partida
	- botón para volver al menú principal
- HUD: vamos a agregar elementos a la UI del juego mientras se esta jugando. Por ahora no tenemos puntaje ni vidas ni nada de eso, asi que solamente vamos a mostrar la cantidad de enemigos que faltan destruir.
