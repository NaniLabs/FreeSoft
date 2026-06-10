# Manual rápido - OrganEyes

## Cómo abrir la aplicación

Haz doble clic en `OrganEyes.exe`.

Si deseas ejecutar el código fuente directamente:

```powershell
python .\OrganEyes.py
```

---

## Modo manual

1. Abre la aplicación.
2. Selecciona `Manual con selector`.
3. Pulsa `Elegir carpeta`.
4. Selecciona la carpeta que deseas organizar.
5. Pulsa `Organizar ahora`.

Este modo ejecuta una única organización y no deja procesos activos en segundo plano.

---

## Modo automático

1. Abre la aplicación.
2. Selecciona `Automático al iniciar Windows`.
3. Pulsa `Agregar carpeta automática`.
4. Elige una o varias carpetas para organizar automáticamente.
5. Pulsa `Guardar y activar`.

A partir de ese momento, OrganEyes revisará las carpetas configuradas cada vez que Windows inicie y se cerrará automáticamente al finalizar.

---

## Cómo desactivar el modo automático

1. Abre la aplicación.
2. Ingresa en `Automático al iniciar Windows`.
3. Pulsa `Desactivar inicio automático`.

La aplicación dejará de ejecutarse durante el arranque del sistema.

---

## Salida de emergencia

Si surge algún problema durante el inicio automático:

1. Enciende la PC.
2. Mientras se carga el escritorio de Windows, mantén presionada la tecla `Shift`.
3. Sostén la tecla durante unos segundos.

Si OrganEyes detecta la tecla `Shift`, cancelará esa ejecución automática y no realizará ninguna modificación durante esa sesión.

Esto no desactiva la función permanentemente; únicamente omite una ejecución para permitir revisar la configuración.

---

## Desactivación manual

Si no puedes abrir la aplicación, elimina el siguiente archivo:

```text
%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

Ruta habitual:

```text
C:\Users\TU_USUARIO\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

---

## Ubicación de la configuración

Las carpetas configuradas para organización automática se almacenan en:

```text
%APPDATA%\OrganEyes\config.json
```

Ruta habitual:

```text
C:\Users\TU_USUARIO\AppData\Roaming\OrganEyes\config.json
```

Para restablecer completamente la configuración:

1. Elimina `OrganEyes.bat`.
2. Elimina `config.json`.

---

## Parámetros configurables

Dentro de `OrganEyes.py` pueden modificarse los siguientes parámetros:

```python
MINIMO_PARA_CARPETA_PROPIA = 2
MAXIMO_CARPETAS_PRINCIPALES = 8
NOMBRE_CARPETA_VARIOS = "Varios"
NOMBRE_CARPETA_SIN_EXTENSION = "Sin extension"
VENTANA_CANCELACION_SEGUNDOS = 5
```

### Descripción

**MINIMO_PARA_CARPETA_PROPIA**

Cantidad mínima de archivos necesarios para crear una carpeta específica para una extensión.

**MAXIMO_CARPETAS_PRINCIPALES**

Cantidad máxima de carpetas por extensión que pueden generarse.

**NOMBRE_CARPETA_VARIOS**

Nombre utilizado para agrupar extensiones poco frecuentes.

**NOMBRE_CARPETA_SIN_EXTENSION**

Nombre utilizado para agrupar archivos sin extensión.

**VENTANA_CANCELACION_SEGUNDOS**

Tiempo disponible para cancelar una ejecución automática manteniendo presionada la tecla `Shift`.
