# Zona Huella 🐾

Zona Huella es una aplicación web orientada a la gestión y comercialización de productos para mascotas. Este repositorio contiene el frontend y backend del sistema desarrollado como proyecto académico.

## Tecnologías utilizadas

### Frontend

- HTML5
- CSS3
- JavaScript

### Backend

- Java
- Spring Boot
- Gradle
- Spring Data JPA

### Base de datos

- MySQL

---

# Requisitos previos

Antes de ejecutar el proyecto, asegúrate de tener instalado:

- Java JDK 17 o superior
- MySQL Server 8.0 o superior
- Git
- Gradle (opcional, el proyecto incluye Gradle Wrapper)

Verifica las instalaciones:

```bash
java -version
mysql --version
```

---

# Clonar el repositorio

```bash
git clone https://github.com/trujillo-jorge-boop/Zona-Huella_Portfolio.git

cd Zona-Huella_Portfolio
```

---

# Configuración de la base de datos

## 1. Crear la base de datos

```sql
CREATE DATABASE zonahuella;
```

## 2. Ejecutar el script de estructura

Ubicación:

```text
backend/zonahuella/src/main/resources/ZONAHUELLA.sql
```

Ejecuta el script utilizando MySQL Workbench o la consola de MySQL.

## 3. Ejecutar el script de datos iniciales

Ubicación:

```text
backend/zonahuella/src/main/resources/Relleno_normalizado.sql
```

Ejecuta este script después de crear las tablas para cargar la información inicial de la aplicación.

---

# Configuración del archivo application.properties

Por motivos de seguridad, se recomienda no compartir credenciales reales en GitHub.

Puedes utilizar el archivo que se encuentra en la siguiente ruta
backend/zonahuella/src/main/resources/application.properties.template

Con una configuración similar a la siguiente:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/DB_NAME
spring.datasource.username=TU_USUARIO
spring.datasource.password=TU_PASSWORD

spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

```

Ejemplo:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/zonahuella
spring.datasource.username=root
spring.datasource.password=1234
```

---

# Ejecutar el backend

Ubícate dentro de:

```text
backend/zonahuella
```

### Windows

```bash
gradlew.bat bootRun
```

### Linux / macOS

```bash
./gradlew bootRun
```

También puedes ejecutar la clase principal de Spring Boot desde IntelliJ IDEA, Eclipse o VS Code.
Esta clase se encuentra en la ruta:
backend\zonahuella\src\main\java\com\generation\zonahuella\ZonahuellaApplication.java

---

# Verificar ejecución

Si el backend inicia correctamente deberías observar un mensaje similar a:

```text
Tomcat started on port(s): 8080
Started Application
```

Accede a:

```text
http://localhost:8080
```

---

# Ejecutar el frontend

Si el frontend es un proyecto estático, abre el archivo principal o utiliza una extensión como Live Server en Visual Studio Code.
El archivo principal a ejecutar es el siguiente: index.html

Ejemplo:

```text
http://127.0.0.1:5500
```

---

# Problemas comunes

## Error de conexión a MySQL

Verifica que:

- MySQL esté en ejecución.
- El usuario y contraseña sean correctos.
- La base de datos `zonahuella` exista.

## Error: Unknown database

Ejecuta:

```sql
CREATE DATABASE zonahuella;
```

## Error: Table does not exist

Asegúrate de ejecutar los scripts en este orden:

1. ZONAHUELLA.sql
2. Relleno_normalizado.sql

---

# Buenas prácticas

Se recomienda agregar el siguiente archivo al `.gitignore`:

```gitignore
**/application.properties
```

Si el archivo ya estaba siendo rastreado por Git:

```bash
git rm --cached backend/zonahuella/src/main/resources/application.properties
```

---

# Licencia

Proyecto desarrollado con fines académicos y educativos.
