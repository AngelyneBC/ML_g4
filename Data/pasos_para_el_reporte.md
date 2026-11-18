# Pasos para terminar el reporte (parte que debe hacerse sin IA)

Regla del proyecto: la IA solo puede usarse en el reporte para **corrección gramatical**. Todo lo demás lo redactan ustedes. Estos pasos están ordenados para llegar a la entrega con tiempo.

## Paso 1. Repartir el trabajo (30 min, todo el grupo)
- Asignen secciones por persona y anótenlo: la sección **Aportes** del reporte y los comentarios del notebook lo piden.
- Decidan quién será el "editor final" que unifique estilo y revise límites de páginas.
- Pregunten al profesor (Escobedo) si rige la plantilla del Entregable 1 o el enunciado: la plantilla no tiene *Experimentación* ni *Aportes*, y el enunciado no menciona *Estado del arte* ni *Trabajos futuros*.

## Paso 2. Leer las fuentes (cada uno 2 a 3 horas)
Lean completos y anoten qué hicieron, qué métricas reportaron y qué limitaciones admiten:
- Artículo de PMC del dataset de obesidad (PMC6710633).
- Artículo ACM de la plantilla (10.1145/3506695).
- Realinho et al. (2022), *Data* 7(11), 146: dataset de deserción.
- De-La-Hoz-Correa et al. (2019), *Journal of Computer Science* 15(1): obesidad con J48, Naive Bayes y Simple Logistic.
- Molina Estren et al. (2021): obesidad con LMT, Random Forest, MLP y SVM, y selección de variables.

Para **Antecedentes** busquen la fuente original de cada técnica y cítenla. Puntos de partida (verifiquen año, revista y datos exactos en la fuente antes de citar): Akiba et al. 2019 (Optuna), Bergstra et al. 2011 (TPE), Chawla et al. 2002 (SMOTE), Cortes y Vapnik 1995 (SVM), Cover y Hart 1967 (KNN), Friedman 2001 (Gradient Boosting), Geurts et al. 2006 (Extra Trees), Pedregosa et al. 2011 (scikit-learn), y un libro de texto como Hastie, Tibshirani y Friedman (*The Elements of Statistical Learning*) o James et al. (*ISLR*).

## Paso 3. Ejecutar y entender el notebook (1 a 2 horas)
1. Corran `proyecto_ML.ipynb` completo. Para mejor afinamiento suban `N_TRIALS` (por ejemplo a 50) en la celda de configuración; tarda más.
2. Abran `resultados/comparativa_modelos.csv` y la carpeta `figuras/`: de ahí salen las tablas y gráficas del reporte.
3. Completen las celdas de **Interpretación** con sus palabras.
4. Completen la cabecera: aportes por integrante y **el prompt exacto** que usaron con la IA. La regla dice que la IA es para cuando estén atascados con algo específico del código; reflejen eso con honestidad.
5. Suban el notebook a un repositorio de GitHub o adjúntenlo, como pide el enunciado.

## Paso 4. Hacer el diagrama de Metodología (1 hora)
Dibujen en draw.io o PowerPoint el flujo: carga → limpieza y EDA → partición 80/20 → preprocesamiento → selección de features → afinamiento con Optuna (validación cruzada en train) → evaluación en test → comparativa. Es obligatorio por el enunciado.

## Paso 5. Redactar cada sección (de dónde sacar el material)

| Sección | Qué sacar y de dónde |
|---|---|
| Introducción | Problema, importancia, quiénes crearon cada dataset (Paso 2), solución en grandes rasgos. Máx. 1 página |
| Antecedentes / Estado del arte | Descripción de SVM, MLP, KNN, regresión logística, Gradient Boosting, Extra Trees, SelectKBest, Optuna/TPE, SMOTE, F1 macro. Con fuentes del Paso 2. Máx. 2 páginas |
| Metodología | Diagrama del Paso 4 + una frase por etapa. Media a una página |
| Experimentación | Descripción de cada dataset (celdas de EDA), decisiones de limpieza (columnas con tabulador, códigos nominales con one-hot, 24 duplicados eliminados), partición, espacio de búsqueda de Optuna (celda `sugerir_modelo`). Máx. 3 páginas |
| Resultados | Tabla de `comparativa_modelos.csv`, gráfica de comparativa, matrices de confusión, historia de Optuna. Interpretarlos, no solo pegarlos. Unas 2 páginas |
| Discusión | Qué decisiones mejoraron resultados (afinamiento, selección de features, escenario sin peso ni altura). **Obligatorio**: un par de párrafos de ética y repercusión social (ver preguntas abajo). 1 a 2 páginas |
| Conclusiones y trabajos futuros | Resultados clave, lecciones, limitaciones y siguientes pasos |
| Aportes | Qué hizo cada integrante en código y en reporte |
| Resumen, Abstract, palabras clave | Escríbanlos **al final**, cuando ya sepan los resultados. Máx. 300 palabras, sin referencias |
| Referencias | Formato APA, solo fuentes realmente citadas |

Preguntas para disparar la discusión ética (respóndanlas ustedes):
- ¿Es justo que un modelo use género, nacionalidad o deuda para predecir quién abandona? ¿Qué le pasaría a un estudiante marcado como "riesgo"?
- ¿Para qué se usaría la predicción: apoyar al estudiante o penalizarlo?
- En obesidad, ¿qué riesgo hay en clasificar a personas por su cuerpo, y en entrenar con 77 % de datos sintéticos de solo tres países?
- ¿Qué pasa si un modelo con 97 % de exactitud se apoya en peso y altura y no en hábitos?

## Paso 6. Dos puntos que conviene que discutan explícitamente
1. **Fuga de información en obesidad**: con `Height` y `Weight` el desempeño es altísimo; sin ellos baja mucho. Interpreten qué significa.
2. **Datos sintéticos (SMOTE)**: por qué una partición aleatoria puede inflar las métricas.

## Paso 7. Corrección gramatical (único uso permitido de IA en el reporte)
Con el texto ya escrito, pueden pedir a una IA solo "corrige ortografía y gramática sin cambiar el contenido ni agregar ideas". Revisen que no haya reescrito nada de fondo.

## Paso 8. Revisión final (el día anterior a la entrega)
- Respeten los límites de páginas de cada sección.
- Portada completa (los cuatro autores, fecha, docente) y correos institucionales.
- Todas las citas del texto están en Referencias y viceversa.
- El notebook corre de punta a punta, trae aportes por integrante y el prompt de IA como comentario.
- Entrega: **viernes de la semana 14, 23:00**. Súbanlo con margen.
