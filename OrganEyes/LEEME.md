# OrganEyes

OrganEyes es una aplicación liviana para Windows que organiza archivos según sus extensiones más comunes.

Está diseñada para personas que quieren limpiar rápidamente carpetas como Descargas, Documentos, Música o cualquier directorio personalizado sin instalar dependencias adicionales.

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

El usuario elige manualmente qué carpetas deben organizarse automáticamente.

![Modo automático](Screenshots/auto-mode.png)

---

## Características

- Modo manual con selector de carpetas
- Modo automático al iniciar Windows
- Agrupación inteligente por extensiones comunes
- Extensiones poco frecuentes agrupadas en `Varios`
- Archivos sin extensión agrupados en `Sin extensión`
- Opción de emergencia para omitir el modo automático manteniendo `Shift` durante el inicio
- Notificación de Windows después de ejecuciones automáticas
- Manejo seguro de archivos duplicados
- Construido únicamente con la librería estándar de Python

---

## Cómo organiza los archivos

1. Analiza únicamente el nivel principal de la carpeta seleccionada.
2. Cuenta las extensiones más comunes.
3. Crea carpetas dedicadas solo para las extensiones más repetidas.
4. Las extensiones menos comunes se agrupan en `Varios`.
5. Los archivos sin extensión se agrupan en `Sin extensión`.
6. Los conflictos de nombres se resuelven de forma segura usando:
   - `archivo (1).ext`
   - `archivo (2).ext`
   - etc.

---

## Ejecutar desde el código fuente

### Requisitos

- Windows
- Python 3.12 o superior recomendado

### Ejecutar

```powershell
python .\OrganEyes.py
```

---

## Compilar el ejecutable

OrganEyes utiliza únicamente la librería estándar de Python.

Para volver a generar el `.exe`, instala PyInstaller y ejecuta:

```powershell
python -m pip install pyinstaller
python -m PyInstaller --onefile --windowed --name OrganEyes .\OrganEyes.py
```

El ejecutable generado aparecerá en:

```txt
dist\
```

---

## Comportamiento del modo automático

El modo automático no selecciona carpetas por sí solo.

El usuario debe elegir explícitamente qué carpetas serán organizadas automáticamente.

Si no hay carpetas configuradas, OrganEyes se cerrará de forma segura sin modificar nada y mostrará una notificación.

---

## Notas de seguridad

- OrganEyes no analiza subcarpetas
- OrganEyes no sobrescribe archivos con el mismo nombre
- El modo automático puede omitirse durante un inicio manteniendo `Shift` mientras Windows carga el escritorio

---

## Descarga

La última versión ejecutable está disponible en la sección Releases del repositorio.

---

## Notas

Este repositorio contiene únicamente el proyecto distribuible de la aplicación.

El script personal utilizado durante el desarrollo no forma parte de este proyecto público.

---

## Créditos

Hecho por Nani2204 & Codex.
