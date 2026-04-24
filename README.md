# Repo para EIEC - DevOps - UNIR

Este repositorio nos servirá para demostrar el uso de Git en la asignatura de EIEC y muchas cosas mas.

---

Los comandos del Makefile funcionarán en Linux y MacOS. En caso de usar Windows, necesitarás adaptarlos o ejecutarlos en una máquina virtual Linux.

## PRA-001: Parámetro de orden ascendente/descendente

Se añadió un nuevo parámetro de línea de comandos que permite indicar si el orden de la lista debe ser **ascendente** (`asc`) o **descendente** (`desc`)

### Cambios realizados

- Se agregó un tercer argumento obligatorio al script `main.py` que acepta los valores `asc` o `desc`.
- El valor se pasa a la función `sort_list` para controlar la dirección del ordenamiento.
- Se actualizaron los mensajes de ayuda para reflejar el nuevo parámetro.

## Ejecución

```bash
python3 main.py <filename> <dup> <order>
```

### Parámetros

| Parámetro | Descripción | Valores |
|-----------|-------------|---------|
| `filename` | Ruta al fichero que contiene la lista de palabras, una por línea | Ruta válida |
| `dup` | Indica si se eliminan palabras duplicadas | `yes` / `no` |
| `order` | Indica el orden de la lista | `asc` (ascendente) / `desc` (descendente) |

### Ejemplos de uso

**Orden ascendente, sin duplicados:**
```bash
python3 main.py words.txt no asc
```
Salida:
```
Se leerán las palabras del fichero words.txt
['go', 'java', 'java', 'javascript', 'kotlin', 'python', 'python', 'python', 'ruby', 'rust', 'swift', 'typescript']
```

**Orden descendente, eliminando duplicados:**
```bash
python3 main.py words.txt yes desc
```
Salida:
```
Se leerán las palabras del fichero words.txt
['typescript', 'swift', 'rust', 'ruby', 'python', 'kotlin', 'javascript', 'java', 'go']
```

**Orden descendente, sin eliminar duplicados:**
```bash
python3 main.py words.txt no desc
```
Salida:
```
Se leerán las palabras del fichero words.txt
['typescript', 'swift', 'rust', 'ruby', 'python', 'python', 'python', 'kotlin', 'javascript', 'java', 'java', 'go']
```

## Ejecución con Docker

```bash
make run
```
