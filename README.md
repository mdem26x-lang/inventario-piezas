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

##  Instalación
### Ambiente de Desarrollo
1. Clonar el repositorio: `git clone https://github.com/mdem26x-lang/inventario-piezas.git`
2. Abrir el proyecto en NetBeans (File > Open Project).
3. Dejar que Maven descargue las dependencias automáticamente.

### Ejecución de Pruebas
* Para pruebas manuales: Hacer clic derecho en el proyecto y seleccionar **"Run"**.
* Verificar la conexión a la base de datos en el panel de "Services" de NetBeans.

##  Configuración
1. **Base de Datos:** Configurar las credenciales en el archivo `src/main/resources/config.properties` (o el archivo de conexión que definamos).
2. **Dependencias:** Asegurarse de tener instalado el conector de MySQL en el archivo `pom.xml`.
