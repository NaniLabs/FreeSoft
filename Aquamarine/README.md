# Aquamarine

Aquamarine is a desktop application built with Qt Widgets and Visual Studio for inventory management, sales tracking, supplier payments, and repair workflow management.

It was designed as a local-first solution for small and medium-sized businesses, focusing on simplicity, portability, and full control over local data.

This public version was prepared as a clean and customizable foundation for future development:

- Neutral and adaptable branding
- Organized and documented codebase
- Local SQLite database
- Portable architecture with no server dependencies
- Structure designed for customization and extension

## Screenshot

![Main Interface](Screenshots/main-ui.png)

---

## Main Features

- Create, edit, search, and delete products
- SKU and barcode search
- Sales tracking and management
- Repair workflow management
- Supplier payment tracking
- Advanced SQLite administration tools
- Local SQLite persistence
- Fully offline operation
- Portable desktop-oriented architecture

---

## Technologies

- C++
- Qt 6 Widgets
- SQLite
- Visual Studio 2022 / MSVC

---

## Project Structure

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

## Building

### Requirements

- Windows 10 or later
- Visual Studio 2022 with MSVC
- Qt 6 for MSVC 2022

### Steps

1. Open `Aquamarine.slnx`
2. Select either `Release` or `Debug`
3. Build the solution using Visual Studio or MSBuild

---

## Portable Release

The release package includes:

- Main executable
- Required Qt DLLs
- Platform plugins
- SQLite drivers

To distribute the application, share the complete portable folder or the ZIP package available in Releases.

---

## SQLite Database

Aquamarine uses a local SQLite database.

By default, the application attempts to store the database in:

```text
Documents/Aquamarine/aquamarine.sqlite
```

If the Documents folder is unavailable, the application automatically falls back to the Windows application data directory.

### Stored Information

The `.sqlite` file contains:

- Products
- Sales
- Repairs
- Database schema

If the file is deleted, the application automatically creates a new empty database during the next startup.

---

## Administrative Tools

Aquamarine includes an internal panel for executing SQL queries manually.

### Shortcut

```text
Ctrl + Alt + S
```

### Password Location

Defined in:

```text
ProyectoAquamarine.cpp
```

Function:

```cpp
requestAdminAccess()
```

### Example Queries

```sql
SELECT * FROM productos;
SELECT * FROM productos WHERE codigo_barras = '7790000000000';
SELECT * FROM ventas;
SELECT * FROM reparaciones;
SELECT * FROM productos WHERE stock <= 3;
DELETE FROM ventas WHERE id = 1;
```

---

## Customization

### Branding and Logo

The main visual banner is rendered from:

```text
Aquamarine/ProyectoAquamarine.cpp
```

Function:

```cpp
renderBrandLogo()
```

Colors, text, shapes, or the entire rendering process can be modified as needed.

### Database Location

Configured in:

```cpp
loadData()
```

### Administrator Password

Configured in:

```cpp
requestAdminAccess()
```

### Pricing Formula

Located in:

```text
Aquamarine/producto.cpp
```

Function:

```cpp
Producto::calcularPrecioML()
```

---

## Code Organization

### ProyectoAquamarine.*

- User interface rendering
- Navigation and events
- Validation logic
- Visual updates

### producto.*

- Product model
- Pricing logic

### venta.*

- Sales model

### reparacion.*

- Repair model

### inventario.*

- Core business logic
- In-memory management

### database_manager.*

- SQLite persistence layer

---

## Future Extensions

- User accounts and permissions
- CSV and Excel export
- Advanced branding customization
- External configuration files
- Advanced filtering
- Cloud synchronization
- Multi-business support

---

## Security Notes

- Uses local SQLite storage only
- No internet connection required
- No external services or servers
- Database can be recreated automatically if missing

---

## License and Usage

This repository is intended as a customizable foundation for future projects.

Before deploying or using it commercially, review:

- Branding and logos
- Administrator password
- Pricing formulas
- Sample data
- Local paths and sensitive information

---

## Credits

Developed by NaniLabs.

This project was created as a practical learning experience focused on desktop application development using C++, Qt, and SQLite.
