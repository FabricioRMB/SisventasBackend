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


### 📁 `includes/`

Carpeta donde se encuentra la configuración global del sistema.

Archivos clave:
- `config.php`: contiene constantes como el nombre del host o credenciales de conexión.
- `db.php`: contiene la clase que gestiona la conexión a la base de datos con PDO.


### 📁 `modelo/`

Contiene las clases que representan entidades o modelos del sistema, en nuestro caso unicamente esta:
- `producto.php`: contiene atributos y funciones para gestionar productos.


### 📁 `vista/`

Es la carpeta que contiene todas las interfaces del sistema (formularios, listados, botones, etc.).  
Está organizada por subcarpetas según el módulo:

- `clientes/`: Vistas para crear, editar y listar clientes.
- `producto/`: Formulario de producto, stock, consulta de ventas.
- `proveedores/`: Mantenimiento de proveedores.
- `usuarios/`: Gestión de usuarios.
- `ventas/`: Registro de ventas, selección de productos.
- `layout/`: Contiene los elementos comunes como cabecera, menú y pie.



### 📄 `index.php`

Punto de entrada principal al sistema. Normalmente redirige al login si no hay sesión iniciada.


### 📄 `login.php` y `logout.php`

- `login.php`: Página de acceso al sistema con usuario y contraseña.
- `logout.php`: Destruye la sesión activa y redirige al login.
---

## 🔍 Descripción de Módulos


### 🛍️ Comprar

Este es el módulo principal de punto de venta. Permite al usuario (vendedor o cajero) seleccionar productos, añadirlos a un **carrito de compras**, y registrar la venta.

Al confirmar la compra:

- Se genera una factura interna.
- El stock de cada producto se **reduce automáticamente**.
- Se muestran alertas visuales si algún producto tiene **stock bajo** o está **agotado**.

Este módulo simula el comportamiento de una tienda real y es el más dinámico del sistema.

**Archivos relacionados:**
- Vista: `vista/producto/store.php`
- Controlador: `controlador/productoController.php`
- Modelo: `modelo/producto.php`



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

![menu productos](https://github.com/user-attachments/assets/5ddf55f0-1cf1-4d26-8dd8-3b13189ce960)


### 👤 Clientes

Módulo para registrar, editar y eliminar clientes. Cada cliente tiene un DNI, nombres, apellidos, teléfono y dirección. Esta información se asocia a cada venta realizada.

**Archivos relacionados:**
- Vistas: `vista/clientes/`
- Controlador: `controlador/clienteController.php`

![menu clientes](https://github.com/user-attachments/assets/ffa17f61-90e7-46dd-b628-3401dec7db04)


### 🚚 Proveedores

Permite registrar proveedores que suministran los productos. Cada proveedor tiene nombre, dirección, teléfono, y correo electrónico.

**Archivos relacionados:**
- Vistas: `vista/proveedores/`
- Controlador: `controlador/proveedorController.php`


### 📊 Ventas

Este módulo permite **consultar las ventas** que se han realizado en el sistema.

Incluye un reporte por producto donde se puede ver:

- Total de unidades vendidas por producto.
- Importe monetario total generado.
- Fecha de cada venta.

Sirve como herramienta de análisis o seguimiento de las operaciones realizadas.

**Archivos relacionados:**
- Vista: `vista/producto/consulta_ventas.php`
- Controlador: `controlador/productoController.php` (función de consulta)
- Modelo: `modelo/producto.php`



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


### 🧩 Layout

Contiene los archivos comunes a todas las páginas del sistema: menú de navegación, encabezado, pie de página, y estilos generales.

**Archivos relacionados:**
- Carpeta: `vista/layout/`
  - `cabecera.php`
  - `menu.php`
  - `pie.php`

---
## 🗃️ Base de Datos

El sistema utiliza una base de datos relacional en MySQL llamada `sistemaventas`.  
Contiene las siguientes tablas principales:

- `usuarios`: Manejo de acceso al sistema.
- `clientes`: Datos de los compradores.
- `proveedores`: Información de empresas que abastecen los productos.
- `productos`: Catálogo de productos disponibles, con control de stock y categorías.
- `categorias`: Clasificación de los productos.
- `facturas`: Registro de las ventas realizadas.
- `detallefactura`: Detalle de cada producto vendido.
- `condicionventa`: Define si la venta fue al contado o al crédito.

📎 Archivo SQL incluido: `sistema_ventas.sql`  
Este archivo permite importar toda la estructura y parte de los datos necesarios para probar el sistema.

---

## ▶️ Cómo Ejecutar el Sistema Localmente

Para probar este sistema en tu computadora, sigue estos pasos:


### ⚙️ 1. Iniciar XAMPP

Abre **XAMPP** y activa los siguientes módulos:

- 🟢 Apache  
- 🟢 MySQL


### 📁 2. Colocar el proyecto en la carpeta correcta

Copia la carpeta del proyecto en la siguiente ruta:
C:\xampp\htdocs\sisventas


### 🛠️ 3. Crear la base de datos

Abre tu navegador y accede a:
http://localhost/phpmyadmin


Luego:

1. Crea una base de datos nueva con el nombre: 'sistemaventas'
2. Haz clic en la pestaña **"Importar"**.
3. Selecciona el archivo: sistema_ventas.sql
4. Haz clic en **"Continuar"** para importar los datos correctamente.


### 🌐 4. Ingresar al sistema web

Abre tu navegador y escribe: http://localhost/sisventas/


### 🔐 5. Acceso con usuario de prueba

Inicia sesión usando las siguientes credenciales:

- 👤 **Usuario:** A01  
- 🔑 **Contraseña:** 1234

✅ ¡Listo! Ya puedes usar el sistema: registrar productos, realizar ventas, ver reportes, manejar usuarios y más.









