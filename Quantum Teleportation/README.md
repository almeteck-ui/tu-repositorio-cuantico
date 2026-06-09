# 🚀 Laboratorio de Computación Cuántica Real (Qiskit 1.x + IBM Quantum)

Este repositorio contiene las pruebas, laboratorios y algoritmos avanzados que he desarrollado para adentrarme en la computación cuántica, ejecutando código directamente sobre hardware cuántico real de IBM utilizando **Kali Linux** como entorno de desarrollo.

---

## 🌌 El Logro Principal: Protocolo de Teletransportación Cuántica

El 8 de junio de 2026, logré implementar y ejecutar con éxito un **Protocolo de Teletransportación Cuántica** con lógica condicional dinámica en tiempo real utilizando el procesador cuántico **ibm_marrakesh** (una máquina física real basada en arquitectura de **156 qubits**).

El objetivo del experimento fue destruir la información de un estado cuántico de superposición en un Qubit A (Alice) y reconstruirlo de manera idéntica en un Qubit B (Bob) utilizando el entrelazamiento cuántico como canal seguro.

### 📊 Detalles Técnicos de la Ejecución:
* **Entorno de Trabajo:** Jupyter Notebook en Kali Linux (Python 3.13 / Qiskit 1.x)
* **ID del Trabajo (Job ID):** `d8jntsjqv2lc7384b5n0`
* **Procesador Cuántico Físico:** `ibm_marrakesh` (156 qubits)
* **Número de Disparos (Shots):** 1024 ejecuciones independientes
* **Fidelidad Obtenida (Fidelity):** **97.17%** (Éxito de reconstrucción en 995 de 1024 disparos)
* **Ideal Teórico Matemático:** 1.0000 (100%)

---

## 🛠️ Estructura del Circuito Implementado

El circuito consta de 3 qubits y utiliza las primitivas modernas de **Qiskit Runtime (SamplerV2)** para la obtención de los conteos brutos (*raw counts*).

1. **Preparación del Mensaje ($q_0$):** Se aplica una compuerta Hadamard ($H$) para poner el mensaje en un estado de superposición perfecta.
2. **Generación del Canal Entrelazado ($q_1$ y $q_2$):** Creación de un Estado de Bell a través de compuertas $H$ y $CNOT$.
3. **Medición de Alice:** Colapso del estado cuántico y envío de dos bits clásicos de información ($c_0$ y $c_1$).
4. **Lógica Condicional Dinámica (Feed-Forward):** Bob aplica correcciones en tiempo real ($X$ o $Z$) sobre $q_2$ dependiendo de los bits clásicos recibidos, utilizando la instrucción `if_else()` adaptada a la última versión de Qiskit.
5. **Verificación:** Rotación final y medición del qubit de Bob ($q_2$) para evaluar la fidelidad del proceso frente al ruido ambiental.

---

## 📈 Análisis de Resultados (Manejo del Ruido Cuántico)

Los conteos brutos devueltos por el chip real de IBM reflejan el comportamiento del hardware en la era NISQ (*Noisy Intermediate-Scale Quantum*):

```python
Raw counts: {
    '000': 249, '011': 232, '001': 263, '010': 251,  # -> ÉXITO (Bob lee 0) = 995 shots
    '100': 6,   '101': 7,   '111': 8,   '110': 8     # -> Ruido Térmico (Bob lee 1) = 29 shots
}
