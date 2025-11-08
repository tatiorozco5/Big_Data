# Actividad 1

**Autores**
Tatiana Orozco Alzate

**Materia:** Big Data
**Tutor:** Andres Felipe Callejas
**Institución:** Institución Universitaria Digital de Antioquia

---

## 🚀 Problema

Electronic, una empresa de comercio electrónico está experimentando altas tasas de abandono de clientes y necesita mejorar la eficiencia de sus esfuerzos de marketing. Se requiere un análisis detallado del comportamiento de compra de los clientes y de las métricas de satisfacción para poder identificar qué clientes están en riesgo de abandonar la plataforma. El análisis está dirigido al equipo de Marketing y de Fidelización de la empresa.

---

## 📦 Dataset

**Fuente:** https://www.kaggle.com/datasets/shriyashjagtap/e-commerce-customer-for-behavior-analysis

---

## 📋 Variables Relevantes y Su Utilidad

El análisis se centra en las siguientes variables clave del dataset, elegidas por su impacto potencial en el comportamiento de abandono.

**Purchase_Date (Temporal):** Se utiliza para calcular hace cuanto tiempo compró el cliente.
**Customer_ID (Numerico):** Permite agrupar las transacciones y medir la frecuencia de cada cliente.
**Product_Category (Categorico):** Permite identificar que categorias son mas compradas.

---

## 🏗️ Diseño del Modelo Entidad-Relación (ERD)

La tabla CLIENTE almacena los datos personales y el indicador de abandono (Churn). La tabla TRANSACCION registra cada compra individual. Ambas tablas están conectadas por el Customer_ID en una relación de UNO a MUCHOS (1:N), lo que permite asociar todas las compras a un cliente específico para el análisis de comportamiento.

*Diagrama incluido como imagen*

---



