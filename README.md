# limpieza_inventario

Limpieza y depuración de un archivo de inventario para uso en procesos contables.

---

## Descripción del notebook "limpieza_inventario"

Este notebook procesa un archivo Excel con el inventario mensual y elimina datos innecesarios. Las operaciones realizadas son:
1. Filas vacías que aparecen antes de la fila en gris.
2. La fila que contiene el RFC de la empresa (ubicada antes de la fila en gris).
3. Filas donde las tres últimas columnas tienen valor cero (0.000) y las demás están vacías.

También se eliminan las columnas identificadas en la fila en gris:
1. Costeo
2. U. base

Finalmente, se realizan limpiezas específicas en celdas particulares:
1. En filas donde la columna "Producto" inicia con "MARCA", se asigna NaN al resto de las celdas de esa fila.
2. En filas donde la columna "Costo unitario" contiene "Total marca:", "Total fila:" o "Total general:", se asigna NaN en la columna "Saldo" correspondiente a esa fila.

El objetivo de esta limpieza es proporcionar un archivo xlsx claro, sin datos irrelevantes para procesos contables.

---

## Tecnologías utilizadas

* **Lenguaje:** Python 3.11.5  
* **Librerías:**
  - `pandas` (2.0.3)  
  - `numpy` (1.24.3)  
  - `openpyxl` (3.0.10)  
  - `os`
  - `math`
  - `sys`

---

## Ejecución

1. Descargar el archivo xlsx con nombre "Inventario General Ejemplo" y el notebook "limpieza_inventario.ipynb". Guardarlos en una misma carpeta.
2. Modificar la última celda del notebook y colocar "Inventario General Ejemplo" en la variable nombre_archivo.
3. Ejecutar todas las celdas del notebook hasta ver el mensaje: "Limpieza del archivo xlsx realizada con éxito."
4. Revisar la carpeta donde se guardó el xlsx y el notebook: aparecerá el nuevo archivo "Inventario General Ejemplo filtrado".
