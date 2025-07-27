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

## 🔍 Descripción de Módulos

---

### 🧾 Productos

Este módulo permite gestionar todos los productos disponibles para la venta. Cada producto tiene nombre, precio, stock actual, stock mínimo, categoría y proveedor asignado.

Incluye una **alerta visual** en el listado cuando el stock actual cae por debajo del mínimo, para facilitar el control de inventario.

También permite realizar **consultas de ventas por producto**, mostrando cuántas veces se vendió cada producto, el total recaudado, y fechas.

**Archivos relacionados:**
- Vistas:
  - `vista/producto/listado.php`: listado de productos con controles de edición y alerta por stock.
  - `vista/producto/crear.php`: formulario de registro de producto.
  - `vista/producto/update.php`: formulario de edición de producto existente.
  - `vista/producto/consulta_ventas.php`: consulta de ventas por producto.
- Controlador: `controlador/productoController.php`
- Modelo: `modelo/producto.php`

---

### 👤 Clientes

Módulo para registrar, editar y eliminar clientes. Cada cliente tiene un DNI, nombres, apellidos, teléfono y dirección. Esta información se asocia a cada venta realizada.

**Archivos relacionados:**
- Vistas: `vista/clientes/`
- Controlador: `controlador/clienteController.php`

---

### 🚚 Proveedores

Permite registrar proveedores que suministran los productos. Cada proveedor tiene nombre, dirección, teléfono, y correo electrónico.

**Archivos relacionados:**
- Vistas: `vista/proveedores/`
- Controlador: `controlador/proveedorController.php`

---

### 🛒 Ventas

Módulo central del sistema. Permite registrar ventas, seleccionando productos disponibles, cantidades y aplicando descuentos. Se genera una **factura** con los detalles de la venta, fecha, cliente y condición de pago (contado o crédito).

Al registrar una venta, el stock de los productos seleccionados **se actualiza automáticamente**.

**Archivos relacionados:**
- Vistas: `vista/ventas/`
- Controlador: *(en desarrollo o dividido entre otros controladores)*
- También se relaciona con `productoController.php` para control de stock.

---

### 👥 Usuarios

Permite crear, editar y eliminar cuentas de usuarios del sistema. Cada usuario tiene un código único, contraseña y nombre.

Incluye control de acceso: solo los usuarios registrados pueden ingresar al sistema.

**Archivos relacionados:**
- Vistas: `vista/usuarios/`
- Controlador: `controlador/usuarioController.php`
- Login:
  - `login.php`: formulario de acceso.
  - `logout.php`: cierre de sesión.
  - `controlador/loginController.php`: verifica las credenciales.

---

### 🧩 Layout (Diseño común)

Contiene los archivos comunes a todas las páginas del sistema: menú de navegación, encabezado, pie de página, y estilos generales.

**Archivos relacionados:**
- Carpeta: `vista/layout/`
  - `cabecera.php`
  - `menu.php`
  - `pie.php`













