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

#### 2. Intents
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

- Configuramos mensajes de confirmación
![confirmation_answers](img/confirmation_answers.png)

- Configuramos el mensaje de cierre
![closing_answer](img/closing_answer.png)

#### 3. Tipos de Slots

- Configuramos aquellos slots que tienen diferentes tipos, como es el caso del tipo de habitación
![slot_type_example](img/slot_type_example.png)

- En este caos volvemos a la página inicial de slots, e incluimos el tipo generado anteriormente
![slot_type_example_into_slot](img/slot_type_example_into_slot.png)