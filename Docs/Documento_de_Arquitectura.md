# Beisboletos - Documento de Requisitos

<div align="center">

  ![Beisboletos Logo](/Docs/Assets/Logo.svg)

</div>

## 1 Introducción

### 1.1 Propósito

Este documento presenta la Arquitectura de Software para el aplicativo Beisboletos, un sistema encargado de la gestión de entradas para partidos de béisbol de las ligas menores y medianas del estado de Yucatán. La arquitectura de software ha sido estructurada siguiendo el modelo de vistas 4+1. 

### 1.2 Alcance

El propósito de este documento es definir y presentar de manera ordenada la arquitectura del sistema Beisbo-letos, que facilita la venta y generación de boletos para partidos de béisbol, ofreciendo a los usuarios información relevante sobre los partidos, como fecha, hora, lugar, precio y disponibilidad. Además, esta arquitectura asegura que el sistema sea escalable, mantenible y fácil de usar, proporcionando una guía para los desarrolladores y otros interesados en entender cómo se estructura y organiza el software.

### 1.3 Objetivos y limitaciones

La arquitectura presentada en este documento cubre todos los aspectos del sistema Beisboletos, desde la interacción con los usuarios para la compra de boletos, hasta la generación de estos y su validación para la entrada a los partidos. El objetivo es ofrecer una solución que atienda las necesidades de las pequeñas y medianas ligas de béisbol en el estado de Yucatán, permitiendo un registro de boletos eficiente y la generación de boletos de manera inmediata.

## 2. Vista lógica

### 2.1 Descripción

La vista lógica del sistema se organiza en cuatro carpetas principales: ModelosDAO, Modelos, Vista y mysqlimplements. Estas carpetas agrupan las clases según su responsabilidad en la aplicación de gestión de boletos de béisbol, siguiendo el patrón arquitectónico DAO (Data Access Object) y el modelo MVC (Modelo-Vista-Controlador). 

#### 1. ModelosDAO.
Esta carpeta contiene las interfaces y clases que definen la estructura del acceso a los datos: 

- **DAO**: Es una clase base o interfaz que define las operaciones genéricas de acceso a los datos, como insertar, eliminar, actualizar y consultar. Las clases concretas (EquipoDAO, PartidoDAO y BoletoDAO) heredan de DAO para proporcionar implementaciones específicas de estas operaciones para cada entidad. 

- **DAO Manager:** Es una clase responsable de manejar y proporcionar acceso a las diferentes implementaciones de DAO. Actúa como un punto central para la gestión de los objetos DAO y su interacción con la capa de persistencia. 

#### 2. Modelos

Esta carpeta agrupa las clases que representan las entidades principales del dominio del sistema: 

- **Boleto:** Representa la entidad de un boleto, incluyendo atributos como clvBoleto, clvPartido. 

- **Equipo:** Define un equipo de béisbol con atributos como clvEquipo, nombreEquipo. 

- **Partido:** Modela un partido de béisbol, incluyendo clvPartido, lugar, equipoUno, equipoDos, hora, día y mes.

#### 3. Vista

Contiene las clases que forman la capa de presentación o interfaz de usuario del sistema: 

- **VistaInicio:** Es la vista inicial que permite a los usuarios acceder al sistema. 

- **VistaEquipo:** Gestiona la presentación de los datos relacionados con los equipos. 

- **VistaPrincipal:** Es la vista central de la aplicación desde donde se accede a las funcionalidades principales. 

- **VistaPartido:** Gestiona la presentación y visualización de los partidos de béisbol disponibles. 

#### 4. Carpeta mysqlimplements 

Esta carpeta contiene las implementaciones concretas de las interfaces de acceso a datos utilizando MySQL como base de datos: 

- **MySQLBoletoDAO:** Implementa las operaciones definidas en BoletoDAO para interactuar con la base de datos MySQL. 

- **MySQLEquipoDAO:** Implementa las operaciones de EquipoDAO para la gestión de datos de equipos en MySQL. 

- **MySQLPartidoDAO:** Implementa las operaciones de PartidoDAO para la gestión de partidos en la base de datos MySQL. 

- **Conexion:** Clase encargada de manejar la conexión con la base de datos MySQL, proporcionando un mecanismo de conexión centralizado para el acceso a los datos. 

- **MySQLDaoManager:** Gestiona las instancias de los DAOs específicos de MySQL, utilizando DAO Manager para centralizar la interacción con la base de datos. 

- **DAOException:** Clase que maneja las excepciones específicas relacionadas con la capa de acceso a datos, proporcionando mensajes de error claros y gestionando errores de conexión o consultas a la base de datos.

### 2.2 Diagrama de clases
![Diagrama de clases de beisboletos](/Docs/Diagramas/Diagrama%20de%20clases.svg)

### 2.3 Modelo - Vista - Controlador
![Diagrama de clases de beisboletos](/Docs/Diagramas/MVCView.svg)

## 3. Vista de implementación

### 3.1 Descripción de los componentes

El Diagrama de Componentes muestra cómo los diferentes módulos y componentes del sistema se organizan e interactúan. Basándonos en la estructura de carpetas y librerías, la organización sería la siguiente: 

#### Componentes principales: 

#### Componente "Vista" 
Contiene los archivos y clases que forman la interfaz gráfica del sistema. 

- **Clases:** VistaInicio, VistaEquipo, VistaPrincipal, VistaPartido 

- **Librerías asociadas:** AbsoluteLayout-RELEASE150.jar, NefAnimacion_V2.1_jdk18.jar, miglayout-4.0.jar 

#### Componente "Controlador"
Gestiona la lógica de control que coordina la interacción entre la vista y los modelos. Ubicado dentro de la carpeta src, en la carpeta controladores. 

- **Clases:** ControladorPrincipal, ControladorVentanaEquipos, ControladorVentanaInicio y ControladorVentanaPartidos. 

#### Componente "Modelo"
Contiene las entidades de negocio del sistema, definidas en las carpetas Modelos y ModelosDAO. 

- **Clases:** Boleto, Equipo, Partido, DAO, DAOManager, etc. 

#### Componente "Persistencia"
Implementa la lógica de acceso a la base de datos, se encuentra en mysqlImplements y utiliza el mysql-connector-j-8.0.31.jar para interactuar con MySQL.

- **Clases:** MySQLBoletoDAO, MySQLPartidoDAO, MySQLEquipoDAO, Conexion, etc. 

#### Componente "Librerías"
Conjunto de librerías externas que proveen funcionalidades adicionales necesarias para el sistema, como jcalendar, mysql-connector-j-8.0.31.jar, AbsoluteLayout-RELEASE150.jar, etc.

### 3.2 Estructura de carpeta y archivos

### 3.3 Herramientas y dependencias

## 4. Vista de procesos

### 4.1 Diagrama de secuencia

## 5 Vista física

### 5.1 Infraestructura

### 5.2 Diagrama de despliegue

### 5.3 Hardware y redes

## 6 Vista de casos de uso

### 6.1 Principales casos de usp

### 6.2 Diagramas de casos de uso

## 7. Vista de base de datos

### 7.1 Diagrama entidad-relación (ER)

![Diagrama entidad-relación](/Docs/Diagramas/Diagrama%20Entidad-Relación.svg)
