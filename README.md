# LunchPass

Es una plataforma web de membresías y reservas de almuerzos que permite a las personas adquirir planes de alimentación y reservar sus almuerzos según la disponibilidad del menú y los días incluidos en su membresía.

## Para quién es?
Está dirigida principalmente a:

- Empleados de empresas: que necesitan almorzar diariamente durante su jornada laboral.
- Estudiantes: que buscan una alternativa práctica para organizar sus almuerzos.
- Personas que trabajan en oficinas: que prefieren planificar sus comidas y evitar comprar almuerzo todos los días.
- Empresas y restaurantes: que quieren ofrecer planes de almuerzos recurrentes y administrar sus reservas.


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
   cd lunchpass
   ```

3. Construir las imágenes e iniciar los contenedores:
   ```bash
   docker compose up --build -d
   ```

4. Acceder a la aplicación desde el navegador:
   ```text
   http://localhost:5173
   ```

### Detener la aplicación

Para detener los contenedores:
```bash
docker compose down
```

## Qué se comprobaría?

- Registro e inicio de sesión de usuarios.
- Consulta de membresías disponibles.
- Consulta del menú diario.
- Creación y cancelación de reservas.
- Descuento correcto de almuerzos disponibles.
- Control de disponibilidad diaria.


## Fuera del alcance inicial: 

- Pagos reales.
- Ubicaciones en tiempo real.
- Domicilios y notificaciones.
