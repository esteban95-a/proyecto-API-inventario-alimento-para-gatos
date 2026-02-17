#  🐱proyecto-API-inventario-alimento-para-gatos

## Estudiante : Didier Esteban Achuri Lopez

### URL de la API : https://6987785d8bacd1d773ed773c.mockapi.io/api/v1/GATOS/alimento

## 1️⃣ MODELO DE DATOS


- Se configuro el recurso gato con la sigiente estructura
[
  {
    "marca": "agility",
    "tipo": "seco",
    "precio": 45000,
    "personalidad": [
      "juegueton"
    ],
    "descripcion": {
      "tamaño": "500gr",
      "etapa": "adulto"
    },
    "disponible": true,
    "id": "1"
  },
  {
    "marca": "agility",
    "tipo": "seco",
    "precio": 70000,
    "personalidad": [
      "casero"
    ],
    "descripcion": {
      "tamaño": "500gr",
      "etapa": "cachorro"
    },
    "disponible": true,
    "id": "2"
  }
]

## 2️⃣ Operaciones CRUD(postman)

### a) Obtener los registros (GET)

- Status : 200 OK
- Respuesta de postman : 
[
    {
        "marca": "agility",
        "tipo": "seco",
        "precio": 45000,
        "personalidad": [
            "juegueton"
        ],
        "descripcion": {
            "tamaño": "500gr",
            "etapa": "adulto"
        },
        "disponible": true,
        "id": "1"
    },
    {
        "marca": "agility",
        "tipo": "seco",
        "precio": 70000,
        "personalidad": [
            "casero"
        ],
        "descripcion": {
            "tamaño": "500gr",
            "etapa": "cachorro"
        },
        "disponible": true,
        "id": "2"
    }
]


### B) CREACION DE UN NUEVO REGISTRO
- status : 201 Created
- Cuerpo enviado en postman :
{
    "marca": "agility",
    "tipo": "seco",
    "precio": 50000,
    "personalidad": [
      "dominante"
    ],
    "descripcion": {
      "tamaño": "500gr",
      "etapa": "cachorro"
    },
    "disponible": true,
    "id": ""
  }

- Respuesta de postman :
{
    "marca": "agility",
    "tipo": "seco",
    "precio": 50000,
    "personalidad": [
        "dominante"
    ],
    "descripcion": {
        "tamaño": "500gr",
        "etapa": "cachorro"
    },
    "disponible": true,
    "id": "3"
}
###  c) Consulta de registro individual (GET)
- Endpoint : /api/v1/GATOS/alimento/1
- Status : 200 OK
- Respuesta de postman :
{
    "marca": "agility",
    "tipo": "seco",
    "precio": 45000,
    "personalidad": [
        "juegueton"
    ],
    "descripcion": {
        "tamaño": "500gr",
        "etapa": "adulto"
    },
    "disponible": true,
    "id": "1"
}

### d) Acualizacion de un reistro (put)
- Status : 200 OK
- modificacion : precio y tamaño del registro id 1
- Respuesta de postman :
{
    "marca": "Agility",
    "tipo": "seco",
    "precio": 52000,
    "personalidad": [
        "juegueton"
    ],
    "descripcion": {
        "tamaño": "500gr",
        "etapa": "adulto"
    },
    "disponible": true,
    "id": "1",
    "tamaño": "1kg",
    "etapa": "adulto"
}

### e) Eliminacion de un registro
- Status : 200 OK
- Respuesta de postman :
{
    "marca": "Agility",
    "tipo": "seco",
    "precio": 52000,
    "personalidad": [
        "juegueton"
    ],
    "descripcion": {
        "tamaño": "500gr",
        "etapa": "adulto"
    },
    "disponible": true,
    "id": "1",
    "tamaño": "1kg",
    "etapa": "adulto"
}
 ### f)Validacion de recurso inexistente :
- Endpoint : /api/v1/GATOS/alimento/1
- Status : 404Not Found
- Respuesta de postman :
"Not found"

## 3️⃣ RESUMEN DE ENDPOINTS  CODIGOS HTTP
| Operación                   | Método HTTP | Endpoint                      | Descripción                        | Código HTTP       |
| --------------------------- | ----------- | ----------------------------- | ---------------------------------- | ----------------- |
| Obtener todos los registros | GET         | `/api/v1/GATOS/alimento`      | Lista todos los alimentos de gatos | **200 OK**        |
| Obtener registro por ID     | GET         | `/api/v1/GATOS/alimento/{id}` | Devuelve un alimento específico    | **200 OK**        |
| Crear nuevo registro        | POST        | `/api/v1/GATOS/alimento`      | Crea un nuevo alimento             | **201 Created**   |
| Actualizar registro         | PUT         | `/api/v1/GATOS/alimento/{id}` | Modifica un alimento existente     | **200 OK**        |
| Eliminar registro           | DELETE      | `/api/v1/GATOS/alimento/{id}` | Elimina un alimento                | **200 OK**        |
| Recurso inexistente         | GET         | `/api/v1/GATOS/alimento/{id}` | Consulta de un ID eliminado        | **404 Not Found** |




