# UBIKA

Proyecto de ubicación de asesores orientado a almacenes de cadena (*retail*).

## Flujo del Modelo de Negocio
* **Asesor:** Se identificará por medio de la aplicación móvil, compartiendo su ubicación para poder habilitar las funciones de localización.
* **Cliente:** Se registra en la aplicación con el producto en el que está interesado o su sección, y llama a un asesor por medio del mapa.
* **Almacén:** Usa la localización del asesor y del cliente como referencia para futuras estrategias de venta.
* **Mapa:** Sirve para unir asesores y clientes, detallar la distribución del almacén y generar datos de los productos más vendidos para nuevas estrategias.

## Sistema de Geolocalización - Retail Tech Advisor

### Arquitectura del Mapa (Bajo Costo)
Para evitar el uso de APIs de pago (como Google Maps), este proyecto utiliza herramientas de código abierto:
* **Mapas base:** OpenStreetMap (Servidor de mapas gratuito).
* **Librería del Frontend:** Leaflet.js (Para renderizar el mapa y los pines).

### Flujo de Datos
1. El Backend almacena las coordenadas (`latitud`, `longitud`) y datos del asesor (nombre, especialidad, disponibilidad).
2. El Frontend Web realiza una petición al servidor para traer la lista de asesores activos.
3. Leaflet dibuja el mapa en pantalla y coloca un pin por cada asesor recibido.
