### 1. Directorio `mri/` (Volúmenes) 🧠

Este directorio contiene los archivos volumétricos del cerebro en diferentes etapas de procesamiento. Son esenciales para el análisis de la materia gris, la blanca y el líquido cefalorraquídeo.

* `orig.mgz`: Es la imagen de RM T1w original del sujeto, después de ser convertida al formato de FreeSurfer y conformada (reescalada y reorientada a un tamaño de voxel y orientación estándar). Es tu punto de partida.
* `brainmask.mgz`: Esta es la imagen del cerebro después de haberle "quitado el cráneo" (skull-stripping). Es crucial porque elimina los tejidos no cerebrales, permitiendo un análisis más limpio.
* `wm.mgz`: Contiene la segmentación de la sustancia blanca. Es una máscara volumétrica de la materia blanca del cerebro.
* `aseg.mgz` (o `aparc+aseg.mgz`, `aparc.a2009s+aseg.mgz`): Este es uno de los archivos más importantes. Contiene la **segmentación volumétrica de las estructuras subcorticales y el tronco encefálico**, así como la **parcellación cortical volumétrica**. Cada voxel tiene una etiqueta numérica que corresponde a una estructura o región cerebral específica (ej., hipocampo, amígdala, tálamo, cerebelo, etc., y también las regiones de la corteza). Es fundamental para obtener volúmenes de estas estructuras.

### 2. Directorio `surf/` (Superficies Corticales) 🌐

Aquí se guardan las reconstrucciones de las superficies 3D del cerebro, que son esenciales para el análisis basado en la superficie, como el grosor cortical.

* `{lh,rh}.white`: Representa la superficie que se encuentra en el límite entre la sustancia blanca y la sustancia gris para el hemisferio izquierdo (`lh`) y el derecho (`rh`). Es la superficie interna de la corteza.
* `{lh,rh}.pial`: Representa la superficie que se encuentra en el límite entre la sustancia gris y el líquido cefalorraquídeo (la superficie "exterior" del cerebro).
* `{lh,rh}.inflated`: Estas son las superficies `white` y `pial` que han sido "infladas" para aplanar los pliegues corticales (surcos y giros). Esto facilita la visualización y la comparación entre sujetos, ya que las regiones se "despliegan".
* `{lh,rh}.thickness`: Este archivo contiene un valor de grosor cortical para cada vértice (punto) en la superficie de la corteza. Es una de las medidas más utilizadas y sensibles en la investigación del envejecimiento y enfermedades como el Alzheimer. 📏
* `{lh,rh}.area`: Similar al grosor, este archivo contiene el área de la superficie cortical por vértice.
* `{lh,rh}.curv`: Contiene información sobre la curvatura de la superficie cortical, lo que ayuda a identificar surcos (curvatura negativa) y giros (curvatura positiva).

### 3. Directorio `stats/` (Estadísticas Resumidas) 📊

Este directorio es donde FreeSurfer condensa gran parte de la información cuantitativa en archivos de texto legibles.

* `{lh,rh}.aparc.stats`: Estos archivos son extremadamente importantes. Contienen tablas de estadísticas resumidas para cada región cortical definida por un atlas (por ejemplo, el atlas Desikan-Killiany o Destrieux, que están integrados en FreeSurfer). Para cada región, obtendrás métricas como:
    * **Volumen de la sustancia gris** (en mm³).
    * **Grosor cortical medio** (en mm).
    * Área de la superficie.
    * Curvatura.
    * Número de vértices.
    Estos datos son ideales para análisis estadísticos a nivel de grupo, por ejemplo, para comparar el grosor de una región específica entre pacientes y controles.
* `aseg.stats`: Similar a los archivos `.aparc.stats`, este archivo contiene las estadísticas volumétricas (en mm³) para cada una de las estructuras subcorticales y del tronco encefálico segmentadas en `aseg.mgz`. Esencial para el análisis de volúmenes de estructuras profundas.

### 4. Directorio `label/` (Etiquetas y Parcellaciones) 🏷️

Contiene archivos que definen regiones específicas del cerebro en las superficies.

* `{lh,rh}.aparc.annot`: Estos archivos de "anotación" contienen la información de las parcellaciones corticales (las divisiones de la corteza en regiones según un atlas, como el Desikan-Killiany). Son la base para generar los archivos `.aparc.stats`.

### 5. Directorio `scripts/` (Registros y Logs) 📜

Aunque no son directamente "datos" para el análisis, son cruciales para entender y depurar el procesamiento.

* `recon-all.log`: Este es el archivo de registro principal. Contiene un historial detallado de todos los comandos ejecutados por FreeSurfer para procesar el sujeto. Si hay errores o problemas, este es el primer lugar donde buscar.

En resumen, para extraer información relevante para tu tesis, te centrarás principalmente en los archivos de los directorios `stats/` (para datos numéricos resumidos como volúmenes y grosores) y `surf/` (para mapas de grosor, área, etc., que se pueden visualizar o usar en análisis basados en la superficie), así como `mri/aseg.mgz` para la segmentación volumétrica detallada. Los archivos en `mri/` y `surf/` se visualizan con herramientas como `Freeview` (propio de FreeSurfer) o `BrainBrowser`, mientras que los archivos `.stats` se leen fácilmente con software de hoja de cálculo o lenguajes de programación como Python o R para análisis estadísticos.

---

## Escala de Demencia Clínica (CDR) hasta Nivel 2 📊

La Escala de Demencia Clínica (CDR) es una herramienta estándar utilizada para clasificar la gravedad del deterioro cognitivo y funcional. Aquí te la presento, enfocándonos en los niveles iniciales y moderados:

* **CDR 0:** **Normal / Sin Demencia**
    * No hay deterioro cognitivo ni funcional significativo. La persona realiza sus actividades diarias sin dificultad.
* **CDR 0.5:** **Demencia Muy Leve (Deterioro Cognitivo Leve Cuestionable)**
    * Hay un deterioro cognitivo ligero, a menudo notable en la memoria, pero que no interfiere de manera sustancial con las actividades cotidianas más complejas. La persona sigue siendo independiente.
* **CDR 1:** **Demencia Leve**
    * El deterioro cognitivo es claro y ya comienza a afectar la participación en actividades diarias habituales, como el trabajo, pasatiempos o interacciones sociales. La persona podría requerir cierta ayuda o supervisión ocasional.
* **CDR 2:** **Demencia Moderada**
    * Existe un deterioro cognitivo considerable. La persona necesita ayuda o supervisión significativa para la mayoría de sus actividades diarias, y su capacidad de juicio y resolución de problemas se ve notablemente afectada.

---
