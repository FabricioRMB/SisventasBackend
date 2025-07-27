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

El proyecto está organizado en carpetas que siguen el enfoque de separación lógica de responsabilidades. A continuación se describe cada una de estas:


### 📁 `controlador/`

Contiene todos los controladores del sistema.  
Aquí se gestiona la lógica principal para cada módulo: productos, clientes, proveedores, usuarios, etc.

Dentro tenemos:
- `clienteController.php`
- `productoController.php`
- `usuarioController.php`

---

### 📁 `includes/`

Carpeta donde se encuentra la configuración global del sistema.

Archivos clave:
- `config.php`: contiene constantes como el nombre del host o credenciales de conexión.
- `db.php`: contiene la clase que gestiona la conexión a la base de datos con PDO.

---

### 📁 `modelo/`

Contiene las clases que representan entidades o modelos del sistema, en nuestro caso unicamente esta:
- `producto.php`: contiene atributos y funciones para gestionar productos.

---

### 📁 `vista/`

Es la carpeta que contiene todas las interfaces del sistema (formularios, listados, botones, etc.).  
Está organizada por subcarpetas según el módulo:

- `clientes/`: Vistas para crear, editar y listar clientes.
- `producto/`: Formulario de producto, stock, consulta de ventas.
- `proveedores/`: Mantenimiento de proveedores.
- `usuarios/`: Gestión de usuarios.
- `ventas/`: Registro de ventas, selección de productos.
- `layout/`: Contiene los elementos comunes como cabecera, menú y pie.

---

### 📄 `index.php`

Punto de entrada principal al sistema. Normalmente redirige al login si no hay sesión iniciada.

---

### 📄 `login.php` y `logout.php`

- `login.php`: Página de acceso al sistema con usuario y contraseña.
- `logout.php`: Destruye la sesión activa y redirige al login.

---














