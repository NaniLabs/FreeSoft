# Aquamarine

Aquamarine es una aplicación de escritorio desarrollada con Qt Widgets y Visual Studio para administrar inventario, ventas, pagos a proveedor y seguimiento de reparaciones en pequeños y medianos negocios.

Esta versión pública fue preparada como una base más limpia y personalizable:
- branding neutro y adaptable
- código comentado a nivel funcional
- base de datos SQLite local sin depender de servidores
- estructura lista para personalizar y publicar en GitHub

![Interfaz principal](Screenshots/main-ui.png)

---

## Funciones principales

- Alta, edición, búsqueda y eliminación de productos
- Búsqueda por SKU o código de barras numérico
- Registro y seguimiento de ventas
- Seguimiento de pagos al proveedor
- Gestión de reparaciones con datos del cliente y del trabajo
- Panel oculto de administración SQLite
- Persistencia local con SQLite
- Arquitectura portable orientada a escritorio

---

## Tecnologías

- C++
- Qt 6 Widgets
- SQLite
- Visual Studio 2022 / MSVC

---

## Estructura del proyecto

```text
aquamarine/
|-- Aquamarine.slnx
|-- README.md
|-- LEEME.md
|-- .gitignore
|-- Screenshots/
`-- Aquamarine/
    |-- main.cpp
    |-- ProyectoAquamarine.cpp
    |-- ProyectoAquamarine.h
    |-- ProyectoAquamarine.ui
    |-- producto.*
    |-- venta.*
    |-- reparacion.*
    |-- inventario.*
    `-- database_manager.*
```

---

## Cómo compilar

### Requisitos

- Windows 10 o superior
- Visual Studio 2022 con compilador MSVC
- Qt 6 para MSVC 2022

### Pasos

1. Abrir `Aquamarine.slnx`
2. Seleccionar `Release` o `Debug`
3. Compilar la solución desde Visual Studio o usando MSBuild

---

## Versión portable

El paquete release del repositorio contiene:

- el ejecutable
- las DLL necesarias de Qt
- plugins de plataforma
- drivers SQLite

Para compartir la aplicación, distribuye la carpeta portable completa o el archivo ZIP disponible en Releases.

---

## Base de datos SQLite

La aplicación utiliza una base SQLite local.

Por defecto intenta guardar la base de datos dentro de la carpeta Documentos del usuario:

```text
Documents/Aquamarine/aquamarine.sqlite
```

Si la carpeta Documentos no está disponible, la aplicación utiliza la ubicación de datos de aplicación proporcionada por Windows.

### Qué guarda la base de datos

El archivo `.sqlite` contiene:
- productos
- ventas
- reparaciones
- estructura de tablas

Si el archivo se elimina, la aplicación crea automáticamente una base vacía al iniciarse nuevamente.

---

## Panel admin oculto

Aquamarine incluye un panel interno para ejecutar SQL manualmente.

### Atajo

```text
Ctrl + Alt + S
```

### Ubicación de la contraseña

Definida dentro de:

```text
ProyectoAquamarine.cpp
```

Función:

```cpp
requestAdminAccess()
```

### Consultas de ejemplo

```sql
SELECT * FROM productos;
SELECT * FROM productos WHERE codigo_barras = '7790000000000';
SELECT * FROM ventas;
SELECT * FROM reparaciones;
SELECT * FROM productos WHERE stock <= 3;
DELETE FROM ventas WHERE id = 1;
```

---

## Puntos comunes de personalización

### Branding y logo

El banner visual principal se renderiza en:

```text
Aquamarine/ProyectoAquamarine.cpp
```

Función:

```cpp
renderBrandLogo()
```

Puedes modificar colores, textos, formas o reemplazar completamente el banner generado.

---

### Ruta de la base de datos

Configurada dentro de:

```cpp
loadData()
```

---

### Contraseña del admin

Configurada dentro de:

```cpp
requestAdminAccess()
```

---

### Fórmula de precio de referencia / marketplace

Ubicada en:

```text
Aquamarine/producto.cpp
```

Función:

```cpp
Producto::calcularPrecioML()
```

---

## Organización del código

- `ProyectoAquamarine.*`
  - renderizado de interfaz
  - eventos de botones
  - manejo de pantallas
  - validaciones
  - refresco visual

- `producto.*`
  - modelo de producto
  - lógica de precios

- `venta.*`
  - modelo de ventas

- `reparacion.*`
  - modelo de reparaciones

- `inventario.*`
  - lógica principal del negocio
  - almacenamiento en memoria

- `database_manager.*`
  - capa de persistencia SQLite

---

## Ideas para extenderlo

- usuarios y permisos
- exportación CSV o Excel
- branding con imágenes reales
- archivos externos de configuración
- filtros avanzados por cliente, fecha o estado
- sincronización en la nube
- soporte multi-negocio

---

## Notas de seguridad

- Utiliza únicamente almacenamiento SQLite local
- No requiere conexión a internet
- No depende de servidores externos
- La base de datos se recrea automáticamente si falta

---

## Licencia y uso

Este repositorio está pensado como una base personalizable.

Antes de publicarlo o desplegarlo comercialmente, revisa:
- branding y logos
- contraseña admin
- fórmulas de precios
- datos de ejemplo
- rutas locales o información personal

---

## Créditos

Hecho por Nani220 & Codex.
