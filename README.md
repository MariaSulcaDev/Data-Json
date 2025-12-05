# Documentación de Ejemplos API - SIGEI

## 🌐 URLs de Swagger - Acceso Directo

| Microservicio | Swagger UI | Puerto |
|---------------|------------|---------|
| 🏢 **Institution Management** | [🔗 Abrir Swagger](https://musical-couscous-69v9q7g576gpfr6pw-9080.app.github.dev/swagger-ui.html) | 9080 |
| 🎓 **Students** | [🔗 Abrir Swagger](https://musical-couscous-69v9q7g576gpfr6pw-9081.app.github.dev/swagger-ui/index.html) | 9081 |
| 👥 **Users Management** | [🔗 Abrir Swagger](https://musical-couscous-69v9q7g576gpfr6pw-9083.app.github.dev/swagger-ui/index.html) | 9083 |
| 📚 **Academic Management** | [🔗 Abrir Swagger](https://musical-couscous-69v9q7g576gpfr6pw-9084.app.github.dev/swagger-ui.html) | 9084 |
| 👨‍🏫 **Teacher Assignment** | [🔗 Abrir Swagger](https://musical-couscous-69v9q7g576gpfr6pw-9099.app.github.dev/swagger-ui.html) | 9099 |

### 📡 URLs Base de APIs

- 🏢 **Institution:** `https://musical-couscous-69v9q7g576gpfr6pw-9080.app.github.dev`
- 🎓 **Students:** `https://musical-couscous-69v9q7g576gpfr6pw-9081.app.github.dev`
- 👥 **Users:** `https://musical-couscous-69v9q7g576gpfr6pw-9083.app.github.dev`
- 📚 **Academic:** `https://musical-couscous-69v9q7g576gpfr6pw-9084.app.github.dev`
- 👨‍🏫 **Teachers:** `https://musical-couscous-69v9q7g576gpfr6pw-9099.app.github.dev`

---

Este documento contiene ejemplos de payloads JSON para probar los endpoints de los microservicios en Swagger.

## 1. Microservicio de Usuarios (`vg-ms-users-management`)

### Crear Usuario (POST /api/v1/users)

**Nota:** El `userId` se genera automáticamente si no se envía, o se puede enviar si se requiere uno específico (dependiendo de la implementación de la BD).

```json
{
  "institutionId": "64a1f2b3e4b0a1b2c3d4e5f6",
  "firstName": "Juan Carlos",
  "lastName": "Pérez López",
  "documentType": "DNI",
  "documentNumber": "12345678",
  "phone": "987654321",
  "address": "Av. Los Álamos 123, Lima",
  "email": "juan.perez@vallegrande.edu.pe",
  "userName": "jperez",
  "role": "PROFESOR",
  "status": "ACTIVE"
}
```

### Listar Usuarios por Rol y Estado (GET /api/v1/users/role/{role}/status/{status})

**Ejemplo:** `/api/v1/users/role/PROFESOR/status/ACTIVE`

Respuesta exitosa:

```json
{
  "message": "Usuarios con rol PROFESOR y estado ACTIVE obtenidos exitosamente",
  "data": [
    {
      "userId": "user-profesor-001",
      "firstName": "Juan Carlos",
      "lastName": "Pérez López",
      "role": "PROFESOR",
      "status": "ACTIVE",
      ...
    }
  ]
}
```

### Actualizar Usuario (PUT /api/v1/users/{id})

```json
{
  "institutionId": "64a1f2b3e4b0a1b2c3d4e5f6",
  "firstName": "Juan Carlos",
  "lastName": "Pérez López",
  "documentType": "DNI",
  "documentNumber": "12345678",
  "phone": "999888777",
  "address": "Av. Las Palmeras 456, Lima",
  "email": "juan.perez.updated@vallegrande.edu.pe",
  "userName": "jperez",
  "role": "PROFESOR",
  "status": "ACTIVE"
}
```

---

## 2. Microservicio de Estudiantes (`vg-ms-students`)

### Crear Estudiante (POST /api/v1/students)

```json
{
  "cui": "20250001",
  "personalInfo": {
    "names": "Mateo Alejandro",
    "lastNames": "Gómez Sánchez",
    "documentType": "DNI",
    "documentNumber": "87654321",
    "gender": "MASCULINO",
    "dateOfBirth": "15/05/2019"
  },
  "address": "Jr. Los Olivos 789, Lima",
  "photoPerfil": "https://example.com/photos/student_20250001.jpg",
  "institutionId": "64a1f2b3e4b0a1b2c3d4e5f6",
  "classroomId": "64b2c3d4e5f6a7b8c9d0e1f2",
  "developmentInfo": {
    "birthType": "normal",
    "complications": "ninguna",
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
      "relationship": "PADRE",
      "names": "Carlos",
      "lastNames": "Gómez",
      "phone": "987123456",
      "documentType": "DNI",
      "documentNumber": "11223344"
    },
    {
      "relationship": "MADRE",
      "names": "Ana",
      "lastNames": "Sánchez",
      "phone": "987654123",
      "documentType": "DNI",
      "documentNumber": "55667788"
    }
  ],
  "healthInfo": {
    "controls": [],
    "healthStatus": "Saludable",
    "illnesses": "Ninguna",
    "vaccines": "Completas según calendario"
  }
}
```

### Actualizar Estudiante (PUT /api/v1/students/{id})

```json
{
    "studentId": "69328014a6a200cbfbe833c5",
    "cui": "20250001",
    "personalInfo": {
      "names": "Mateo Alejandro",
      "lastNames": "Gómez Sánchez",
      "documentType": "DNI",
      "documentNumber": "87654321",
      "gender": "MASCULINO",
      "dateOfBirth": "15/05/2019",
      "age": 6
    },
    "dateOfBirth": null,
    "address": "Jr. Los Olivos 789, Lima",
    "photoPerfil": "https://example.com/photos/student_20250001.jpg",
    "status": "ACTIVE",
    "institutionId": "64a1f2b3e4b0a1b2c3d4e5f6",
    "classroomId": "64b2c3d4e5f6a7b8c9d0e1f2",
    "developmentInfo": {
      "birthType": "normal",
      "complications": "ninguna",
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
        "relationship": "PADRE",
        "names": "Carlos",
        "lastNames": "Gómez",
        "phone": "987123456",
        "documentType": "DNI",
        "documentNumber": "11223344",
        "userId": "69328013bb60cebb4628793a"
      },
      {
        "relationship": "MADRE",
        "names": "Ana",
        "lastNames": "Sánchez",
        "phone": "987654123",
        "documentType": "DNI",
        "documentNumber": "55667788",
        "userId": "69328013bb60cebb4628793b"
      }
    ],
    "healthInfo": {
      "controls": [],
      "healthStatus": "Saludable",
      "illnesses": "Ninguna",
      "vaccines": "Completas según calendario"
    }
}
```

---

## 3. Microservicio de Asignaciones (`vg-ms-teacher-assignment`)

### Crear Asignación (POST /api/v1/teacher-assignments)

```json
{
  "teacherUserId": "68f960c40791bb1b468aa8c3",
  "institutionId": "68fda092d832a694a0c77a87",
  "assignmentType": "REGULAR",
  "startDate": "2025-03-01",
  "endDate": "2025-12-20",
  "notes": "Asignación principal para el año académico 2025",
  "classrooms": [
    {
      "classroomId": "68fda093d832a694a0c77a88",
      "isPrimary": true
    }
  ],
  "schedules": [
    {
      "courseId": "9bac96a4-4f1f-47cf-88e5-5616ff4ca100",
      "dayOfWeek": "MONDAY",
      "startTime": "08:00",
      "endTime": "10:00",
      "classroomId": "68fda093d832a694a0c77a88",
      "sessionType": "MULTI_CLASSROOM",
      "sessionName": "Matemática - Sesión 1",
      "notes": "Aula Principal"
    },
    {
      "courseId": "9bac96a4-4f1f-47cf-88e5-5616ff4ca100",
      "dayOfWeek": "WEDNESDAY",
      "startTime": "10:30",
      "endTime": "12:30",
      "classroomId": "68fda093d832a694a0c77a88",
      "sessionType": "MULTI_CLASSROOM",
      "sessionName": "Comunicación - Sesión 1",
      "notes": "Aula Principal"
    }
  ]
}
```

### Actualizar Asignación (PUT /api/v1/teacher-assignments/{id})

ID = 995017f4-0590-41c4-9a47-c6573cf1e96f

```json
{
  "teacherUserId": "68f960c40791bb1b468aa8c3",
  "institutionId": "68fda092d832a694a0c77a87",
  "assignmentType": "REGULAR",
  "startDate": "2025-03-01",
  "endDate": "2025-12-20",
  "notes": "Asignación principal para el año académico 2025",
  "classrooms": [
    {
      "classroomId": "68fda093d832a694a0c77a88",
      "isPrimary": true
    }
  ],
  "schedules": [
    {
      "courseId": "9bac96a4-4f1f-47cf-88e5-5616ff4ca100",
      "dayOfWeek": "MONDAY",
      "startTime": "09:30",
      "endTime": "10:00",
      "classroomId": "68fda093d832a694a0c77a88",
      "sessionType": "MULTI_CLASSROOM",
      "sessionName": "Matemática - Sesión 1",
      "notes": "Aula Principal"
    },
    {
      "courseId": "9bac96a4-4f1f-47cf-88e5-5616ff4ca100",
      "dayOfWeek": "WEDNESDAY",
      "startTime": "10:30",
      "endTime": "12:30",
      "classroomId": "68fda093d832a694a0c77a88",
      "sessionType": "MULTI_CLASSROOM",
      "sessionName": "Comunicación - Sesión 1",
      "notes": "Aula Principal"
    }
  ]
}
```
