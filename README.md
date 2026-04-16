Sistema de Inventario de Refacciones Industriales
 Descripción
Este proyecto consiste en una aplicación de escritorio desarrollada en Java diseñada para la gestión y control de inventarios de refacciones críticas en un entorno industrial. El sistema permite centralizar la información técnica de los componentes, facilitando su localización física y el seguimiento de existencias.

 Problema Identificado
En la actualidad, el registro de piezas se lleva a cabo mediante bitácoras manuales y hojas de papel. Esta metodología presenta deficiencias críticas:

Inconsistencia de datos: Los registros escritos a mano suelen ser difíciles de leer, provocando errores en los números de parte.

Tiempos de respuesta lentos: Localizar una pieza específica entre más de 50 hojas de papel retrasa las reparaciones durante paros de maquinaria.

Falta de respaldo: La información física es vulnerable a pérdidas o daños, lo que compromete el control del almacén.

 Solución
Se ha desarrollado una plataforma digital que consolida un catálogo de 224 números de parte extraídos de registros físicos. La solución ofrece:

Búsqueda Instantánea: Filtrado por código de parte o descripción.

Control de Ubicaciones: El sistema indica el estante y nivel exacto (ej. D.2.41) para cada componente.

Digitalización Total: Migración de más de 50 registros fotográficos a una base de datos relacional.

Arquitectura
El sistema implementa el patrón de diseño Modelo-Vista-Controlador (MVC) para garantizar un código organizado y escalable:

Modelo: Gestiona la lógica de los datos de las refacciones (Clases Java POJO).

Vista: Interfaz gráfica desarrollada en NetBeans (Swing) para la interacción con el usuario.

Controlador: Gestiona la comunicación entre la interfaz y la lógica de negocio.
## Requerimientos Técnicos Detallados

### Servidores y Base de Datos
* **Servidor de Base de Datos:** MySQL Server 8.0 (Localhost) o MariaDB. Se utilizará para el almacenamiento persistente de los 224 registros de refacciones.
* **Servidor de Aplicación:** No requiere (Aplicación de escritorio Standalone ejecutada mediante Java Runtime Environment).

### Versión de Java y Entorno
* **Java Development Kit (JDK):** Versión 17 (LTS) o superior. Se recomienda OpenJDK por su compatibilidad con proyectos Maven.
* **IDE de Desarrollo:** Apache NetBeans IDE 21.
* **Gestor de Proyectos:** Apache Maven 3.9 (para la gestión automatizada de dependencias).

### Paquetes Adicionales (Dependencias Maven)
Para el correcto funcionamiento de la solución, se han integrado los siguientes paquetes:
* **MySQL Connector/J:** Librería oficial para permitir que Java se comunique con la base de datos MySQL.
* **FlatLaf:** (Opcional) Paquete para modernizar la apariencia visual de la interfaz Swing.
* **Apache POI:** (Sugerido) Para permitir que el sistema exporte el inventario actual a archivos de Excel.
## Tabla de Contenidos
- [Requerimientos](#-requerimientos)
- [Instalación](#-instalación)
- [Configuración](#-configuración)
- [Uso](#-uso)

## Requerimientos
Para ejecutar este proyecto, se requiere el siguiente entorno:
* **Java:** JDK 17+
* **IDE:** NetBeans IDE
* **Build Tool:** Maven 3.0+
* **Base de Datos:** MySQL / Local Derby
* **SO:** Windows 11
##  Tabla de Contenidos
- [Requerimientos](#-requerimientos)
- [Instalación](#-instalación)
- [Configuración](#-configuración)
- [Uso](#-uso)

##  Requerimientos
Para ejecutar este proyecto, se requiere el siguiente entorno:
* **Java:** JDK 17 o superior.
* **IDE:** NetBeans IDE 21.
* **Build Tool:** Maven 3.0+.
* **Base de Datos:** MySQL 8.0 / Derby Local.
* **SO:** Windows 11.

## Instalación

### 1. Instalación del Ambiente de Desarrollo
Para poner en marcha el proyecto en una computadora nueva, siga estos pasos:
1. **Instalar el JDK:** Descargue e instale Java Development Kit 17 desde el sitio oficial de Oracle o Adoptium.
2. **Configurar el IDE:** Instale Apache NetBeans IDE (versión 21 recomendada).
3. **Clonar el Proyecto:** Abra una terminal o use la interfaz de GitHub para clonar este repositorio:
   `git clone https://github.com/mdem26x-lang/inventario-piezas.git`
4. **Importar en NetBeans:** - Vaya a `File` > `Open Project`.
   - Seleccione la carpeta descargada (identificada con el icono de Maven).
   - Espere a que el IDE descargue las librerías necesarias (dependencias del pom.xml).

### 2. Ejecución de Pruebas Manuales
Antes de usar el sistema, realice estas verificaciones:
1. **Prueba de Conexión:** En NetBeans, vaya a la pestaña "Services" > "Databases" y asegúrese de que la conexión a MySQL esté activa.
2. **Ejecución del Sistema:** Haga clic derecho en el proyecto y seleccione `Run`. El sistema debe abrir la ventana principal de inventario.
3. **Verificación de Datos:** Ingrese un código de parte conocido (ej. A0162543-M) en la barra de búsqueda para confirmar que la base de datos responde correctamente.

### 3. Implementación (Producción)
#### Ambiente Local:
Para ejecutar la aplicación fuera de NetBeans:
1. En NetBeans, haga clic en `Clean and Build`.
2. Busque el archivo generado en la carpeta `/target` con extensión `.jar`.
3. Ejecute el comando: `java -jar nombre-del-archivo.jar`.

#### Ambiente en la Nube (Heroku):
1. Crear una cuenta en Heroku y un nuevo "App".
2. Configurar el Add-on `Heroku Postgres` o `ClearDB MySQL`.
3. Vincular este repositorio de GitHub a Heroku y activar los "Automatic Deploys".
4. El sistema se compilará automáticamente usando el archivo `system.properties` para definir la versión de Java.

### Ejecución de Pruebas
* Para pruebas manuales: Hacer clic derecho en el proyecto y seleccionar **"Run"**.
* Verificar la conexión a la base de datos en el panel de "Services" de NetBeans.

##  Configuración
1. **Base de Datos:** Configurar las credenciales en el archivo `src/main/resources/config.properties` (o el archivo de conexión que definamos).
2. **Dependencias:** Asegurarse de tener instalado el conector de MySQL en el archivo `pom.xml`.

   ## Configuración

### 1. Configuración del Producto
La aplicación utiliza archivos específicos para gestionar el comportamiento del sistema sin necesidad de modificar el código fuente:

* **Archivo de Conexión (`src/main/resources/db.properties`):** En este archivo se deben configurar las credenciales de la base de datos:
  - `db.url`: Dirección del servidor (ej. localhost:3306/inventario).
  - `db.user`: Nombre de usuario de MySQL.
  - `db.password`: Contraseña de acceso.
* **Archivo de Log:** Configuración para el registro de errores y eventos del sistema durante la ejecución.

### 2. Configuración de los Requerimientos
Para asegurar que todos los paquetes adicionales funcionen, se deben validar los siguientes puntos:

* **Configuración de Maven (`pom.xml`):** Es el corazón del proyecto. Aquí se definen las dependencias que mencionamos en los requerimientos. Se debe asegurar que el conector de MySQL esté correctamente declarado para evitar errores de "Driver not found".
* **Variables de Entorno:** Es necesario verificar que la variable `JAVA_HOME` apunte correctamente a la ruta de instalación del JDK 17 en Windows 11 para que NetBeans pueda compilar el proyecto sin conflictos.
* **Privilegios de Base de Datos:** El usuario configurado debe tener permisos de `SELECT`, `INSERT`, `UPDATE` y `DELETE` sobre la tabla de los 224 números de parte para permitir la gestión completa del inventario.

## Uso

### 1. Referencia para el Usuario Final (Manual de Operación)
Este manual está diseñado para el personal de almacén o mantenimiento que requiere localizar refacciones de forma rápida:

* **Búsqueda de Refacciones:** - Ingrese el número de parte o el nombre de la pieza en el cuadro de búsqueda principal.
  - El sistema filtrará automáticamente los 224 registros en tiempo real.
* **Localización Física:** - Una vez encontrada la pieza, observe la columna "Ubicación". El sistema le indicará el estante y nivel (ej. D.2.41) para reducir el tiempo de traslado.
* **Consulta de Existencias:** - El color de la fila indicará el estado del stock: Verde (Disponible), Amarillo (Stock bajo) y Rojo (Agotado).

### 2. Referencia para el Usuario Administrador
Sección destinada al responsable de mantener la integridad de la base de datos:

* **Alta de Nuevas Partes:** Utilice el formulario de "Nuevo Registro" para ingresar el código, descripción, categoría y ubicación de nuevas piezas que lleguen al inventario.
* **Actualización de Inventario:** Para modificar la cantidad de piezas tras un mantenimiento, seleccione la pieza y use la función "Editar Stock".
* **Respaldo de Información:** El administrador tiene acceso al botón "Exportar", que genera un archivo con el listado completo de los 224 números de parte para auditorías o revisiones externas.

## Contribución

Para mantener el orden en el desarrollo del sistema de inventario, se solicita a los colaboradores seguir este flujo de trabajo:

1. **Clonar el repositorio:**
   Obtenga una copia local del proyecto:
   `git clone https://github.com/mdem26x-lang/inventario-piezas.git`

2. **Crear una nueva rama (Branch):**
   Antes de hacer cambios, cree una rama específica para la tarea (ej. añadir nuevos números de parte):
   `git checkout -b feature/nueva-funcionalidad`

3. **Realizar cambios y Commits:**
   Realice las modificaciones necesarias y guarde sus cambios con mensajes descriptivos:
   `git commit -m "Añade lógica de búsqueda para refacciones neumáticas"`

4. **Enviar Pull Request (PR):**
   Suba su rama al repositorio remoto y abra un Pull Request en GitHub explicando los cambios realizados.

5. **Revisión y Merge:**
   El administrador revisará el código y, si todo es correcto, realizará el "Merge" a la rama principal (main). No se permite hacer cambios directamente en la rama main sin revisión previa.
