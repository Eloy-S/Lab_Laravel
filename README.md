# Laboratorio #2 - Implementación del Login y Registro en Laravel (Patrón MVC)

Repositorio académico correspondiente al **Laboratorio #2** de la asignatura **Desarrollo Web** de la Facultad de Ingeniería de Sistemas Computacionales (FISC) de la Universidad Tecnológica de Panamá (UTP).

---

## 📋 1. Requisitos Previos y Entorno de Desarrollo

Para la ejecución exitosa de este laboratorio, se configuró el siguiente ecosistema:
* **Servidor Local:** WampServer (Apache y PHP 8.3).
* **Gestor de Dependencias:** Composer.
* **Entorno Frontend:** Node.js y npm (compilación mediante Vite).
* **Base de Datos:** MySQL / MariaDB (motor InnoDB).
* **Editor:** Visual Studio Code.

### Secuencia de Comandos Principales
```bash
# Crear proyecto y entrar a la carpeta
laravel new Proyecto_L
cd Proyecto_L

# Instalar paquete de autenticación y vistas con Bootstrap
composer require laravel/ui --dev
php artisan ui bootstrap --auth

# Instalar dependencias frontend y levantar entorno
npm install
composer run dev
```

## 🏗️ 2. Introducción y Arquitectura MVC
El framework Laravel organiza su estructura bajo el patrón Modelo-Vista-Controlador (MVC):
- Modelos (app/Models): Manejan la lógica de datos y Eloquent ORM.

- Vistas (resources/views): Contienen las interfaces de usuario en archivos Blade (incluyendo las vistas de autenticación).

- Controladores (app/Http/Controllers): Gestionan las peticiones del usuario entre los modelos y las vistas.
   
   Comandos de Base de Datos y Configuración

```Bash
php artisan key:generate
php artisan config:clear
php artisan migrate
```

## 3. Resultados Visibles (Capturas de Pantalla)
A continuación se evidencia el funcionamiento del sistema de Autenticación con Bootstrap:

![Laravel](Img\Capture_laravel.png)

![Vista de Registro (Register)](Img\Capture_register.png)

![Vista de Inicio de Sesión (Login)](Img\Captura_login.png)

## 🗄️4. Configuración de la Base de Datos

- **Archivo `.env`:** Configurado para apuntar al servidor local y la base de datos `Proyecto_L`:
    
    Fragmento de código
    
    ```
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=nombre_de_tu_base_de_datos
    DB_USERNAME=tu_usuario_db
    DB_PASSWORD=tu_contraseña_segura
    ```
    
- **Migraciones:** Se ejecutaron correctamente para desplegar las tablas de usuarios y sesiones en phpMyAdmin

## ⚠️5. Dificultades Encontradas y Soluciones

    Dificultad: Error MissingAppKeyException al cargar la página por primera vez.

        Solución: Se generó la llave de encripción ejecutando php artisan key:generate y limpiando la caché con php artisan config:clear.

    Dificultad: Falta del archivo .env inicial en el directorio raíz del proyecto al clonar o crear la estructura base.

        Solución: Se configuró el archivo .env manual con las credenciales correctas de conexión a la base de datos local de WampServer.


## 6. Referencias Bibliográficas

    Documentación Oficial de Laravel. Installation & Database Migrations. https://laravel.com/docs.

    Guía de Laboratorio Oficial UTP. Desarrollo Web: Patrón MVC y Autenticación en Laravel. Ing. Irina Fong, 2026

## 7. Footer del Estudiante

Este laboratorio ha sido desarrollado por el estudiante de la Universidad Tecnológica de Panamá:

    Nombre: Eloy Samaniego

    Correo Institucional: [eloy.samaniego@utp.ac.pa]

    Curso: Desarrollo Web

    Instructor del Laboratorio: Ing. Irina Fong