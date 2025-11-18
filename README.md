# OSMIO - Sistema de Gestión de Citas Médicas

![OSMIO Logo](img/logo_osmio.png)

## 📋 Descripción del Proyecto

**OSMIO** es una aplicación web desarrollada para la gestión integral de citas médicas, diseñada como solución digital para el bienestar y la salud. El sistema permite a los usuarios registrarse, gestionar sus citas médicas de manera eficiente y mantener un historial organizado de sus consultas.

Este proyecto forma parte del módulo **DAW II - Bloque 1** y ha sido desarrollado siguiendo las mejores prácticas de desarrollo web, utilizando tecnologías modernas y un enfoque profesional en la experiencia de usuario.

## ✨ Características Principales

### 🔐 Sistema de Autenticación
- **Registro de usuarios**: Formulario de registro con validación de datos
- **Inicio de sesión**: Autenticación segura mediante correo electrónico y contraseña
- **Gestión de sesiones**: Control de acceso mediante sesiones PHP
- **Cierre de sesión**: Funcionalidad para cerrar sesión de forma segura

### 📅 Gestión de Citas Médicas
- **Registro de citas**: Formulario intuitivo para crear nuevas citas médicas
- **Visualización de citas**: Listado de todas las citas del usuario autenticado
- **Ordenamiento automático**: Las citas se ordenan automáticamente por fecha y hora
- **Eliminación de citas**: Posibilidad de eliminar citas pasadas
- **Validación de datos**: Verificación de duplicados y validación de campos

### 🎨 Interfaz de Usuario
- **Diseño moderno**: Interfaz desarrollada con Tailwind CSS
- **Responsive**: Diseño adaptable a diferentes tamaños de pantalla
- **Experiencia de usuario**: Formularios intuitivos y mensajes de feedback claros
- **Navegación intuitiva**: Menú de navegación con indicadores de página activa

## 🛠️ Tecnologías Utilizadas

### Backend
- **PHP 7.4+**: Lenguaje de programación del lado del servidor
- **Sesiones PHP**: Gestión de autenticación y estado de usuario
- **XML**: Almacenamiento de datos estructurado (usuarios y citas)
- **SimpleXML**: Manipulación de archivos XML
- **DOMDocument**: Procesamiento avanzado de XML para operaciones complejas

### Frontend
- **HTML5**: Estructura semántica de las páginas
- **Tailwind CSS**: Framework CSS utility-first para diseño moderno
- **JavaScript**: Interactividad del lado del cliente (via CDN)
- **Flaticon**: Iconos y elementos visuales

### Almacenamiento
- **Archivos XML**: 
  - `usuarios.xml`: Base de datos de usuarios registrados
  - `citas.xml`: Base de datos de citas médicas

## 📁 Estructura del Proyecto

2526-daw2-bloc1-a12-team-osmio/
│
├── includes/
│ ├── header.php # Cabecera común con navegación
│ ├── footer.php # Pie de página común
│ └── auth.php # Funciones de autenticación
│
├── modules/
│ └── libros.php # Módulo de libros (en desarrollo)
│
├── css/
│ └── style.css # Estilos personalizados
│
├── img/
│ ├── logo_osmio.png # Logo principal
│ └── [redes sociales] # Iconos de redes sociales
│
├── citas.php # Formulario de registro de citas
├── citas.proc.php # Procesamiento de registro de citas
├── citas_mostrar.php # Visualización de citas del usuario
├── citas_mostrar.proc.php # Lógica de filtrado de citas
├── citas_delete.proc.php # Eliminación de citas
│
├── login.php # Formulario de inicio de sesión
├── login.proc.php # Procesamiento de autenticación
├── register.php # Formulario de registro
├── register.proc.php # Procesamiento de registro
├── logout.php # Cierre de sesión
│
├── usuarios.xml # Base de datos de usuarios
├── citas.xml # Base de datos de citas
│
└── README.md # Este archivo


## 🚀 Instalación y Configuración

### Requisitos Previos
- Servidor web (Apache, Nginx, o XAMPP)
- PHP 7.4 o superior
- Extensiones PHP habilitadas:
  - `simplexml`
  - `dom`
  - `session`

### Pasos de Instalación

1. **Clonar el repositorio**
  
   git clone [url-del-repositorio]
   cd 2526-daw2-bloc1-a12-team-osmio
   
2. **Configurar el servidor web**
   - Colocar el proyecto en el directorio `htdocs` de XAMPP o en la raíz del servidor web
   - Asegurarse de que el servidor web tenga permisos de lectura/escritura en el directorio

3. **Permisos de archivos**
   
   chmod 666 usuarios.xml
   chmod 666 citas.xml
      O crear los archivos XML vacíos si no existen:
   <?xml version="1.0"?>
   <usuarios/>
   
   <?xml version="1.0"?>
   <citas/>
   4. **Acceder a la aplicación**
   - Abrir el navegador y dirigirse a: `http://localhost/2526-daw2-bloc1-a12-team-osmio/`
   - O según la configuración de tu servidor local

## 📖 Uso de la Aplicación

### Para Usuarios

1. **Registro**
   - Acceder a la página de registro
   - Completar el formulario con nombre, correo electrónico y contraseña
   - El sistema validará que el correo no esté duplicado

2. **Inicio de Sesión**
   - Ingresar correo electrónico y contraseña
   - El sistema validará las credenciales y creará una sesión

3. **Gestionar Citas**
   - **Crear cita**: Acceder a "Citas" → "Registrar Cita Médica"
   - Completar fecha, hora, título y descripción
   - Las citas se ordenan automáticamente por fecha y hora
   - **Ver citas**: Las citas se muestran ordenadas cronológicamente
   - **Eliminar cita**: Disponible para citas pasadas mediante botón de eliminación

### Para Desarrolladores

#### Estructura de Datos XML

**usuarios.xml**
<?xml version="1.0"?>
<usuarios>
  <usuario>
    <nombre>Juan Pérez</nombre>
    <correo>juan@example.com</correo>
    <contrasena_md5>hash_md5</contrasena_md5>
  </usuario>
</usuarios>**citas.xml**
<?xml version="1.0"?>
<citas>
  <cita>
    <usuario_email>juan@example.com</usuario_email>
    <fecha>2025-11-20</fecha>
    <hora>10:30</hora>
    <titulo>Consulta General</titulo>
    <descripcion>Revisión anual</descripcion>
  </cita>
</citas>## 🔒 Seguridad

- **Contraseñas**: Almacenadas con hash MD5 (considerar migración a algoritmos más seguros en producción)
- **Validación de sesiones**: Verificación de autenticación en cada página protegida
- **Sanitización de datos**: Uso de `htmlspecialchars()` para prevenir XSS
- **Validación de entrada**: Verificación de datos antes de procesar

## 🎯 Funcionalidades Implementadas

- ✅ Sistema de registro e inicio de sesión
- ✅ Gestión completa de citas médicas (CRUD)
- ✅ Ordenamiento automático de citas por fecha/hora
- ✅ Filtrado de citas por usuario autenticado
- ✅ Eliminación de citas pasadas
- ✅ Validación de duplicados
- ✅ Interfaz responsive con Tailwind CSS
- ✅ Mensajes de feedback al usuario
- ✅ Manejo de errores y validaciones

## 🚧 Próximas Mejoras

- [ ] Módulo de libros completamente funcional
- [ ] Migración de MD5 a algoritmos de hash más seguros (bcrypt, Argon2)
- [ ] Implementación de base de datos relacional (MySQL/PostgreSQL)
- [ ] Sistema de notificaciones por email
- [ ] Calendario visual de citas
- [ ] Exportación de citas a PDF
- [ ] Búsqueda y filtros avanzados
- [ ] Panel de administración

## 👥 Equipo de Desarrollo

**Team OSMIO** - DAW II Bloque 1

Este proyecto ha sido desarrollado como parte del aprendizaje en Desarrollo de Aplicaciones Web.

## 📝 Licencia

Este proyecto es de carácter educativo y forma parte del módulo DAW II - Bloque 1.

## 📧 Contacto

- **Correo**: osmio@corporation.com
- **Dirección**: Carrer 55 Gracia 08016, Barcelona - España

## 🙏 Agradecimientos

Agradecemos a todos los colaboradores y al equipo docente por su apoyo durante el desarrollo de este proyecto.

---

**OSMIO** - Tu compañero digital para el bienestar integral: salud, mente y conocimiento.

*Copyright 2025 - Proyecto Osmio - Daw II*
