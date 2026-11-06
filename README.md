# Plataforma de sostenibilidad por activo

Prototipo en Python y Excel para explorar consumos de energía y agua, huella de carbono, riesgos e iniciativas de inversión sostenible en activos inmobiliarios de Colombia.

> **Estado: experimental.** Esta herramienta se comparte para pruebas y comentarios con datos ficticios. Sus resultados requieren revisión técnica independiente y no deben utilizarse todavía para decisiones de inversión, inventarios oficiales de emisiones o informes de auditoría.

## ¿Para qué sirve?

La plataforma permite trabajar con un activo a la vez y explorar:

- Consumos mensuales de energía y agua.
- Una estimación preliminar de huella de carbono.
- Riesgos y vacíos de información para due diligence.
- Iniciativas de inversión o CAPEX, como energía solar y eficiencia energética.
- Un informe por activo y un registro básico de trazabilidad.

## ¿Qué necesitas?

- Un computador con Windows.
- Python 3.14 instalado. Puedes descargarlo desde [python.org](https://www.python.org/downloads/).
- Microsoft Excel u otro programa compatible con archivos `.xlsx`.
- Conexión a internet para instalar las dependencias.

El análisis se ejecuta localmente en el computador.

## Instalación paso a paso

### 1. Descarga el proyecto

En la página del repositorio, selecciona **Code → Download ZIP** y descomprime el archivo.

### 2. Abre la consola

Abre la carpeta descomprimida. En la barra de dirección del Explorador de archivos escribe:

```text
cmd
```

Presiona **Enter**. Se abrirá una ventana de comandos dentro de la carpeta del proyecto.

### 3. Prepara el entorno

Copia y ejecuta estas líneas **una por una**:

```cmd
py -3.14 -m venv .venv
```

```cmd
.venv\Scripts\python.exe -m pip install -r requirements.txt
```

La instalación puede tardar algunos minutos.

### 4. Abre la plataforma

Escribe:

```cmd
.venv\Scripts\python.exe main.py
```

Presiona **Enter**. Aparecerá el menú de la plataforma.

## Cómo hacer una prueba

### Paso 1. Crea la plantilla

En el menú, escribe `1` y presiona **Enter**.

Cuando aparezca:

```text
Ruta para la plantilla [datos/plantilla_activo.xlsx]:
```

Presiona **Enter** sin escribir nada para aceptar la ubicación propuesta.

### Paso 2. Diligencia el Excel

Abre el archivo:

```text
datos\plantilla_activo.xlsx
```

Completa las hojas que apliquen a tu prueba. Usa **datos ficticios** y deja vacíos los campos para los que no tengas información. Guarda y cierra el archivo antes de continuar.

### Paso 3. Analiza el activo

Regresa al menú, escribe `2` y presiona **Enter**. Cuando solicite la ruta del archivo, escribe:

```text
datos\plantilla_activo.xlsx
```

Selecciona el ejercicio que deseas probar o presiona **Enter** para utilizar la opción `completo`.

### Paso 4. Revisa los resultados

La herramienta indicará la carpeta donde guardó los resultados. Por defecto, se encuentran dentro de la carpeta:

```text
output
```

Según la información disponible, encontrarás un Excel de reporte, archivos de datos, un informe, una bitácora y gráficos.

## Limitaciones conocidas

- Los factores de emisión, sus unidades, vigencia y fuentes requieren revisión independiente.
- La falta de datos de agua puede aparecer como cero y la ausencia de un factor puede producir emisiones evitadas de cero.
- Los datos estimados o imputados pueden participar en los cálculos y en el análisis antes/después de una intervención.
- Los duplicados y vacíos pueden afectar las series y los resultados.
- Una comparación antes/después no demuestra por sí sola que una intervención causó el cambio.
- La evaluación CAPEX es preliminar y no constituye un caso financiero completo.
- La bitácora y el hash de entrada ayudan a la trazabilidad, pero no equivalen a una auditoría ni garantizan la integridad de todo el proceso.
- La plataforma no incluye inteligencia artificial ni integración directa con SharePoint.
- No se ha validado el cumplimiento de IFRS S2, ISSA 5000 ni ISAE 3000.

## Privacidad

Para las pruebas, utiliza información ficticia. No subas a GitHub facturas, datos personales, archivos confidenciales, contraseñas ni claves de API.

Las carpetas `datos` y `output` están incluidas en `.gitignore`, pero debes revisar el contenido antes de publicar cualquier archivo.

## Ejecutar las pruebas

Desde la carpeta del proyecto:

```cmd
.venv\Scripts\python.exe -m pytest -q
```

## Comentarios y mejoras

Si encuentras errores o tienes sugerencias, puedes abrir un **Issue** en este repositorio. Describe qué intentaste hacer, qué esperabas y qué ocurrió, sin incluir información confidencial.

## Licencia

Aún no se ha seleccionado una licencia de código abierto. La disponibilidad pública del repositorio no concede automáticamente permiso para reutilizar, modificar o distribuir el código.
