# Proyecto Integrador (Interdisciplinario) en Java: Batalla Naval

## Descripción del Proyecto
Este proyecto consiste en el desarrollo de un juego multijugador de **Batalla Naval** operado por consola (sin interfaz gráfica), implementado en **Java** bajo una arquitectura **Cliente-Servidor**. 

El objetivo principal es poner en práctica las comunicaciones en red utilizando **Sockets** y el manejo de **Hilos (concurrencia)** para administrar las conexiones y el flujo de la partida en tiempo real entre distintos procesos.

---

## Estructura del Código (`package batallanaval`)

El proyecto está organizado en las siguientes clases principales:

1. **`Barco.java`**: Modela un barco dentro del juego, almacenando su tamaño, su posición inicial (fila y columna) y su orientación (horizontal o vertical).
2. **`Tablero.java`**: Administra la matriz de $10 \times 10$ casillas, la colocación aleatoria y segura de la flota de barcos (verificando que no se encimen ni salgan de los límites), y la validación de los disparos (agua, tocado o repetido)[cite: 1].
3. **`Jugador.java`**: Representa a cada participante conectado. Utiliza un hilo independiente (`Thread`) para escuchar de forma asincrónica y continua los mensajes enviados desde el cliente sin bloquear el sistema[cite: 1].
4. **`Servidor.java`**: El núcleo de la aplicación. Espera las conexiones de dos jugadores mediante `ServerSocket`, coordina los turnos de manera estricta, procesa los disparos y detecta la condición de victoria[cite: 1].
5. **`Cliente.java`**: La interfaz de consola para cada jugador. Se conecta al servidor mediante red, recibe los avisos de estado y permite ingresar las coordenadas de ataque de forma interactiva[cite: 1].

---

## Instrucciones de Compilación y Ejecución

Asegurate de tener instalado el **JDK de Java** en tu computadora y ubícate en la carpeta raíz del proyecto (la carpeta que contiene el directorio `batallanaval`).

### 1. Compilación
Compilá todos los archivos del paquete de un solo golpe ejecutando el siguiente comando en la terminal:

```bash
javac batallanaval/*.java

