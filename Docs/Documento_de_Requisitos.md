# Beisboletos - Documento de Requisitos

<div align="center">

  ![Beisboletos Logo](/Docs/Assets/Logo.svg)

</div>

## 1 Introducción

Este documento es la Especificación de Requisitos Software (ERS) para el aplicativo encargado de la gestión de entradas para partidos de béisbol de las ligas tanto menores como medianas del estado de Yucatán. Esta especificación se ha estructurado basándose en las directrices dadas por el estándar IEEE Práctica Recomendada para Especificaciones de Requisitos Software IEEE 830.

### 1.1 Proposito

Definir y presentar ordenadamente los requisitos y especificaciones que debe cumplir el software construido, que permite vender boletos a los partidos que se llevarán a cabo, así como proporcionar información acorde a ellos como el día, hora, lugar, precio y disponibilidad, y generación de boletos luego del registro para ser válidos para entrar hacia los partidos. 

### 1.2 Alcance

Beisboletos tiene como objetivo llegar hacia personas u organizaciones de pequeñas a medianas ligas de beisbol que requieran un sistema de registro de boletos que pueda ser usado para generar boletos de forma inmediata.

### 1.3 Definiciones, acrónimos y abreviaturas

N/A

### Referencias

N/A

## 2 Descripción general

### 2.1 Perspectiva del producto 

Con el proyecto se busca desarrollar e implementar una aplicación que gestione de forma óptima y ordenada la venta de boletos para los partidos que harán diferentes equipos previamente registrados. 

El proyecto busca suplir las siguientes necesidades: 

1. Registro de información de equipos y partidos.
2. Seguimiento de la venta de boletos.  
3. Control de los lugares disponibles. 
4. Control de ingresos durante la venta de boletos de un partido.
5. Recolectar estadísticas sobre los equipos y partidos.

### 2.2 Funcionalidades del producto

1. Registrar y editar equipos de Béisbol.
2. Buscar equipos de Béisbol mediante el nombre del equipo. 
3. Registrar y editar partidos de Béisbol. 
4. Buscar partidos de Béisbol. 
5. Registrar la venta de boletos para los partidos. 
6. Proporcionar seguimiento a los boletos de los partidos. 
7. Manejar los lugares disponibles en el estadio. 
8. Generar reportes de ganancias obtenidas de la venta de boletos. 
9. Inicio de sesión por parte de los usuarios.

### 2.3 Caracteristicas de los usuarios
| Tipo de usuario | Administrador |
| --------------- | ------------- |
| Nivel educativo | Educación superior |
| Experiencia | Gestión de sistemas de información |
| Actividades |  -  Configurar y ajustar los parámetros de funcionamiento del software. <br> - Administración de Usuarios. <br> - Presentar Encuestas. |

### 2.4 Restricciones
- Validación de sesión.
- Uso de la arquitectura modelo-vista-controlador para una mejor conexión entre las interfaces y los modelos. 
- Uso del lenguaje de programación java de la versión 17. 
- Base de datos clara y ordenada sin la repetición de contenidos creada a partir de mySql. 
- Revisiones exhaustivas de los datos para comprobar su correcta captura correspondiente. 
- Uso del framework spring de java.

### 2.5 Suposiciones y dependencias

El registro de cada partido está a cargo de un administrador; por cada equipo que disputa y que tiene la aplicación corriendo en un equipo que presente conexión a la base de datos. 

El sistema cuenta y contará con el respaldo suficiente para no caerse ante un flujo máximo de n registros simultáneos donde n representa los equipos que disputan partidos los mismos días. El eje principal es el manejo y manipulación de los registros, cambios en su forma o algún requisito que se quite o añada, tendrá que verificar si tiene un alto acoplamiento con dicho requisito.

### 2.6 Evolución previsible del sistema

En la entrega del 12 de diciembre del año 2022 se entregará todo lo estipulado en la versión uno de la especificación de requisitos de software. Aunque luego de la entrega no se descarta añadirle ciertas funcionalidades adicionales como son la encriptación de los datos, manejo de cuentas de calendarios que indiquen los días que habrá juegos y una tabla de posiciones que marque las victorias y derrotas disponible para los compradores de boletos.

## 3 Requisitos específicos

### 3.1 Requisitos funcionales

### 3.1.1 Requisitos funcional 1

| # de requisito      | RqF01  |
| ------------------- | ------ |
| Nombre              | Altas de boleto |
| Descripción         | El administrador registra los datos del usuario y del evento dentro del programa para ser enviados a la base de datos. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | - nombre <br> - equipos que se enfrentan <br> - fecha <br> - hora <br> - lugar <br> - número de asiento  |
| Salida              | Boleto |

### 3.1.2 Requisito funcional 2

| # de requisito      | RqF02  |
| ------------------- | ------ |
| Nombre              | Cálculo de ganancias |
| Descripción         | El administrador genera un reporte donde se presentan las entradas vendidas y el valor monetario recaudado. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Precio de boletos y número de boletos |
| Salida              | Precio del boleto por el número de boletos |

### 3.1.3 Requisito funcional 3

| # de requisito      | RqF03 |
| ------------------- | ------ |
| Nombre              | Altas de partido |
| Descripción         | El administrador puede registrar un nuevo enfrentamiento. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | - Equipos que se enfrentan <br> - fecha <br> - lugar |
| Salida              | Nuevo partido |

### 3.1.4 Requisito funcional 4

| # de requisito      | RqF04 |
| ------------------- | ------ |
| Nombre              | Altas de equipo |
| Descripción         | El administrador registra los datos del equipo. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | - Nombre de equipo |
| Salida              | Nuevo equipo |

### 3.1.5 Requisito funcional 5

| # de requisito      | RqF05 |
| ------------------- | ------ |
| Nombre              | Bajas de boleto |
| Descripción         | El administrador puede eliminar los datos que contenía el boleto correspondiente. Dentro del programa para ser eliminados de la base de datos. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Boleto |
| Salida              | Boleto eliminado |

### 3.1.6 Requisito funcional 6

| # de requisito      | RqF06 |
| ------------------- | ------ |
| Nombre              | Bajas de equipo |
| Descripción         | El administrador elimina al equipo de la base de datos, lo que ocasiona en un efecto conectado que los partidos que tenía programado por jugar no puedan llevarse a cabo, eliminándolos del registro. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Equipo |
| Salida              | Equipo eliminado |

### 3.1.7 Requisito funcional 7

| # de requisito      | RqF07 |
| ------------------- | ------ |
| Nombre              | Bajas de partidos |
| Descripción         | El administrador elimina los partidos que se iban a realizar. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Partido |
| Salida              | Partido eliminado |

### 3.1.8 Requisito funcional 8

| # de requisito      | RqF08 |
| ------------------- | ------ |
| Nombre              | Búsqueda de boleto |
| Descripción         | El administrador busca en base al nombre del usuario o al enfrentamiento, los boletos. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Boleto |
| Salida              | Datos de boleto encontrado |

### 3.1.9 Requisito funcional 9

| # de requisito      | RqF09 |
| ------------------- | ------ |
| Nombre              | Búsqueda de equipo |
| Descripción         | El administrador del equipo busca los partidos que este jugará o ya jugó. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Equipo ingresado |
| Salida              | Equipo encontrado |

### 3.1.10 Requisito funcional 10

| # de requisito      | RqF09 |
| ------------------- | ------ |
| Nombre              | Búsqueda de partidos |
| Descripción         | El administrador busca partidos según la proporción de dos nombres dados o mediante la fecha en que se realizará. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Partido |
| Salida              | Partido encontrado |

### 3.2 Requisitos no funcionales

### 3.2.1 Disponibilidad

| # de requisito      | RqNF01 |
| ------------------- | ------ |
| Nombre              | Ante todo, los boletos son primero. |
| Descripción         | No importa en qué parte de la aplicación se encuentre el administrador, siempre tiene la opción de dar de alta los boletos. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | Petición para ver los objetos |
| Salida              | Boletos encontrados |

### 3.2.2 Seguridad

| # de requisito      | RqNF02 |
| ------------------- | ------ |
| Nombre              | Privacidad de la información. |
| Descripción         | Toda la información proporcionada será únicamente para fines corporativos para llevar a cabo operaciones de índole privada y limpia con el consentimiento del usuario. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | - nombre <br> - contraseña |
| Salida              | Valor bandera |

### 3.2.3 Fiabilidad

| # de requisito      | RqNF03 |
| ------------------- | ------ |
| Nombre              | Robustez. |
| Descripción         | El software tendrá un manejo fluido y correcto de la información que se proporciona asegurando que no existan redundancias en las tuplas de información y siendo lo más fresca posible. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |
| Entrada             | N/A |
| Salida              | N/A |

### 3.3 Otros requisitos

### 3.3.1 Politica de administración

| # de requisito      | RqNF04 |
| ------------------- | ------ |
| Nombre              | Tratar a los administradores como seres humanos. |
| Descripción         | La aplicación será amigable con el administrador y, si se equivoca o se equivoca, la aplicación tendrá que explicar lo ocurrido o dará un mensaje donde diga qué hacer. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Baja/Opcional |

### 3.3.2 Análisis

| # de requisito      | RqNF05 |
| ------------------- | ------ |
| Nombre              | Análisis |
| Descripción         | El software tendrá un análisis de los datos que entran asegurándose de que existan congruencias con los tipos de datos capturados y requeridos. |
| Tipo                | Requisito |
| Fuente              | Administrador |
| Prioridad           | Alta/Esencial |

## 4 Anexos

### A1. Formato de usuario

| Tipo de usuario |  |
| --------------- | ------------- |
| Nivel educativo |  |
| Experiencia     |  |
| Actividades     |  |

### A2. Formato de requisito

| # de requisito      | RqF0 |
| ------------------- | ------ |
| Nombre              | |
| Descripción         | |
| Tipo                | |
| Fuente              | |
| Prioridad           | |
| Entrada             | |
| Salida              | |