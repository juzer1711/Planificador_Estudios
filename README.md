# Planificador de Estudios

Aplicación web educativa para organizar actividades académicas, distribuir el tiempo de estudio y hacer seguimiento al progreso. Permite dividir el trabajo en subtareas, visualizar fechas en un calendario y recibir recomendaciones para equilibrar la carga diaria.

Este repositorio reúne el **frontend** y el **backend** como submódulos de Git y sirve como punto de entrada para conocer el proyecto y explorar sus componentes.

## Demo

**[Abrir el Planificador de Estudios](https://planificador-estudios-frontend.vercel.app)**

La aplicación está desplegada con la siguiente distribución:

| Componente | Servicio | Acceso |
| --- | --- | --- |
| Frontend | Vercel | [Aplicación web](https://planificador-estudios-frontend.vercel.app) |
| Backend | Render | [Documentación de la API](https://planificador-estudios-backend-80p8.onrender.com/api/docs/) |
| Base de datos | Supabase | PostgreSQL, conectado desde el backend |

Para explorar sus funciones, crea una cuenta desde la aplicación e inicia sesión.

## Funcionalidades

- **Registro e inicio de sesión:** cada usuario dispone de sus propias actividades y configuración de estudio.
- **Gestión de actividades:** creación, consulta, edición y eliminación de actividades con título, curso, tipo, descripción, fecha y horario.
- **Organización por subtareas:** división de las actividades en pasos con fecha objetivo, horas estimadas y estado de finalización.
- **Vista del día:** consulta de subtareas pendientes, completadas y vencidas, junto con un resumen de la jornada.
- **Calendario mensual:** visualización de actividades y subtareas, con acceso a los detalles de la actividad asociada.
- **Seguimiento del progreso:** porcentaje de subtareas completadas y registro de avances con estados y notas, consultables en un historial.
- **Límite diario configurable:** definición de las horas de estudio disponibles para detectar sobrecargas al planificar.
- **Recomendaciones de planificación:** sugerencias para mover una subtarea a otra fecha, dividir sus horas entre dos días o ajustar el tiempo estimado, según la disponibilidad.
- **Reprogramación de actividades:** cambio de fecha y búsqueda automática de un día con capacidad para las subtareas pendientes.

Las recomendaciones se generan mediante reglas que consideran las horas pendientes, las fechas objetivo, el límite diario y los días de estudio inferidos del historial de subtareas.

## Tecnologías

| Capa | Tecnologías principales | Uso |
| --- | --- | --- |
| Frontend | JavaScript, React 19, Vite | Interfaz web y herramientas de desarrollo |
| Interfaz y navegación | Material UI, Emotion, React Router | Componentes visuales, estilos y rutas |
| Calendario y comunicación | FullCalendar, Axios | Visualización de eventos y consumo de la API |
| Backend | Python, Django, Django REST Framework | Lógica de negocio y API REST |
| Autenticación | Django Auth, tokens de Django REST Framework | Registro, inicio de sesión y acceso a datos del usuario |
| Documentación de API | drf-spectacular, OpenAPI, Swagger UI y ReDoc | Esquema y consulta de los endpoints |
| Persistencia | PostgreSQL en Supabase, Django ORM | Almacenamiento de usuarios, actividades, subtareas y avances |
| Despliegue | Vercel, Render, Gunicorn | Publicación del frontend y ejecución del backend |

En desarrollo, el backend utiliza SQLite cuando no se define la variable `DATABASE_URL`.

## Arquitectura

```text
Usuario
   |
   v
Frontend · React / Vercel
   |
   | HTTP · API REST · autenticación por token
   v
Backend · Django REST Framework / Render
   |
   | Django ORM
   v
Base de datos · PostgreSQL / Supabase
```

El frontend presenta las vistas de planificación y consume la API. El backend administra la autenticación, los datos de cada usuario, el seguimiento de avances y las recomendaciones de distribución del tiempo.

## Repositorios del proyecto

| Componente | Código en este repositorio | Repositorio de origen |
| --- | --- | --- |
| Frontend | [planificador-estudios-frontend](./planificador-estudios-frontend/) | [Sepul11/planificador-estudios-frontend](https://github.com/Sepul11/planificador-estudios-frontend) |
| Backend | [planificador_estudios_backend](./planificador_estudios_backend/) | [CristianOspina03/planificador_estudios_backend](https://github.com/CristianOspina03/planificador_estudios_backend) |

Cada componente conserva su propio repositorio e historial. Los submódulos permiten navegar desde este repositorio general hacia el código de cada parte.

### Clonar el proyecto completo

Para descargar el repositorio principal junto con ambos submódulos:

```bash
git clone --recurse-submodules https://github.com/juzer1711/Planificador_Estudios.git
```

Si ya clonaste el repositorio principal, puedes descargar los submódulos con:

```bash
git submodule update --init --recursive
```

## Recorrido de uso

1. Crea una cuenta e inicia sesión.
2. Configura tus horas de estudio disponibles por día en el perfil.
3. Registra una actividad académica y divídela en subtareas con fechas y horas estimadas.
4. Consulta la vista del día o el calendario para organizar tu trabajo.
5. Registra tus avances y revisa el progreso de cada actividad.
6. Consulta las recomendaciones y reprograma el trabajo cuando necesites redistribuir la carga.

## Propósito educativo

El proyecto integra una interfaz en React, una API REST en Django y una base de datos relacional para abordar un caso práctico de organización académica. Su objetivo es facilitar la planificación del estudio y aplicar conceptos de desarrollo web full stack, autenticación, persistencia de datos y lógica de planificación.
