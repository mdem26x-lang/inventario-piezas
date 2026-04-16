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
