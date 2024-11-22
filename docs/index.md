# Documentación de la API Currency Exchange

Bienvenido a la documentación técnica de la API **Currency Exchange**. Aquí encontrarás una descripción general de sus capacidades, endpoints disponibles, y detalles técnicos importantes.

---

## **Descripción General**
La API Currency Exchange proporciona las siguientes funcionalidades principales:
- **Crear intenciones de intercambio de divisas**: Generar intenciones para operaciones de intercambio.
- **Procesar operaciones de intercambio de divisas**: Completar transacciones basadas en intenciones previas.

Esta API está diseñada para manejar operaciones seguras y eficientes, con soporte para trazabilidad y validación mediante firmas.

---

## **Ambientes Disponibles**
La API está disponible en los siguientes entornos:

- **Desarrollo:**  
  [https://apidev-account.xxxprueba.cl/api-currency-exchange/v1](https://apidev-account.xxxprueba.cl/api-currency-exchange/v1)

- **QA:**  
  [https://apiqa-account.xxxprueba.cl/api-currency-exchange/v1](https://apiqa-account.xxxprueba.cl/api-currency-exchange/v1)

---

## **Cómo Empezar**

1. **Consulta la especificación completa de Swagger:**
   - La especificación OpenAPI está disponible en la pestaña **API Docs**.
   - Incluye todos los detalles sobre los endpoints, parámetros y ejemplos de solicitudes.

2. **Configura los encabezados requeridos:**
   - **x-user-id:** Identificación del usuario.
   - **x-message-id:** Identificador único de la transacción.

3. **Prueba los endpoints en los entornos de desarrollo o QA.**

---

## **Principales Endpoints**

### **1. Crear Intención de Intercambio**
- **Método:** `POST`  
- **Endpoint:** `/currency-exchange-intent`
- **Descripción:**  
  Este endpoint permite crear una intención de intercambio de divisas. La intención es necesaria para realizar una operación posterior.
- **Encabezados requeridos:**
  - `x-user-id`
  - `x-sender-id`
  - `x-message-id`
- **Códigos de respuesta:**
  - `201`: Intención creada exitosamente.
  - `400`: Solicitud inválida.
  - `500`: Error interno del servidor.

### **2. Procesar Operación de Intercambio**
- **Método:** `POST`  
- **Endpoint:** `/currency-exchange`
- **Descripción:**  
  Completa una operación de intercambio basada en una intención válida.
- **Encabezados requeridos:**
  - `x-sender-id`
  - `x-jws-signature`
  - `x-message-id`
- **Códigos de respuesta:**
  - `201`: Operación completada exitosamente.
  - `400`: Solicitud inválida.
  - `409`: Conflicto (intención ya utilizada).
  - `500`: Error interno del servidor.

---

## **Recursos Importantes**
- **Swagger/OpenAPI:**  
  Consulta la especificación Swagger en la pestaña **API Docs** de Backstage. Incluye toda la información técnica sobre los endpoints y ejemplos de uso.

---

## **Contacto**
Para soporte o preguntas adicionales, contáctanos en:  
[xxxpruebaaccount@xxxprueba.cl](mailto:xxxpruebaaccount@xxxprueba.cl).
