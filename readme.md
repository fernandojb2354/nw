# B2B Order Management System - Prueba Técnica

Esta es una arquitectura de microservicios diseñada para gestionar pedidos B2B, utilizando una estrategia de orquestación mediante una función Lambda.

## 🚀 Arquitectura
- **Microservicios:** Express.js corriendo en contenedores Docker.
- **Orquestador:** AWS Lambda (emulado localmente con Serverless Offline).
- **Base de Datos:** MySQL 8.0.
- **Validación:** Zod para esquemas de datos.
- **Resiliencia:** Implementación de Idempotency Key y Correlation ID.

## 🛠️ Cómo ejecutar el proyecto
1. **Infraestructura:** En la raíz, ejecuta:
   `docker-compose up --build`
2. **Orquestador:** En una nueva terminal, entra a `/lambda-orchestrator` y ejecuta:
   `npx serverless offline`

## 🧪 Pruebas (Postman)
1. **Crear Cliente:** `POST http://localhost:3001/customers`
2. **Crear Orden (Orquestador):** `POST http://localhost:3000/dev/orchestrator/create-and-confirm-order`