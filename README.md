# 🛒 Sistema de Ventas

**Trabajo Aplicativo Final** – Sistema web desarrollado para la gestión de ventas, productos, clientes, proveedores y usuarios en una tienda. Permite llevar el control del stock, registrar facturas, y consultar ventas por producto.
![Menu principal sisventas](https://github.com/user-attachments/assets/a886dab2-6765-4fe3-9a23-59c4b80a71bc)


---

## ⚙️ Tecnologías Utilizadas

- PHP (Programación Orientada a Objetos)
- MySQL
- HTML y CSS
- JavaScript
- Servidor local: XAMPP
- Universe.io (Diseño de interfaces y prototipos)


---

## 📁 Estructura del Proyecto

El sistema está organizado siguiendo el patrón Modelo - Vista - Controlador (MVC) de forma simplificada. A continuación, se describen las carpetas principales:

sisventas/
├── controlador/ # Controladores que gestionan la lógica de cada módulo
├── includes/ # Configuración general y conexión a base de datos
├── modelo/ # Clases que representan entidades (ej. Producto)
├── vista/ # Archivos de interfaz para cada módulo (CRUD, listados, etc.)
├── index.php # Punto de entrada principal
├── login.php # Pantalla de inicio de sesión
└── logout.php # Cierre de sesión

### 🧭 Módulos del sistema

- **Usuarios**: Registro, edición y control de acceso.
- **Clientes**: Gestión de clientes (crear, editar, eliminar).
- **Proveedores**: Registro y edición de proveedores.
- **Productos**: Control de stock, categorías y CRUD de productos.
- **Ventas**: Registro de ventas, selección de productos, generación de factura.
- **Consultas**: Permite ver ventas por producto y estado del inventario.

Cada módulo tiene su propio controlador (`controlador/`), vistas (`vista/[modulo]/`) y lógica asociada.














