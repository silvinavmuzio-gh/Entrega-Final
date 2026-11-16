# Predicción final · Analista Sr · Silvina Muzio

**Competencia:** labo-1-virtual-2026-analista-sr

**Submit final:** `KA9507_s25_10000.csv`, con 10.000 envíos. Score: 454.998

**Script:** `739_final_senior-SVM-7.ipynb`

## Estrategia

**Intenté hacer:**

- un semillerío en la función a maximizar en la Optimización Bayesiana
- un semillerío para la creación de modelos, para luego obtener una probabilidad promedio para cada cliente
- un ensemble de estas probabilidades obtenidos con varias corridas de las notebooks con semillas distintas (5 por falta de tiempo, de hecho no llegué a completar estas ejecuciones)
- tomando el baseline de la cátedra para FE (aunque exploré en algún momento alguna variación)

## Detalle de corridas

|  | Intentos iniciales (3) | 739_final_senior-SVM-4.ipynb | 739_final_senior-SVM-5.ipynb | 739_final_senior-SVM-6.ipynb | 739_final_senior-SVM-7.ipynb<br>(ENVIADA A KAGGLE) | 739_final_senior-SVM-8.ipynb | 739_final_senior-SVM-9.ipynb |
|---|---|---|---|---|---|---|---|
| **Objetivo/Resultado** | Correr un primer algoritmo y lograr buena ganancia/<br>Fallido. Se morían las VMs | Lograr finalizar una corrida/Logrado, pero con mala ganancia | Mejorar la ganancia/Fallido. Se murió la VM | Mejorar la ganancia/Fallido. Lo cancelé por tiempo (demoraba demasiado) | Mejorar la ganancia/Logró finalizar (2 ds). Ganancia mejorada. | Mejorar la ganancia/Fallido. Lo cancelé por tiempo (llevaba dia y medio, le faltaba mucho para terminar y me restaba probar con el ensemble de predicciones) | Mejorar la ganancia/Aun ejecutando al cierre de la competencia (no llegó a postear en Kaggle antes del fin del dia 15/11) |
| **Catastrophe Analysis** |  | Interpolar | NA | NA | NA | NA | NA |
| **FEhist Feature Engineering historico** |  | 1 lag/delta lag | 2 lag/delta lag | 2 lag/delta lag | 2 lag/delta lag | 2 lag/delta lag | 2 lag/delta lag |
| **Training Strategy (meses)** |  | 012021 a 052021 | 012019 a 052021 | 012019 a 052021 | 012019 a 052021 | 012019 a 052021 | 012021 a 052021 |
| **Training Strategy (validación)** |  | 072021 | 072021 | 072021 | 072021 | 072021 | 072021 |
| **Training Strategy (undersampling)** |  | 0,5 | 0,2 | 0,2 | 0,2 | 0,2 | 0,2 |
| **Hyperparameter Tuning-num iterations** |  | 50 | 50 | 50 | 45 | 42 | 40 |
| **Hyperparameter Tuning-Semillerío BO** |  | 100 | 100 | 100 | 50 | 22 | 8 |
| **Hyperparameter Tuning-Optimiz de: num_iterations** |  | 4 a 8 (2^x) | 4,5 a 9 (2^x) | 4,5 a 9 (2^x) | 4,5 a 9 (2^x) | 9 a 12 (2^x) | 9 a 10,8 (2^x) |
| **Hyperparameter Tuning-Optimiz de: num_leaves** |  | 5 a 8 (2^x) | 4 a 8 (2^x) | 4 a 8 (2^x) | 4 a 8 (2^x) | 6 a 11,5 (2^x) | 6 a 10 (2^x) |
| **Hyperparameter Tuning-Optimiz de: learning_rate** |  | -5 a 0 (2^x) | -5,5 a 0 (2^x) | -5,5 a 0 (2^x) | -5,5 a 0 (2^x) | -7 a -1 (2^x) | -7 a -1 (2^x) |
| **Hyperparameter Tuning-Optimiz de: feature_fraction** |  | 0,15 a 0,5 | 0,15 a 0,5 | 0,15 a 0,5 | 0,15 a 0,5 | 0,15 a 0,4 | 0,15 a 0,4 |
| **Hyperparameter Tuning-Optimiz de: min_sum_hessian_in_leaf** |  | -5 a 5 (2^x) | -5 a 5 (2^x) | -5 a 5 (2^x) | -5 a 5 (2^x) | 3 a 6,5 (2^x) | 3 a 6,5 (2^x) |
| **Final Training (meses)** |  | 012021 a 072021 | 012019 a 072021 | 012019 a 072021 | 012019 a 072021 | 012019 a 072021 | 012021 a 072021 |
| **Final Training (semillerío)** |  | 30 | 50 | 50 | 25 | 32 | 15 |
| **Ensemble Predicciones** |  | 1 (sin) | 1 (sin) | 1 (sin) | 1 (sin) | 1 (sin) | 5 (con) |
| **Kaggle-Mejor Ganancia** |  | 419,218 | -- | -- | 454998 | -- | -- |
| **VM** |  | 8vCPU-128GB | 8vCPU-128GB | 12vCPU-512GB | 12vCPU-512GB | 12vCPU-512GB | 12vCPU-512GB |

**Nota:** Datadrifting y FE intra-mes, FE clasif clientes (RF), Red Dimensiones (Canaritos): siempre standard (sin cambios)

## Issues presentados

- Perdida de tiempo en corridas fallidas.
- Y, en corrida final: Al crear las 5 corridas para luego hacer el ensemble, puse 9509-1, 9509-2, etc. R toma este guión como un menos. Es decir, 9509-1 comenzó a grabar sobre 9508 y 9509-2 comenzó a grabar sobre 9507 (pisando algunos de los archivos de la corrida que había enviado a Kaggle al momento. Fueron pocos, porque lo finalicé pronto. Los de FE.)

## Archivos entregados

- `739_final_senior-SVM-7.ipynb`
- `WF9507`:
  - Archivos de ejecución
  - `KA9507_s25_10000.csv`
