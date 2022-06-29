# Red BioPersona

**Red BioPersona** es un software que permite mediante la aplicación de técnicas matemáticas y estadísticas la verificación e identificación de la identidad de un individuo mediante el reconocimiento inequívoco de personas basado en uno o más rasgos físicos.

El objetivo de **Red BioPersona** es aplicar los conceptos de Biometría, de manera puntual reconocimiento facial, dactilar, voz e iris. Tomando como base científica su fiabilidad, facilidad de uso y aceptación.

Las operaciones que realiza **Red BioPersona** son las siguientes:

- **Detección**: Proceso en el cual se valida que la muestra cumpla con los estándares internacionales para ser enrolada, verificada o identificada, permite conocer el nivel de calidad de la muestra, para el caso del rostro se obtienen los datos (bigote, sexo, edad, boca abierta, lentes, ojos rojos, guiño etc.) tomando como base el ICAO.

- **Enrolamiento**: Proceso en el cual se valida la calidad de la muestra que será almacenada y posterior puede ser utilizada para el proceso de verificación e identificación.

- **Verificación**: Proceso en el que un sujeto puede ser identificado (1-1) de forma única mediante la evaluación de sus características biométricas y compararlos con la plantilla específica almacenada en base de datos para verificar que el individuo es la persona que dice ser.

- **Identificación**: Proceso en el que un sujeto puede identificarse de forma única mediante la evaluación de sus características biométricas y compararlos con todas las plantillas almacenadas en una base de datos (1-N o 1-M) para obtener la identificación de la persona u otra información relacionada.

- **Eliminación**: Proceso que elimina una muestra biométrica enrolada o los datos del sujeto.

Los alcances de **Red BioPersona** y posible implementación en el mercado son:
- Autenticación e inicio de sesión del usuario
- Pago y transferencias eléctronicas mediante el uso de biometria 
- Autenticación a información sensible
- Aceptación por medio de voz a procesos telefonicos 
- Control perimetral, acceso fisico a sitios restringidos

[========]

# Caso de uso
### Control de acceso

El sistema de asistencias o control de acceso, permite almacenar los registros de asistencia de los empleados

### Registro de Visitas


[========]

# Instalación y Configuración para la ambientación de Red BioPersona

### Paso 1. Descargar e instalar el jdk de Java

Es necesario descargar el JDK, o el JRE de java versión 8 o superior desde su [sitio oficial](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)., también definir la variable de entorno JAVA_HOME.

### Paso 2. Descargar e instalar meteor JS

Es necesario descargar el framework de Meteor JS desde su [sitio oficial](https://www.meteor.com/).

### Paso 3. Descargar e instalar dependencias

Es necesario descargar e instalar las siguientes dependencias adjuntas en el zip [enlace.](https://www.dropbox.com/sh/pmwvbu7lxmithxv/AADQ30BTzS0zy8wOZZTwRj2Aa?dl=0)

### Paso 4. Descargar e instalar la base de datos MongoDB
Es necesario descargar e instalar el motor de base de datos [MongoDB](https://www.mongodb.com/es), asi como el cliente [RoboMongo](https://robomongo.org/) para validar la información almacenada.

### Paso 5. Descargar e instalar Eclipse
Es necesario descargar e instalar [Eclipse](https://www.eclipse.org/downloads/).


### Paso 6. Descargar e instalar los controladores del dispositivo

Es necesario descargar e instalar los controladores del dispositivo con el cual se va hacer la captura, para los dispositivos biométricos (huella, iris, foto) los controladores están disponibles en el siguiente [enlace](https://download.neurotechnology.com/Scanner_Drivers.zip).

En caso de no contar con dispositivos, es posible usar las muestras del folder [x-resources](https://gitlab.com/redbiopersona/x-resources "x-resources")

### Paso 7.  Configuración del codigo

El sistema de RedBioPersona de manera integral cuenta con los siguientes servicios:
| Servicio  | Descripción  |
| ------------ | ------------ |
|   face-service | Servicio encargado de las operaciones biometricas faciales  |
|  finger-service |  Servicio encargado de las operaciones biometricas dactilar |
|  iris-service |  Servicio encargado de las operaciones biometricas con iris |
|  voz-service | Servicio encargado de las operaciones biometricas de voz  |
|  api-gateway | Orquestador de las peticiones  |
|  client-service | Servicio que valida al usuario que ejecuta la petición  |
|  persistence-service | Servicio que opera sobre la mongo DB  |

Cada servicio cuenta con un archivo de configuración:
- config_en.properties._ se encarga de definir el comportamiento de la aplicación como lo son (Dirección y puerto del los servicios, el QualityThreshold, MatchingThreshold de la captura y si se desea o no salvar la muestra capturada en el directorio, así como él envió de emails en caso de una exception).


Por ultimo, importe desde Eclipse los proyectos y ejecutelos para realizar el flujo de RedBioPersona.


### Paso 8.  Consumir el demo


Para consumir el servicio es necesario:
- La dirección IP del servicio [api-gateway](https://gitlab.com/redbiopersona/api-gateway "api-gateway") el cual es la puerta de enlace hacia los micro servicios restantes, adicional es el orquestador y balanceador de las peticiones.

Es posible validar el funcionamiento del orquestador, mediante el uso de [Postman](https://www.postman.com/ "Postman"), las colecciones y muestras de las peticiones, se encuentra en el repositorio [resources](https://gitlab.com/redbiopersona/x-resources "resources")
