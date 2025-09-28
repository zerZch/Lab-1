
Introducción

Este laboratorio tuvo como objetivo implementar un módulo de Login y Registro en Laravel aplicando la arquitectura MVC (Modelo-Vista-Controlador).
Se documentan los pasos de instalación, configuración, migración de base de datos, y generación del scaffolding de autenticación.

Requisitos Previos

Sistema Operativo: Windows 10/11

Servidor local: WampServer (Apache + MySQL/MariaDB)

PHP: 7.4.33

Composer: 2.8.11

Laravel: 8.x

Node.js: v23.9.0

npm: 10.9.2

Editor recomendado: Visual Studio Code

Iconos de tecnologías: PHP 🐘, Composer 🎼, Laravel 🔴, MySQL 🗄️, Node.js 🟢, npm 📦

📂 Arquitectura MVC en Laravel

Models (app/Models): representan la lógica de datos (ej. User.php).

Views (resources/views): contienen la interfaz de usuario en Blade.

Controllers (app/Http/Controllers): manejan la lógica de negocio.

Routes (routes/web.php): definen las URL y acciones correspondientes.

🖥️ Flujo de Comandos Utilizados
# Crear proyecto Laravel 8
composer create-project laravel/laravel:"^8.0" lab2

# Configuración de entorno
copy .env.example .env
php artisan key:generate

# Migraciones
php artisan migrate

# Paquete de autenticación
composer require laravel/ui:"^3.0"
php artisan ui bootstrap --auth

# Instalación frontend
npm install
npm run dev

# Servidor de desarrollo
php artisan serve

🗄️ Base de Datos

Gestor: MySQL (phpMyAdmin en WampServer).

Base creada: lab2 con cotejamiento utf8mb4_unicode_ci.

Migraciones ejecutadas: tablas users, password_resets, failed_jobs, personal_access_tokens.

Archivo .env configurado con:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=lab2
DB_USERNAME=root
DB_PASSWORD=


Backup: exportado desde phpMyAdmin y guardado en /database/backups/lab2.sql.

📸 Evidencia de Resultados

Inserta aquí capturas de pantalla de:

Página principal de Laravel (http://127.0.0.1:8000).

Formulario de Register.

Usuario creado en la tabla users dentro de phpMyAdmin.

⚠️ Dificultades y Soluciones

Error: Specified key was too long (1071) en migraciones.
Solución: agregar Schema::defaultStringLength(191) en AppServiceProvider.php.

Error: Could not open input file: artisan.
Solución: ejecutar comandos dentro de la carpeta del proyecto (lab2).

Conflictos con npm por Node 23.
Solución: usar npm install --legacy-peer-deps.

📚 Referencias

Documentación oficial Laravel

WampServer

phpMyAdmin Docs

✍️ Footer
Este laboratorio ha sido desarrollado por el estudiante de la Universidad Tecnológica de Panamá:

Nombre: David Pimentel 
Correo: david.pimentel3@utp.ac.pa
Curso: Ingeniería Web - Grupo 1SF132  
Instructor del Laboratorio: Ing. Irina Fong  

Fecha de Ejecución: septiembre 28 del 2025 
