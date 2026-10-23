# FASE 2 - DESARROLLO PRÁCTICO DE CADA SERVICIO (70%)

## Proyecto: SaludCerca - Migración a Google Cloud Platform

### DATOS GENERALES
- Nombre del Proyecto: SaludCerca
- Plataforma: Google Cloud Platform (GCP)
- Caso de estudio: Plataforma web para localizar centros municipales de salud en La Paz, Bolivia.
- Versión: GCP - Aplicada a la versión funcional existente

---

## 1. SERVICIO 1: CLOUD RUN

### 1.1 Nombre del Servicio
Google Cloud Run

### 1.2 Categoría
Cómputo - Plataforma como Servicio (PaaS)

### 1.3 Justificación
SaludCerca cuenta con un backend en NestJS y frontend en React. Cloud Run permite desplegar contenedores o aplicaciones sin servidor, con escalado automático (de 0 a N instancias), HTTPS automático y pago por uso.

### 1.4 Aplicación al Proyecto
- Desplegar el backend (API REST NestJS) como servicio en Cloud Run.
- Exposición mediante URL HTTPS para acceso desde cualquier dispositivo.
- Conexión con Cloud SQL mediante VPC Serverless Access.

### 1.5 Pasos a realizar en Google Cloud Console
1. [PASO 1 - Crear proyecto en GCP]
2. [PASO 2 - Habilitar API de Cloud Run]
3. [PASO 3 - Crear servicio Cloud Run para Backend]
4. [PASO 4 - Configurar variables de entorno]
5. [PASO 5 - Probar acceso a la API (/api/health)]

### 1.6 Evidencias
- Captura 1_1: Creación del proyecto en GCP
- Captura 1_2: Habilitación de Cloud Run API
- Captura 1_3: Creación de servicio Cloud Run
- Captura 1_4: Configuración de variables de entorno
- Captura 1_5: URL del servicio funcionando

### 1.7 Resultados
[Descripción de lo obtenido]

### 1.8 Conclusión
Cloud Run permite desplegar SaludCerca de forma eficiente, escalable y con mínima administración.

---

## 2. SERVICIO 2: CLOUD SQL (POSTGRESQL)

### 2.1 Nombre del Servicio
Google Cloud SQL - PostgreSQL

### 2.2 Categoría
Bases de Datos - Base de Datos como Servicio (DBaaS)

### 2.3 Justificación
El proyecto utiliza PostgreSQL + Prisma ORM. Cloud SQL gestiona copias de seguridad automáticas, actualizaciones, parches, alta disponibilidad, cifrado y acceso controlado.

### 2.4 Aplicación al Proyecto
- Migrar base de datos local (saludcerca) a Cloud SQL PostgreSQL.
- Ejecutar migraciones (Prisma migrate deploy).
- Ejecutar seed de datos.

### 2.5 Pasos a realizar
1. [PASO 1 - Habilitar Cloud SQL API]
2. [PASO 2 - Crear instancia PostgreSQL]
3. [PASO 3 - Crear base de datos 'saludcerca']
4. [PASO 4 - Crear usuario y contraseña]
5. [PASO 5 - Configurar conexión con Cloud Run]
6. [PASO 6 - Ejecutar migraciones]

### 2.6 Evidencias
- Captura 2_1: Creación de instancia Cloud SQL
- Captura 2_2: Base de datos creada
- Captura 2_3: Usuario creado
- Captura 2_4: Migraciones ejecutadas
- Captura 2_5: Datos verificados

### 2.7 Resultados
[Descripción de lo obtenido]

### 2.8 Conclusión
Cloud SQL proporciona una base de datos robusta, segura y gestionada para SaludCerca.

---

## 3. SERVICIO 3: CLOUD STORAGE

### 3.1 Nombre del Servicio
Google Cloud Storage

### 3.2 Categoría
Almacenamiento - Almacenamiento de Objetos

### 3.3 Justificación
Permite almacenar archivos estáticos del frontend y recursos del proyecto con alta disponibilidad.

### 3.4 Aplicación al Proyecto
- Crear bucket para alojar archivos estáticos del frontend (dist).
- Configurar como sitio web estático.
- Servir la aplicación desde Cloud Storage.

### 3.5 Pasos a realizar
1. [PASO 1 - Crear bucket de Cloud Storage]
2. [PASO 2 - Subir build del frontend]
3. [PASO 3 - Configurar sitio web estático]
4. [PASO 4 - Configurar permisos]
5. [PASO 5 - Probar acceso]

### 3.6 Evidencias
- Captura 3_1: Creación del bucket
- Captura 3_2: Archivos subidos
- Captura 3_3: Configuración sitio web estático
- Captura 3_4: Frontend accesible

### 3.7 Resultados
[Descripción de lo obtenido]

### 3.8 Conclusión
Cloud Storage permite alojar el frontend de SaludCerca de manera escalable.

---

## 4. SERVICIO 4: CLOUD IAM

### 4.1 Nombre del Servicio
Google Cloud IAM

### 4.2 Categoría
Seguridad e Identidad

### 4.3 Justificación
Garantiza el principio de mínimo privilegio para conectar los servicios de forma segura.

### 4.4 Aplicación al Proyecto
- Crear cuenta de servicio para Cloud Run
- Asignar roles mínimos (Cloud SQL Client, Storage Object Viewer)
- Vincular a servicios

### 4.5 Pasos a realizar
1. [PASO 1 - Crear cuenta de servicio]
2. [PASO 2 - Asignar roles]
3. [PASO 3 - Vincular a Cloud Run]
4. [PASO 4 - Verificar permisos]

### 4.6 Evidencias
- Captura 4_1: Cuenta de servicio creada
- Captura 4_2: Roles asignados
- Captura 4_3: Vinculación a Cloud Run

### 4.7 Results: [Descripción]
### 4.8 Conclusión: Cloud IAM mejora la seguridad aplicando menor privilegio.

---

## 5. SERVICIO 5: VPC + SERVERLESS VPC ACCESS

### 5.1 Nombre del Servicio
VPC + Serverless VPC Access Connector

### 5.2 Categoría
Redes

### 5.3 Justificación
Conexión privada entre Cloud Run y Cloud SQL sin exponer la BD a internet.

### 5.4 Aplicación al Proyecto
- Crear VPC Access Connector
- Configurar Cloud SQL con IP privada
- Conectar Cloud Run al conector

### 5.5 Pasos a realizar
1. [PASO 1 - Crear VPC Access Connector]
2. [PASO 2 - Configurar IP privada en Cloud SQL]
3. [PASO 3 - Conectar Cloud Run al conector]
4. [PASO 4 - Probar conexión]

### 5.6 Evidencias
- Captura 5_1: VPC Access Connector
- Captura 5_2: Cloud SQL IP privada
- Captura 5_3: Cloud Run con VPC
- Captura 5_4: Conexión exitosa

### 5.7 Resultados
[Descripción de lo obtenido]

### 5.8 Conclusión
Fortalece la seguridad mediante comunicación privada.

---

## 6. SERVICIO 6: CLOUD LOGGING Y CLOUD MONITORING

### 6.1 Nombre del Servicio
Cloud Logging + Cloud Monitoring

### 6.2 Categoría
Observabilidad

### 6.3 Justificación
Monitoreo, logs, alertas para asegurar disponibilidad de SaludCerca.

### 6.4 Aplicación al Proyecto
- Revisar logs de Cloud Run
- Crear Dashboard
- Configurar alertas

### 6.5 Pasos a realizar
1. [PASO 1 - Revisar logs en Cloud Logging]
2. [PASO 2 - Crear Dashboard en Monitoring]
3. [PASO 3 - Configurar alertas]
4. [PASO 4 - Verificar monitoreo]

### 6.6 Evidencias
- Captura 6_1: Logs de Cloud Run
- Captura 6_2: Dashboard personalizado
- Captura 6_3: Alertas configuradas

### 6.7 Resultados
[Descripción de lo obtenido]

### 6.8 Conclusión
Permite garantizar operatividad y trazabilidad.

---

## CONCLUSIÓN GENERAL DE LA FASE 2

Se aplicaron los 6 servicios de Google Cloud para desplegar, securizar, conectar y monitorear la plataforma SaludCerca.

## ANEXOS
- Capturas de pantalla en carpeta docs/FASE2/capturas/
- URLs de servicios desplegados
