# 🚀 API de Usuarios en PHP

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=for-the-badge&logo=php)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg?style=for-the-badge)

Una API RESTful sencilla desarrollada en PHP puro para realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre una tabla de usuarios.

## ✨ Características

-   **Listar todos los usuarios:** Obtiene una lista completa de los usuarios registrados.
-   **Obtener usuario por ID:** Consulta la información de un usuario específico.
-   **Crear nuevo usuario:** Registra un nuevo usuario en la base de datos.
-   **Actualizar usuario:** Modifica los datos de un usuario existente.
-   **Eliminar usuario:** Borra un usuario de la base de datos.

---

## 🔧 Instalación y Puesta en Marcha

Para poder ejecutar esta API localmente, necesitas un entorno de servidor como **XAMPP**.

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/usersAPI-php.git](https://github.com/tu-usuario/usersAPI-php.git)
    ```

2.  **Mover a `htdocs`:**
    Copia la carpeta del proyecto dentro de la carpeta `htdocs` de tu instalación de XAMPP. Para que los endpoints de ejemplo funcionen directamente, la ruta debería quedar así:
    `C:/xampp/htdocs/apis/apirest/`

3.  **Configurar la Base de Datos:**
    -   Inicia los servicios de **Apache** y **MySQL** desde el panel de control de XAMPP.
    -   Abre `phpMyAdmin` (usualmente en `http://localhost/phpmyadmin`).
    -   Crea una nueva base de datos. Puedes llamarla `users_test`.
    -   Selecciona la base de datos recién creada y ve a la pestaña **Importar**.
    -   Sube el archivo `users_test.sql` que se encuentra en la carpeta `BD script` del proyecto.

4.  **Verificar Conexión:**
    Revisa que las credenciales de la base de datos en `api/config/Database.php` coincidan con tu configuración local. Por defecto, XAMPP suele usar `root` como usuario y sin contraseña.

¡Y listo! La API ya debería estar operativa.

---

## 📚 Endpoints de la API

La URL base para esta API es: `http://localhost/apis/apirest/api`

### `GET` /users
Consulta todos los usuarios registrados.

-   **URL:** `http://localhost/apis/apirest/api/users`
-   **Respuesta Exitosa (200):**
    ```json
    [
        {
            "id": "1",
            "name": "Juan Perez",
            "document": "12345678",
            "age": "30",
            "phone": "3101234567",
            "address": "Calle Falsa 123"
        },
        {
            "id": "2",
            "name": "Ana Gomez",
            "document": "87654321",
            "age": "25",
            "phone": "3207654321",
            "address": "Avenida Siempre Viva 742"
        }
    ]
    ```

### `GET` /users/{id}
Consulta un usuario específico por su ID.

-   **URL:** `http://localhost/apis/apirest/api/users/1`
-   **Respuesta Exitosa (200):**
    ```json
    {
        "id": "1",
        "name": "Juan Perez",
        "document": "12345678",
        "age": "30",
        "phone": "3101234567",
        "address": "Calle Falsa 123"
    }
    ```

### `POST` /users
Crea un nuevo usuario. Los datos se envían en el cuerpo (body) de la solicitud en formato JSON.

-   **URL:** `http://localhost/apis/apirest/api/users`
-   **Cuerpo (Body):**
    ```json
    {
        "name": "Carlos Ruiz",
        "document": "11223344",
        "age": 45,
        "phone": "3001112233",
        "address": "Plaza Mayor 10"
    }
    ```
-   **Respuesta Exitosa (201):**
    ```json
    {
        "message": "Usuario creado exitosamente"
    }
    ```

### `PUT` /users/{id}
Actualiza los datos de un usuario existente.

-   **URL:** `http://localhost/apis/apirest/api/users/1`
-   **Cuerpo (Body):**
    ```json
    {
        "phone": "3998887766",
        "address": "Nueva Direccion 456"
    }
    ```
-   **Respuesta Exitosa (200):**
    ```json
    {
        "message": "Usuario actualizado exitosamente"
    }
    ```

### `DELETE` /users/{id}
Elimina un usuario por su ID.

-   **URL:** `http://localhost/apis/apirest/api/users/1`
-   **Respuesta Exitosa (200):**
    ```json
    {
        "message": "Usuario eliminado exitosamente"
    }
    ```

---

## 📂 Estructura del Proyecto

El proyecto está organizado en las siguientes carpetas para separar responsabilidades:
