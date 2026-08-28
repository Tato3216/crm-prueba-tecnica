# CRM básico — Prueba técnica

Aplicación web mínima para registrar clientes y sus oportunidades de venta. Está escrita en JavaScript sin frameworks ni dependencias externas. No usa base de datos ni escribe archivos: toda la información se guarda en el `localStorage` del navegador.

## Requisitos

- Node.js 18 o superior (solo se usa para servir los archivos estáticos).
- Un navegador moderno (Chrome, Edge o Firefox actualizados).

## Cómo ejecutar

```bash
node server.js
```

Luego abre `http://localhost:3000`. Para usar otro puerto: `PORT=8080 node server.js`.

La primera vez se cargan tres clientes de ejemplo. El botón **Restablecer datos de ejemplo** borra todo lo guardado en el navegador y vuelve a cargarlos.

## Estructura

```
server.js            Servidor HTTP estático (sin dependencias)
public/
  index.html         Página principal
  styles.css         Estilos
  js/
    app.js           Interfaz: renderizado, formularios y eventos
    modelos.js       Entidades (cliente, oportunidad), límites y validaciones
    almacen.js       Lectura y escritura en localStorage, datos de ejemplo
```

## Funcionalidad actual

- Registrar, editar y eliminar clientes (nombre y contacto).
- Registrar oportunidades por cliente con título, monto y etapa.
- Cambiar la etapa de una oportunidad y eliminarla.
- Resumen del monto abierto (oportunidades que no están ganadas ni perdidas).

## Entrega de la parte offline

1. Crea tu propio repositorio a partir de este código (conserva el historial).
2. Trabaja siguiendo **Git Flow**: las ramas `main` y `develop` ya existen; crea tu rama `feature/...` a partir de `develop` e intégrala ahí al terminar. Deja `main` intacta.
3. Haz commits pequeños con mensajes descriptivos.
4. Actualiza este README con una sección **Notas de la entrega**: qué implementaste, decisiones que tomaste, qué dejaste fuera y por qué.
5. Si usaste herramientas de IA, indícalo en esa misma sección. No penaliza; nos interesa saber cómo trabajas.
6. Comparte el enlace al repositorio (público o con acceso al evaluador).

No agregues dependencias ni frameworks. El objetivo es evaluar tu criterio con JavaScript, HTML y CSS.


## Notas de la entrega

### Funcionalidades implementadas

- Filtro de clientes en tiempo real por nombre o contacto.
- Filtro de oportunidades por etapa para el cliente seleccionado.
- Opción para mostrar todas las etapas.
- Mensajes cuando los filtros no tienen resultados.

### Corrección realizada

Se corrigió la inconsistencia entre el límite de caracteres indicado en el formulario y el límite aplicado al guardar el nombre de un cliente.

### Decisiones técnicas

- No se agregaron frameworks ni dependencias externas.
- El filtro de clientes se ejecuta mediante el evento `input`.
- Las oportunidades se filtran después de seleccionar un cliente.
- Al seleccionar otro cliente, el filtro vuelve a mostrar todas las etapas.
- El resumen del pipeline conserva el total de todas las oportunidades abiertas del cliente.

### Pruebas manuales

Se comprobaron los siguientes casos:

- Búsqueda de clientes por nombre.
- Búsqueda de clientes por contacto.
- Búsqueda sin coincidencias.
- Selección de un cliente desde la lista filtrada.
- Filtrado de oportunidades por cada etapa disponible.
- Visualización de todas las oportunidades.
- Cambio de cliente después de seleccionar una etapa.
- Visualización del mensaje cuando una etapa no tiene oportunidades.
- Creación, edición y eliminación de clientes y oportunidades.
- Restablecimiento de los datos de ejemplo.

### Uso de herramientas de IA

Se utilizó una herramienta de IA como apoyo para organizar los cambios y revisar la implementación. El código final fue revisado y probado manualmente.