<div class="row">
  <div class="column"><img src="https://github.com/analiticafp/Conflicto-de-intereses/blob/16a1c1133735c5bdef2527b96ec502e8b0e6f63d/img/layout_set_logo.png" align="left" alt="Función Pública"></div>
  <div class="column" align="center"><div><b>Documentación proyecto analítica V.1</b><br>Ultima actualización: Junio de 2021</div>
</div>

<br>
<h1 > Análisis de datos para la identificación y parametrización de posibles conflictos de interes en el aplicativo de reporte de Ley 2013 </h1>

<h2>Participantes</h2>
<ul>
 <li type="circle">Maritza Ibarra Duarte, Analista de datos,  mibarra@funcionpublica.gov.co</li>
 <li type="circle">Camilo Alejandro Tamayo Quintana, Analista de datos,  ctamayo@funcionpublica.gov.co</li>
 <li type="circle">Leonardo Sanchez Acuña, Analista de negocio, lsanchez@funcionpublica.gov.co</li>
 <li type="circle">Miguel Sebastian Rincon Ortega, Analista de datos, mrincon@funcionpublica.gov.co</li>
</ul>
  
<h2>Resumen</h2>
<p>Para el desarrollo de este ejercicio se tomó el reporte de ley 2013 y conflictos de interés diligenciado por los sujetos obligados para el periodo de 2021, con el fin de identificar y clasificar los posibles conflictos de interés que se puedan generar, para lo cual se utilizo minería de texto para extraer aquella frases y palabras que nos describieran el posible conflicto de interés y finalmente se agruparon por categorías.</p>
  
<h2>Problema</h2>
<p>Actualmente, según lo establece la Ley 2013 de 2019, Función Pública captura en el aplicativo dispuesto para ello, la infomación de declaraciones de bienes, rentas y conflictos de intereses de los sujetos obligados a declarar, la cual es un insumo importante para el desarrollo de acciones en torno a las políticas de transparencia, integridad, rendición de cuentas y control social; sin embargo, esta información, en particular la correspondiente a los posibles conflictos de interés, no es de fácil interpretación y no está siendo procesada ni analizada, dado que esto demanda tiempo y recursos para realizarlo.</p>

<h2>Justificación</h2>
<p>La DPTSC tiene a su cargo las políticas de transparencia, integridad en el Servicio Público, así como las de rendición de cuentas y control social y asesora a las entidades en la identificación y gestión de los riesgos asociados a los posibles conflictos de interés, por lo que requiere identificar, categorizar, analizar y procesar los posibles conflictos de intereses que reportan los diferentes sujetos obligados, para desarrollar productos a partir de los resultados obtenidos, que contribuyan de forma efectiva a la toma de decisiones, definición de líneas de trabajo e insumos para la implementación de acciones en el marco de estas políticas.</p>
  
 
 <h2>Marco de referencia</h2>
  
  <table>
  <tr>
    <th>Marco contextual</th>
  </tr>
  <tr>
    <td>Con la expedición de la Ley 2013 de 2019, la cual tiene por objeto: «Dar cumplimiento a los principios de transparencia y publicidad, y la promoción de la participación y control social a través de la publicación y divulgación proactiva de la declaración de bienes y rentas, del registro de conflictos de interés y la declaración del impuesto sobre la renta y complementarios», y establece en el artículo 4 que dicha información debe ser registrada en el SIGEP o las herramientas que lo sustituyan, Función Pública desarrolló el aplicativo de Ley 2013 de 2019.<br>
Con el fin de que los sujetos obligados realicen sus declaraciones, este aplicativo presenta formularios diferenciados para persona natural y jurídica, divididos por secciones (información general, declaración de bienes y rentas, posibles conflictos de interes e impuesto sobre la renta y complementarios) en las cuales deben registrar su información en los términos descritos por la ley.</td>
  </tr>
</table>
<table>
  <tr>
    <th colspan="3">Estado del arte</th>
  </tr>
  <tr>
    <th>Título</th>
    <th>Descripción/Resumen</th>
    <th>Referencia Bibliográfica</th>
  </tr>
  <tr>
    <td>CLASIFICACIÓN DE DOCUMENTOS DEL DIARIO OFICIAL MEDIANTE ANÁLISIS DE TEXTO – ACTUALIZACIÓN</td>
    <td>Se actualizó el modelo para clasificar la producción normativa emitida por el Diario Oficial en 9 sectores productivos, mediante la lectura, limpieza y procesamiento de textos con los cuales se entrenaron numerosos modelos de aprendizaje de máquina.</td>
    <td><a href="https://colaboracion.dnp.gov.co/CDT/Desarrollo%20Digital/Big%20Data/2020/03_Mejora_regulatoria_2020/Mejora_regulatoria_2020_Informe.pdf">Link</a></td>
  </tr>
  <tr>
    <td>DENTIFICACIÓN DE USO DE PROYECTOS TIPO CON SIMILITUD DE TEXTO</td>
    <td>Se buscó determinar una forma de medir el uso de la información de proyectos tipo, en proyectos que ya son viables y que, aunque no tienen una marcación especifica como “proyecto tipo”  han basado su formulación en el uso de información, esto mediante comparación de los proyectos tipo y viables.</td>
    <td><a href="https://colaboracion.dnp.gov.co/CDT/Desarrollo%20Digital/Big%20Data/2020/20_Similitud_proyectos_tipo/Similitud_proyectos_tipo_Informe_final.pdf">Link</a></td>
  </tr>
  
</table>  

<div>
<h2>Objetivos</h2>
 <p><b>Obejtivos del Negocio</b><br>
Asegurar el registro de la declaración de bienes y rentas, de los posibles conflictos de interés y la declaración del impuesto sobre la renta y complementarios por parte de los sujetos obligados de la Ley 2013 de 2019 en el aplicativo dispuesto para ello, así como la publicación y divulgación proactiva de esta información.<br>

<b>Objetivo de la Mineria de datos:</b><br>
 <ul>
 <li type="circle">Identificar y clasificar los posibles conflictos de interes registrados por los sujetos obligados. </li>
 <li type="circle">Parametrizar los posibles conflictos de interés registrados en el Aplicativo de Ley 2013 de 2019 para desarrollar productos y acciones en desarrollo de las políticas descritas.</li>
<li type="circle">Analizar los perfiles y  las caracteristicas en común de los diferentes sujetos obligados que registran un posible conflicto de interes en el aplicativo.</li>
    <ul>
</p>
</div>
   
<h2>Criterios de Éxito</h2>
   <p>Desde el punto de vista de negocio, se puede considerar como criterio de éxito que todos los campos del aplicativo estén diligenciados correctamente y tengan correspondencia entre ellos, así como que la descripción del posible conflicto de interes identificado por los sujetos obligados sea clara y suficiente.</p>

<div>  
<h2>Riesgos y contingencias</h2>
   <p>  
    <ul>
 <li type="circle">Inconsistencias en la base de datos. </li>
 <li type="circle">Insuficiencia de datos.</li>
<li type="circle">Falta de claridad en la descripción del posible conflicto de interes que impida su identificación, clasificación y agrupación.</li>
    <ul>  
   </p>
</div>
  
<h2>Costos y beneficios</h2>
      <p>El desarrollo de este ejercicio de analítica de datos no genera costos para la entidad, dado que se realizará tomando como fuente de información la base de datos del aplicativo de Ley 2013 de 2019, desarrollado por la entidad para la captura de la información.<br>
Como beneficios se pueden mencionar que el desarrollo de estos ejercicios es un valor agregado para la entidad al contar con información confiable y con procedimientos y metodologías reconocidas y estandarizadas que respaldan las cifras. De otra parte, se puede decir que con los resultados obtenidos en este ejercicio se realiza una identificación y clasificación de los posibles conflictos de interes de los sujetos obligados, así como aquellos que son más frecuentes, facilitando las asesorias a las entidades en la mitigación de los riesgos presentados por estos conflictos de interes identificados. </p>

 <div>
 <h2>Productos/Entregables</h2>
 <ul>
 <li type="circle">Identificación y parametrización de posibles conflictos de intereses.</li>
 <li type="circle">Analisis de posibles conflictos de intereses identificados y su relación con las variables relacionadas.</li>
 <ul>
 </div>
   
 <h2>Metodología y Alcance</h2>
   <p><b>Metodología:</b>  Para el desarrollo de este ejercicio se aplicará la metodologia Crisp DM, en la cual se inicia con con análisis y entendimiento del negocio y objetivos del ejercicios y, posteriormente, se realiza una revisión y entendimiento de los datos y preparación de los mismos, para luego pasar a la fase de modelamiento donde se aplican las técnicas estadísticas y algoritmos desarrollados para dar cumplimiento a los objetivos. Para este caso puntal, se aplicará analítica de texto y, finalmente, se realizará la evaluación del modelo y se procederá a la entrega de resultados e informe final.<br>
<b>Alcance:</b>  Para este ejercicio se aplicarán técnicas de mineria de datos a la información de la base de datos más reciente del aplicativo, correspondiente a aquellos sujetos obligados (persona natural y jurídica) que manifestaron un posible conflicto de interes en el formulario dispuesto para tal fin.</p>

<h2>Recursos tecnológicos del proyecto</h2>
<table>
   <tr>
    <th colspan="3">Descripción de software</th>
  </tr>
  <tr>
    <th>Software</th>
    <th>Justificación</th>
    <th>Archivos generados</th>
  </tr>
  <tr>
    <td>Python</td>
    <td>Lenguaje de programación open source y con respaldo de una gran comunidad que permitirá emprender acciones de transformación y extracción de información útil para la toma de decisiones, bajo el ciclo de vida de ejercicios no supervisados se dictaminan las tareas principalmente de preparación de datos, aprendizaje, evaluación y perfilamiento de los datos.</td>
    <td>Notebook Jupyter (algoritmo): se emprende y explica el proceso para análisis de datos en el proyecto puede establecerse en formato PDF, HTML u otros para su consulta</td>
  </tr>
  <tr>
    <td>Weka</td>
    <td>Es una plataforma de software para el aprendizaje automático y la minería de datos, escrita en Java y desarrollada en la Universidad de Waikato, que permite la aplicación de técnicas ya establecidas para el análisis de datos de una forma más rápida y es de código abierto.</td>
    <td>Modelo y análisis generado por la aplicación en formato Arff.</td>
  </tr>
</table>

 
 <h2>Presentación y análisis de resultados</h2>
   
 <h3>Validación de datos</h3>
     
   <table>
  <tr>
    <th>Hoja en archivo excel </th>
    <th>Número total de registros</th>
    <th>Registros usados para ejercicio</th>
    <th>Descripción de problemas encontrados</th>
  </tr>
  <tr>
    <td>CONYUGE_COMPANERO</td>
    <td>133.406</td>
    <td>0</td>
    <td>La información disponible en la descripción no cumple con los criterios para mineria de texto</td>
  </tr>
  <tr>
    <td>DONACIONES</td>
    <td>307</td>
    <td>0</td>
    <td>La información disponible en la descripción no cumple con los criterios para mineria de texto</td>
  </tr>
   <tr>
    <td>CI_PARIENTES</td>
    <td>10.801</td>
    <td>0</td>
    <td>La información disponible en la descripción no cumple con los criterios para mineria de texto</td>
  </tr>
  <tr>
    <td>POSIBLES_CI</td>
    <td>135.442</td>
    <td>807</td>
    <td>Se filtran los registros cuyo estado es finalizado o en revisión, además de los registros donde posible conflicto es “SÍ”. Por otro lado, existen casos donde en la descripción hay caracteres especiales o mencionan ninguno o no tengo, algunos de estos casos fueron excluidos.</td>
  </tr>
   <tr>
    <td>CI_INFO_PJ</td>
    <td>2.036</td>
    <td>0</td>
    <td>La información disponible en la descripción no cumple con los criterios para mineria de texto</td>
  </tr>
   </table>
   
<p>Como se observa en la tabla anterior del total de registros de la base de datos se trabajara únicamente con 807 registros que describen los posibles conflictos de intrés</>
 
<h3>Minería de texto</h3> 
<p>Después de seleccionar las descripciones presentes en el conflicto de interés se realizó un proceso de limpieza donde se convierten las palabras a minúsculas, se quitan espacios en blanco innecesarios, se remueven puntuación y caracteres especiales, se eliminan las palabras vacías como artículos y preposiciones, además se reduce la palabra a su raíz para no sobredimensionar al modelo.</p>
   
   ```python
import re
from nltk.corpus import stopwords
from nltk.stem import SnowballStemmer
   
   def saltos_linea(x)
   def minuscula(x)
   def quitarotros(x)
   def stopword(x)   
   def stemmer(x)
```
   
   <p>Realizado el proceso de limpieza del texto con las librerías y funciones (Ver <a href="https://github.com/analiticafp/Conflicto-de-intereses/blob/4086e130ef53886f52c725e1d28c1b275e33d2ae/Descripcion_analisis_texto.ipynb">Descripcion_analisis_texto.ipynb</a>) se transforma a una representación numérica (indexa miento) para que pueda ser procesado con técnicas de aprendizaje automático, esto se logra con el enfoque de bolsa de palabras y utilizando el algoritmo TF-IDF, medida estadística utilizada para evaluar la importancia de una palabra para un documento y para el conjunto de documentos.</p>
   
  
   ```python
from sklearn.feature_extraction.text import TfidfVectorizer
vectorizer = TfidfVectorizer(max_features=50,max_df=0.9,min_df=0.09,ngram_range=(1, 1))  
```
   <p>Para agrupar las descripciones se utilizó kmeans como modelo, para una búsqueda de similaridades teniendo en cuenta todas las características según parámetros de aparición. De la misma forma, el número de clusters se determina bajo el método del codo.</p>
   
 <div align="center">
   <img src="https://github.com/analiticafp/Conflicto-de-intereses/blob/22dca21223dc43a61d82f2dbfb15d0f2bf575ea5/img/codo.png" alt="Método del codo">
 </div>
 <p>Se realizan 6 grupos y se entena el modelo.</p>
 
```python
cluster = KMeans(n_clusters=6, init='k-means++',max_iter = 1500)
cluster.fit(tfidf)
```
<table>
  <tr>
    <th>Cluster</th>
    <th>Número de registros</th>
    <th>actividades (agricolas, comerciales, economicas…)</th>
    <th>empresas vinculos</th>
    <th>hace parte (listas candidatos…)</th>
    <th>sas (empresas)</th>
    <th>sociedad</th>
  </tr>
  <tr>
    <td>1</td>
    <td>501</td>
    <td>8,3266E-17</td>
    <td>-2,4980E-16</td>
    <td>-1,24903E-16</td>
    <td>-1,3877E-17</td>
    <td>1,2490E-16</td>
  </tr>
  <tr>
    <td>2</td>
    <td>78</td>
    <td>0,0329</td>
    <td>2,7755E-17</td>
    <td><b>0,9877</b></td>
    <td>-1,3877E-17</td>
    <td>-1,3877E-17</td>
  </tr>
  <tr>
    <td>3</td>
    <td>65</td>
    <td><b>0,9920</b></td>
    <td>0,0146</td>
    <td>-2,7755E-17</td>
    <td>0,0048</td>
    <td>0,0122</td>
  </tr>
  <tr>
    <td>4</td>
    <td>47</td>
    <td>0,2772</td>
    <td>0,0176</td>
    <td>0,0272</td>
    <td>0,0083</td>
    <td><b>0,8938</b></td>
  </tr>
  <tr>
    <td>5</td>
    <td>68</td>
    <td>0,0909</td>
    <td>0,2316</td>
    <td>0,0322</td>
    <td><b>0,7948</b></td>
    <td>0,209</td>
  </tr>
  <tr>
    <td>6</td>
    <td>48</td>
    <td>0,0645</td>
    <td><b>0,9321</b></td>
    <td>0,0433</td>
    <td>0,0257</td>
    <td>0,0692</td>
  </tr>
</table>
   <p>Basándose en las palabras mas frecuentes es posible realizar la clasificación de registros teniendo en cuenta la guía de conflicto de intereses proporcionada por la Entidad, así:</p>
 <table> 
   <tr>
     <th>Clasificación</th>
     <th>Descripción </th>
     <th>Grupo</th>
   </tr>
    <tr>
     <td>Organización, sociedad o asociación a la cual perteneció o continúa siendo miembro</td>
     <td>Que el servidor sea socio de alguna de las personas interesadas en la actuación administrativa o su representante o apoderado en sociedad de personas.</td>
     <td>4, 6</td>
   </tr>
    <tr>
     <td>Lista de candidatos</td>
     <td>Que el servidor haya hecho parte de listas de candidatos a cuerpos colegiados de elección popular inscritas o integradas también por el interesado en el período electoral coincidente con la actuación administrativa o en alguno de los dos períodos anteriores.</td>
     <td>2</td>
   </tr>
   <tr>
     <td>Relación contractual o de negocios</td>
     <td>Que alguno de los interesados en la actuación administrativa sea representante, apoderado, dependiente, mandatario o administrador de los negocios del servidor público</td>
     <td>3, 5</td>
   </tr>
   </table> 
   
  
 <h2>Conclusiones</h2>
<p> Una vez analizadas la base de datos relacionada con la identificación de conflictos intereses por el reporte de Ley 2013, se concluye que la base de datos tiene problemas de calidad,lo que dificulta el procesamiento y el analisis de los datos, de otra parte, del total de hojas del archivo que contienen infomación de conflictos de interes no fue viable el analisis por analitica de texto, dado que en su mayoría la descripción del conflicto de intertes es igual a al campo diligenciado, es decir, en el caso de la hoja de conyuge la descripción dice es mi espos@, en la hoja de parientes, la descripción esta asociada a dependientes economicos y el tipo de parentezco. Por lo anterior el analisis con mineria de texto se realizo únicamente para la hoja de posibles conflictos de interés donde se encontro lo siguiente.....</p>
    
 <li type="circle">111</li>
 <li type="circle">222</li>
 <li type="circle">333</li>
 <li type="circle">444</li>
</ul>
 <h2>Recomendaciones</h2>
 <p>Desde la Oficina Asesora de Planeación y el equipo de trabajo que desarrollo este ejercicio se sugiere lo siguiente:</p>
  
<li type="circle">Parametrizar el sistema de tal forma que no permita marcar un si y en la descripción incluir signos o simbolos o que no se tiene ningun conflicto de    interes</li> 
<li type="circle">Reforzar capacitaciones con los sujetos obligados para el correcto diligenciamiento del aplicativo</li>
<li type="circle">Establecer algún tipo de lista desplegable de conflictos de interes de acuerdo con la normatividad, con la cual los sujetos obligados se puedan identificar y de esta manera se facilia la clasificación de los posibles conflictos de interes</li> 
     
 <h2>Bibliografía</h2>  
    <ul>
 <li type="circle">[Steven Bid, Edwan Klein & Edward Loper] <i>Natural Language Processing with Python</i>. O'REILLY, 2009.</li>
 <li type="circle">[Dirección de Participación, Transparencia y Servicio al Ciudadano] <i>Guía para la identificación y declaración del conflicto de intereses en el sector público colombiano</i>. Función Pública, 2019.</li>
 <li type="circle">333</li>
 <li type="circle">444</li>
   </ul>    
  
```python
from contexto.limpieza import *
```
