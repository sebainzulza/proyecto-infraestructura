# Infraestructura - API de Inventario de Servidores

Este repositorio contiene la configuración de infraestructura y CI/CD para el proyecto de API Laravel.

##  Estructura del Repositorio

\\\
proyecto-infraestructura/
 docker-compose.yml              # Orquestación de servicios
 DOCKER_DEPLOYMENT.md            # Guía de despliegue con Docker
 docker/
    nginx/
        nginx.conf              # Configuración de Nginx
 environments/
    .env.production             # Variables de entorno de producción
 ansible/                        # Playbooks de automatización (próximamente)
    inventory/
    playbooks/
    roles/
 .github/
    workflows/                  # Pipelines CI/CD (próximamente)
 scripts/                        # Scripts de despliegue (próximamente)
\\\

##  Repositorio de Aplicación

El código fuente de la aplicación Laravel se encuentra en:
**https://github.com/sebainzulza/proyecto-laravel-api**

##  Despliegue con Docker

### Requisitos Previos

- Docker Engine 20.10+
- Docker Compose 2.0+

### Pasos para Despliegue

1. **Clonar este repositorio:**
   \\\ash
   git clone https://github.com/sebainzulza/proyecto-infraestructura.git
   cd proyecto-infraestructura
   \\\

2. **Configurar variables de entorno:**
   \\\ash
   cp environments/.env.production .env
   # Editar .env con tus configuraciones
   \\\

3. **Levantar los servicios:**
   \\\ash
   docker-compose up -d
   \\\

4. **Ejecutar migraciones:**
   \\\ash
   docker-compose exec app php artisan migrate --force
   \\\

##  Servicios Disponibles

- **app**: Aplicación Laravel (PHP-FPM)
- **nginx**: Servidor web (puerto 8080)
- **db**: Base de datos MySQL 8.0

##  Referencias

- **Repositorio de Aplicación**: https://github.com/sebainzulza/proyecto-laravel-api
- **Documentación de Despliegue**: Ver DOCKER_DEPLOYMENT.md
