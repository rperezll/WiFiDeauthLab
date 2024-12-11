# 🛜 Entendiendo los Ataques de Desautenticación WiFi

Un ataque de desautenticación WiFi es una técnica utilizada para interrumpir la conexión entre un dispositivo y una red WiFi. Este tipo de ataque pertenece al grupo denominado *denial-of-service attack* o ataques de denegación de servicio (DoS).

## 🤔 Una red WiFi *for Dummies*

Una red WiFi permite que dispositivos de diversa índole se conecten a una misma red, habilitando el acceso a Internet. Para que esto ocurra, deben considerarse algunos elementos y principios clave:

1. Punto de acceso (AP): Es el router o dispositivo que emite la red WiFi. Piensa en el AP como el "centro" de la red.

2. Dispositivos conectados: Son los clientes, como tu teléfono, que se conectan al AP para usar Internet.

3. Comunicación constante: Los dispositivos y el AP están enviándose mensajes todo el tiempo para mantenerse conectados.

## El ataque

Un ataque de desautenticación interrumpe esta comunicación constante mediante el envío de mensajes falsificados a los dispositivos conectados o al AP, indicándoles que deben desconectarse.

Los ataques de desautenticación WiFi son una forma interesante de entender cómo funcionan las redes, pero también un recordatorio de la importancia de mantener nuestras conexiones seguras.

**¿Por qué es tan fácil desactivar dispositivos conectados a una red WiFi, incluso sin estar autenticados en ella?**

- La respuesta es sencilla, atendiendo a cómo funciona una red WiFi. Durante la comunicación entre el punto de acceso (AP) y los dispositivos, se intercambian diversos tipos de paquetes, algunos de los cuales son de "gestión". A diferencia de otros paquetes, los de gestión no están cifrados, lo que significa que no requieren autenticación para ser enviados. Esto permite a un atacante, con solo estar dentro del alcance de la red, enviar estos paquetes y potencialmente interrumpir las conexiones de los dispositivos conectados.

## Contramedidas

Aunque no existe una forma definitiva de prevenir completamente los ataques de desautenticación, hay diversas medidas que pueden reducir significativamente su impacto y probabilidad. A continuación, se resumen las principales acciones y consideraciones:

1. **Habilitar 802.11w (Protected Management Frames)**
    - Este estándar cifra y autentica los paquetes de gestión, como los de desautenticación, dificultando que un atacante falsifique estos paquetes.
    - Es fundamental verificar si tu punto de acceso (AP) soporta 802.11w y habilitarlo para proteger tu red frente a este tipo de ataques.
2. **Uso de múltiples AP con el mismo ESSID**
    - Si tu red cuenta con varios puntos de acceso configurados con el mismo ESSID, los dispositivos podrán reconectarse automáticamente al AP más cercano en caso de ser desconectados de uno. Esta estrategia aumenta la robustez de la red.
3. **Considerar (pero no depender de) esconder el SSID**
    - Ocultar el nombre de tu red puede disuadir a atacantes menos avanzados, pero no previene los ataques, ya que el SSID sigue siendo detectable mediante algunas herramientas.
    - No es una solución de seguridad robusta por sí sola.
4. **Usar la banda de 5GHz**
    - Muchas herramientas y tarjetas Wi-Fi diseñadas para ataques operan únicamente en la banda de 2.4GHz.
    - Configurar tu AP en la banda de 5GHz hace que tu red sea invisible para estos dispositivos, siempre que los dispositivos de tu red también sean compatibles.
    - Actualmente, existen pocas herramientas y placas de desarrollo compatibles con esta frecuencia.
5. **Adoptar estándares modernos**
    - 802.11ac y 802.11ax (Wi-Fi 6): Estos estándares hacen obligatorio el uso de PMF, protegiendo los paquetes de gestión.
    - WPA3: Proporciona una capa adicional de seguridad frente a ataques de fuerza bruta. Sin embargo, todos los dispositivos de la red deben ser compatibles para implementar esta mejora. Aunque sea una mejora, no presenta una protección eficaz contra ataques de desautorización.
6. **Mantener el firmware actualizado**
    - Asegúrate de que el firmware de tu router esté actualizado para aprovechar las últimas medidas de seguridad.
    - Los fabricantes lanzan actualizaciones regularmente para mitigar nuevas vulnerabilidades.
7. **Monitorear el tráfico para detectar ataques**
    - Es fundamental saber si alguien está enviando paquetes de desautenticación maliciosos. Esto puede lograrse mediante:
    - Uso de herramientas como Wireshark para capturar y analizar el tráfico.
    - Dispositivos especializados, como detectores de desautenticación.

La implementación de estándares avanzados como **WPA3** o **802.11w** depende de que los dispositivos de tu red también los soporten. Es importante evaluar si todos tus equipos son compatibles antes de hacer cambios significativos. Con estas medidas, es posible construir una red más robusta frente a los ataques de desautenticación, combinando seguridad y monitoreo proactivo.