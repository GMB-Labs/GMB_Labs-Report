---
title: "Universidad Peruana de Ciencias Aplicadas - Informe de Trabajo Final"
subtitle: "Arquitectura de Software Emergentes - 7273 - 1ASI0728"

author: |
  \begin{flushleft}
  Startup: GMB Labs\\
  Producto: Foodlytics\\
  Profesor: Ocampo Tello, Ernesto\\[0.8em]
  \textbf{Integrantes:}\\[0.3em]
  \begin{minipage}{0.92\linewidth}
  Zavala Quedena, Gonzalo Andre (U202113656)\\
  Poma Espinoza, Gustavo (U20221C138)\\
  Del Castillo Bueno, Daniel Mateo (U202211212)\\
  Vilchez Rios, Mateo Alejandro (U202210059)\\
  Ramos Rios, Belén del Rocio (U202216246)
  \end{minipage}
  \end{flushleft}


date: "2025-02"
lang: "es"
colorlinks: true
footer-left: "GMB Labs"
titlepage: true
titlepage-color: "DC143C"
titlepage-text-color: "FFFAFA"
titlepage-rule-color: "FFFAFA"
titlepage-rule-height: 2
subject: "Markdown"
keywords: [Markdown, Report]

block-headings: true
titlepage-geometry: "top=3.5cm, bottom=3.5cm, left=3.5cm, right=3.5cm"

titlepage-logo: "src/img/logo/logo-upc.pdf"
logo-width: 30mm

book: true
classoption: oneside
code-block-font-size: \scriptsize
nocite: |
  @gothelf2021,
  @hernandez2018,
  @kasparova2022,
  @kalbach2016,
  @smith2020,
  @johnson2019,
  @brown2022,
  @igartua2019desconexion,
  @jiang2024pervasive,
  @kaspersky_privacy,
  @collave2024datos
header-includes:
- |
  ```{=latex} 
  \makeatletter
  \renewcommand{\and}{\\[0.35em]}
  \makeatother
  \usepackage{morefloats}
  \usepackage{awesomebox}
  \usepackage{fontawesome5}
  \usepackage{tcolorbox}
  \usepackage{graphicx}
  \usepackage{parskip}
  \usepackage{xcolor}
  \usepackage{float} 
  \usepackage{longtable}
  \usepackage{array}
  \usepackage{lscape}
  \usepackage{multirow}
  \usepackage{booktabs}
  \providecommand{\pandocbounded}[1]{#1}

  \newtcolorbox{info-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black}
  \newtcolorbox{error-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!75!black}
  \newtcolorbox{norm-box}{colback=gray!5!white,arc=0pt,outer arc=0pt,colframe=gray!60!black}
  \newtcolorbox{warn-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black}
  \newtcolorbox{attn-box}{colback=green!5!white,arc=0pt,outer arc=0pt,colframe=green!75!black}
  \newtcolorbox{code-box}{colback=pink!5!white,arc=0pt,outer arc=0pt,colframe=pink!80!black}
  \newtcolorbox{learn-box}{colback=blue!5!white,arc=0pt,outer arc=0pt,colframe=blue!40!black,title=\textbf{Objectives:}}
  \newtcolorbox{scenario-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black,title=\textbf{Scenario:}}
  \newtcolorbox{outline-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black,title=\textbf{Outline:}}
  \newtcolorbox{prereqs-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!60!black,title=\textbf{Prerequisites:}}
  \newtcolorbox{labtime-box}{colback=yellow!5!white,arc=0pt,outer arc=0pt,colframe=yellow!60!black,title=\textbf{Lab:}}
 
  ```
pandoc-latex-environment:
  tcolorbox: [box]
  info-box: [info]
  error-box: [error]
  norm-box: [norm]
  warn-box: [warn]
  attn-box: [attn]
  code-box: [code]
  learn-box: [learn]
  scenario-box: [scenario]
  outline-box: [outline]
  prereqs-box: [prereqs]
  labtime-box: [labtime]
  noteblock: [note]
  tipblock: [tip]
  warningblock: [warning]
  cautionblock: [caution]
  importantblock: [important]
---

**Registro de Versiones del Informe**

A continuación se detalla los avances y las correciones relevantes durante el desarrollo del presente proyecto, donde demostramos nuestra participación efectiva dentro de su ciclo de vida. 

\begin{longtable}{|c|c|c|p{6cm}|}
  \hline
  \textbf{Versión} & \textbf{Fecha} & \textbf{Autor} & \textbf{Descripción de Modificación} \\
  \hline
  tb1 & 15/09/2025 & Zavala Quedena, Gonzalo Andre & Elaboré el análisis de competidores, desarrollando el estudio del mercado y las estrategias frente a la competencia. Contribuí con la justificación de la propuesta de valor dentro del informe. \\
  \hline
  tb1 & 15/09/2025 & Poma Espinoza, Gustavo Poma  & Desarrollé el diseño de entrevistas, el registro de resultados y su respectivo análisis. Además, apoyé en la elaboración de los apartados relacionados con el modelado de dominios (EventStorming y Context Mapping) \\
  \hline
  tb1 & 25/04/2025 & Del Castillo Bueno, Daniel Mateo & Redacté los apartados relacionados con las decisiones técnicas y arquitectónicas, incluyendo escenarios de calidad, restricciones y drivers de diseño. También colaboré en la estructuración del backlog arquitectónico. \\
  \hline
  tb1 & 25/04/2025 & Ramos Rios, Belén del Rocio & Integré todos los apartados del documento en LaTeX, asegurando uniformidad en la redacción, formato y referencias. Además, coordiné la coherencia entre secciones y la presentación final del entregable. \\
  \hline
  tb1 & 25/04/2025 & Vilchez Rios, Mateo Alejandro & Redacté los antecedentes y la problemática inicial, así como los objetivos del proyecto. También elaboré las secciones de User Stories y Product Backlog, contribuyendo a la definición de requerimientos del sistema.. \\
  \hline

\end{longtable}

\newpage

***Project Report Collaboration Insights***

Github Collaboration Insights proporciona un cronograma que muestra las principales ramas y los procesos de fusión que han ocurrido. Todas las ramas se han generado siguiendo los principios de GitFlow, lo que garantiza una organización efectiva al utilizar un sistema de control de versiones. 

**Entregable TB1:**

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/GMB-Labs/GMB_Labs-Report/pulse)
:::

A continuación se presentan los gráficos de colaboración de los integrantes del equipo en el repositorio de nuestro primer sprint. Estos gráficos ofrecen una representación visual de la cantidad de contribuciones realizadas por cada miembro del equipo, junto con la fecha en que se llevaron a cabo. Además, se presenta información sobre la cantidad de líneas de código que se han modificado en cada uno de los commits.


**Tablero Kanban:**

![Organización GMB Labs, imagen extraída de Github](src/img/cap1/insights-kanban-todo.png){ width=85% }

**Kanban List:**

![Organización GMB Labs, imagen extraída de Github](src/img/cap1/insights-kanban-list.png){ width=85% }

\newpage

**Network Graph:**

![Organización GMB Labs, imagen extraída de Github](src/img/cap1/insights-network-graph.png){ width=85% }

**Traffic Map:**

![Organización GMB Labs, imagen extraída de Github](src/img/cap1/insights-traffic.png){ width=85% }

\newpage


***Student Outcome***

El curso contribuye al cumplimiento del ***Student Outcome ABET:*** *ABET-EAC - Student Outcome 3*

* **Criterio:** *Capacidad de comunicarse efectivamente con un rango de audiencias. En el siguiente cuadro se describe las acciones realizadas y enunciados de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro del ABET – EAC - Student Outcome 3.*.

En el siguiente cuadro se describe las acciones realizadas y enunciadas de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro de ***ABET - EAC - Student Outcome 3.***


\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} & \multicolumn{1}{c|}{\textbf{Acciones Realizadas}} & \multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead
\parbox[t]{4cm}{
\textit{Comunica oralmente sus ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerarquicos, en el marco del desarrollo de un proyecto en ingeniería.}
} 
&  
\parbox[t]{6cm}{
\textbf{TB1:} \\
\textbf{Zavala Quedena, Gonzalo Andre} \\
Presenté los resultados del análisis de mercado y la propuesta de valor, comunicando con objetividad la ventaja. \\
\textbf{Poma Espinoza, Gustavo} \\
Expliqué los hallazgos de la investigación y cómo estos influyeron en la definición de los requerimientos y la arquitectura inicial. \\
\textbf{Del Castillo Bueno, Daniel Mateo} \\
Me encargué de exponer las decisiones técnicas y de diseño, explicando los fundamentos y la relevancia de cada elección para el desarrollo del proyecto. \\
\textbf{Vilchez Ríos, Mateo Alejandro} \\
Desarrollé la presentación de los avances iniciales del proyecto, exponiendo de forma clara los objetivos y alcances de la propuesta. \\
\textbf{Ramos Ríos, Belén del Rocío} \\
Coordiné y aseguré la presentación global del proyecto, reforzando la coherencia del discurso del grupo. \\
}
&
\parbox[t]{5cm}{
\textbf{TB1:} \\
Como grupo, concluimos que la comunicación oral de nuestras ideas y resultados fue esencial para validar el proyecto frente a diferentes públicos. Se logró transmitir tanto la visión estratégica como los aspectos técnicos de manera comprensible, lo cual facilitó la retroalimentación, redujo ambigüedades y fortaleció la confianza en el trabajo presentado.
} \\ 
\hline

\parbox[t]{4cm}{
\textit{Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerarquicos, en el marco del desarrollo de un proyecto en ingeniería.}
}
&  
\parbox[t]{6cm}{
\textbf{TB1:} \\
\textbf{Zavala Quedena, Gonzalo Andre} \\
Elaboré los apartados de análisis de mercado y justifiqué las ventajas competitivas del proyecto. \\
\textbf{Poma Espinoza, Gustavo} \\
Redacté los hallazgos de las entrevistas y la interpretación de los resultados para guiar las decisiones del proyecto. \\
\textbf{Del Castillo Bueno, Daniel Mateo} \\
Documenté las decisiones técnicas y justifiqué los criterios empleados en el diseño, manteniendo precisión y claridad. \\
\textbf{Vilchez Ríos, Mateo Alejandro} \\
Redacté los apartados que describen la propuesta y los objetivos del proyecto, estructurando de manera clara los resultados. \\
\textbf{Ramos Ríos, Belén del Rocío} \\
Integré todos los apartados en LaTeX, asegurando uniformidad en redacción, formato y referencias. \\
}
& 
\parbox[t]{5cm}{
\textbf{TB1:} \\
Concluimos que la documentación escrita permitió plasmar los avances con claridad y objetividad, generando un entregable académico y técnico que refleja el esfuerzo colectivo. La escritura consolidó tanto la justificación del proyecto como la evidencia de los análisis realizados, facilitando que los resultados sean comprendidos y evaluados por distintos perfiles (académicos, técnicos y de negocio). Además, el uso de LaTeX aportó uniformidad, profesionalismo y rigurosidad en la presentación del documento.
} \\
\hline
\end{longtable}

\newpage

# Capítulo I: Introducción

## Startup Profile

### Descripción de la Startup

***Foodluytics:*** **Tu nutrición, más inteligente cada día.**

GMB Labs es una startup dedicada a la investigación, diseño y desarrollo de soluciones digitales en el ámbito del cuidado personal, la salud y la nutrición. Nos enfocamos en aprovechar tecnologías emergentes como inteligencia artificial y análisis de datos para crear productos innovadores que ayuden a las personas a mejorar su bienestar, y a los profesionales de la salud a contar con herramientas más eficientes para acompañar a sus pacientes. 

![GMB Labs logo](src/img/logo/GMBLabs-logo.png)


\newpage

::: box 
**Misión**

Impulsar la transformación digital en el cuidado de la salud y la nutrición, desarrollando soluciones accesibles e innovadoras que fortalezcan la relación entre profesionales y pacientes, fomentando hábitos saludables y sostenibles. 
:::

::: box
**Visión**

Ser reconocidos como un laboratorio de innovación líder en Latinoamérica en el desarrollo de soluciones tecnológicas para el cuidado personal, integrando ciencia, tecnología y compromiso social para contribuir a un futuro más saludable. 
:::

\newpage

### Perfiles de integrantes del equipo

Nuestro equipo está conformado por individuos apasionados y comprometidos, cada uno aportando sus habilidades únicas para lograr nuestros objetivos de manera efectiva y colaborativa. Aquí se muestran a nuestros miembros clave:

![](src/img/cap1/Belen.png)
![](src/img/cap1/Gonzalo.png)
![](src/img/cap1/Gustavo.png)
![](src/img/cap1/Tocayo.png)
![](src/img/cap1/Mateo.png)

\newpage

## Solution Profile

El presente apartado tiene como propósito contextualizar y fundamentar la solución tecnológica propuesta por la startup GMB Labs. Para ello, se abordan los principales antecedentes que explican la necesidad de innovar en el ámbito de la salud y la nutrición, así como la problemática específica que motiva el diseño de un producto digital orientado a mejorar la interacción entre pacientes y profesionales. De esta manera, se establece la base conceptual que guiará la definición de la propuesta de valor y el diseño posterior de la aplicación.

![Recurso extraído de Canva](src/img/cap1/solution.png)

\newpage

### Antecedentes y problemática

En el Perú, la prevalencia de enfermedades crónicas como la obesidad y la diabetes está en aumento. Según el Ministerio de Salud, más del 60 % de adultos presenta exceso de peso, lo que incrementa la demanda de servicios de nutrición y seguimiento personalizado. A esto se suma que gran parte de la población no recibe un acompañamiento constante debido a limitaciones de tiempo, acceso a especialistas o barreras geográficas. Los nutricionistas y médicos deportivos requieren herramientas digitales que centralicen la información de sus pacientes y faciliten un monitoreo objetivo de dietas y rutinas. 

La penetración de teléfonos inteligentes en el país supera el 85 %, y el uso de aplicaciones móviles para la salud y el bienestar ha crecido de forma sostenida en los últimos años. Sin embargo, las alternativas disponibles suelen estar diseñadas para un mercado global y no consideran particularidades locales, como la diversidad de alimentos típicos peruanos o la necesidad de una sincronización directa entre paciente y especialista. Esta brecha justifica la creación de una solución adaptada al contexto nacional, que incorpore inteligencia artificial para reconocer alimentos, estimar calorías y macros, y permita al médico acceder en tiempo real a la información de cada paciente. 

::: info
***What*(Qué)**

Se identifica la ausencia de herramientas digitales locales capaces de reconocer alimentos, calcular calorías y sincronizar datos entre paciente y especialista, además de la dificultad para registrar con precisión la ingesta diaria y la actividad física.
:::

::: info
***Why*(Por qué)**

El problema se explica por la alta prevalencia de exceso de peso y mala alimentación como retos de salud pública, la falta de monitoreo continuo que disminuye la adherencia a los planes y la inexistencia de soluciones locales con IA y conexión en tiempo real.
:::

::: info
***Where*(Dónde)**

El contexto se sitúa en el Perú, principalmente en zonas urbanas con alto acceso a smartphones, aunque también resulta relevante en áreas con limitaciones para acceder a consultas presenciales.
:::

::: info
***When*(Cuándo)**

La necesidad surge en el seguimiento nutricional y deportivo cotidiano, donde la retroalimentación constante es esencial para la efectividad de los planes alimenticios y de entrenamiento.
:::

::: info
***Who*(Quiénes)**

La problemática involucra a pacientes que buscan mejorar su alimentación y condición física, así como a nutricionistas y médicos del deporte que necesitan monitorear de manera continua a sus pacientes.
:::

::: attn
***How*(Cómo)**

La propuesta consiste en una aplicación móvil para pacientes, que utiliza IA para identificar alimentos y calcular nutrientes, complementada con una plataforma web para profesionales que centraliza información, genera reportes y facilita ajustes personalizados.
:::

::: attn
***How Much*(Cuánto)**

El impacto esperado es mejorar la precisión del seguimiento, reducir riesgos asociados a la mala alimentación y optimizar el trabajo de los especialistas. A nivel económico, se plantea un modelo escalable con planes diferenciados para profesionales y clínicas que sustenten la inversión en infraestructura tecnológica.
:::

\newpage

### *Lean UX Process.*

El proceso Lean UX permite estructurar el entendimiento del problema y orientar el diseño de la solución mediante la validación temprana de supuestos. A través de esta metodología se busca comprender de manera integral las necesidades del usuario, formular hipótesis verificables y definir un marco inicial que guíe el desarrollo del producto digital. En el caso de Foodlytics, la aplicación de este enfoque facilita identificar las brechas en el seguimiento nutricional y deportivo, para luego transformarlas en oportunidades de innovación tecnológica adaptadas al contexto peruano.

![Recurso extraído de Google](src/img/cap1/LeanUXProcess.png)

#### *Lean UX Problem Statements.*

::: note

***Problem Statement***

- Hemos observado que muchos pacientes en el Perú no registran adecuadamente su alimentación diaria debido a la falta de herramientas digitales adaptadas al contexto local. Esto ocasiona registros incompletos, baja precisión en la estimación de calorías y dificultades para mantener la adherencia a los planes nutricionales. ¿Cómo podríamos ofrecer una aplicación que, mediante inteligencia artificial, facilite el reconocimiento de alimentos típicos peruanos y automatice el cálculo de nutrientes, de modo que al menos el 60 % de los usuarios registre de manera consistente sus comidas durante la primera fase de uso?\newline

- Hemos observado que los nutricionistas y médicos deportivos carecen de plataformas que centralicen en tiempo real la información alimentaria y de actividad física de sus pacientes. Esta carencia limita el monitoreo continuo, retrasa la personalización de dietas y reduce la efectividad del tratamiento. ¿Cómo podríamos desarrollar una plataforma web que organice y visualice los datos de los pacientes, permitiendo a los especialistas realizar ajustes oportunos y mejorando en un 40 % la eficiencia de las consultas de seguimiento?\newline

- Hemos observado que las aplicaciones globales de nutrición disponibles en el mercado no consideran particularidades culturales ni alimenticias del Perú, lo que genera una desconexión entre las necesidades reales de los usuarios y las soluciones ofrecidas. Esta brecha provoca desmotivación en los pacientes y limita la utilidad de dichas herramientas para los profesionales. ¿Cómo podríamos diseñar una solución local que incorpore la diversidad gastronómica peruana y fortalezca el vínculo paciente–especialista, aumentando la satisfacción de los usuarios en al menos un 30 % durante los primeros meses de adopción?\newline

- Hemos observado que la falta de retroalimentación constante en el seguimiento nutricional reduce la motivación de los pacientes y aumenta el riesgo de abandono de los planes alimenticios y deportivos. Esta situación genera un bajo impacto en la prevención de enfermedades crónicas y limita los resultados de los programas de salud. ¿Cómo podríamos implementar un sistema de notificaciones y reportes personalizados que fomente la adherencia a los tratamientos y logre que al menos un 50 % de los pacientes mantenga la continuidad de su plan durante los primeros tres meses de uso?
:::


***Domain ***

- El dominio es la salud y nutrición personalizada, con enfoque en la prevención y control del sobrepeso en el Perú mediante aplicaciones digitales. 

***Customer Segments ***

- Pacientes entre 18 y 45 años con sobrepeso o enfermedades relacionadas. 

- Médicos nutricionistas y del deporte que necesitan dar seguimiento continuo a sus pacientes. 

***Pain Points ***

- Los pacientes no registran con precisión sus comidas ni sus actividades físicas. 

- Falta de herramientas locales que consideren alimentos típicos peruanos. 

- Los especialistas pierden tiempo revisando información dispersa o poco confiable. 

***Gap***

- Existen apps globales de nutrición, pero no adaptadas al contexto peruano ni integradas con el trabajo directo del especialista. 

***Visión / Strategy***

- Crear una solución digital que permita a los pacientes registrar su dieta de manera rápida y precisa mediante IA, y a los médicos acceder en tiempo real a datos confiables para personalizar planes de alimentación y ejercicio. 

***Initial Segment***

- Pacientes de zonas urbanas con acceso a smartphone y especialistas que trabajan en clínicas privadas o consultorios deportivos. 


\newpage

#### *Lean UX Assumptions.*

***Business Assumptions***

**1. El cliente necesita** monitorear su dieta y ejercicio en tiempo real.

**2. Las necesidades del cliente se resolverán mediante** una aplicación móvil que use inteligencia artificial para reconocer alimentos y calcular calorías y macronutrientes.

**3. Mis clientes iniciales son (o serán)** pacientes con sobrepeso o en control nutricional, y médicos nutricionistas o del deporte.

**4. El principal valor que mis clientes esperan de mi servicio es** una manera simple y confiable de registrar sus comidas y compartir avances con su especialista. 

**5. El cliente también puede obtener beneficios adicionales** como recomendaciones personalizadas, motivación a través de reportes y tableros de progreso.

**6. Obtendré mi base de clientes mediante** alianzas con clínicas, gimnasios y campañas de marketing digital. 

**7. Generaré ingresos ofreciendo** planes de suscripción para especialistas y versiones premium para pacientes.

**8. Mi principal competencia en el mercado serán** aplicaciones globales como MyFitnessPal o Yazio, además de prácticas locales sin herramientas digitales.

**9. Superaremos a la competencia** adaptando la base de datos a alimentos peruanos, integrando tableros para especialistas y ofreciendo reconocimiento rápido y preciso

**10. Nuestro mayor riesgo es** que la inteligencia artificial no reconozca adecuadamente las porciones o los alimentos locales.

**11. Resolveremos este riesgo mediante** ajustes manuales, entrenamiento continuo del modelo con imágenes de comida peruana y validación por parte de nutricionistas.

**12. ¿Cuáles son las suposiciones que, si se demuestran falsas, harán que el proyecto fracase?**

- Los pacientes no usarán la aplicación diariamente. 
    
- Los especialistas no verán valor en pagar por el servicio.  
  
- La Inteligencia Artifical no será aceptada como confiable para el registro de comidas. 

\newpage

***Business Outcomes***

- **Esperamos incrementar la retención de usuarios en un 30 % durante los primeros tres meses,** siempre que resolvamos de manera efectiva los problemas asociados al registro automático de comidas.

- **Queremos lograr que al menos el 50 % de los nutricionistas participantes gestionen 10 o más pacientes activos en la plataforma durante el primer año,**lo que evidenciará un nivel adecuado de adopción y uso profesional del sistema.

- **Proyectamos establecer alianzas con al menos dos clínicas privadas en el primer año,** con el fin de ampliar la cobertura del servicio y validar su escalabilidad en el sector institucional.

- **Buscamos alcanzar una tasa de registro de comidas del 60 % en los primeros seis meses,** medida a través de la frecuencia con que los pacientes suben fotografías de sus alimentos a la aplicación.

- **Anticipamos que al menos el 40 % de los pacientes mantendrán la continuidad en el uso de la aplicación durante un periodo mínimo de tres meses,** como indicador de adherencia a los planes nutricionales.

- **Esperamos que al finalizar el primer año, al menos el 70 % de los especialistas valore la aplicación como una herramienta útil para optimizar la personalización de dietas,** según encuestas de satisfacción aplicadas tras el uso de la plataforma.\newline


***User Assumptions***

**1. ¿Quién es el usuario?**  

Pacientes entre 18 y 45 años, con exceso de peso o riesgo de enfermedades crónicas, que usan smartphones. También nutricionistas y médicos del deporte que atienden a esos pacientes.


**2. ¿Dónde encajaría nuestro producto en la vida (o trabajo) del usuario?**  

- Para los pacientes: en su rutina diaria, al registrar sus comidas mediante fotografías y recibir retroalimentación sobre su progreso.
  
- Para los especialistas: en su práctica profesional, al centralizar datos, revisar reportes y ajustar dietas o entrenamientos según la información registrada por los pacientes.
  

**3. ¿Qué problemas resuelve el producto para el usuario?**  

- Registro incompleto o impreciso de la alimentación diaria.

- Falta de monitoreo continuo entre consultas presenciales.

- Dificultad de los especialistas para analizar datos objetivos y en tiempo real.

- Ausencia de soluciones que contemplen la diversidad de alimentos locales.

**4. ¿En qué contexto utiliza el usuario el producto?**  

- Los pacientes lo usan varias veces al día desde su celular para registrar sus comidas y actividad física.

- Los especialistas acceden desde un panel web en sus consultas o en sesiones de seguimiento remoto para evaluar el progreso y generar recomendaciones

**5. ¿Qué características son esenciales para el usuario? ¿Y por qué?**  

- **Reconocimiento automático de alimentos con IA:** facilita el registro y mejora la precisión.

- **Cálculo de calorías y macronutrientes:** permite al paciente conocer el impacto de su dieta.

- **Base de datos con alimentos peruanos:** asegura la relevancia cultural y nutricional.

- **Dashboard para especialistas:** centraliza datos y agiliza el seguimiento.

- **Interfaz intuitiva y amigable:** motiva el uso diario y reduce la curva de aprendizaje.


**6. ¿Cómo debería verse y comportarse el producto?** 

- Diseño limpio y moderno, con colores que transmitan salud y bienestar.

- Navegación fluida y rápida, con menús claros y accesibles.

- La app debe permitir registrar comidas con fotografías en segundos.

- Notificaciones motivacionales y recordatorios discretos pero efectivos.

- Reportes visuales y tableros dinámicos para los profesionales de la salud.\newline

***User Outcomes***

**Los pacientes quieren sentirse acompañados en su proceso de mejora alimentaria**, sabiendo que sus registros son precisos y que reciben retroalimentación personalizada.

**Los nutricionistas quieren optimizar su tiempo de consulta**, centralizando datos en un panel que les permita ajustar planes de manera rápida y basada en evidencia.

**Los pacientes esperan que la aplicación reconozca alimentos locales**, evitando la frustración de usar bases de datos extranjeras poco relevantes.

**Los usuarios valoran una solución fácil de usar**, con una interfaz amigable y accesible desde cualquier dispositivo móvil.

**Los especialistas desean contar con reportes automáticos y visuales**, que les permitan evaluar tendencias y tomar decisiones informadas.

**Los usuarios esperan mayor precisión y confiabilidad**, tanto en el registro de información como en la interpretación de los resultados.

**Los usuarios desean una experiencia fluida**, que se adapte sin fricciones a sus rutinas diarias y mejore la comunicación entre paciente y especialista.\newline


***Features Assumptions***

**1. Reconocimiento automático de alimentos (IA)**

- **Suposición:** Si los pacientes pueden registrar sus comidas tomando una foto, usarán la aplicación con mayor frecuencia y con menor esfuerzo.
  
- **Riesgo:** Si la IA no reconoce adecuadamente alimentos locales o porciones no estándar, los usuarios perderán confianza y abandonarán la función.


**2. Dashboards de progreso para pacientes:**

- **Suposición:** Los tableros visuales motivarán a los usuarios al mostrar avances claros sobre calorías, macronutrientes y evolución de peso.
  
- **Riesgo:** Si los dashboards no son intuitivos, visualmente claros o personalizables, los pacientes podrían desmotivarse y no ver valor en la aplicación.


**3. Panel web sincronizado para especialistas**

- **Suposición:** Los nutricionistas confiarán más en la plataforma si pueden acceder en tiempo real a los datos centralizados de cada paciente.
  
- **Riesgo:** Si los datos no se consideran confiables o si la interfaz no se ajusta a su flujo de trabajo, los profesionales no adoptarán la herramienta.


**4. Base de datos con alimentos peruanos:**

- **Suposición:** Incluir alimentos locales aumentará la relevancia cultural de la aplicación y facilitará su adopción en el mercado peruano.
  
- **Riesgo:** Si la base de datos es limitada o no contempla suficientes variaciones, los usuarios podrían percibir la app como incompleta o poco útil.

**5. Reportes automáticos para especialistas:**

- **Suposición:** Los profesionales valorarán recibir reportes listos para consultas y decisiones clínicas, ahorrando tiempo en el análisis de datos.
  
- **Riesgo:** Si los reportes no son claros, exportables o personalizables, los especialistas podrían considerarlos inútiles y no justificar el uso del sistema.


**6. Sistema de notificaciones configurables:**

- **Suposición:** Dar control al usuario sobre qué alertas recibir y cuándo aumentará la satisfacción y percepción de personalización.
  
- **Riesgo:** Si el sistema de configuración es complejo o no cumple con lo prometido, generará frustración y desuso de las notificaciones.\newline

#### *Lean UX Hypothesis Statements.*

::: tip

**1. Creemos que lograremos** aumentar la retención de usuarios en un 30 % durante los primeros tres meses **si** los pacientes con sobrepeso en zonas urbanas del Perú **obtienen** un registro automático de comidas rápido y preciso **con** la función de reconocimiento de alimentos mediante fotos.\newline

**2. Creemos que lograremos** mejorar el compromiso con los planes nutricionales en un 60 % durante los primeros tres meses **si** los pacientes supervisados por especialistas **obtienen** una visualización clara y frecuente de su progreso (calorías, macronutrientes y peso) con tableros de progreso personalizados dentro de la aplicación.\newline

**3. Creemos que lograremos** que un 50 % de los nutricionistas activos adopte la plataforma durante el primer año **si** los médicos del deporte y nutricionistas que atienden múltiples pacientes **obtienen** informes diarios confiables con un panel web sincronizado con los registros de los pacientes.\newline

**4. Creemos que lograremos** alcanzar una tasa de satisfacción superior al 70 % al finalizar el primer año **si** los pacientes y nutricionistas que usan la aplicación **obtienen** mejoras medibles en precisión del registro, adherencia a planes nutricionales y eficiencia en consultas con funcionalidades adaptadas al contexto peruano y soporte continuo.\newline
:::

\newpage

#### Lean UX Canvas.

![Artefacto creado en Figma [URL](https://www.figma.com/design/K3gw63Gdzr8KOgE32BgreJ/Lean-UX-Canvas-Template-by-Jeff-Gothelf-(Community)?node-id=0-1&t=q5cZNvpSyA30WQQd-1)](src/img/cap1/LeanUXCanvas.pdf) 

\newpage

## Segmentos objetivo.

En el marco del dominio de la nutrición y el cuidado de la salud, la solución Foodlytics está dirigida a dos segmentos principales de usuarios: médicos nutricionistas y del deporte, y pacientes jóvenes y adultos que buscan mejorar su alimentación. A continuación, se describen sus características demográficas y el sustento estadístico que justifica su relevancia en el contexto peruano.

::: box
**Segmento Objetivo 1:** Médicos nutricionistas y del deporte
:::

![Recurso extraído de Canva](src/img/cap1/SegmentoObjetivo1.pdf) 

**Demografía:** Profesionales de la salud entre 25 y 45 años, concentrados en áreas urbanas como Lima y las principales capitales regionales.

**Sustento:** El Colegio de Nutricionistas del Perú (CNP, 2023) reporta más de 17 mil nutricionistas colegiados en el país, de los cuales una proporción importante ejerce en el ámbito privado y deportivo. El sector salud privado creció en 6,5 % durante 2022, lo que refleja una mayor demanda por servicios personalizados y herramientas digitales de apoyo.

**Relevancia:** Este segmento requiere soluciones que permitan optimizar la revisión de dietas, generar reportes automáticos sobre el progreso de los pacientes y diferenciarse con el uso de tecnología aplicada a la consulta nutricional.

\newpage

::: box
**Segmento Objetivo 2:** Pacientes jóvenes y adultos (15 a 45 años)
:::

![Recurso extraído de Canva](src/img/cap1/SegmentoObjetivo2.pdf) 

**Demografía:** Adolescentes desde los 15 años y adultos jóvenes hasta los 45 años, con acceso a smartphones y motivación por controlar su peso, mejorar su estado nutricional o potenciar su rendimiento físico. La mayoría se concentra en zonas urbanas, donde la penetración de internet en la población de 12 años a más alcanza el 89,4 % (INEI, 2023).

**Sustento:** Según la Encuesta Demográfica y de Salud Familiar (ENDES, 2023), el 36 % de peruanos entre 15 y 29 años presenta sobrepeso u obesidad, convirtiendo a este grupo en un segmento crítico para la prevención y control de enfermedades crónicas.

**Relevancia:** Este segmento necesita una aplicación sencilla y confiable que permita registrar alimentos de manera automática mediante reconocimiento por cámara, calcular calorías y macronutrientes, y visualizar su progreso sin depender únicamente de consultas presenciales.

\newpage
