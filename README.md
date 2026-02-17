# Limpieza y Preparación de Datos — Ventas y RRHH

## Descripción
Se realizó el proceso de limpieza, estandarización y validación de tres datasets empresariales (Ventas, Empleados y Evaluaciones) con el objetivo de obtener datos consistentes y confiables para análisis en Power BI.

**Datos originales**
- ventas.xlsx  
- empleados.xlsx  
- evaluaciones.csv  

**Datos finales**
- ventas_limpio.csv  
- empleados_limpio.csv  
- evaluaciones_limpio.csv  

---

# Dataset: Ventas

## 📌 Problema
Dataset de 150 registros con alta presencia de nulos, inconsistencias entre producto y precio, errores de formato y registros incompletos.

## 🔎 Detección
- precio en formato texto  
- incoherencia producto–precio  
- cantidad en float  
- columna fecha_venta con alta nulidad  
- registros sin información recuperable  

## 🛠 Decisiones
- Eliminación de fecha_venta  
- Conversión y normalización de precio  
- Corrección de producto según precio  
- Estandarización de categoría  
- Imputación mínima de cantidad = 1  
- Reemplazo de cliente nulo por "cliente_no_informado"  
- Eliminación de registros sin valor analítico  

## ✅ Resultado
Dataset consistente, tipado correctamente y con mínima pérdida de información.

---

# Dataset: Empleados

## 📌 Problema
Registros con tipos incorrectos, valores nulos, duplicados lógicos y datos irreales (edad, salario, sexo y fechas).

## 🔎 Detección
- edad, salario y fecha en texto  
- edades atípicas  
- inconsistencias en sexo y departamento  
- múltiples registros contradictorios por nombre  

## 🛠 Decisiones
- Estandarización de texto  
- Conversión de tipos (edad, salario, fecha)  
- Normalización de sexo  
- Eliminación de edades irreales  
- Eliminación de registros con nulos críticos  
- Resolución de duplicados por reglas de negocio  
- Validación con escalas salariales y género  

## ✅ Resultado
Dataset depurado y coherente, apto para análisis de RRHH.

---

# Dataset: Evaluaciones

## 📌 Problema
Registros de desempeño incompletos y evaluaciones sin correspondencia válida con empleados.

## 🔎 Detección
- comentarios faltantes  
- evaluaciones sin score  
- empleados sin métricas evaluativas  
- duplicidad de nombre en empleados  

## 🛠 Decisiones
- Completar comentarios según score_desempeño (tabla de equivalencias)  
- Eliminación de evaluaciones sin métricas objetivas  
- Exclusión de empleados sin evaluación válida  
- Vinculación con padrón depurado de empleados  

## ✅ Resultado
Dataset de evaluaciones consistente y correctamente vinculado con empleados para análisis de desempeño.

---

# Resultado final
Se obtuvieron tres datasets limpios y relacionados que permitieron construir un modelo analítico confiable en Power BI para análisis comercial y de RRHH.

**Herramientas:** Python (pandas), Excel, Power BI
