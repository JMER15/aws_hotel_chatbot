https://www.youtube.com/watch?v=RB8yw2nzA2Q
# AWS HOTEL CHATBOT

## Contenidos

### Configuración en AWS

#### 1. Configuración del chatbot

- Creamos un nuevo chatbot en blanco y añadimos el nombre.
  
![chatbot_settings_name](img/chatbot_settings_name.png)

- Activamos los permisos correspondientes.
  
![chatbot_settings_permissions](img/chatbot_settings_permissions.png)

- Campo obligatorio de Ley de Protección de la Privacidad Infantil en Internet 
  
![chatbot_settings_children_protection](img/chatbot_settings_children_protection.png)

- Configuración del idioma. En nuestro caso, español e inglés.
  
![chatbot_language_settings](img/chatbot_language_settings.png)

#### 2. Creación de los Intents

- Creamos los _intents_ que consideremos. 
  
![intents_create](img/intents_create.png)

- Añadimos respuesta inicial.
  
![initial_answer](img/initial_answer.png)

- Agregamos todos los enunciados que están relacionados con ese _intent_. 
  
![intents_utterances](img/intents_utterances.png)

- En algunos casos usaremos _slots_ para definir parámetros como ciudades, cantidades, etc.
   
![slot_example](img/slots_example.png)

- Incluiremos esos slots en algunos de nuestros enunciados.
   
![utterances_with_slots](img/utterances_with_slots.png)

- Configuramos mensajes de confirmación.
  
![confirmation_answers](img/confirmation_answers.png)

- Configuramos el mensaje de cierre.
  
![closing_answer](img/closing_answer.png)

#### 3. Tipos de Slots hay que revisarlo posiblemente haya que borrar.

- Configuramos aquellos slots que tienen diferentes tipos, como es el caso del tipo de habitación.
  
![slot_type_example](img/slot_type_example.png)

- En este caos volvemos a la página inicial de slots, e incluimos el tipo generado anteriormente.
  
![slot_type_example_into_slot](img/slot_type_example_into_slot.png)

## TODO

#### 4. Creación de los formularios.

- Añadir fórmularios nº de personas por habitación, añadir calendarios para fecha_entrada y salida y añadir cierre de confirmación de reserva y añadir lambda para confirmar la reserva.

**Implementación del formulario.** falta revisar fechas

![form_room 1](img/formulario_habitacion_1.png)

Deberemos de elegir la ranura tipo de habitación y añadir el tipo de habitación que queremos que se muestre en el formulario.

Elegimos opciones avanzadas.

![form_room 2](img/formulario_habitacion_2.png)

![form_room 3](img/formulario_habitacion_3.png)

![form_room 4](img/formulario_habitacion_4.png)

![form_room 5](img/formulario_habitacion_5.png)

#### 5. Creación de la Lambda para la confirmación de la reserva.

- Creamos una nueva función Lambda.

![lambda_create](img/lambda1.png)

![lambda_create2](img/lambda2.png)

![lambda_create3](img/lambda3.png)

![lambda_create4](img/lambda4.png)

![lambda_create5](img/lambda5.png)

![lambda_create6](img/lambda6.png)

![lambda_create7](img/lambda7.png)

![lambda_create8](img/lambda8.png)

**crear intent pagar habitación**
**revisar confirmación y cumplimiento**
**lambda para la confirmación de la reserva** hecho
**especificar formato fecha YYYY-MM-DD**
**buscar inglés**