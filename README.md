/*
README.md — Tono senoidal usando I2S con ESP32
==============================================

🎯 Descripción
--------------
Este proyecto genera una señal de audio continua mediante el periférico I2S del ESP32. Se utiliza para enviar una onda senoidal (440 Hz) a través de los pines configurados para I2S, útil para pruebas de audio digital o como oscilador simple.

🔧 Detalles técnicos
--------------------
- Muestra de 16 bits
- Canal estéreo (misma señal en L y R)
- Frecuencia de muestreo: 44100 Hz
- Frecuencia del tono: 440 Hz (nota La estándar)
- Amplitud: 30000 (valor en 16 bits con signo)
- DMA usa buffers circulares

📌 Pines I2S en uso
-------------------
- BCLK (GPIO 7)
- LRC / WS (GPIO 6)
- DOUT (GPIO 5)

🔄 Funcionamiento
------------------
En cada iteración del `loop()` se genera un nuevo bloque de muestras de una onda senoidal, que se transmite al DAC externo conectado al bus I2S. Esto permite una reproducción continua del tono sin pausas.

📦 Dependencias
---------------
- `driver/i2s.h`
- `math.h` (para la función `sin()`)

🧪 Comprobación
---------------
Puedes conectar un amplificador o altavoz con DAC I2S para verificar que el tono suena de forma estable. También puedes capturarlo con un osciloscopio si trabajas en laboratorio.

👤 Autor
--------
Script realizado como ejercicio para practicar el uso del periférico I2S en proyectos de audio digital con ESP32.
*/
