# Mi Primer Experimento en Hardware Cuántico Real (IBM Quantum + Qiskit)

¡Hola! Este repositorio contiene las pruebas y laboratorios que he desarrollado para adentrarme en el mundo de la computación cuántica, ejecutando algoritmos directamente sobre hardware real de IBM desde mi entorno de Kali Linux.

## 🚀 El Logro
El 4 de junio de 2026, logré conectar con éxito mi entorno virtual local con el procesador cuántico **ibm_marrakesh** (un sistema físico real de **156 qubits**).

### 📊 Detalles de la Ejecución:
* **Entorno:** Jupyter Notebook en Kali Linux (Python 3.13 / Qiskit 1.x)
* **ID del Trabajo (Job):** `d8ge3m9e8nrc73bfqueg`
* **Circuito:** Estado de Bell (Entrelazamiento Cuántico de 2 qubits)
* **Tiempo de uso del chip:** 12 segundos (Neto de procesamiento)
* **Resultado del valor esperado (Observable ZZ):** `0.989447...`

> 💡 *Nota de análisis:* El valor teórico ideal para este circuito es `1.0`. El resultado obtenido de `0.989` refleja el impacto del **ruido cuántico real** (decohorencia y fluctuaciones térmicas) sobre los qubits físicos de IBM, confirmando que la prueba se corrió en hardware real y no en un simulador clásico.
