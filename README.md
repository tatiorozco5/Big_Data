# 🚀Unidad 1. Evidencia de Aprendizaje 1 - Creación de una base de datos analítica

**Autores**

*Tatiana Orozco Alzate*
<br>
*Santiago Mesa Parra*

**Materia:** *Big Data*
<br>
**Tutor:** *Andres Felipe Callejas*
<br>
**Institución:** *Institución Universitaria Digital de Antioquia*

---

## ⚙️ Problema

La necesidad real de este análisis radica en que la empresa de e-commerce, simulada por el dataset, requiere reducir el coste de adquisición de clientes mediante la implementación de una estrategia de retención proactiva. El trabajo está dirigido al Equipo de Marketing y Fidelización, proporcionando una herramienta predictiva para intervenir solo en clientes en riesgo. Este problema requiere analítica avanzada porque el volumen de datos (comportamiento, compras, devoluciones) es demasiado complejo para el análisis manual. Se necesita modelos de clasificación que predigan el Churn y técnicas de segmentación que definan grupos de clientes para optimizar los esfuerzos y el presupuesto de retención.

---

## 📦 Dataset

**Fuente:** https://www.kaggle.com/datasets/shriyashjagtap/e-commerce-customer-for-behavior-analysis

---

## 📋 Variables Relevantes y Su Utilidad

El análisis se centra en las siguientes variables clave del dataset, elegidas por su impacto potencial en el comportamiento de abandono.

- **Churn (Binario):** Entrena el modelo para clasificar a los clientes como activos o inactivos.

- **Purchase_Date (Temporal):** Se utiliza para calcular hace cuanto tiempo compró el cliente.

- **Customer_ID (Numerico):** Permite agrupar las transacciones y medir la frecuencia de cada cliente.

- **Total_Purchase_Amount (Numerico):** Usada para calcular el gasto total. Permite priorizar a los clientes de alto valor para la retención..

---

## 🏗️ Diseño del Modelo Entidad-Relación (ERD)

La tabla CLIENTE almacena los datos personales y el indicador de abandono (Churn). La tabla TRANSACCION registra cada compra individual. Ambas tablas están conectadas por el Customer_ID en una relación de UNO a MUCHOS (1:N), lo que permite asociar todas las compras a un cliente específico para el análisis de comportamiento.

![alt text](docs/Diagrama%20ERD.png)

---

## 🛠️ Creación Base de Datos e Insertar Información

- **Carga con un SELECT * LIMIT 5**

![alt text](docs/image-1.png)

## 💾 Carga y Validación de Datos en Databricks SQL

- **Conteo de registros:**

Esta consulta devuelve un único número. Este valor representa la cantidad total de clientes únicos que existen en la tabla. Es la primera verificación de integridad de datos y confirma cuántas filas de cliente procesará el modelo de predicción de abandono (Churn).

![alt text](docs/image.png)

- **Nombres y tipo de comumnas - Databricks**

Esta información es crucial para verificar que los tipos de datos se cargaron correctamente y que el proceso de ingeniería de características podrá funcionar sin errores de casting.

![alt text](docs/image-2.png)

- **Consulta con filtro**

El resultado muestra una pequeña submuestra de los clientes que la empresa ha perdido o que han abandonado la plataforma. Esto permite a los analistas inspeccionar rápidamente las características de estos clientes (edad, género, etc.) antes de la etapa de modelado predictivo para buscar patrones iniciales.

![alt text](docs/SELECT.JPG)

##

# 🚀 Unidad 3. Evidencia de aprendizaje (EA2). Taller: procesamiento de datos en una infraestructura cloud


# Como levantar un Cluster en Databricks y reiniciar uno existente.

## 💻 1. Crear un Nuevo Cluster (Levantarlo)

Esta es la forma de "levantar" uno por primera vez con la configuración deseada:

**1. Ir a la sección de Cómputo (Compute):**

- En la barra lateral izquierda de tu espacio de trabajo de Databricks, haz clic en el icono de "Proceso" o "Compute" (dependiendo de la versión de la interfaz).

**2. Iniciar la Creación:**

- Haz clic en el botón "Crear Proceso" o "Create Compute".

**3. Configurar el Clúster:**

- **Nombre del Clúster:** Asigna un nombre único y descriptivo (ej: mi-cluster-analisis).

- **Política (Policy):** (Opcional) Si tu organización usa políticas, selecciona la adecuada.

- **Tipo de Clúster:** Generalmente será "Multiuso" (All-Purpose) para análisis interactivo o "Trabajo" (Job) para tareas automatizadas.

- **Versión de Databricks Runtime:** Selecciona la versión de Spark y Scala/Python que deseas usar (se recomienda la última versión estable).

- **Tipo de Nodo (Node Type) y Workers:** Define el tipo de máquina virtual (CPU, RAM) para el nodo controlador (Driver) y para los nodos de trabajo (Workers).

- **Número de Workers:** Especifica un número fijo o habilita el Autoescalado (Autoscaling) para establecer un rango mínimo y máximo de workers.

- **Terminación Automática (Auto-Termination):** Define un tiempo de inactividad (ej: 120 minutos) después del cual el clúster se apagará automáticamente para ahorrar costos.

**3. Lanzar el Clúster:**

- Haz clic en el botón "Crear Cómputo" o "Create Compute" en la parte inferior.

El clúster comenzará a arrancar. Verás su estado cambiar de "Pending" a "Starting" y finalmente a "Running" (en color verde). Una vez que esté en "Running", ya está "levantado" y listo para ser utilizado en tus Notebooks.

## 🔧 2. Reiniciar un Clúster Terminado (Terminated)

Si un clúster ya existe y se apagó automáticamente (terminó) o fue detenido manualmente:

**1. Ir a la sección de Cómputo (Compute):**

- Haz clic en "Proceso" o "Compute" en la barra lateral.

**2. Buscar el Clúster:**

- Localiza el clúster que deseas levantar. Estará en estado "Terminated" (ícono gris o rojo).

**3. Iniciar o Reiniciar:**

- Haz clic en el icono de "Play" (Iniciar) o el botón "Reiniciar" (Restart) junto al nombre del clúster.

Databricks recreará el clúster con el mismo ID, la misma configuración y volverá a instalar las librerías necesarias.


