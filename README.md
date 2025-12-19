# QAOA-TSP-Quantum-Project
Proyecto para la cátedra Fundamentos de la Computación Cuántica 2025-II (UCN). Implementación de QAOA para resolver el Problema del Viajante (TSP) utilizando Qiskit. Grupo 1.

# Resolución del Problema del Viajante (TSP): Enfoque Cuántico vs Clásico

Este repositorio contiene la implementación y análisis comparativo para resolver el Problema del Viajante (Traveling Salesman Problem - TSP) utilizando dos paradigmas de computación:

1.  **Computación Cuántica (QAOA):** Implementación del algoritmo *Quantum Approximate Optimization Algorithm* utilizando Qiskit para validar la formulación del Hamiltoniano en instancias pequeñas.
2.  **Computación Clásica (Gurobi):** Optimización exacta utilizando el solver Gurobi para resolver la instancia completa.

## Descripción del Proyecto

El objetivo es encontrar la ruta óptima para un conjunto de ciudades definido en `Europa.txt` (29 ciudades).

Debido a las limitaciones actuales de escalabilidad ($N^2$ qubits necesarios), se adoptó una estrategia híbrida:
* **Validación Teórica:** Se utiliza QAOA para resolver una sub-instancia de **3 ciudades** ($3^2=9$ qubits), demostrando la corrección del modelo de energía (Hamiltoniano).
* **Solución Real:** Se utiliza el algoritmo clásico *Branch-and-Bound* para resolver la instancia completa de **29 ciudades** de manera eficiente.

## Requisitos Previos

* Python 3.8 o superior.
* Visual Studio Code (recomendado) con la extensión de Jupyter instalada.
* Git.

## Instalación y Configuración (Paso a Paso)

Para ejecutar este proyecto sin errores en Visual Studio Code, sigue estos pasos exactos en tu terminal:

### 1. Clonar el repositorio
```bash
git clone [https://github.com/Grupo1-QAOA-UCN/QAOA-TSP-Quantum-Project](https://github.com/Grupo1-QAOA-UCN/QAOA-TSP-Quantum-Project)
cd QAOA-TSP-Quantum-Project
```
### 2. Crear y activar un entorno virtual
Es necesario aislar las librerías del proyecto.

En **Windows**:
```bash
python -m venv venv
.\venv\Scripts\activate
```

En **Mac/Linux**:
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar Dependencias
Instala las librerías de Qiskit, Gurobi y herramientas de visualización:
```bash
pip install numpy matplotlib networkx qiskit qiskit-optimization qiskit-algorithms gurobipy ipykernel
```

### 4. Registrar el Kernel para VS Code
Para asegurar que VS Code detecte este entorno virtual como un Kernel de Jupyter válido, ejecuta:
```bash
python -m ipykernel install --user --name=venv --display-name "Python (venv)"
```

## Cómo Ejecutar
1. Abre el archivo `TSP_Quantum_vs_Classical.ipynb` en VS Code.
2. En la parte superior derecha, haz clic en **"Select Kernel"** (o "Seleccionar Kernel").
3. Selecciona la opción **"Python (venv)"** que acabamos de crear.
4. Ejecuta las celdas secuencialmente.
