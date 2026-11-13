# LunchPass

Es una plataforma web de membresías y reservas de almuerzos que permite a las personas adquirir planes de alimentación y reservar sus almuerzos según la disponibilidad del menú y los días incluidos en su membresía.

## ¿Para quién es?

Está dirigida principalmente a:

- **Empleados de empresas:** que necesitan almorzar diariamente durante su jornada laboral.
- **Estudiantes:** que buscan una alternativa práctica para organizar sus almuerzos.
- **Personas que trabajan en oficinas:** que prefieren planificar sus comidas y evitar comprar almuerzo todos los días.
- **Empresas y restaurantes:** que quieren ofrecer planes de almuerzos recurrentes y administrar sus reservas.

## Stack tecnológico

| Tecnología | Versión propuesta |
|---|---|
| Docker Engine | 29.9.3 |
| Docker Compose | 5.7.1 |
| Next.js | 16.4.x |
| React | 19.3.0 |
| TypeScript | 7.0.2 |
| PostgreSQL | 18.7 |
| Node.js | 22 LTS |

Las versiones se fijarán en los archivos de configuración y dependencias del proyecto. Se utilizarán versiones estables, evitando versiones beta, alpha o release candidate.

## Arquitectura

Se utilizará **Clean Architecture** como base para organizar el proyecto, separando las responsabilidades de presentación, lógica de negocio y acceso a datos.

La aplicación partirá de una arquitectura modular, donde cada funcionalidad tendrá sus propias responsabilidades y dependencias.

### Estructura inicial

```text
lunchpass/
│
├── src/
│   ├── app/
│   │   ├── api/
│   │   ├── (customer)/
│   │   ├── layout.tsx
│   │   └── page.tsx
│   │
│   ├── modules/
│   │   ├── menu/
│   │   │   ├── domain/
│   │   │   ├── application/
│   │   │   ├── infrastructure/
│   │   │   └── presentation/
│   │   │
│   │   ├── memberships/
│   │   │   ├── domain/
│   │   │   ├── application/
│   │   │   ├── infrastructure/
│   │   │   └── presentation/
│   │   │
│   │   └── reservations/
│   │       ├── domain/
│   │       ├── application/
│   │       ├── infrastructure/
│   │       └── presentation/
│   │
│   └── shared/
│       ├── components/
│       ├── types/
│       └── utils/
│
├── Dockerfile
├── compose.yaml
├── .dockerignore
├── .env.example
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md
```

### Responsabilidades de las capas

- **Domain:** entidades y reglas de negocio.
- **Application:** casos de uso y lógica de aplicación.
- **Infrastructure:** conexión y persistencia de datos en PostgreSQL.
- **Presentation:** componentes, interfaces y elementos visuales.

## ¿Cómo se ejecutaría?

### Requisitos previos

- Tener [Docker](https://www.docker.com/) instalado.
- Tener Docker Compose disponible.

### Ejecución

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/mcastaneda846/LunchPass.git
   ```

2. Ingresar a la carpeta del proyecto:

   ```bash
   cd LunchPass
   ```

3. Configurar las variables de entorno:

   ```bash
   cp .env.example .env
   ```

4. Construir las imágenes e iniciar los contenedores:

   ```bash
   docker compose up --build -d
   ```

5. Verificar que los servicios estén activos:

   ```bash
   docker compose ps
   ```

6. Acceder a la aplicación desde el navegador:

   ```text
   http://localhost:3000
   ```

### Consultar los registros

```bash
docker compose logs -f
```

### Detener la aplicación

Para detener los contenedores:

```bash
docker compose down
```

Para detenerlos y eliminar también los volúmenes asociados:

```bash
docker compose down -v
```

> El último comando elimina los datos persistidos en los volúmenes del proyecto. Utilizarlo únicamente cuando se quiera reiniciar el entorno desde cero.

## ¿Qué se comprobaría?

- Consulta de membresías disponibles.
- Consulta del menú diario.
- Visualización de la disponibilidad de almuerzos.
- Registro de una reserva.
- Validación de disponibilidad antes de confirmar.
- Consulta de las reservas realizadas.
- Actualización de los almuerzos disponibles después de una reserva.
- Persistencia de la información en PostgreSQL.
- Ejecución de los servicios mediante Docker Compose.

## Fuera del alcance inicial

- Pagos reales e integración con pasarelas de pago.
- Ubicaciones en tiempo real.
- Domicilios.
- Notificaciones.
- Panel administrativo avanzado.
- Gestión completa de usuarios y roles.
- Microservicios o microfrontends.

## Plan de desarrollo

El objetivo es construir un MVP funcional en un máximo de 8 horas.

| Etapa | Actividad | Tiempo |
|---|---|---:|
| 1 | Configuración de Next.js, TypeScript y Docker | 1 h |
| 2 | Estructura base y organización con Clean Architecture | 1 h |
| 3 | Configuración de PostgreSQL y modelo de datos | 1 h |
| 4 | Consulta de menús y membresías | 1.5 h |
| 5 | Implementación del sistema de reservas | 1.5 h |
| 6 | Integración y pruebas básicas | 1 h |
| 7 | Verificación y documentación | 1 h |
| | **Total** | **8 h** |

## Estado actual del proyecto

**Estado: Planificación inicial.**

- [x] Definición de la idea y objetivo.
- [x] Identificación del público objetivo.
- [x] Selección del stack tecnológico.
- [x] Definición de la arquitectura base.
- [x] Definición del alcance del MVP.
- [ ] Configuración inicial del proyecto.
- [ ] Configuración de Docker y PostgreSQL.
- [ ] Implementación de funcionalidades.
- [ ] Integración y pruebas.
- [ ] Validación del MVP.

---

**LunchPass** — Plataforma de membresías y reservas de almuerzos.
