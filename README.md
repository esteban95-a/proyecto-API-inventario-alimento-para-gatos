# 🐱 Proyecto API Inventario de Alimento para Gatos

## Estudiante
Didier Esteban Achuri Lopez

## URL de la API
https://6987785d8bacd1d773ed773c.mockapi.io/api/v1/GATOS/alimento

## Tabla de Contenidos
- [1. Modelo de Datos](#1️⃣-modelo-de-datos)
- [2. Operaciones CRUD (Postman)](#2️⃣-operaciones-crud-postman)
  - [a) Obtener los registros (GET)](#a-obtener-los-registros-get)
  - [b) Creación de un nuevo registro](#b-creación-de-un-nuevo-registro)
  - [c) Consulta de registro individual (GET)](#c-consulta-de-registro-individual-get)
  - [d) Actualización de un registro (PUT)](#d-actualización-de-un-registro-put)
  - [e) Eliminación de un registro](#e-eliminación-de-un-registro)
  - [f) Validación de recurso inexistente](#f-validación-de-recurso-inexistente)
- [3. Resumen de Endpoints y Códigos HTTP](#3️⃣-resumen-de-endpoints-y-códigos-http)

## 1️⃣ Modelo de Datos

Se configuró el recurso "gato" con la siguiente estructura:

```json
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
```

## 2️⃣ Operaciones CRUD (Postman)

### a) Obtener los registros (GET)
- **Status**: 200 OK
- **Respuesta de Postman**:

```json
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
```

### b) Creación de un nuevo registro
- **Status**: 201 Created
- **Cuerpo enviado en Postman**:

```json
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
```

- **Respuesta de Postman**:

```json
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
```

### c) Consulta de registro individual (GET)
- **Endpoint**: `/api/v1/GATOS/alimento/1`
- **Status**: 200 OK
- **Respuesta de Postman**:

```json
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
```

### d) Actualización de un registro (PUT)
- **Status**: 200 OK
- **Modificación**: Precio y tamaño del registro ID 1
- **Respuesta de Postman**:

```json
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
```

### e) Eliminación de un registro
- **Status**: 200 OK
- **Respuesta de Postman**:

```json
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
```

### f) Validación de recurso inexistente
- **Endpoint**: `/api/v1/GATOS/alimento/1`
- **Status**: 404 Not Found
- **Respuesta de Postman**:
  ```
  "Not found"
  ```

## 3️⃣ Resumen de Endpoints y Códigos HTTP

| Operación                   | Método HTTP | Endpoint                      | Descripción                        | Código HTTP       |
|-----------------------------|-------------|-------------------------------|------------------------------------|-------------------|
| Obtener todos los registros | GET         | `/api/v1/GATOS/alimento`      | Lista todos los alimentos de gatos | **200 OK**        |
| Obtener registro por ID     | GET         | `/api/v1/GATOS/alimento/{id}` | Devuelve un alimento específico    | **200 OK**        |
| Crear nuevo registro        | POST        | `/api/v1/GATOS/alimento`      | Crea un nuevo alimento             | **201 Created**   |
| Actualizar registro         | PUT         | `/api/v1/GATOS/alimento/{id}` | Modifica un alimento existente     | **200 OK**        |
| Eliminar registro           | DELETE      | `/api/v1/GATOS/alimento/{id}` | Elimina un alimento                | **200 OK**        |
| Recurso inexistente         | GET         | `/api/v1/GATOS/alimento/{id}` | Consulta de un ID eliminado        | **404 Not Found** |




