Funcionalidades del motor de requerimientos:

Tipos de notificaciones: 
    ¿Qué eventos generan notificaciones? 
    (e.g., reservación confirmada, cancelación,
     recordatorios de partidos).
    Notificación inmediata
        -> X se anotó al partido.
        -> X creó un partido para Y fecha.
        -> X se bajó del partido.
        -> X se agregó al grupo por invitación de Y.
    Notificación programada (recordatorios)
        -> Faltan X jugadores y Y días para el partido
        -> X se juega(Mañana se juega!)


Canales de notificación: 
    ¿Cómo se enviarán las notificaciones? 
    (e.g., correo electrónico, SMS, notificaciones push).
    Push notifications

Usuarios destinatarios: 
    ¿Quiénes recibirán las notificaciones? 
    (e.g., jugadores, administradores de canchas).
    Destinatarios (Depende de la notificación)
        -> Jugador
        -> Equipo
        -> Grupo

Personalización: 
    ¿Se podrán personalizar las notificaciones? 
    (e.g., mensajes personalizados según el tipo de usuario).
        -> Existirá una manera de enviar 
        un mensaje custom a un usuario específico


Especificación API
Definir la API con especificaciones OpenAPI/Swagger. Esto incluiría:

Endpoints: 
Crear endpoints para enviar, programar, y gestionar notificaciones.

    Enviar:
    POST: 
    /api/v1/notifications

    Body type: Notification
    Response type: 202 Accepted (Ya que será asincrono)
    A futuro
        Headers -> Authorization (JWT)

Modelos de datos: 
Definir los modelos de datos para las solicitudes y respuestas (e.g., estructuras de datos para una notificación).
    
    Commons
        Message
        {
            "id":"",
            "message_type": MESSAGE_TYPE,
            "content": Json Body
            "trace_id": number
        }
    
    Entities
        NotificationStructure
        {
            "id":"",
            "title": "",
            "body": "",
            "notificationType": NotificationType
        }
        Notification
        {
            "id":"",
            "status": NOTIFICATION_STATUS,
            "title":"",
            "body": ""
        }