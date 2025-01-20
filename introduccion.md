## Introducción

Nginx (pronunciado "Engine-X") es un servidor web de código abierto desarrollado por Igor Sysoev en 2004, diseñado inicialmente para resolver el problema del rendimiento de los servidores web en situaciones de alta concurrencia. A diferencia de Apache, que sigue un modelo basado en procesos o hilos, Nginx utiliza una arquitectura basada en eventos asíncronos, lo que le permite manejar miles de conexiones concurrentes utilizando una cantidad relativamente pequeña de recursos.

Nginx no solo actúa como un servidor web, sino que también se desempeña como un proxy inverso, balanceador de carga, y servidor de correo. Su flexibilidad y eficiencia lo han convertido en la elección predilecta para muchas empresas y desarrolladores que necesitan una solución escalable y de alto rendimiento para sus aplicaciones web.

En este proyecto, realizado para Servicios Web RC, S.A., nos proponemos migrar desde Apache a Nginx para mejorar el rendimiento, la gestión de recursos, y la facilidad de configuración de nuestros servicios web. A través de este informe, exploraremos las diferencias clave entre Nginx y Apache, configuraremos un entorno de servidor web completo con Nginx, y cubriremos casos prácticos que demuestran su capacidad para manejar múltiples sitios web, controlar el acceso, y asegurar las comunicaciones mediante SSL/TLS.
