# AWS HOTEL CHATBOT - Reservas de Hotel 

<p align = "center">
    <img src="img/portada.png" width="300">
</p>

## Índice

- **[Descripcion](#Descripción)**
- **[Objetivo](#Objetivo)**
- **[Fuentes](#Fuentes)**
- **[Planificación](#Planificación)**
- **[Tecnologías utilizadas](#Tecnologías-utilizadas)**
- **[Requisitos previos](#Requisitos-previos)**
- **[Licencia](#Licencia)**
- **[Autores](#Autores)**
- **[Desarrollo del proyecto](#Desarrollo-del-proyecto)**
  - **[Configuración en AWS](#Configuración-en-AWS)**
  - **[Realiazación de pruebas](#Realiazación-de-pruebas)**
  - **[Implementación del chatbot en una página web](#Implementación-del-chatbot-en-una-página-web)**
  - **[Pruebas de funcionalidad](#Pruebas-de-funcionalidad)**
    - **[Prueba de saludo](#Prueba-de-saludo)**

### Descripción

Este proyecto crea un chatbot que permite a los usuarios realizar reservas de habitaciones de hotel. El chatbot está desarrollado utilizando AWS Lex y se integra con otros servicios de AWS como Lambda. El proyecto forma parte del módulo **"Modelos de Inteligencia Artificial"** del Curso de **Especialización en Inteligencia Artificial y Big Data**.

### Objetivo

El chatbot puede ser utilizado por los hoteles para ofrecer un servicio de atención al cliente más eficiente y mejorar la experiencia de los usuarios. Los usuarios pueden utilizar el chatbot para realizar reservas de habitaciones, obtener información sobre los servicios del hotel y hacer preguntas frecuentes.

### Fuentes

- [How to Make a Chatbot Using Amazon Lex and AWS Lambda (Python)](https://www.youtube.com/watch?v=RB8yw2nzA2Q) -> en el que nos hemos basado para la realización de este proyecto.
- [Interact with an Amazon Lex V2 bot with the AWS CLI, AWS SDK for Python (Boto3), and AWS SDK for DotNet](https://aws.amazon.com/es/blogs/machine-learning/interact-with-an-amazon-lex2v2-bot-with-the-aws-cli-aws-sdk-for-python-and-aws-sdk-dotnet/)
- [Curso de AWS Desde Cero | Amazon Web Services](https://www.youtube.com/watch?v=zQyrhjEAqLs)
- [AWS LEX - Build & Deploy Chatbots (A Crash Course](https://www.youtube.com/watch?v=82WduX8A99g)
- [Building a Menu-Based Chatbot using Amazon Lex](https://www.youtube.com/watch?v=NVs1Y2MrZSA)
- [Learn About New Amazon Lex Features to Accelarate Customer Time to Value- AWS Online Tech Talks](https://www.youtube.com/watch?v=t5prCwYTdT0)
- [Usar el generador visual de conversaciones](https://docs.aws.amazon.com/es_es/lexv2/latest/dg/visual-conversation-builder.html)
- [Amazon Lex: Validate Slot data with Lambda](https://www.youtube.com/watch?v=1xRl8Ipa018)

### Planificación

El proyecto se desarrollará en las siguientes fases:

**Fase 1:** Diseño del chatbot

**Fase 2:** Desarrollo del chatbot

**Fase 3:** Pruebas del chatbot

**Fase 4:** Despliegue del chatbot

### Tecnologías utilizadas:

- **AWS Lex**
- **AWS Lambda**
- **Node.js**

### Requisitos previos:

- Tener una cuenta de AWS
- Tener conocimientos básicos de AWS Lex
- Tener conocimientos básicos de JavaScript.

[subir](#Índice)

### Licencia:

Este proyecto está licenciado bajo la licencia MIT.

### Autores:

- [José Miguel Escribano Ruiz](https://github.com/JMER15)

- [Virginia Ordoño Bernier](https://github.com/viorbe20)

## Desarrollo del proyecto

### Configuración en AWS

#### 1. Creación del chatbot

- Creamos un nuevo chatbot en blanco y añadimos el nombre.
  
![chatbot_settings_name](img/chatbot_settings_name.png)

- Creamos los permisos correspondientes.
  
![chatbot_settings_permissions](img/chatbot_settings_permissions.png)

- Campo obligatorio de Ley de Protección de la Privacidad Infantil en Internet. En nuestro caso, no es necesario.
  
![chatbot_settings_children_protection](img/chatbot_settings_children_protection.png)

- Configuración del idioma. En nuestro caso, español e inglés.
  
![chatbot_language_settings](img/chatbot_language_settings.png)

#### 2. Creación de los Intents

- Creamos los _intents_ que consideremos. En nuestra caso hemos creado ReservarHabitacion, Saludar.
  
![intents_create](img/intents_create.png)

- Añadimos respuesta inicial.
  
![initial_answer](img/initial_answer.png)

- Agregamos todos los enunciados que están relacionados con ese _intent_. 
  
![intents_utterances](img/intents_utterances.png)

- En algunos casos usaremos _slots_ para definir parámetros como ciudades, cantidades, etc.
   
![slot_example](img/slots_example.png)

![slot_example2](img/slots_example2.png)

- Hemos creado 7 ranuras: tipo de habitación, fecha de entrada, fecha de salida, número de habitaciones, número de personas, ciudad y nombre de la reserva.

- Incluiremos esos slots en algunos de nuestros enunciados.
   
![utterances_with_slots](img/utterances_with_slots.png)

- Configuramos mensajes de confirmación.
  
![confirmation_answers](img/confirmation_answers.png)

- Configuramos el mensaje de cierre.
  
![closing_answer](img/closing_answer.png)

#### 3. Tipos de Slots hay que revisarlo posiblemente haya que borrar.

- Configuramos aquellos slots que tienen diferentes tipos, como es el caso del tipo de habitación.
  
![slot_type_example](img/slot_type_example.png)

- En este caso volvemos a la página inicial de slots, e incluimos el tipo generado anteriormente.
  
![slot_type_example_into_slot](img/slot_type_example_into_slot.png)

#### 4. Creación de los formularios.

- Añadir fórmularios nº de personas por habitación, añadir calendarios para fecha_entrada y salida y añadir cierre de confirmación de reserva y añadir lambda para confirmar la reserva.

![form_room 1](img/formulario_habitacion_1.png)

Deberemos de elegir la ranura tipo de habitación y añadir el tipo de habitación que queremos que se muestre en el formulario.

Elegimos opciones avanzadas y dentro de ahí elegimos más opciones de mensaje.

![form_room 2](img/formulario_habitacion_2.png)

- Agregamos grupo de tarjetas para el formulario.

![form_room 3](img/formulario_habitacion_3.png)

- Ponemos todos lo inputs que queramos con Título del botón y valor del botón, este valor es el valor que se pondrá en el formulario cuando el usuario pulse la opción.

![form_room 4](img/formulario_habitacion_4.png)

- Actualizamos y volvemos a construir el bot. Podemos observar que el formulario funciona bien, como se ve en la imagen siguiente.

![form_room 5](img/formulario_habitacion_5.png)

#### 5. Creación de la Lambda para la confirmación de la reserva.

- Creamos una nueva función Lambda, esta lambda se creará para que haga una recopilación de las opciones que ha ido eligiendo el usuario para que la tenga al final de la reserva, con lo que ha ido seleccionando.

![lambda_create](img/lambda1.png)

- Elegimos rol existente. En nuestro caso el rol es **"LabRole"**.

![lambda_create2](img/lambda2.png)

- Elegiremos node para crear la lambda.

- Añadimos el código de la lambda.

![lambda_create3](img/lambda3.png)

- Añadimos el nombre de la función y la descripción.

![lambda_create4](img/lambda4.png)

- Elegimos **"TestBotAlias"**.

![lambda_create5](img/lambda5.png)

- Elegimos el idioma de la lambda.

![lambda_create6](img/lambda6.png)

- Elegimos nuestra función lambda, y versión $LATEST y guardamos.

![lambda_create7](img/lambda7.png)

- Se lo asignamos al cumplimiento de la resreva del hotel.

![lambda_create8](img/lambda8.png)

Y ya estará creada y asignada la lambda, para recopilar los datos de la reserva, ahora sólo faltaría probarlo.

# TODO 2

### Realiazación de pruebas

En este apartado se realizarán pruebas para comprobar que el chatbot funciona correctamente. Se probarán diferentes escenarios y se documentarán los resultados.

### Pruebas de funcionalidad

#### 1. Prueba de saludo

Se prueban varios salidos y vemos que el chatbot responde correctamente.

![prueba_saludo](img/prueba1.png)

![prueba_saludo2](img/prueba2.png)

#### 2. Prueba de reserva de habitación

Se prueban diferentes escenarios de reserva de habitación y se comprueba que el chatbot responde correctamente. Se harán diferentes preguntas cómo: nº de habitaciones, nº de personas, fecha de entrada y salida, tipo de habitación, etc.

![prueba_reserva](img/prueba3.png)

![prueba_reserva2](img/prueba4.png)

![prueba_reserva3](img/prueba5.png)

![prueba_reserva4](img/prueba6.png)

### Implementación del chatbot en una página web

#### 1. Creación de la página web

- Creamos una página web sencilla con HTML y CSS.
- Añadimos el código de AWS Lex para integrar el chatbot en la página web.
- Subimos la página web a un servidor.
- Probamos la página web y comprobamos que el chatbot funciona correctamente.
- Documentamos el proceso de integración del chatbot en la página web.

Para ello usaremos esta página que nos permite alojar páginas web gratuitamente.

- [kommunicate](https://www.kommunicate.io/)

Nos registramos con nuestro correo y elegimos el rol de estudiante.

Seleccionamos la opción de integración de chatbot.

![kommunicate1](img/bot_integration1.png)

Elegimos la opción Bot Integrations para integrar nuestro bot. Tenemos varias formas de integrarlo como por ejemplo AWS que será nuestra opción, también tenemos DialogFlow ES, OpenAi entre otras.

![kommunicate2](img/bot_integration2.png)

Seleccionamos AWS

![kommunicate3](img/bot_integration3.png)

Seleccionamos AWS Lex v2

![kommunicate4](img/bot_integration4.png)

Necesitaremos una access key y una secret key que nos proporcionara AWS.

![kommunicate5](img/bot_integration5.png)

Para ello deberemos de ir a IAM y ver el rol asignado y de ahí sacamos la access key y la secret key.

![kommunicate6](img/bot_integration6.png)

En nuestro caso este es el rol que se le asigno al crear nuestro rol, porque se le asigno el rol de LabRole.

- **revisar confirmación y cumplimiento con la función lambda** ✅

- **lambda para la confirmación de la reserva** ✅

- **especificar formato fecha YYYY-MM-DD tanto en salida como en entrada** ✅ puesto en el formulario que tiene que introducir fecha formato dd/mm/yyyy

- **¿Implementar ingles?**
- 
- **Sugerencia actividades**