# LIMPIEZA-DE-UN-ARCHIVO.2
# Limpieza de Base de Datos en Excel 🧹📊

En Python  limpia y normaliza datos de un archivo Excel llamado base_datos_sucia.xlsx

**ES IMPORTANTE CREAR UN ARCHIVO PARA QUE TRABAJEN EN CONJUNTO EL PROGRAMA Y LA BASE DE DATOS PARA QUE DE IGUAL MANERA SE GUARDE LA BASE DE DATOS LIMPIA DENTRO DE ESTE ARCHIVO**

## 📌 Características del Script

✅ **Carga de datos** desde Excel con openpyxl  
✅ **Corrección de nombres y ciudades**  
✅ **Conversión de edades escritas en texto a números**  
✅ **Normalización de fechas**  
✅ **Corrección de errores en correos electrónicos**  
✅ **Eliminación de datos vacíos**  
✅ **Generación de un archivo limpio** (`BASE DE DATOS LIMPIA.xlsx`)  

## 🚀 Requisitos
- Python 3.x  
- Librerías: openpyxl y pandas

Puedes instalarlas con:
pip install openpyxl/pandas

📂 Estructura del Código
# Cargar archivo Excel
wb = load_workbook("base_datos_sucia.xlsx")
hoja = wb.active

# Extraer encabezados y datos
encabezados = [celda.value for celda in hoja[1]]
datos_extraidos = [fila for fila in hoja.iter_rows(min_row=2, values_only=True)]

# Crear DataFrame
df = pd.DataFrame(datos_extraidos, columns=encabezados)

# Normalización de datos
df["Nombre"] = df["Nombre"].str.strip().str.title().fillna("Desconocido")
df["Fecha de Registro"] = pd.to_datetime(df["Fecha de Registro"], errors="coerce")

# Guardar archivo limpio
df.to_excel("base de datos limpia.xlsx", index=False)

🎯 Objetivo
Este script facilita la limpieza y estructuración de datos en Excel, asegurando un formato uniforme para análisis.

Listo para usar 😃
