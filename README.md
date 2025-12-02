# Swagger Guide

This document contains the Swagger URLs for your microservices and the JSON payloads with **real IDs** for testing.

## 1. Swagger URLs

| Microservice | Port | Swagger URL |
| :--- | :--- | :--- |
| **Institution Management** | 9080 | [http://localhost:9080/swagger-ui.html](http://localhost:9080/swagger-ui.html) |
| **Students** | 9081 | [http://localhost:9081/swagger-ui/index.html](http://localhost:9081/swagger-ui/index.html) |
| **Users Management** | 9083 | [http://localhost:9083/swagger-ui/index.html](http://localhost:9083/swagger-ui/index.html) |
| **Academic Management** | 9084 | [http://localhost:9084/swagger-ui.html](http://localhost:9084/swagger-ui.html) |
| **Notes** | 9086 | [http://localhost:9086/swagger-ui.html](http://localhost:9086/swagger-ui.html) |
| **Teacher Assignment** | 9099 | [http://localhost:9099/swagger-ui.html](http://localhost:9099/swagger-ui.html) |

---

## 2. JSON Payloads (with Real IDs)

Use these payloads to test the `students` and `users` services.

### Students Service (`vg-ms-students`)

#### Create Student (POST /api/v1/students)

```json
{
  "cui": "20250002",
  "personalInfo": {
    "names": "Nuevo Estudiante",
    "lastNames": "Con IDs Reales",
    "documentType": "DNI",
    "documentNumber": "70809011",
    "gender": "MASCULINO",
    "dateOfBirth": "15/05/2016"
  },
  "address": "Av. Real 123, Lima",
  "photoPerfil": "https://example.com/photo.jpg",
  "institutionId": "68ffa692b0f5ad304fa6510c",
  "classroomId": "68ffa693b0f5ad304fa6510d",
  "developmentInfo": {
    "birthType": "Normal",
    "complications": "Ninguna",
    "hasAuditoryDisability": false,
    "hasVisualDisability": false,
    "hasMotorDisability": false,
    "otherDisability": "",
    "liftedHeadAt": "3 meses",
    "satAt": "6 meses",
    "crawledAt": "8 meses",
    "stoodUpAt": "10 meses",
    "walkedAt": "12 meses",
    "controlledSphinctersAt": "2 años",
    "spokeFirstWordsAt": "1 año",
    "spokeFluentlyAt": "3 años"
  },
  "guardians": [
    {
      "relationship": "Padre",
      "names": "Carlos",
      "lastNames": "Perez",
      "phone": "999888777",
      "documentType": "DNI",
      "documentNumber": "40506070",
      "userId": "692f32963fba67882b0a16ab"
    }
  ],
  "healthInfo": {
    "controls": [
      {
        "date": "15/01/2025",
        "weight": 35.5,
        "height": 135.0
      }
    ],
    "healthStatus": "Saludable",
    "illnesses": "Ninguna",
    "vaccines": "Completas"
  }
}
```

#### Update Student (PUT /api/v1/students/{id})

**ID to use in URL**: `68ff8ecc7fbd0ce8e3a8e902`

```json
{
  "studentId": "68ff8ecc7fbd0ce8e3a8e902",
  "cui": "1234567890124",
  "personalInfo": {
    "names": "Ana María",
    "lastNames": "González Vásquez",
    "documentType": "DNI",
    "documentNumber": "12345679",
    "gender": "FEMENINO",
    "dateOfBirth": "20/04/2019"
  },
  "address": "Jr. Los Olivos 456, Miraflores, Lima (Actualizado)",
  "photoPerfil": "https://example.com/photos/student124.jpg",
  "institutionId": "68ffa692b0f5ad304fa6510c",
  "classroomId": "68ffa693b0f5ad304fa6510d",
  "developmentInfo": {
    "birthType": "NATURAL",
    "complications": "Ninguna",
    "hasAuditoryDisability": false,
    "hasVisualDisability": false,
    "hasMotorDisability": false,
    "otherDisability": "",
    "liftedHeadAt": "3 meses",
    "satAt": "6 meses",
    "crawledAt": "8 meses",
    "stoodUpAt": "10 meses",
    "walkedAt": "12 meses",
    "controlledSphinctersAt": "2 años",
    "spokeFirstWordsAt": "10 meses",
    "spokeFluentlyAt": "3 años"
  },
  "guardians": [
    {
      "relationship": "PADRE",
      "names": "Roberto Carlos",
      "lastNames": "González Mendoza",
      "phone": "+51987654323",
      "documentType": "DNI",
      "documentNumber": "87654323",
      "userId": "692f32963fba67882b0a16ab"
    }
  ],
  "healthInfo": {
    "controls": [
      {
        "date": "15/01/2024",
        "weight": 18.5,
        "height": 105.0
      }
    ],
    "healthStatus": "Saludable",
    "illnesses": "Ninguna",
    "vaccines": "Esquema completo"
  },
  "status": "ACTIVE"
}
```

### Users Service (`vg-ms-users-management`)

#### Create User (POST /api/v1/users)

```json
{
  "institutionId": "68ffa692b0f5ad304fa6510c",
  "firstName": "Nuevo",
  "lastName": "Profesor",
  "documentType": "DNI",
  "documentNumber": "41239999",
  "phone": "987654321",
  "address": "Jr. Union 100, Lima",
  "email": "nuevo.profesor@example.com",
  "userName": "nprofesor",
  "role": "TEACHER"
}
```

#### Update User (PUT /api/v1/users/{id})

**ID to use in URL**: `68ee548a0daac6689a3bec4c`

```json
{
  "userId": "68ee548a0daac6689a3bec4c",
  "institutionId": "68ffa692b0f5ad304fa6510c",
  "firstName": "Carla",
  "lastName": "Torres (Actualizado)",
  "documentType": "DNI",
  "documentNumber": "36254785",
  "phone": "963852741",
  "address": "AV. Los girasoles 123",
  "email": "carla@gmail.com",
  "userName": "Carla10",
  "role": "AUXILIAR",
  "status": "ACTIVE"
}
```
