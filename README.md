# SISTEMA PQR - Backend

Desarrollado por: Juan Felipe Londoño Gaviria

## Contenido:

```bash
# POST - Crear nueva solicitud
# GET - Obtener todas las solicitudes
# GET - Obtener la solicitud del id específico.
# PUT - Responder solicitud (Proceso manual - Colección de Postman cargada en el repo)
# PUT - Reclamar
# PUT - Responder Reclamo (Proceso manual - Colección de Postman cargada en el repo)
# PUT - Nivel de Satisfacción de Respuesta obtenida
```

## Herramientas

``` bash
# Node JS
# Express
# MongoDB
```

## Modelo de Datos

``` python
{
  ":id": {"type": "integer"}, #Código Radicado Único - String con Key única
  "user": {"type": "string"},
  "date": {"type": "string"},
  "details": {
    "type": "object",
    "properties": {
        "solicitud": {
            "type": {"type": "string"}, #P - Petición, Q - Quejas  
            "subject": {"type": "string"},
            "description": {"type": "string"},
            "status": {"type": "boolean"}, #TRUE: Revisado, FALSE: No Revisado,
        },
        "reply" : { #SI STATUS = TRUE se hace append de Response con el contenido de la respuesta
            "description": {"type": "string"},
        },
        "isSatisfied": {"type": "boolean"} #TRUE: Cliente satisfecho, FALSE: No satisfecho.
    }
  },
  "claim": { 
        "type": "object",
        "properties" : {
            "claim": {
                "subject": {"type": "string"},
                "description": {"type": "boolean"},
                "status": {"type": "boolean"}, #TRUE: Revisado, FALSE: No Revisado,
            },
            "reply": {
                "description": {"type": "string"}
            }
        }
    }
}

```
