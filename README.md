# 🧪 API Stand Tests
### Automatización de pruebas de API · QA Engineering · TripleTen

Validación del campo `firstName` en una API de creación de usuarios mediante pruebas automatizadas con **Python y pytest**.

**10 casos de prueba** · **Valores límite** · **Casos positivos y negativos**

---

## 🎯 Objetivo

Comprobar cómo responde la API al crear usuarios con nombres válidos, inválidos y valores límite. Las pruebas verifican códigos HTTP, mensajes de error y datos de la respuesta.

## 🛠️ Herramientas y técnicas

| Herramientas | Técnicas |
|---|---|
| Python y pytest | Automatización de pruebas de API |
| Respuestas HTTP y JSON | Validación de códigos y mensajes |
| Funciones auxiliares | Clases de equivalencia y valores límite |

## 🔎 Cobertura de pruebas

| Caso | Dato utilizado | Respuesta esperada |
|---|---|---|
| Longitud mínima válida | 2 caracteres | HTTP `201` |
| Longitud máxima válida | 15 caracteres | HTTP `201` |
| Debajo del mínimo | 1 carácter | HTTP `400` |
| Encima del máximo | 16 caracteres | HTTP `400` |
| Nombre con espacios | `"A Aaa"` | HTTP `400` |
| Símbolos especiales | Combinación de símbolos | HTTP `400` |
| Dígitos como texto | `"123"` | HTTP `400` |
| Campo ausente | Sin `firstName` | HTTP `400` |
| Campo vacío | `""` | HTTP `400` |
| Tipo de dato incorrecto | Número `12` | HTTP `400` |

### Comprobaciones adicionales

- **Casos positivos:** token de autenticación no vacío y registro del usuario presente una sola vez en la tabla consultada.
- **Casos negativos:** código y mensaje de error en los casos que incluyen estas comprobaciones.

## 👩‍💻 Mi contribución

Implementé las pruebas del campo `firstName` y las funciones auxiliares para preparar los datos y comprobar las respuestas.

Organicé los casos positivos y negativos para verificar tanto la creación de usuarios como el manejo de datos inválidos.

## 📂 Estructura del proyecto

| Archivo | Función |
|---|---|
| `create_user_test.py` | Pruebas automatizadas y funciones de comprobación |
| `sender_stand_request.py` | Solicitudes a la API |
| `data.py` | Datos para las solicitudes |
| `configuration.py` | Configuración de conexión al servidor |

## ▶️ Cómo ejecutar las pruebas

### 1. Clonar el repositorio

```bash
git clone https://github.com/IsmeraiToledo/api_stand_tests.git
cd api_stand_tests
```

### 2. Instalar las dependencias

```bash
pip install pytest requests
```

### 3. Configurar el entorno

Actualizar la dirección del servidor en `configuration.py`.

El entorno de la API debe estar activo y accesible antes de ejecutar las pruebas.

### 4. Ejecutar

```bash
pytest -v create_user_test.py
```

## 📋 Alcance y resultados

La suite contiene **10 casos automatizados** centrados en la validación del nombre durante la creación de usuarios.

La tabla de cobertura muestra las respuestas esperadas. Para confirmar los resultados obtenidos, es necesario ejecutar las pruebas contra un servidor activo.

---

Desarrollado por **Ismerai Toledo Contreras** durante su formación en QA Engineering en **TripleTen**.
