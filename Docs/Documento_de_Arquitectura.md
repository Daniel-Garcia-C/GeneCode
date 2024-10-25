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
