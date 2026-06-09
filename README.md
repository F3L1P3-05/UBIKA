# UBIKA

Proyecto de ubicación de asesores orientado a almacenes de cadena (*retail*).

## Flujo del Modelo de Negocio
* **Asesor:** Se identificará por medio de la aplicación móvil, compartiendo su ubicación para poder habilitar las funciones de localización.
* **Cliente:** Se registra en la aplicación con el producto en el que está interesado o su sección, y llama a un asesor por medio del mapa.
* **Almacén:** Usa la localización del asesor y del cliente como referencia para futuras estrategias de venta.
* **Mapa:** Sirve para unir asesores y clientes, detallar la distribución del almacén y generar datos de los productos más vendidos para nuevas estrategias.

## 1. Sistema de Geolocalización - Retail Tech Advisor

### Arquitectura del Mapa (Bajo Costo)
Para evitar el uso de APIs de pago (como Google Maps), este proyecto utiliza herramientas de código abierto:
* **Mapas base:** OpenStreetMap (Servidor de mapas gratuito).
* **Librería del Frontend:** Leaflet.js (Para renderizar el mapa y los pines).

### Flujo de Datos
1. El Backend almacena las coordenadas (`latitud`, `longitud`) y datos del asesor (nombre, especialidad, disponibilidad).
2. El Frontend Web realiza una petición al servidor para traer la lista de asesores activos.
3. Leaflet dibuja el mapa en pantalla y coloca un pin por cada asesor recibido.
# UBIKA

Proyecto de ubicación de asesores en tiempo real orientado a almacenes de cadena (*retail*) con enfoque tecnológico.

---

## 📱 2. Sistema del Asesor (Aplicación Móvil)
Este módulo permite al asesor reportar su estado y ubicación física dentro de los pasillos de la tienda.

* **Estado de Disponibilidad:** Un interruptor simple para marcarse como `Disponible` u `Ocupado`.
* **Geolocalización Nativa:** El teléfono envía las coordenadas (`latitud` y `longitud`) del asesor automáticamente mediante el GPS del dispositivo.
* **Perfil Técnico:** El asesor registra su nombre y su área de experiencia (ej. Computadores, Celulares, Smart Home).

---

## 🛒 3. Sistema del Cliente (Web App Móvil por QR)
El cliente escanea un código QR en el pasillo de la tienda y accede instantáneamente a una página web desde su celular sin necesidad de descargar aplicaciones de una tienda virtual.

* **Filtro de Categorías:** El cliente presiona botones grandes con la sección tecnológica donde necesita ayuda.
* **Mapa Interactivo (Costo $0):** El sistema renderiza un mapa gratuito usando **OpenStreetMap** y **Leaflet.js**, mostrando pines visuales únicamente de los asesores que están disponibles para esa categoría.
* **Botón de Alerta:** El cliente puede presionar "Llamar Asesor" para notificar que requiere asistencia en su ubicación exacta.

---

## 📊 4. Sistema del Almacén / Jefe (Panel de Administración Web)
Una plataforma web de escritorio diseñada para que el gerente de la tienda supervise y analice la operación en tiempo real.

* **Mapa de Calor Comercial:** Muestra de forma gráfica en qué pasillos se concentran más los clientes pidiendo ayuda, facilitando la toma de decisiones para futuras estrategias de venta.
* **Métricas en Tiempo Real:** Gráficas simples con el número total de asesores conectados y el número de solicitudes atendidas durante el día.
* **Gestión de Personal:** Permite al jefe monitorear si las áreas tecnológicas de alta demanda cuentan con suficientes asesores disponibles.

---

## ⚙️ Arquitectura del Prototipo Técnico
Para mantener los costos de desarrollo en **$0 USD**, el proyecto simulará la lógica de estos tres sistemas dentro de un solo archivo de pruebas unificado:

```javascript
// Prototipo de base de datos simulada en memoria para el mapa gratuito
let asesoresConectados = [
    { id: 1, nombre: "Juan Pérez", especialidad: "Celulares e IA", lat: 4.6097, lng: -74.0817, disponible: true },
    { id: 2, nombre: "María Gómez", especialidad: "Línea Blanca y Smart Home", lat: 4.6120, lng: -74.0830, disponible: true }
];
```

