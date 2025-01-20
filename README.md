# Nginx

## Introducción
Nginx es un servidor web y proxy inverso de alto rendimiento que también puede funcionar como balanceador de carga y caché HTTP. Se caracteriza por su arquitectura eficiente en el manejo de múltiples conexiones simultáneas, lo que lo convierte en una excelente opción para aplicaciones de alta demanda. Este proyecto tiene como objetivo la migración de Apache a Nginx en Servicios Web RC, S.A, aprovechando sus ventajas en rendimiento y configuración.

## Comparativa con Apache
### Apache
- Arquitectura de procesos múltiples.
- Modularidad alta con soporte para múltiples módulos.
- Más utilizado en hosting compartido.
- Configuración más compleja para un rendimiento óptimo.

### Nginx
- Arquitectura basada en eventos asíncronos.
- Uso eficiente de recursos, especialmente en operaciones de E/S.
- Ideal para servir contenido estático y manejar grandes volúmenes de tráfico.
- Configuración más sencilla para tareas comunes como proxy inverso y balanceo de carga.

| Característica      | Apache                            | Nginx                              |
|---------------------|-----------------------------------|------------------------------------|
| Modelo de Procesos  | Basado en procesos e hilos        | Basado en eventos asíncronos       |
| Rendimiento         | Más bajo en altas cargas          | Mejor manejo de grandes cantidades de conexiones |
| Configuración       | Más compleja                      | Más simple para tareas comunes     |
| Uso de Recursos     | Más consumo de memoria            | Menor uso de recursos              |

## Esquema de Red
El servidor tendrá dos tarjetas de red:
- **Red Interna:** 192.168.1.0/24
- **Red Externa:** Configurada según la red pública.

```plaintext
+---------------------------+
|          Servidor         |
|---------------------------|
| Red Interna  | Red Externa |
| 192.168.1.X  | 203.0.113.X |
+---------------------------+
