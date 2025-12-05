# BIOINFORMATICA-BLAST
**Autores:** Raul Mendoza, Adrian Ojeda  
**Asignatura:** Bioinformática (ULPGC)

Este repositorio contiene la resolución completa de la **práctica de BLAST (Sesión 04)**.  
El proyecto implementa scripts en Python (utilizando **Biopython**) para realizar alineamientos de secuencias biológicas tanto en servidores remotos (**Online**) como en la propia máquina (**Local**).

---

# Contenido del Proyecto

El cuaderno principal `Bioinformatica_Sesion04_BLAST.ipynb` resuelve los 4 ejercicios propuestos:

---

## 1. EJERCICIO 1: BLASTN (ADN)
- Búsqueda de secuencias nucleotídicas introducidas por teclado.
- **Online:** Contra la base de datos `nt` del NCBI.
- **Local:** Contra una base de datos propia (`genomasbase`).
- Incluye identificación del mejor hit, E‑value y descripción.

---

## 2. EJERCICIO 2: BLASTP (Proteínas)
- Búsqueda de secuencias proteicas.
- **Filtrado:** Genera un archivo `.txt` con todos los hits cuyo **E-value < 0.001**.
- Incluye cálculo de porcentaje de identidad y longitud del alineamiento.

---

## 3. EJERCICIO 3: Filtrado por Organismo
- Lectura de secuencias desde archivo FASTA.
- **Online:** Utiliza filtros nativos de NCBI (`entrez_query`) para restringir resultados a una especie concreta.
- **Local:** Aplica filtrado analizando la descripción o ID de cada hit.
- Calcula el E‑value medio de los hits filtrados.

---

## 4. EJERCICIO 4: Suite Completa BLAST
Incluye ejemplos ejecutables de las 5 herramientas principales:

- `blastn`
- `blastp`
- `blastx`
- `tblastn`
- `tblastx`

Con secuencias reales y análisis de resultados biológicos coherentes.

---

# Requisitos Previos

### 1. Python 3.8+ y dependencias
```bash
pip install biopython jupyter
```

### 2. BLAST+ del NCBI
Debes tener instalado BLAST+:

https://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/

**Importante:**  
La carpeta `bin` debe estar añadida al PATH del sistema.

Ejemplo en Windows:

```
C:\Program Files\NCBI\blast-2.17.0+\bin
```

Puedes comprobarlo ejecutando:

```bash
blastn -version
```

---

# Instalación y Configuración (LOCAL)

Para que los ejercicios locales funcionen, debes crear las bases de datos BLAST de forma manual o automática.

## 1. Clonar el repositorio
```bash
git clone https://github.com/raulmendoza21/BIOINFORMATICA-BLAST.git
cd BIOINFORMATICA-BLAST
```

## 2. Generar las Bases de Datos Locales

Asegúrate de tener los archivos:

```
mis_genomas.fasta
mis_proteinas.fasta
```

(Están incluidos en el repositorio o pueden ser creados manualmente.)

### A) Crear base de datos de nucleótidos (genomasbase)
```bash
makeblastdb -in mis_genomas.fasta -dbtype nucl -out genomasbase
```

### B) Crear base de datos de proteínas (proteinasbase)
```bash
makeblastdb -in mis_proteinas.fasta -dbtype prot -out proteinasbase
```

⚠️ **Nota importante en Windows:**  
Evita trabajar en rutas con espacios, tildes o la letra Ñ, ya que BLAST+ puede fallar al generar o buscar los archivos de base de datos.

---

# Guía de Ejecución

### 1. Iniciar Jupyter Notebook
```bash
jupyter notebook
```

### 2. Abrir el archivo  
`Bioinformatica_Sesion04_BLAST.ipynb`

### 3. Ejecutar el cuaderno
Primero ejecuta todas las celdas con definiciones (`def ...`).  
Luego usa las celdas de prueba para lanzar cada ejercicio.

---

# Ejemplos de llamadas a funciones

```python
# Ejercicio 1 (Online)
blastn_online_desde_teclado_mejorado()

# Ejercicio 2 (Local)
blastp_local_filtrado()

# Ejercicio 4 completo (Online)
ejercicio_4_online_completo()
```

---

# Solución de Problemas Comunes

### ❗ 1. `Command not found` o `FileNotFoundError`
BLAST+ no está instalado o no está en el PATH.  
Comprueba con:

```bash
blastn -version
```

### ❗ 2. Error “No alias or index file found”
La base de datos local no existe o no se generó bien.  
Ejecuta nuevamente `makeblastdb`.

### ❗ 3. BLAST Online tarda mucho
Es normal. Depende de los servidores del NCBI.

### ❗ 4. Cero resultados en BLAST local
Asegúrate de que las secuencias existen realmente en tus `.fasta`.  
Si la secuencia es muy corta, `blastn-short` puede ayudar.

---

# Estructura del repositorio

```
BIOINFORMATICA-BLAST/
│── Bioinformatica_Sesion04_BLAST.ipynb
│── mis_genomas.fasta
│── mis_proteinas.fasta
│── genomasbase.*      (generados con makeblastdb)
│── proteinasbase.*    (generados con makeblastdb)
│── README.md
```

Este README resume la práctica completa de BLAST y cómo ejecutar cada ejercicio en modo **online** y **local**.
