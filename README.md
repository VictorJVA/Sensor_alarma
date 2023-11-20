# Sensor_alarma

Este proyecto utiliza un dispositivo ESP32 junto con varios componentes electrónicos para crear un sistema de detección de objetos cercanos. El objetivo principal es monitorear la distancia medida por un sensor ultrasónico y tomar acciones específicas, como encender diferentes LEDs y activar una alarma, según la distancia detectada. Además, se proporciona una interfaz de usuario en tiempo real a través del dashboard de Arduino IoT para visualizar la distancia actual y el estado de la alarma.

## Componentes Necesarios

- **ESP32:** El microcontrolador que se encarga de gestionar la conexión WiFi y controlar los componentes.
- **Sensor Ultrasónico:** Mide la distancia entre el dispositivo y un objeto.
- **3 LEDs (Rojo, Amarillo, Verde):** Indican visualmente el nivel de riesgo según la distancia medida.
- **Resistencias:** Utilizadas para limitar la corriente y proteger los LEDs.
- **Alarma:** Un dispositivo sonoro que se activa cuando la distancia es menor a 10 unidades.
- **Conexión a WiFi:** Necesaria para el envío de datos al dashboard de Arduino IoT.

## Instalación y Configuración

1. **Conexión de Componentes:**
    - Conecte el sensor ultrasónico al ESP32 según las especificaciones del fabricante.
    - Conecte los LEDs y las resistencias de acuerdo con el esquema de conexión.

2. **Configuración del Proyecto:**
    - Clone este repositorio en su máquina local.
    - Abra el archivo de configuración (`config.h`) y ajuste las credenciales de WiFi según su red.
    
    ```c
    #define WIFI_SSID "TuSSID"
    #define WIFI_PASSWORD "TuContraseña"
    ```

    - Configure cualquier otro parámetro específico del hardware en este archivo.

3. **Instalación del IDE de Arduino:**
    - Asegúrese de tener el [Arduino IDE](https://www.arduino.cc/en/software) instalado en su sistema.

4. **Carga del Código:**
    - Abra el archivo principal (`sensor_alarma.ino`) en el Arduino IDE.
    - Seleccione el tipo de placa (ESP32) y el puerto COM correcto.
    - Cargue el código en el ESP32.

5. **Visualización en el Dashboard:**
    - Cree una cuenta en el [dashboard de Arduino IoT](https://create.arduino.cc/iot/dashboard).
    - Cree un nuevo proyecto y obtenga las credenciales necesarias.
    - Actualice el archivo `config.h` con las credenciales del dashboard.

    ```c
    #define IOT_PROJECT_ID "TuIDdeProyecto"
    #define IOT_DEVICE_ID "TuIDdeDispositivo"
    #define IOT_DEVICE_SECRET "TuSecreto"
    ```

6. **Ejecución del Proyecto:**
    - Encienda el ESP32 y observe el comportamiento de los LEDs y la alarma según la distancia medida.
    - Acceda al dashboard de Arduino IoT para visualizar la información en tiempo real.

## Funcionamiento

El sistema sigue estas reglas básicas:

- Si la distancia medida es mayor a 25 unidades, el LED verde se enciende.
- Si la distancia está entre 25 y 10 unidades, se enciende el LED amarillo.
- Si la distancia es menor a 10 unidades, se enciende el LED rojo y la alarma.

El estado actual del sistema, incluida la distancia y la activación de la alarma, se refleja en el dashboard de Arduino IoT.
