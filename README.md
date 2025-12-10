# Secuenciacion de ADN y prediccion del tipo de gen usando IA

Este proyecto implementa un pipeline de aprendizaje automatico para predecir el **tipo de gen (GeneType)** a partir de **secuencias de ADN**.  
Se utilizan datos reales de genes humanos anotados (NCBI) y modelos de **regresion logistica** con representacion **TF-IDF de 3-gramas de caracteres** (codones).

El trabajo integra conceptos de **bioinformatica** y **aprendizaje automatico**, dentro de la materia de Inteligencia Artificial.

---

## Contexto academico

- **Universidad**: Universidad Mayor de San Andres (UMSA)  
- **Carrera**: Informatica  
- **Materia**: INF-372 Inteligencia Artificial  
- **Docente**: PhD Moises Martin Silva Choque  

### Integrantes

- Carlos Manuel Miranda Aguirre  
- Geneiss Jalid Tapia Cortez  
- Alan Israel Arnez Flores  

---

## Objetivo del proyecto

Desarrollar y evaluar un sistema de IA que, a partir de la secuencia de nucleotidos de un gen, sea capaz de predecir su **tipo de gen** (`GeneType`) y analizar el comportamiento del modelo bajo distintas definiciones de etiqueta:

1. Clasificacion multiclase original (todas las clases de `GeneType`).
2. Clasificacion binaria `PSEUDO` vs `OTHERS`.
3. Clasificacion binaria (`PSEUDO`, `BIOLOGICAL_REGION`) vs `OTHERS`.
4. Clasificacion multiclase reducida (`PSEUDO`, `BIOLOGICAL_REGION`, `ncRNA`, `OTHERS`).

---

## Descripcion biologica breve

Una secuencia genetica de ADN se compone de:

- **Nucleotidos**: A, C, G, T.  
- **Codones**: tripletes de nucleotidos que codifican aminoacidos o senales STOP.  
- **Exones**: regiones codificantes (producen proteina).  
- **Intrones**: regiones no codificantes.  
- **Regiones reguladoras**: promotores, potenciadores, UTR, etc.  
- **Genes funcionales vs pseudogenes**: los pseudogenes suelen tener marcos de lectura alterados, mutaciones o interrupciones.

El modelo usa **TF-IDF de 3-gramas a nivel de caracteres**, lo que equivale a trabajar directamente con **codones**, capturando patrones caracteristicos de exones, intrones, regiones reguladoras y pseudogenes.

---

## Dataset

- Dataset basado en genes humanos anotados en NCBI.  
- Archivos utilizados:
  - `dna-sequence-prediction/train.csv`
  - `dna-sequence-prediction/validation.csv`
  - `dna-sequence-prediction/test.csv`
- Columnas principales:
  - `NCBIGeneID`
  - `Symbol`
  - `Description`
  - `GeneType`
  - `GeneGroupMethod`
  - `NucleotideSequence`

El dataset viene ya dividido en **entrenamiento**, **validacion** y **prueba**, lo que permite una evaluacion limpia de los modelos.


