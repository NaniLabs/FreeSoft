# OrganEyes

OrganEyes es una aplicación ligera para Windows que organiza archivos automáticamente según sus extensiones y tipos más comunes.

Está diseñada para ayudar a mantener ordenadas carpetas como Descargas, Documentos, Música o cualquier directorio personalizado sin necesidad de instalar dependencias adicionales.

## Captura de pantalla

![Interfaz principal](Screenshots/app-main.png)

---

## Ejemplo

### Antes de organizar

![Antes](Screenshots/before.png)

### Proceso de organización

![Organizando](Screenshots/organizing.png)

### Después de organizar

![Después](Screenshots/after.png)

---

## Modo automático

OrganEyes también puede ejecutarse automáticamente al iniciar Windows.

El usuario selecciona manualmente qué carpetas desea organizar de forma automática.

![Modo automático](Screenshots/auto-mode.png)

---

## Características

* Organización manual mediante selector de carpetas
* Ejecución automática al iniciar Windows
* Agrupación inteligente por extensiones comunes
* Extensiones poco frecuentes agrupadas en `Varios`
* Archivos sin extensión agrupados en `Sin extensión`
* Opción de emergencia para omitir la ejecución automática manteniendo `Shift` durante el inicio
* Notificaciones de Windows tras ejecuciones automáticas
* Manejo seguro de archivos duplicados
* Desarrollado únicamente con la biblioteca estándar de Python

---

## Cómo funciona

1. Analiza únicamente el nivel principal de la carpeta seleccionada.
2. Identifica las extensiones más frecuentes.
3. Crea carpetas específicas para los tipos de archivo predominantes.
4. Agrupa las extensiones menos frecuentes en `Varios`.
5. Agrupa los archivos sin extensión en `Sin extensión`.
6. Resuelve conflictos de nombres de forma segura utilizando sufijos incrementales.

Ejemplos:

* `archivo (1).ext`
* `archivo (2).ext`

---

## Ejecutar desde el código fuente

### Requisitos

* Windows
* Python 3.12 o superior recomendado

### Ejecución

```powershell
python .\OrganEyes.py
```

---

## Generar el ejecutable

OrganEyes utiliza exclusivamente la biblioteca estándar de Python.

Para generar nuevamente el ejecutable:

```powershell
python -m pip install pyinstaller
python -m PyInstaller --onefile --windowed --name OrganEyes .\OrganEyes.py
```

El archivo generado se encontrará en:

```text
dist\
```

---

## Comportamiento del modo automático

El modo automático no selecciona carpetas por sí solo.

El usuario debe configurar explícitamente qué ubicaciones serán organizadas automáticamente.

Si no existen carpetas configuradas, la aplicación finalizará sin realizar cambios y mostrará una notificación informativa.

---

## Seguridad

* No analiza subcarpetas
* No sobrescribe archivos existentes
* El modo automático puede omitirse manteniendo `Shift` durante el inicio de Windows

---

## Descargas

La última versión ejecutable está disponible en la sección Releases.

---

## Notas

Este repositorio contiene únicamente la versión distribuible del proyecto.

Las herramientas y scripts personales utilizados durante el desarrollo no forman parte de esta publicación.

---

## Créditos

Desarrollado por NaniLabs.
