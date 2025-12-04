# BIOINFORMATICA-BLAST  
Autores: Raul Mendoza, Adrian Ojeda  
Asignatura: Bioinformatica (ULPGC)

Este repositorio contiene exclusivamente la **práctica de BLAST (Sesión 04)** del laboratorio de Bioinformática.  
Aquí encontrarás el cuaderno `Bioinformatica_Sesion04_BLAST.ipynb`, donde se resuelven todos los ejercicios relacionados con el uso de **BLAST online y local** mediante Biopython.

---

# Contenido del proyecto

## Archivo principal
### `Bioinformatica_Sesion04_BLAST.ipynb`
Este cuaderno resuelve los cuatro ejercicios de la práctica:

---

## EJERCICIO 1 – BLASTN con secuencia introducida por teclado  
**Objetivo:**  
Pedir al usuario una secuencia de ADN por teclado y realizar un **BLASTN**:

- De forma **online** usando los servidores de NCBI.  
- De forma **local** usando BLAST+ instalado en la máquina.

**El programa debe mostrar:**
- Número de resultados (hits).  
- E-value del mejor hit.  
- Descripción del hit más similar.  

**Funciones implementadas:**
- `blastn_online_desde_teclado()`  
- `blastn_local_desde_teclado()`

**Cómo ejecutarlas en una celda nueva:**
```python
blastn_online_desde_teclado()
# o
blastn_local_desde_teclado()
```

---

## EJERCICIO 2 – BLASTP con filtrado por E-value  
**Objetivo:**  
Pedir una secuencia proteica por teclado y realizar un **BLASTP**:

- Online y local.  
- Guardar en un fichero todos los hits con **E-value < 0.001**, incluyendo:  
  - ID  
  - Longitud  
  - E-value  
  - Porcentaje de identidad  

**Funciones:**
- `blastp_online_filtrado()`  
- `blastp_local_filtrado()`

**Ejemplo de uso:**
```python
blastp_online_filtrado()
# Genera el archivo: blastp_online_filtrado.txt
```

---

## EJERCICIO 3 – BLASTN desde un archivo FASTA filtrando por organismo  
**Objetivo:**  
Leer una secuencia de ADN desde un archivo FASTA, ejecutar BLASTN y **filtrar resultados por organismo**.

**El programa debe:**
- Mostrar cuántos resultados pertenecen al organismo filtrado.  
- Calcular y mostrar el **E-value medio** de esos hits.  

**Funciones:**
- `blastn_online_desde_fasta_filtrado_organismo(fasta, organismo)`  
- `blastn_local_desde_fasta_filtrado_organismo(fasta, organismo)`

**Ejemplo de uso:**
```python
blastn_online_desde_fasta_filtrado_organismo("query.fasta", "Homo sapiens")
```

---

## EJERCICIO 4 – Uso de las cinco utilidades de la suite BLAST  
Las herramientas evaluadas son:

1. `blastn`  
2. `blastp`  
3. `blastx`  
4. `tblastn`  
5. `tblastx`

El objetivo es:
- Ejecutar un ejemplo online y local con cada utilidad.  
- Revisar qué especies contienen los homólogos más cercanos.  
- Observar porcentajes de identidad y cobertura.  

**Funciones online:**
- `lanzar_blastn_online(secuencia)`
- `lanzar_blastp_online(secuencia)`
- `lanzar_blastx_online(secuencia)`
- `lanzar_tblastn_online(secuencia)`
- `lanzar_tblastx_online(secuencia)`

**Funciones locales:**
- `ejemplos_blast_local(dna_seq, prot_seq)`

**Mostrar resumen de hits:**
```python
resumen_mejor_hit(record)
```

---

# Requisitos

## Python
- Python 3.8+  
- Bibliotecas necesarias:
  ```
  pip install biopython jupyter
  ```

## Para BLAST online
- Conexión a internet.  
- Una dirección de correo (NCBI lo solicita por responsabilidad).

## Para BLAST local
- Tener instalado **BLAST+** (blastn, blastp, blastx, tblastn, tblastx).  
- Tener bases de datos locales creadas con `makeblastdb`.  
- Tener los ejecutables en el PATH o indicar sus rutas completas.

---

# Cómo ejecutar el proyecto

## 1. Clonar el repositorio
```bash
git clone https://github.com/raulmendoza21/BIOINFORMATICA-BLAST.git
cd BIOINFORMATICA-BLAST
```

## 2. Abrir Jupyter Notebook
```bash
jupyter notebook
```

## 3. Abrir el archivo
`Bioinformatica_Sesion04_BLAST.ipynb`

## 4. Ejecutar todas las celdas de definición
Menú: **Cell → Run All**

## 5. Llamar a las funciones según el ejercicio
Cada ejercicio requiere que escribas una celda nueva con llamadas como:

```python
blastn_online_desde_teclado()
blastp_online_filtrado()
blastn_online_desde_fasta_filtrado_organismo("query.fasta", "Homo sapiens")
ejemplos_blast_local(dna_ejemplo, prot_ejemplo)
```

---

# Notas finales

- Si usas BLAST local, asegúrate de que las bases de datos existen y están bien configuradas.  
- El cuaderno está comentado en estilo claro de alumno universitario, según lo pedido en la práctica.  
- El repositorio contiene exclusivamente la práctica de BLAST, sin incluir contenidos de alineamientos.

