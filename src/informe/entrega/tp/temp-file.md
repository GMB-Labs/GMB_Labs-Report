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
  \usepackage{tabularx}
  \providecommand{\pandocbounded}[1]{#1}
  % Estética de tabla 
  \usepackage{booktabs}   % \toprule \midrule \bottomrule
  \usepackage{tabularx}   % columna X autoajustable
  \usepackage{array}      % nuevos tipos de columna
  \usepackage{float}      % [H]
  \usepackage{seqsplit}   % partir identificadores largos
  \newcolumntype{L}[1]{>{\raggedright\arraybackslash}p{#1}}
  \newcolumntype{Y}{>{\raggedright\arraybackslash}X}
  \newcommand{\code}[1]{\texttt{\seqsplit{#1}}}
  \renewcommand{\arraystretch}{1.25}
  \setlength{\tabcolsep}{6pt}
  \usepackage{longtable} % agrégalo en el preámbulo si aún no está
  \usepackage{ltablex}   % combina longtable + tabularx
  \keepXColumns          % mantiene las proporciones de columnas

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
  tb1 & 25/09/2025 & Del Castillo Bueno, Daniel Mateo & Redacté los apartados relacionados con las decisiones técnicas y arquitectónicas, incluyendo escenarios de calidad, restricciones y drivers de diseño. También colaboré en la estructuración del backlog arquitectónico. \\
  \hline
  tb1 & 25/09/2025 & Ramos Rios, Belén del Rocio & Integré todos los apartados del documento en LaTeX, asegurando uniformidad en la redacción, formato y referencias. Además, coordiné la coherencia entre secciones y la presentación final del entregable. \\
  \hline
  tb1 & 25/09/2025 & Vilchez Rios, Mateo Alejandro & Redacté los antecedentes y la problemática inicial, así como los objetivos del proyecto. También elaboré las secciones de User Stories y Product Backlog, contribuyendo a la definición de requerimientos del sistema.. \\
  \hline
  tp & 30/09/2025 & Zavala Quedena, Gonzalo Andre & Tactical-Level Software Design of Payments \\
  \hline
  tp & 30/09/2025 & Poma Espinoza, Gustavo Poma  & Tactical-Level Software Design of IAM \\
  \hline
  tp & 02/10/2025 & Del Castillo Bueno, Daniel Mateo & Tactical-Level Software Design of Diet Tracking, Profile, Notifications and Image Recognition\\
  \hline
  tp & 05/09/2025 & Ramos Rios, Belén del Rocio & Solution UX Design of Landing Page and Mobile Application \\
  \hline
  tp & 10/09/2025 & Vilchez Rios, Mateo Alejandro & Solution UX Design of Web Application \\
  \hline

\end{longtable}

\newpage

***Project Report Collaboration Insights***

**Entregable TB1:**

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/GMB-Labs/GMB_Labs-Report/pulse)
:::


**Tablero Kanban:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/1)](src/img/cap1/insights-kanban-todo.png){ width=85% }

**Kanban List:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/2)](src/img/cap1/insights-kanban-list.png){ width=85% }

\newpage

**Traffic Map:**

![Organización GMB Labs, imagen extraída de Github](src/img/cap1/insights-traffic.png){ width=85% }

El informe del proyecto se desarrolla de manera colaborativa en el repositorio de la organización GMB-Labs en GitHub. En la Figura 1 se muestra el tablero Kanban, en el cual se gestionaron todas las secciones del entregable. Para la presente entrega, todas las tareas asignadas se encuentran completadas (“Done”), lo cual refleja la finalización de los apartados definidos en la planificación. Asimismo, en las Figuras 2 y 3 se presentan los analíticos de colaboración y evidencias de commits, que demuestran la participación activa de cada integrante del equipo en la construcción del informe. Finalmente, esta evidencia es consistente con el Registro de Versiones del Informe.

\newpage

***Student Outcome***

El curso contribuye al cumplimiento del ***Student Outcome ABET:*** *ABET-EAC - Student Outcome 3*

* **Criterio:** *Capacidad de comunicarse efectivamente con un rango de audiencias. En el siguiente cuadro se describe las acciones realizadas y enunciados de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro del ABET – EAC - Student Outcome 3.*.

En el siguiente cuadro se describe las acciones realizadas y enunciadas de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro de ***ABET - EAC - Student Outcome 3.***

% Usa tus tipos L{..} ya definidos
\begin{longtable}{|L{4cm}|L{6cm}|L{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endhead
\endfoot
\endlastfoot

\textit{Comunica oralmente sus ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco del desarrollo de un proyecto en ingeniería.}
&
\begin{minipage}[t]{\linewidth}\small\setlength{\parskip}{2pt}
\textbf{TB1:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Presenté los resultados del análisis de mercado y la propuesta de valor.\\
\textbf{Poma Espinoza, Gustavo}\\
Expliqué hallazgos de investigación y su impacto en requisitos y arquitectura.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Exposé decisiones técnicas y de diseño con sus fundamentos.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Presenté avances y alcances de la propuesta.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Coordiné la presentación global del proyecto.\\[0.3em]
\textbf{TP:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Expuse objetivamente el \textit{Tactical Level Software Design}.\\
\textbf{Poma Espinoza, Gustavo}\\
Presenté flujos y contratos del diseño táctico.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Comuniqué decisiones y riesgos del diseño táctico.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Exposé el \textit{Solution UX Design} conectando hallazgos y pantallas.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Aseguré la coherencia de la exposición del grupo.
\end{minipage}
&
\begin{minipage}[t]{\linewidth}\small\setlength{\parskip}{2pt}
\textbf{TB1:}\\
La comunicación oral permitió validar la propuesta con públicos diversos y obtener retroalimentación útil, reduciendo ambigüedades.\\[0.3em]
\textbf{TP:}\\
La exposición del diseño táctico y del UX fue clara para perfiles técnicos y no técnicos, facilitando decisiones y alineamiento.
\end{minipage}
\\
\hline

\textit{Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco del desarrollo de un proyecto en ingeniería.}
&
\begin{minipage}[t]{\linewidth}\small\setlength{\parskip}{2pt}
\textbf{TB1:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Redacté análisis de mercado y ventajas competitivas.\\
\textbf{Poma Espinoza, Gustavo}\\
Documenté hallazgos de entrevistas y su interpretación.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Justifiqué criterios técnicos y de diseño con precisión.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Describí propuesta y objetivos con estructura clara.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Integré en \LaTeX{} con uniformidad y referencias.\\[0.3em]
\textbf{TP:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Documenté el \textit{Tactical Level Software Design} para audiencias mixtas.\\
\textbf{Poma Espinoza, Gustavo}\\
Redacté flujos y contratos del diseño táctico con trazabilidad.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Escribí decisiones y riesgos del diseño táctico con sustento.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Normalicé guías y criterios de accesibilidad del \textit{Solution UX Design}.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Unifiqué estilo y precisión del \textit{Solution UX Design}.
\end{minipage}
&
\begin{minipage}[t]{\linewidth}\small\setlength{\parskip}{2pt}
\textbf{TB1:}\\
La redacción consolidó evidencia y resultados con objetividad; \LaTeX{} aportó rigor y consistencia.\\[0.3em]
\textbf{TP:}\\
Los entregables escritos de diseño táctico y UX aseguraron claridad, trazabilidad y consistencia para todas las audiencias.
\end{minipage}
\\
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

# Capítulo II: Requirements Elicitation & Analysis

Para construir una solución digital que responda de manera efectiva al dominio de la nutrición y el cuidado de la salud, es necesario comprender en profundidad a los usuarios, sus necesidades y el contexto en el que interactuarán con la aplicación. Este capítulo aborda el proceso de Requirements Elicitation & Analysis, etapa fundamental para garantizar que Foodlytics se desarrolle como una herramienta alineada a las expectativas del mercado y con un impacto positivo en la vida de pacientes y profesionales de la salud.

En esta fase se identifican y analizan los requerimientos del público objetivo, se estudia la oferta existente en el mercado y se emplean técnicas como entrevistas, análisis competitivo, mapeo de tareas y escenarios de uso. Todo ello permite definir de manera clara los requisitos funcionales y no funcionales del sistema. La información obtenida en este capítulo constituye la base sólida para el diseño y la implementación de una solución tecnológica innovadora, con capacidad de mejorar la adherencia a los planes nutricionales y optimizar el trabajo de los especialistas.

\newpage

## Competidores

![Recurso extraído de Canva](src/img/cap2/competidores-introduccion.png)

Después de realizar un análisis del mercado, se identificaron diversas plataformas y aplicaciones que ofrecen servicios vinculados a la nutrición digital, el seguimiento alimenticio y la salud preventiva. Estas soluciones constituyen referencias relevantes, ya que presentan características orientadas a resolver problemas similares a los abordados por Foodlytics, tales como el registro de la dieta diaria, la adherencia a planes nutricionales y la interacción entre pacientes y profesionales de la salud.

El estudio de estos competidores permite reconocer fortalezas y limitaciones en sus propuestas, lo cual representa un insumo fundamental para identificar oportunidades de mejora y diseñar una propuesta de valor diferencial. De esta manera, Foodlytics podrá posicionarse como una alternativa innovadora y adaptada al contexto local, aportando beneficios concretos tanto a pacientes como a especialistas en nutrición y medicina deportiva.

\newpage

**Competidores:**

- ***MyFitnessPal:*** Es una de las aplicaciones de nutrición más utilizadas a nivel mundial. Permite registrar alimentos, contar calorías y realizar un seguimiento de macronutrientes. Su ventaja radica en la base de datos global de alimentos y su integración con dispositivos de salud (relojes inteligentes, apps de ejercicio). Sin embargo, no está diseñada específicamente para el contexto peruano y carece de un componente directo de interacción entre nutricionista y paciente.

![Imagen extraída de MyFitnessPal [(URL)](https://www.myfitnesspal.com/es)](src/img/cap2/MyFitnessPal-landing.png)

\vspace{1em}

- ***Nutrify:*** Es una aplicación presente en varios países de Latinoamérica que se centra en la gestión de pacientes para nutricionistas. Ofrece herramientas para planificar dietas, enviar recordatorios y dar seguimiento al progreso de los pacientes. Su fortaleza está en que está adaptada a la realidad latinoamericana, pero se enfoca más en generar planes y menús que en la recolección de datos del paciente en tiempo real mediante fotos o retroalimentación interactiva.

![Imagen extraída de Nutrify [(URL)](https://nutrify.io/)](src/img/cap2/Nutrify-landing.png)

\newpage

- ***Google Fit*** Es una aplicación de salud y bienestar desarrollada por Google. Está disponible de forma gratuita en Android y también se puede sincronizar con dispositivos iOS mediante Google Health Connect. Su objetivo principal es el monitoreo integral de la actividad física y la salud.

![Imagen extraída de Google Fit [(URL)](https://www.google.com/fit/)](src/img/cap2/GoogleFit-landing.png)

\vspace{1em}

- ***Nutrium:*** Es un software para nutricionistas que combina gestión de pacientes, planificación de dietas y seguimiento del progreso. Su fortaleza es ofrecer un ecosistema integral para profesionales, con recordatorios y comunicación directa con los pacientes. Sin embargo, no cuenta con reconocimiento automático de alimentos por imágenes y su base de datos no está adaptada al contexto peruano.

![Imagen extraída de Nutrium [(URL)](https://nutrium.com/es/professionals?gad_source=1&gad_campaignid=22771486204&gbraid=0AAAAADfQ3ofimzajEaWw5uP39K7JmbCxW&gclid=Cj0KCQjw267GBhCSARIsAOjVJ4EVhNU-t-XwvyVAUj2iCTc8oVZQtl1vYb_d7P96jMWgLa0kUh2v5QsaAg2xEALw_wcB)](src/img/cap2/Nutrium-landing.png)

\newpage

### Análisis competitivo  

Tras haber identificado a los principales actores en el ámbito de la nutrición digital y la salud preventiva, se presenta a continuación un análisis comparativo que permite evaluar sus propuestas de valor. Este análisis se centra en aspectos clave como el enfoque de mercado, las funcionalidades principales, el nivel de especialización y los elementos diferenciadores. La finalidad es reconocer patrones, ventajas competitivas y áreas de oportunidad que orienten el posicionamiento estratégico de Foodlytics, asegurando que su propuesta responda de manera efectiva a las necesidades de pacientes y profesionales de la salud en el contexto peruano.

![](src/img/cap2/analisisCompetitivo_1.png)

![](src/img/cap2/analisisCompetitivo_2.png)

![](src/img/cap2/analisisCompetitivo_3.png)

\newpage

### Estrategias y tácticas frente a competidores  

En el cambiante entorno de la salud digital y la nutrición personalizada, desarrollar estrategias competitivas efectivas implica no solo conocer las capacidades internas de la organización, sino también adaptarse de forma proactiva a las tendencias tecnológicas y las expectativas del mercado.

\begin{quote}
Una estrategia digital bien diseñada es clave para el éxito competitivo en el sector salud, ya que permite atraer pacientes, fortalecer la marca y adaptarse a las tendencias tecnológicas emergentes (Cutipa-Coro, 2024)
\end{quote}

\vspace{1em}

Este enfoque resulta clave para identificar oportunidades de diferenciación, incorporar herramientas tecnológicas innovadoras y anticipar los cambios en las dinámicas de consumo de salud y bienestar.

En este contexto, Foodlytics —una solución basada en inteligencia artificial orientada a mejorar la alimentación y la gestión nutricional— ha llevado a cabo un análisis competitivo que le ha permitido mapear a los principales actores del mercado, detectar tendencias emergentes y encontrar espacios estratégicos aún poco aprovechados.

A partir de este diagnóstico, se presentan a continuación las estrategias y tácticas que permitirán a Foodlytics fortalecer su ventaja competitiva, adaptarse a las nuevas exigencias del sector y consolidar su liderazgo en el ámbito de la salud digital personalizada.

\vspace{1em}

**Estrategias competitivas para Foodlytics**

\vspace{1em}

::: box
**Diferenciación cultural con base en alimentos locales**
:::

**Estrategia:** Foodlytics debe posicionarse como la primera plataforma de nutrición digital que reconoce y analiza platos típicos peruanos y latinoamericanos, resolviendo la brecha cultural de las apps globales.

**Tácticas propuestas:**

  - Entrenar la IA con un banco de imágenes de platos peruanos (ej. lomo saltado, ají de gallina) y de la región.

  - Generar reportes comparativos de consumo local vs. recomendaciones nutricionales internacionales.

  - Establecer un ciclo de actualizaciones periódicas basado en retroalimentación de pacientes y especialistas.

\vspace{2em}

::: box
**Inteligencia Artificial como ventaja competitiva central**
:::

**Estrategia:** A diferencia de Nutrify o Nutrium, Foodlytics debe basar su propuesta en la captura de datos en tiempo real a través de IA, reduciendo la carga manual de pacientes y aumentando la adherencia.

**Tácticas propuestas:**

  - Optimizar la velocidad y precisión del reconocimiento de alimentos.

  - Permitir correcciones manuales rápidas que alimenten el modelo.

  - Convertir cada interacción en un dataset que fortalezca la IA (aprendizaje continuo).

\vspace{2em}

::: box
**Segmentación según perfil de usuario**
:::

**Estrategia:** La propuesta de Foodlytics debe adaptarse a las necesidades de pacientes jóvenes/adultos en control de peso o rendimiento deportivo, y a nutricionistas que gestionan múltiples pacientes.

**Tácticas propuestas:**

  - Diseñar planes escalables para pacientes (gratuito/premium) y profesionales (suscripción mensual o institucional).

  - Personalizar dashboards clínicos según tipo de especialista (nutricionista clínico, deportivo o de consulta privada).

  - Implementar campañas educativas en redes sociales y webinars según el perfil del usuario objetivo.

\vspace{2em}

::: box
**Integración con la práctica clínica**
:::

**Estrategia:** Foodlytics debe ser más que una app de registro, convirtiéndose en un aliado de los nutricionistas en la consulta, con reportes automáticos y paneles que ahorren tiempo de análisis.

**Tácticas propuestas:**

  - Incluir gráficos comparativos de evolución (peso, IMC, calorías).

  - Generar reportes exportables para historia clínica digital.

  - Ofrecer módulos adicionales para nutrición deportiva y control preventivo de enfermedades crónicas.

\vspace{2em}

::: box
**Construcción de redes y alianzas estratégicas**
:::

**Estrategia:** Foodlytics debe fortalecer su posicionamiento a través de alianzas con clínicas, universidades y asociaciones de nutricionistas que validen la confiabilidad del sistema y faciliten su adopción en la práctica profesional.

**Tácticas propuestas:**

  - Establecer convenios con clínicas privadas y consultorios nutricionales para validar la herramienta en entornos reales.

  - Vincularse con asociaciones profesionales de nutricionistas para generar credibilidad.

  - Integrarse con dispositivos de salud (básculas inteligentes, relojes deportivos) para ampliar el ecosistema de valor.

\vspace{3em} 

**Tácticas Específicas para para el Fortalecimiento de *Foodlytics***

\vspace{1em}

::: box
**Posicionamiento como la app de nutrición “localizada” para Perú y Latinoamerica**
:::

**Táctica:**  
Construir una identidad de marca confiable que comunique el valor de Foodlytics como solución accesible, científica y culturalmente adaptada, destacando su capacidad para mejorar la adherencia a planes nutricionales y la práctica profesional de los especialistas.

**Acciones:**

  - Crear campañas gráficas y audiovisuales que muestren casos reales de pacientes que mejoraron su alimentación usando la app.

  - Participar en congresos de nutrición, ferias de salud y espacios universitarios para aumentar la visibilidad académica y profesional.

  - Adaptar los mensajes de comunicación según el público: pacientes (simplicidad y motivación) y nutricionistas (precisión y ahorro de tiempo).

\vspace{2em}

::: box
**Mejora continua del reconocimiento automático de alimentos**
:::

**Táctica:**  
Mantener la IA como el núcleo diferenciador del producto, asegurando precisión y confianza clínica.

**Acciones:**

  - Implementar entrenamientos periódicos con datasets de imágenes de platos peruanos y latinos.

  - Permitir que los usuarios corrijan manualmente errores y usar esa data como retroalimentación para entrenar al modelo.
  
  - Integrar validaciones con nutricionistas: panel de revisión donde especialistas confirmen datos de porciones y nutrientes.

\vspace{2em}

::: box
**Optimización continua de la experiencia de usuario (UX)**
:::

**Táctica:** Garantizar que tanto la app de pacientes como el panel web para nutricionistas sean intuitivos, rápidos y funcionales, priorizando la simplicidad de registro y la claridad en los reportes clínicos.

**Acciones:**

   - Implementar un sistema de feedback en la app para recibir sugerencias de pacientes y profesionales.

   - Realizar pruebas de usabilidad con grupos de nutricionistas y jóvenes pacientes para detectar fricciones en la interfaz.

   - Ajustar la app para minimizar el tiempo de registro de comidas y ofrecer reportes automáticos en formatos fáciles de interpretar.

\vspace{2em}

::: box
**Adherencia y motivación de pacientes**
:::

**Táctica:** Evitar el abandono de la app creando mecanismos de motivación continua y personalización.

**Acciones:**

   - Diseñar notificaciones inteligentes: felicitaciones al registrar comidas, recordatorios cuando omiten registros o metas alcanzadas.

   - Crear retos cortos (“Registra tus comidas 7 días seguidos”) con recompensas digitales.

   - Generar dashboards simples donde el paciente pueda ver visualmente su progreso (peso, calorías, macros).

\vspace{2em}

::: box
**Fidelización de profesionales y pacientes:**
:::

**Táctica:** Fortalecer las relaciones de largo plazo con nutricionistas y pacientes, creando un ecosistema de soporte y motivación que incremente la adherencia y reduzca el abandono de la app.

**Acciones:**

   - Crear un programa de referidos que ofrezca beneficios (descuentos o funciones premium) a quienes inviten a colegas o pacientes.

   - Brindar capacitaciones virtuales y guías prácticas a los nutricionistas para optimizar el uso del panel clínico.

   - Generar notificaciones personalizadas y reportes periódicos que motiven a los pacientes y refuercen el vínculo con su especialista.

\newpage

## Entrevistas  

Las entrevistas fueron diseñadas como técnica principal de recolección cualitativa para comprender tanto aspectos objetivos (edad, ocupación, nivel educativo, acceso a tecnología) como subjetivos (hábitos alimenticios, motivaciones para mejorar su nutrición, frustraciones con el uso de aplicaciones actuales y expectativas respecto a herramientas digitales). Esta información resulta esencial para la construcción de arquetipos de usuarios (User Personas), así como para la elaboración de Empathy Maps y Journey Maps que orienten el diseño centrado en el usuario de Foodlytics.

![Recurso extraído de Canva](src/img/cap2/entrevistas-introduccion.png)

::: note
Para acceder al video de las entrevistas, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202211212_upc_edu_pe/EUSHZe96_IJCpJ01PldFNykBAJ6ZEiuDjDqJJdvSMM-YyA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=YFJYGO)
:::

\newpage

### Diseño de entrevistas  

Para el diseño de entrevistas se definieron dos segmentos objetivo con perfiles claramente diferenciados: **Médicos Nutricionistas o del deporte** y **Pacientes**. 

::: box
**Segmento Objetivo 1:** Médicos Nutricionistas o del deporte
:::

**Objetivo:**

Explorar cómo los nutricionistas gestionan actualmente a sus pacientes, qué herramientas usan, cuáles son sus principales dificultades en el control de dietas y rutinas, y conocer su interés en usar soluciones tecnológicas de apoyo.

**Perfil general**

1) ¿Podría indicarnos su nombre, edad y especialidad? 

2) ¿Hace cuánto tiempo ejerce como nutricionista o médico especialista? 

3) ¿Atiende principalmente en consultorio privado, clínica u hospital? 

**Gestión actual de pacientes**

4) ¿Cómo lleva actualmente el registro de dietas y rutinas de sus pacientes? (Ejemplo: cuadernos, Excel, apps)

5) ¿Con qué frecuencia actualiza los planes de alimentación de sus pacientes?

6) ¿Qué tan confiables considera los reportes que le dan sus pacientes sobre su consumo de alimentos?

**Uso de herramientas y tecnología**

7) ¿Ha probado antes alguna herramienta digital o app para seguimiento nutricional? ¿Cuál fue su experiencia?

8) ¿Qué limitaciones encuentra en los métodos actuales de seguimiento (ejemplo: falta de datos reales, poca adherencia del paciente)?

9) ¿Qué tan dispuesto estaría a usar un sistema con IA que reconozca alimentos y calcule macros automáticamente?

**Interés y expectativas sobre soluciones digitale**

10) ¿Qué funcionalidades considera más útiles en una plataforma de este tipo?
   - Seguimiento de la dieta en tiempo real
   - Reportes automáticos de calorías y macros 
   - Registro de peso y evolución 
   - Panel de control con reportes por paciente 

11) ¿Qué beneficios cree que traería para su práctica profesional contar con una app así? 

12) ¿Qué obstáculos ve para implementar una herramienta digital en su consulta? (ejemplo: tiempo de uso, costos, confianza en IA, resistencia de pacientes) 

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación 
:::

**Objetivo:**  
Entender cómo los pacientes perciben el control de su dieta, sus frustraciones con los métodos actuales, su interés en usar tecnología para registrar lo que comen y su disposición a pagar por un servicio que mejore su salud y seguimiento.

**Perfil general** 

1) ¿Cuál es su nombre, edad y ocupación? 

2) ¿Actualmente sigue un plan nutricional? ¿Con qué frecuencia visita a un nutricionista? 

3) ¿Ha usado alguna aplicación o método para controlar su dieta y peso? 

**Experiencia y percepción actual**  

4) ¿Cómo suele registrar o recordar lo que come en el día?

5) ¿Qué tan difícil le resulta seguir las recomendaciones de su nutricionista?

6) ¿Cuál ha sido su mayor frustración al intentar mejorar su alimentación o controlar su peso?

**Uso y apertura a tecnología** 

7) ¿Qué tipo de celular usa actualmente (Android o iPhone)?

8) ¿Usa apps relacionadas con salud o nutrición? ¿Cuáles y para qué?

9) ¿Le gustaría que una aplicación móvil le calcule automáticamente calorías y macros a partir de fotos de sus comidas? ¿Por qué?

10) ¿Le sería útil recibir notificaciones automáticas (ejemplo: recordatorios de comida, control de peso, alertas de metas)?


**Confianza y motivación** 

11) ¿Qué es lo que más le generaría confianza en una aplicación móvil de nutrición? (ejemplo: respaldo del nutricionista, precisión de datos, facilidad de uso)

12) ¿Qué tendría que pasar para que dejara de usar la app?

13) ¿Confía más en su propio registro manual, en lo que le indica el nutricionista, o en una app con IA que lo acompañe diariamente?

**Valor percibido y disposición de pago** 

14) Si una aplicación le ayudara a mejorar su salud y mantener sus metas, ¿estaría dispuesto/a a pagar por ella?

15) ¿Qué características debería tener para sentir que vale la pena el costo?

16) Imagine su sistema de nutrición ideal:
  - ¿Cómo le informaría sobre sus progresos? 
  - ¿Qué vería en su celular? 
  - ¿Qué control tendría usted mismo?

\newpage

### Registro de entrevistas 

::: note
Para acceder al video de las entrevistas, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202211212_upc_edu_pe/EUSHZe96_IJCpJ01PldFNykBAJ6ZEiuDjDqJJdvSMM-YyA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=YFJYGO)
:::


::: box
**Segmento Objetivo 1:** Médicos Nutricionistas o del deporte
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Luisa Fernanda Gutiérrez Herrera \\ \hline
\textbf{Edad}                 & 30 años \\ \hline
\textbf{Ubicación geográfica} & La libertad, Trujillo \\ \hline
\textbf{Cargo}                & Licenciada en Nutrición, especialista en Nutrición Clínica con mención en Oncología \\ \hline
\textbf{Tiempo de entrevista} & 00:00 - 10:16 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Luisa Fernanda Gutiérrez Herrera es licenciada en nutrición desde 2009, con especialidad en nutrición clínica y oncología. Se desempeña en un hospital de alta complejidad en Trujillo y también en consulta privada. En su práctica, utiliza un sistema manual basado en *cardex* para registrar dietas y evolución de pacientes; sin embargo, menciona que actualmente cuenta con una aplicación institucional en fase de implementación, aunque esta no está completamente desarrollada y aún presenta limitaciones que la hacen poco práctica para su día a día.

Sobre los reportes de pacientes, considera que no siempre son confiables, ya que algunos omiten información o cambian de opinión constantemente respecto a su dieta. Aunque ha probado sistemas digitales básicos para notas de ingreso y evaluaciones nutricionales, destaca que la mayoría de ellos son costosos y poco adaptados a la práctica clínica cotidiana.

Frente a la posibilidad de usar una aplicación con inteligencia artificial que reconozca alimentos y calcule automáticamente calorías y macronutrientes, afirma que sería de gran utilidad, pues reduciría el tiempo de cálculo y permitiría un seguimiento más preciso en casos complejos, como niños y pacientes hospitalizados con desnutrición. Además, considera fundamental que la aplicación se base en una tabla nutricional confiable y adaptada a alimentos peruanos, lo que garantizaría la veracidad de la información.

Resalta que la falta de herramientas digitales efectivas dificulta el seguimiento detallado de pacientes, sobre todo en contextos complejos como la oncología o la desnutrición infantil. En Trujillo, la alta prevalencia de desnutrición hace indispensable contar con registros confiables y mediciones frecuentes de peso, talla y consumo real de alimentos. La ausencia de este control riguroso retrasa intervenciones oportunas y compromete la recuperación de pacientes vulnerables.

Finalmente, advierte que el éxito de la solución dependerá de que sea ágil, intuitiva y fácil de integrar en la rutina clínica. Un sistema engorroso podría ser descartado rápidamente, mientras que una herramienta confiable y sencilla podría mejorar la eficiencia del profesional, la adherencia de los pacientes y la calidad del servicio de nutrición en el país.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS11.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Gianella Rodríguez  \\ \hline
\textbf{Edad}                 & 29 años \\ \hline
\textbf{Ubicación geográfica} & La Libertad, Trujillo \\ \hline
\textbf{Cargo}                & Licenciada en Nutrición Clínica \\ \hline
\textbf{Tiempo de entrevista} & 10:17 - 20:40 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**
Gainella Rodríguez, licenciada en nutrición clínica con 29 años de edad, cuenta con alrededor de 10 años de experiencia profesional y actualmente se desempeña en un hospital nacional del sector público. Su práctica combina registros en historias clínicas físicas con el Sistema de Gestión de Servicios de Salud  ***SGSS*** ( herramienta informática desarrollada en entorno web, que permite el registro e integración de las actividades asistenciales y administrativas), donde documenta evolución nutricional y diagnósticos de pacientes. Además, ha utilizado herramientas digitales básicas como Google Drive para registrar y dar seguimiento a la información, aunque reconoce que estos métodos siguen siendo limitados en precisión y agilidad.

Explica que en pacientes hospitalizados las actualizaciones nutricionales son diarias, mientras que en consulta externa se realizan mensualmente. Reconoce, sin embargo, que los reportes entregados por pacientes, en especial adultos mayores, suelen ser poco confiables debido a olvidos o dificultad para estimar cantidades. Para superar esta brecha, emplea imágenes o medidas caseras que facilitan el recuerdo de los alimentos consumidos.

Valora positivamente la propuesta de una aplicación como Foodlytics, ya que considera que el registro fotográfico con análisis automático de calorías y macronutrientes permitiría un seguimiento más preciso, reduciendo tiempos de consulta y mejorando la educación alimentaria del paciente. Además, resalta que el sistema podría integrar información relevante como antecedentes patológicos, consumo de medicamentos y evaluaciones antropométricas (peso, pliegues cutáneos, análisis bioquímicos), lo que lo convertiría en una herramienta más completa y clínica.

Entre los beneficios más importantes identifica el ahorro de tiempo en la atención, la posibilidad de personalizar planes nutricionales y la educación directa del paciente mediante visualizaciones claras de su consumo. Sin embargo, advierte sobre riesgos como la confidencialidad de datos sensibles, la resistencia tecnológica de adultos mayores y la limitada disponibilidad de dispositivos móviles en ciertos sectores. Finalmente, recalca la importancia de que la plataforma se respalde en guías de la OMS y referencias científicas, para generar confianza en los profesionales de salud y garantizar la validez de los cálculos.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS12.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Graciela del Rocío Alza \\ \hline
\textbf{Edad}                 & 50 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Nutricionista especializada en nutrición deportiva \\ \hline
\textbf{Tiempo de entrevista} & 20:41 - 25:41 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Graciela del Rocío Alza es nutricionista con más de 25 años de experiencia en el ámbito clínico y deportivo. Actualmente trabaja en una clínica privada en Lima y ofrece consultas particulares a pacientes que buscan mejorar su rendimiento físico y su estado de salud general. Su práctica combina el uso de hojas de cálculo y aplicaciones básicas como Excel y WhatsApp, donde los pacientes suelen enviar fotos de sus comidas. No obstante, reconoce que estos métodos son poco sistemáticos, lo que dificulta llevar un control confiable de la adherencia a los planes nutricionales.

Explica que uno de los mayores retos en su trabajo es el seguimiento detallado de la ingesta calórica y proteica, especialmente en deportistas y pacientes con requerimientos específicos. Señala que los pacientes jóvenes tienden a registrar sus consumos de forma más activa, mientras que los adultos muestran menor constancia, lo que genera vacíos en la información.

Respecto a la propuesta de Foodlytics, considera que la app sería altamente beneficiosa al permitir el reconocimiento automático de alimentos mediante fotos, con cálculos inmediatos de calorías y macronutrientes. Para los nutricionistas, el panel web clínico representaría una ventaja significativa, ya que facilitaría la comparación de progresos y el ajuste de planes sin depender de registros manuales.

Graciela subraya que, además de la precisión en los cálculos, la aplicación debería incluir un módulo de recordatorios y alertas motivacionales que ayude a los pacientes a mantener la adherencia. También recomienda que se incorporen opciones para registrar suplementos nutricionales y horarios de ingesta, aspectos especialmente relevantes en la nutrición deportiva.

Finalmente, advierte que el éxito de Foodlytics dependerá de su facilidad de uso y de que esté adaptada a la realidad peruana, con bases de datos de alimentos locales. Concluye que, si cumple con estas condiciones, se convertiría en una herramienta clave no solo para pacientes jóvenes, sino también para profesionales con amplia trayectoria que buscan digitalizar su práctica.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS13.png)

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Elizabeth Quedina \\ \hline
\textbf{Edad}                 & 59 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Contadora \\ \hline
\textbf{Tiempo de entrevista} & 25:45 - 30:25 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Elizabeth Quedina, de 59 años, trabaja como contadora y muestra un interés creciente en mejorar su alimentación. Actualmente, sus visitas al nutricionista son esporádicas —aproximadamente una vez al año— y se basa principalmente en un recetario inicial para organizar sus comidas, reduciendo el consumo de arroz y priorizando verduras según las indicaciones médicas. Reconoce que no utiliza aplicaciones móviles para el control de la dieta ni herramientas de seguimiento, lo que limita la precisión de sus registros.

Al describir sus hábitos, menciona que suele recordar mentalmente qué alimentos puede consumir y organiza sus comidas de forma intuitiva, sin un control sistemático. Considera que una aplicación con inteligencia artificial que calcule automáticamente calorías y macronutrientes a partir de fotos sería muy útil, ya que le permitiría llevar un control más práctico y constante. Además, valora positivamente la posibilidad de recibir notificaciones automáticas como recordatorios de comidas o alertas sobre metas nutricionales, pues admite que con frecuencia se olvida de comer de manera ordenada debido a su carga laboral.

Destaca que la facilidad de uso y la precisión de los datos son los factores que más le generarían confianza en una app de este tipo. Está dispuesta a pagar por el servicio siempre que la aplicación le proporcione horarios claros, alarmas para recordarle qué alimentos consumir y reportes sobre sus progresos semanales. Señala que dejaría de usarla únicamente si logra cumplir sus metas nutricionales, aunque reconoce que el control alimenticio debería ser un proceso continuo.

Finalmente, Elizabeth enfatiza que una aplicación como Foodlytics no solo simplificaría su rutina, sino que también se convertiría en un apoyo motivacional para mantener hábitos saludables en el tiempo.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS21.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Carlos Sánchez \\ \hline
\textbf{Edad}                 & 22 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Estudiante de Ingeniería en la UPC \\ \hline
\textbf{Tiempo de entrevista} & 30:27 - 37:21 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**
Carlos Sánchez, estudiante de 22 años en la Universidad Peruana de Ciencias Aplicadas (UPC), visita al nutricionista una o dos veces cada seis meses. Actualmente utiliza aplicaciones digitales como MyFitnessPal para registrar su alimentación diaria y la app vinculada a su balanza digital para monitorear su peso. Además, emplea una pulsera inteligente para medir calorías quemadas y calidad de sueño.

Reconoce que seguir los planes nutricionales le resulta difícil por falta de tiempo y por el esfuerzo que requiere cocinar y medir calorías. Estas limitaciones lo llevan con frecuencia a recurrir a comida rápida o snacks poco saludables. Identifica el tiempo y la organización como sus principales frustraciones al intentar mejorar su alimentación.

Valora positivamente la idea de una aplicación que, mediante fotos, calcule automáticamente calorías y macronutrientes, ya que le ahorraría el proceso de pesar y medir alimentos. Considera fundamental la precisión de los datos, pues desconfía cuando las apps presentan valores diferentes a los empaques de los productos. También vería útil recibir notificaciones automáticas de recordatorios de comidas y metas nutricionales, dado que suele olvidar mantener su dieta.

Está dispuesto a pagar por la aplicación siempre que garantice precisión y facilidad de uso. Además, sugiere que se incorporen funcionalidades adicionales, como recomendaciones personalizadas ajustadas al presupuesto, lo cual sería de gran ayuda para estudiantes. Sobre los reportes de progreso, prefiere un esquema combinado: reportes semanales para seguimiento inmediato y uno mensual más completo para evaluar resultados generales.

Concluye que su permanencia en el uso de la aplicación dependería de que los cálculos sean confiables y la experiencia de usuario sencilla. De ser así, afirma que la adoptaría de manera continua.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS22.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Luciana \\ \hline
\textbf{Edad}                 & 20 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Estudiante de Odontología \\ \hline
\textbf{Tiempo de entrevista} & 37:21 - 41:57 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Luciana, estudiante de odontología de 20 años, visita al nutricionista de manera esporádica (aproximadamente una vez al año) y nunca ha usado aplicaciones móviles para el control de su dieta o peso. Suele registrar sus comidas de manera básica en su celular, aunque admite que su alimentación es balanceada en general, salvo fines de semana en los que se descontrola un poco.

No percibe grandes dificultades en mantener sus hábitos durante la semana, pero reconoce que sería útil contar con una aplicación que calcule calorías y macronutrientes automáticamente a partir de fotos. Valora positivamente la idea de recibir notificaciones y recordatorios de comidas o metas, ya que podrían ayudarle a organizar mejor su alimentación.

Respecto a la confianza en una app, considera indispensable que esté respaldada por nutricionistas profesionales, pues eso garantizaría su validez. Señala que dejaría de usar la aplicación si los cálculos resultaran poco precisos. También menciona que prefiere recibir reportes semanales de su progreso, en lugar de diarios o mensuales, ya que le resultaría más práctico.

En cuanto a la disposición de pago, afirma que sí estaría dispuesta a invertir en una aplicación siempre que tenga el respaldo de especialistas y combine facilidad de uso con información confiable. Concluye que la app sería más valiosa si le permitiera organizarse en coordinación con un nutricionista.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS23.png)

\newpage

### Análisis de entrevistas

::: box
**Segmento Objetivo 1:** Médicos nutricionistas o del deporte
:::

**Perfil Demográfico**

- **Edades:** Entre 29 y 50 años, con un promedio aproximado de 36 años.

- **Ubicación geográfica:** Principalmente en ciudades urbanas como Trujillo y Lima.

**Cargos ocupados:**

- Nutricionista clínica con especialización en oncología.

- Nutricionista en hospital público.

- Nutricionista deportiva en clínica privada.

Este segmento está compuesto por profesionales con formación especializada y más de 10 años de experiencia promedio. Desempeñan labores en hospitales, clínicas y consultas privadas, atendiendo tanto a pacientes con enfermedades crónicas como a deportistas y población general.

**Experiencia y Conocimientos sobre Nutrición Digital**

Los nutricionistas entrevistados muestran un panorama mixto respecto al uso de tecnología. Aunque en algunos contextos ya emplean aplicaciones institucionales o el *SGSS* (Sistema de Gestión de Servicios de Salud), estas plataformas aún presentan limitaciones de usabilidad y adaptación a la práctica clínica cotidiana. La mayoría depende de herramientas básicas como hojas de cálculo, notas manuales o incluso *WhatsApp* para el envío de fotos de comidas por parte de los pacientes.

Los principales problemas identificados fueron:

- Información incompleta o poco confiable entregada por los pacientes (olvidos, estimaciones imprecisas).

- Falta de adaptación cultural de las apps globales, que no incluyen alimentos locales peruanos.

- Alto costo y poca accesibilidad de sistemas digitales especializados.

- Escasa automatización en el cálculo de calorías, macronutrientes y reportes clínicos.

**Herramientas y Tecnología Actual**

- **Herramientas usadas:**

  - SGSS en hospitales públicos (registro administrativo y clínico).

  - Aplicaciones institucionales en fase inicial de implementación.

  - Google Drive y hojas de Excel como registros complementarios.

  - Comunicación por WhatsApp para recibir evidencia de consumo alimenticio.

- **Brechas tecnológicas:**

  - Ausencia de un sistema integral que combine IA, registro fotográfico y panel clínico.

  - Dificultad para obtener datos antropométricos y bioquímicos integrados en un mismo espacio.

  - Falta de trazabilidad en el seguimiento entre consulta presencial y rutina diaria del paciente.


**Intereses y Necesidades Tecnológicas**

Los nutricionistas entrevistados destacan el interés por una solución como Foodlytics, siempre que responda a sus necesidades reales:

- **Necesidades principales:**

  - Registro fotográfico con análisis automático de calorías y macronutrientes.

  - Base de datos confiable con alimentos peruanos y locales.

  - Panel clínico web que permita ver evolución de peso, talla y reportes de adherencia.

  - Módulos complementarios para antecedentes médicos, medicamentos y suplementos.

  - Recordatorios y alertas motivacionales para mejorar la adherencia del paciente.

- **Valor percibido:**

  - Ahorro de tiempo en la consulta.

  - Reportes clínicos más completos y confiables.

  - Mejora de la adherencia y motivación de los pacientes.

  - Reputación profesional al integrar tecnología moderna en la práctica clínica.

- **Viabilidad económica:**

  Aunque los costos son un factor crítico, se percibe que clínicas privadas y pacientes con interés en nutrición deportiva estarían dispuestos a invertir, siempre que la herramienta ofrezca beneficios claros y medibles.

**Preferencias y Comportamientos**

- **Comportamientos actuales:**

  - Uso combinado de registros manuales y herramientas digitales básicas.

  - Comunicación directa con pacientes vía WhatsApp.

  - Control antropométrico periódico con reportes físicos.

- **Cambios que buscan:**

  - Un sistema automatizado que reduzca la dependencia de reportes manuales.

  - Integración de todos los datos del paciente en una sola plataforma.

  - Soporte a la toma de decisiones con reportes visuales y objetivos.

En síntesis, los nutricionistas constituyen un segmento dispuesto a adoptar soluciones tecnológicas siempre que sean prácticas, confiables y culturalmente adaptadas. Una aplicación como Foodlytics tiene el potencial de convertirse en un aliado clave en la modernización de la nutrición clínica y deportiva en el Perú.

**Estadísticas y Porcentajes**

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico1.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico2.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico3.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico4.png)

\newpage

**Análisis de datos**

Las entrevistas realizadas permitieron identificar coincidencias importantes en el perfil y necesidades de los nutricionistas. Un hallazgo clave es que todos utilizan herramientas digitales básicas (Excel, WhatsApp, SGSS) pero reconocen que estas son insuficientes para garantizar precisión, trazabilidad y adherencia del paciente.

En cuanto al acceso tecnológico, se observa un uso diversificado de dispositivos: dos de las entrevistadas utilizan iOS y una Android en móviles, mientras que en laptops predominan los entornos de Windows (66.7%) frente a MacOS (33.3%). Esto sugiere que la plataforma debe ser multiplataforma y priorizar la accesibilidad en entornos comunes.

Respecto a las funcionalidades más mencionadas, destacan:

Registro fotográfico con IA y análisis automático de nutrientes, visto como la solución al principal dolor de los nutricionistas: la falta de precisión en reportes de pacientes.

Paneles clínicos con reportes automáticos y datos antropométricos, mencionados como clave para ahorrar tiempo y personalizar tratamientos.

Alertas y recordatorios motivacionales, percibidos como esenciales para combatir la falta de constancia de los pacientes.

::: note
En síntesis, los datos muestran que existe una brecha clara entre el nivel de digitalización actual y las necesidades clínicas de los nutricionistas. Aunque cuentan con herramientas básicas, la falta de precisión y personalización limita su efectividad. Una solución como Foodlytics, que combine IA para reconocimiento de alimentos, paneles clínicos adaptados al contexto peruano y mecanismos de motivación para pacientes, podría cerrar esta brecha y posicionarse como una herramienta estratégica para el sector.
:::

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación
:::

**Perfil Demográfico**

- **Edades:** Entre 20 y 59 años, con un promedio de 33.6 años.

- **Ubicación geográfica:** Principalmente en Lima, Perú.

**Cargos ocupados:**

- Contadora (trabajadora adulta con vida laboral activa).

- Estudiante de Ingeniería en la UPC (joven universitario).

- Estudiante de Odontología (joven universitaria).

Este segmento incluye a adultos y jóvenes que buscan mejorar sus hábitos alimenticios, pero con distintos niveles de disciplina y familiaridad tecnológica. Mientras los adultos tienden a basarse en recetas tradicionales y rutinas intuitivas, los jóvenes muestran mayor disposición a usar herramientas digitales, aunque enfrentan dificultades de tiempo, organización y constancia.

**Experiencia y Conocimientos sobre Alimentación Digital**

El uso de tecnología es variado. Algunos pacientes nunca han empleado aplicaciones móviles para registrar su dieta, mientras que otros recurren a plataformas globales como MyFitnessPal, balanzas digitales con apps vinculadas o pulseras inteligentes.

- **Los principales problemas mencionados fueron:**

  - Falta de constancia para registrar comidas (olvidos, desorganización, falta de tiempo).

  - Registros poco precisos, ya que los pacientes no suelen medir cantidades con exactitud.

  - Alimentación desordenada en fines de semana, lo que interrumpe hábitos saludables.

  - Desconfianza en la precisión de las aplicaciones actuales, especialmente cuando los cálculos difieren de la información de etiquetas o recomendaciones profesionales.

**Herramientas y Tecnología Actual**

  - Parte del segmento no utiliza aplicaciones digitales, organizando sus dietas de forma intuitiva.

  - Otro grupo combina distintas herramientas como apps de registro, dispositivos inteligentes y balanzas digitales.

Este contraste revela una brecha tecnológica: aunque existe interés por digitalizar los hábitos, las soluciones actuales no satisfacen plenamente la necesidad de precisión, facilidad de uso y adaptación cultural.

**Intereses y Necesidades Tecnológicas**

Los pacientes coinciden en que una aplicación como Foodlytics sería de gran utilidad si responde a necesidades concretas:

- **Necesidades principales:**

  - Registro automático de alimentos con fotos y cálculo confiable de calorías y macronutrientes.

  - Notificaciones y recordatorios para organizar horarios de comidas.

  - Reportes periódicos de progreso (con preferencia por reportes semanales).

  - Respaldo profesional que garantice la confiabilidad de la información.

  - Recomendaciones personalizadas adaptadas a distintos contextos, incluyendo presupuesto en el caso de estudiantes.

- **Valor percibido:**

  - Simplificación en la rutina de registro alimentario.

  - Motivación para mantener la adherencia a planes nutricionales.

  - Ahorro de tiempo en cálculos manuales.

  - Mayor confianza en datos validados por especialistas.

- **Viabilidad económica:**

  Existe disposición a pagar por el servicio siempre que ofrezca precisión, facilidad de uso y credibilidad profesional.


**Preferencias y Comportamientos**

- **Comportamientos actuales:**

  - Registro manual, intuitivo o uso limitado de apps globales sin personalización cultural.

  - Organización parcial de rutinas, con tendencia a romper hábitos saludables durante fines de semana.

- **Cambios que buscan:**

  - Automatización del registro alimentario.

  - Recordatorios constantes que ayuden a sostener la disciplina.

  - Funcionalidades que combinen confiabilidad, simplicidad y pertinencia cultural (incluyendo alimentos locales).

En síntesis, este segmento muestra una alta disposición a adoptar soluciones digitales, siempre que sean fáciles de usar, confiables y adaptadas al contexto peruano. Foodlytics puede posicionarse como una herramienta estratégica para transformar el interés en mejorar la alimentación en resultados sostenibles y medibles.

**Estadísticas y Porcentajes**

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico5.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico6.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico7.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico8.png)

\newpage

**Análisis de datos**

Las entrevistas realizadas a pacientes interesados en mejorar su alimentación permiten identificar patrones de comportamiento, brechas tecnológicas y oportunidades de diseño para la solución propuesta.

En términos de uso tecnológico, se observan diferencias generacionales: los pacientes jóvenes (19 a 30 años) tienden a utilizar principalmente iOS en sus dispositivos móviles, mientras que los de mayor edad prefieren Android. En cuanto a laptops, el sistema más común es Windows, con una presencia menor de MacOS, lo que confirma la necesidad de garantizar compatibilidad multiplataforma con prioridad en entornos de mayor uso.

Respecto a los hábitos de registro, la mayoría de los pacientes no emplea aplicaciones de manera constante. Algunos utilizan apps globales como MyFitnessPal o dispositivos inteligentes vinculados a balanzas y pulseras, mientras que otros llevan un control básico o incluso intuitivo, sin registros sistemáticos. Esto evidencia una brecha clara: el interés por digitalizar sus hábitos existe, pero las herramientas actuales no logran generar confianza ni fomentar la constancia.

En relación con los problemas más recurrentes, se destacan la falta de constancia en el registro de comidas, la poca precisión de los reportes, la dificultad para organizar tiempos y la tendencia a descuidar la dieta los fines de semana. Estos hallazgos refuerzan la importancia de incorporar recordatorios automáticos y reportes periódicos que motiven la adherencia al plan nutricional.

En cuanto a las funcionalidades más valoradas, los pacientes coinciden en la utilidad del registro automático de comidas con fotos y análisis por IA, acompañado de notificaciones personalizadas y reportes semanales de progreso. Asimismo, resaltan la necesidad de contar con el respaldo profesional para validar la confiabilidad de los cálculos, y algunos sugieren la incorporación de recomendaciones adaptadas al presupuesto como valor agregado.

::: note
En síntesis, los datos muestran que los pacientes tienen una alta disposición a adoptar soluciones digitales siempre que estas sean precisas, fáciles de usar, validadas por profesionales y adaptadas a su contexto. Foodlytics puede posicionarse como un puente entre el interés por mejorar la alimentación y la falta de herramientas locales que acompañen de manera constante y confiable la rutina de los usuarios.
:::

\newpage

**Comparación entre Segmentos**

El análisis de entrevistas a nutricionistas y pacientes evidencia tanto necesidades compartidas como demandas específicas, lo que permite entender cómo debe posicionarse Foodlytics como una solución integral.

1) **Similitudes identificadas:**

Ambos segmentos coinciden en la importancia de contar con datos precisos y confiables sobre la alimentación.

Existe un interés común en que la aplicación incorpore reconocimiento automático de alimentos mediante IA, reduciendo errores de registro y tiempos de cálculo.

Tanto pacientes como profesionales valoran la existencia de reportes claros y periódicos, que permitan visualizar progresos de manera sencilla y motivadora.

En ambos casos, la adherencia a los planes nutricionales aparece como un reto central que puede resolverse con notificaciones, recordatorios y retroalimentación continua.

2) **Diferencias principales:**

  - Los nutricionistas priorizan la existencia de un panel clínico web que centralice información de múltiples pacientes, con capacidad de integrar datos antropométricos, antecedentes médicos y reportes automáticos para la toma de decisiones.

  - Los pacientes, en cambio, demandan principalmente facilidad de uso, recordatorios personalizados y motivación constante, elementos que les ayuden a sostener la disciplina en su vida diaria.

  - En términos tecnológicos, los profesionales ya interactúan con sistemas institucionales (como SGSS o apps en fase piloto), aunque limitados; mientras que los pacientes muestran un uso heterogéneo: algunos recurren a apps globales y dispositivos inteligentes, y otros carecen de experiencia digital en el control de la dieta.

3) **Complementariedad de los segmentos:**
Las entrevistas confirman que la efectividad de Foodlytics dependerá de su capacidad para articular la experiencia del paciente con las necesidades clínicas del profesional. Mientras los pacientes requieren una aplicación intuitiva y motivadora, los nutricionistas demandan una herramienta robusta que garantice confiabilidad y respaldo científico.

::: note
En conclusión, la solución debe diseñarse bajo un enfoque de doble valor: para los pacientes, simplicidad y motivación; para los nutricionistas, precisión y control clínico. Esta integración permitirá que Foodlytics se posicione no solo como una aplicación de registro alimentario, sino como un ecosistema digital que fortalece la relación paciente–profesional y contribuye a la mejora sostenible de los hábitos nutricionales en el Perú.
:::

\newpage

## Needfinding

Para diseñar soluciones que realmente respondan a los desafíos del transporte escolar, fue crucial comprender profundamente a los usuarios, sus contextos y sus experiencias. En un entorno donde aumentan las exigencias de seguridad, puntualidad y confianza, adoptar un enfoque centrado en el usuario permitió identificar no solo problemas evidentes, sino también necesidades latentes y oportunidades de innovación reales. 

\begin{quote}
Según Brown (2009), el diseño centrado en las personas comienza con una inmersión empática en la vida de los usuarios, observando lo que hacen, cómo piensan y qué sienten para revelar soluciones que de otro modo pasarían desapercibidas.
\end{quote}

\vspace{1em}

Durante esta etapa de needfinding, se aplicaron métodos como observación directa, entrevistas semiestructuradas y herramientas de empatía. Esto permitió descubrir tareas críticas, frustraciones y aspiraciones de padres, estudiantes, colegios y operadores. Además, se elaboraron perfiles de usuario, mapas de empatía y customer journeys que ayudaron a visualizar la experiencia completa, identificando puntos de fricción y momentos clave donde intervenir con soluciones más efectivas.

![Imagen extraída de Canva](src/img/cap2/intro_needfinding.png)

\newpage

### User Personas

Presentamos perfiles representativos de nuestros usuarios objetivos. Estos arquetipos nos ayudan a diseñar centrados en sus motivaciones, frustraciones y objetivos.

**Segmento  1: Médicos Nutricionistas / Nutricionistas Deportivos**

Frank Zane representa a profesionales con formación clínica o deportiva que atienden a pacientes con sobrepeso o que desean mejorar su rendimiento físico. Este perfil busca herramientas digitales que les permitan ofrecer un servicio más eficiente, moderno y con respaldo en datos objetivos.

- **Objetivos clave:** optimizar el tiempo de consulta, automatizar reportes y mejorar la adherencia de los pacientes.

- **Motivaciones:** diferenciarse como profesionales innovadores y mostrar evidencia clara de los progresos de sus pacientes.

- **Frustraciones:** pérdida de tiempo por información desordenada, falta de trazabilidad y métodos manuales poco ágiles (uso de cardex, hojas sueltas o mensajes por WhatsApp).

- **Necesidades implícitas:** una plataforma que integre funciones clínicas con una interfaz intuitiva, capaz de adaptarse al ritmo de la consulta sin requerir tiempo extra.

Este arquetipo inspira el diseño del dashboard web clínico, la automatización de reportes, y las funciones que convierten el registro de pacientes en una herramienta confiable de monitoreo.

![User Persona 1 - Recurso de UXPRESSIA](src/img/cap2/userperson1.png)

**Segmento 2:Pacientes con interés en mejorar su alimentación**

Mike Mentzer representa a adolescentes y jóvenes adultos con acceso a internet, motivados por metas físicas visibles, pero sin conocimientos técnicos sobre nutrición. Este perfil busca resultados rápidos, claridad en sus acciones y herramientas que lo guíen paso a paso.

- **Objetivos clave:** ganar masa muscular, controlar su dieta, mejorar su imagen y rendimiento.

- **Motivaciones:** alcanzar metas visibles que refuercen su disciplina, inspirarse en referentes fitness y destacar entre sus pares.

- **Frustraciones:** dificultad para calcular calorías, contradicciones en internet, y desmotivación por falta de seguimiento profesional.

- **Conductas comunes:** toma fotos de sus comidas, usa apps o redes sociales para buscar información, pero con baja constancia.

Este arquetipo orienta el diseño de la app móvil del paciente, especialmente en funcionalidades como el registro fotográfico automático, alertas personalizadas, visualización de progreso, y herramientas educativas fáciles de entender.

![User Persona 2 - Recurso de UXPRESSIA](src/img/cap2/userperson2.png)

\newpage

### User Task Matrix

Se ha mapeado la relación entre los distintos perfiles de usuarios y las tareas clave que realizan dentro del ecosistema de la solución. Esta matriz permite visualizar qué actividades son más relevantes para cada segmento, y con ello, priorizar las funcionalidades más críticas del sistema. De esta forma, se alinean las decisiones de diseño con las verdaderas necesidades y expectativas de los usuarios.

\begin{longtable}{|m{6cm}|m{4.5cm}|m{4.5cm}|}
\hline
\textbf{Tarea} & \textbf{Médico Nutricionista} & \textbf{Paciente joven-adulto} \\ \hline
Registrar historial de alimentación & Media & Baja \\ \hline
Revisar dieta diaria & Alta & Media \\ \hline
Asignar planes nutricionales & Alta  & – \\ \hline
Controlar peso y progreso & Media & Alta \\ \hline
Diseñar rutinas de ejercicio personalizadas & Media & – \\ \hline
Revisar cumplimiento de la rutina & Media  & Alta  \\ \hline
Buscar información confiable sobre nutrición & Media  & Alta \\ \hline
Tomar fotos de las comidas & – & Alta  \\ \hline
Ajustar cantidades de comida registradas & – & Media \\ \hline
Consultar calorías y macros ingeridos & Media  & Alta  \\ \hline
Coordinar próxima cita / contacto & Media  & Baja  \\ \hline
Compartir resultados con el médico & – & Media  \\ \hline
Usar apps o herramientas digitales & Media  & Alta \\ \hline
Buscar motivación en redes sociales o influencers & Baja & Alta \\ \hline
\end{longtable}

\newpage

### Empathy Mapping  

Permite profundizar en la perspectiva emocional y racional de los usuarios: lo que piensan, sienten, ven, escuchan, dicen y hacen. Esta herramienta ayuda a identificar barreras cognitivas, motivaciones profundas y oportunidades de diseño centradas en la experiencia real.

**Empathy Map – Frank Zane (Nutricionista Deportivo)**

![Empathy Mapping 1 – Frank Zane](src/img/cap2/empathy1.png){ width=75% }

La figura, nos permite comprender las necesidades y tensiones de Frank como profesional de la salud que busca optimizar su tiempo de consulta, diferenciarse digitalmente y mejorar el seguimiento nutricional de sus pacientes mediante herramientas confiables.

\newpage

**Empathy Map – Mike Mentzer (Paciente joven con interés en mejorar su alimentación)**

![Empathy Mapping 2 – Mike Mentzer](src/img/cap2/empathy2.png){ width=75% }

La figura, expone los hábitos, frustraciones y aspiraciones de Mike, un usuario motivado por mejorar su físico y salud, que necesita guía clara, acompañamiento profesional y tecnología accesible para avanzar con seguridad en sus objetivos nutricionales.

\newpage

### As-is Scenario Mapping

Describe cómo es actualmente la experiencia de los usuarios sin una solución tecnológica centralizada. A través de sus rutinas diarias, se evidencian fricciones, ineficiencias y puntos críticos que limitan tanto el progreso del paciente como la calidad de atención del profesional. Estas limitaciones representan oportunidades clave para la intervención digital.

**As-Is Scenario – Frank Zane (Nutricionista clínico-deportivo)**

Frank gestiona sus consultas con herramientas básicas como Excel y WhatsApp, lo que le obliga a invertir tiempo valioso recolectando información dispersa. Al depender de datos incompletos de sus pacientes, no puede personalizar de forma efectiva los planes de alimentación ni medir el progreso con objetividad. Esta falta de trazabilidad diaria y seguimiento confiable afecta la adherencia del paciente y complica la evaluación de resultados. Además, le impide posicionarse como un profesional moderno e innovador en su campo.

![As-is Scenario Mapping – Frank Zane](src/img/cap2/asis1.jpg)

\newpage

**As-Is Scenario – Mike Mentzer (Paciente joven-adulto)**

Mike enfrenta una experiencia fragmentada y poco eficiente en su camino hacia una mejor alimentación y rendimiento físico. Registra sus comidas con fotos desordenadas, sigue rutinas de influencers sin supervisión profesional y recopila información de forma manual o incompleta. Al momento de asistir a una consulta, no cuenta con datos precisos ni organizados para evaluar su progreso. Esto le genera frustración, dudas sobre su avance real y desmotivación por no ver resultados claros.

![As-is Scenario Mapping – Mike Mentzer](src/img/cap2/asis2.jpg)

\newpage

### Ubiquitous Language

* **Paciente**: Persona que busca mejorar su alimentación o rendimiento físico. Puede estar en consulta ambulatoria, deportiva o en hospitalización. (Sinónimos: Usuario, Cliente)

* **Nutricionista**: Profesional de la salud que diseña, ajusta y monitorea planes alimentarios, con base en datos clínicos, antropométricos y de consumo. (Sinónimos: Profesional de nutrición, Especialista)

* **Consulta Nutricional**: Interacción entre Nutricionista y Paciente en la cual se evalúa el estado actual, se registran datos y se definen estrategias dietéticas.

* **Cardex Nutricional**: Formato clínico manual utilizado tradicionalmente para registrar la evolución diaria del paciente, sus comidas y anotaciones sobre tolerancia o consumo. (Usado en hospitales)

* **SGSS** (*Sistema de Gestión de Servicios de Salud*): Plataforma institucional usada para documentar diagnósticos, evolución y acciones nutricionales en hospitales del sector público. Puede tener limitaciones en velocidad o usabilidad.

* **Evaluación Antropométrica**: Conjunto de mediciones como peso, talla, pliegues cutáneos y perímetros corporales. Se utilizan para evaluar el estado nutricional.

* **Análisis Bioquímico**: Pruebas de laboratorio utilizadas como soporte diagnóstico (glucosa, colesterol, hemoglobina, etc.)

* **Registro Fotográfico**: Funcionalidad que permite al paciente subir imágenes de sus comidas. Puede ser procesado automáticamente por IA para estimar calorías y macros.

* **Macronutrientes (Macros)**: Nutrientes energéticos fundamentales: carbohidratos, proteínas y grasas. Se calculan en gramos y kilocalorías por día. (Sinónimos: Macros)

* **Tabla Nutricional Peruana**: Base de datos de referencia local con valores nutricionales de alimentos comunes en Perú. Fundamental para cálculos contextualizados.

* **Plan Nutricional**: Estrategia alimentaria personalizada que incluye porciones, horarios, alimentos sugeridos y objetivos metabólicos.

* **Adherencia Nutricional**: Grado en que el paciente sigue el plan alimentario propuesto. Puede medirse por registros, fotos, peso y otros indicadores.

* **Dashboard Clínico**: Panel web para Nutricionistas que permite visualizar progresos, comparar datos, generar reportes y ajustar planes. (Sinónimos: Plataforma del profesional)

* **App Foodlytics (Paciente)**: Aplicación móvil donde el usuario registra comidas, consulta metas, visualiza avances y recibe recordatorios.

* **Recordatorio Nutricional**: Alerta o mensaje enviado por la app para fomentar la constancia (por ejemplo: registrar almuerzo, pesar alimentos, hidratarse).

* **Registro de Suplementos**: Módulo opcional donde el paciente puede anotar proteínas, creatina, multivitamínicos u otros productos consumidos.

* **Reporte de Consumo**: Documento visual generado automáticamente por el sistema, que resume el consumo calórico, proteico, cumplimiento y frecuencia.

* **Medidas Caseras**: Unidades no estandarizadas como “una taza”, “una cucharada” o “medio plato”, usadas por pacientes para estimar cantidades.

* **Reconocimiento de Alimentos**: Funcionalidad basada en IA que analiza fotos para identificar ingredientes, porciones y estimar calorías/macros automáticamente.

* **Seguimiento Nutricional**: Monitoreo continuo del progreso del paciente en función de metas, registros, cambios físicos y adherencia al plan.

* **Consulta Externa**: Modalidad ambulatoria donde los pacientes asisten regularmente al nutricionista para controles.

* **Paciente Hospitalizado**: Usuario en estado clínico más complejo que requiere registro diario y constante revisión por parte del equipo nutricional.

* **Perfil del Paciente**: Ficha digital que contiene información como antecedentes médicos, alergias, diagnósticos, objetivos y evolución.

* **Educación Alimentaria**: Funcionalidad o módulo que entrega al paciente explicaciones visuales, gráficas o interactivas sobre su dieta, metas o errores comunes.

* **Sistema Interoperable**: Capacidad de la plataforma para integrarse con otras bases clínicas o aplicativos existentes (SGSS, historiales electrónicos, etc.)

* **Privacidad de Datos**: Consideración ética y legal para proteger la información clínica y personal del paciente. Incluye consentimiento informado y cifrado de datos.

\newpage

# Capítulo III: Requirements Specification  

Este capítulo presenta la especificación detallada de los requisitos del sistema, la cual constituye la base para su diseño, implementación y evaluación. Su propósito es traducir las necesidades detectadas durante el proceso de investigación en características concretas que debe cumplir la solución tecnológica. Esta especificación actúa como un acuerdo claro entre el equipo de desarrollo y los stakeholders, garantizando que todas las funcionalidades estén alineadas con las expectativas del usuario final y con los objetivos del proyecto.

Los requisitos se derivaron de entrevistas, análisis de flujos actuales y observación contextual, y están organizados en dos categorías principales: requisitos funcionales, que describen los comportamientos y capacidades esperadas del sistema; y requisitos no funcionales, que definen criterios de calidad como usabilidad, rendimiento y seguridad.

Una especificación de requisitos centrada en el usuario es fundamental para lograr productos útiles, usables y deseables. Como destaca Benyon (2014), comprender las tareas, contextos y motivaciones de los usuarios permite diseñar soluciones que verdaderamente resuelven problemas reales y se integran naturalmente en sus rutinas

![Recurso extraído de Canva](src/img/cap3/requirements-specification-intro.png)

\newpage

## To-Be Scenario Mapping  

En esta sección se presenta el escenario futuro esperado (To-Be), una representación visual y narrativa de cómo se transformará la experiencia del usuario con la incorporación de la solución tecnológica propuesta. A partir del análisis de los escenarios actuales (As-Is) y las necesidades detectadas, se define un flujo mejorado que elimina las fricciones, automatiza tareas repetitivas y facilita la interacción entre pacientes y profesionales de la salud.

\vspace{1em}

**To-Be Scenario – Frank Zane (Nutricionista clínico-deportivo)**

Con la implementación de la app, Mike comienza su día tomando una foto de su desayuno, y la inteligencia artificial reconoce automáticamente los alimentos y estima las cantidades. Luego, registra su rutina de ejercicios, la cual es procesada por el sistema para estimar calorías quemadas. A lo largo del día, visualiza su progreso a través de gráficos, ajusta los registros si es necesario y mantiene un control activo de su balance calórico.

Al asistir a su consulta médica o nutricional, Mike ya no necesita recordar ni justificar su comportamiento alimentario con fotos dispersas o suposiciones. Puede compartir desde la app un historial completo y confiable, lo que refuerza su confianza y disciplina, y permite al profesional tomar decisiones más precisas.

![To-Be Scenario Mapping – Frank Zane](src/img/cap3/tobe1.jpg)

Este escenario evidencia una transformación en su relación con la alimentación y la salud: pasa de la incertidumbre y frustración, a la autonomía, control y motivación sostenida gracias al uso de una solución tecnológica centrada en el usuario.


\newpage

**To-Be Scenario – Mike Mentzer (Paciente joven-adulto)**

En la consulta, Frank accede desde el panel web al perfil de su paciente, donde encuentra registros diarios organizados automáticamente: consumo calórico, distribución de macronutrientes, peso, rutinas de ejercicio, y notas relevantes. Esta información, recolectada de forma continua por el paciente a través de la app, permite a Frank realizar un análisis detallado sin necesidad de recopilar manualmente datos dispersos.

Gracias a esta integración, puede ajustar recomendaciones desde el mismo sistema y enviarlas directamente al paciente, quien las recibe de forma clara en su aplicación móvil. Además, monitorea el cumplimiento en tiempo real y detecta desviaciones a tiempo, lo que permite intervenir proactivamente para mejorar la adherencia.

![To-Be Scenario Mapping – Mike Mentzer](src/img/cap3/tobe2.jpg)

El nuevo flujo no solo optimiza el tiempo de consulta, sino que fortalece la relación entre profesional y paciente, al basarse en datos objetivos, precisos y procesados automáticamente. Frank ya no depende de la memoria del paciente ni de herramientas improvisadas: ahora toma decisiones informadas y personaliza sus planes con mayor eficacia.

\newpage

## Requsitos Funcionales y No Funcionales

En el desarrollo de software, los requisitos funcionales y no funcionales son la base para definir lo que el sistema debe hacer y cómo debe comportarse.

Los requisitos funcionales (RF) describen los servicios, procesos o comportamientos específicos que el sistema debe realizar para satisfacer las necesidades de los usuarios. Es decir, responden al qué hace el sistema, por ejemplo: registro de usuarios, gestión de pacientes o generación de reportes.

En cambio, los requisitos no funcionales (RNF) establecen las propiedades de calidad que debe cumplir el sistema, tales como rendimiento, seguridad, usabilidad, escalabilidad o disponibilidad. En otras palabras, indican el cómo debe funcionar el sistema, garantizando que la experiencia del usuario y la operación técnica sean confiables y seguras.

En conjunto, ambos tipos de requisitos permiten reducir ambigüedades, alinear expectativas entre usuarios y desarrolladores, y sirven como base para el diseño, implementación y validación del software

\newpage

### Requisitos Funcionales

\begin{longtable}{|p{1.5cm}|p{14cm}|}
\hline
\textbf{ID} & \textbf{Requisito funcional} \\
\hline
\endfirsthead
\hline
\textbf{ID} & \textbf{Requisito funcional} \\
\hline
\endhead
\hline
\endfoot
\hline
\endlastfoot
\textbf{RF-01} & El \textbf{paciente} debe poder registrarse proporcionando nombres, apellidos, correo electrónico válido y contraseña, para crear su cuenta en la aplicación. \\
\hline
\textbf{RF-02} & El usuario (paciente o nutricionista) debe poder iniciar y cerrar sesión de forma segura mediante autenticación con credenciales, para proteger su información personal. \\
\hline
\textbf{RF-03} & El paciente debe poder editar su perfil con edad, peso, talla y objetivos de salud, para mantener sus datos actualizados. \\
\hline
\textbf{RF-04} & El paciente debe poder registrar comidas mediante fotografía con reconocimiento automático por IA, para acelerar el ingreso de alimentos. \\
\hline
\textbf{RF-05} & El paciente debe poder \textbf{corregir manualmente} alimentos o porciones detectadas por la IA, para asegurar precisión en el registro. \\
\hline
\textbf{RF-06} & El paciente debe poder visualizar un \textbf{resumen diario} de calorías y macronutrientes consumidos, para monitorear su ingesta. \\
\hline
\textbf{RF-07} & El paciente debe poder consultar un \textbf{historial semanal} de comidas y balance calórico, para identificar tendencias de consumo. \\
\hline
\textbf{RF-08} & El paciente debe poder registrar \textbf{actividad física manual} con tipo, duración e intensidad, para completar el cálculo de su gasto energético. \\
\hline
\textbf{RF-09} & El paciente debe poder registrar periódicamente su \textbf{peso corporal}, para hacer seguimiento de su progreso. \\
\hline
\textbf{RF-10} & El paciente debe poder visualizar el \textbf{cálculo automático del IMC} en base a su peso y talla, para conocer su clasificación nutricional. \\
\hline
\textbf{RF-12} & El nutricionista debe poder visualizar un \textbf{dashboard} con métricas semanales de cada paciente (calorías, macros, peso, actividad), para evaluar su evolución. \\
\hline
\textbf{RF-13} & El nutricionista debe poder \textbf{generar reportes históricos} descargables en PDF o CSV, para compartirlos o archivarlos como evidencia de progreso. \\
\hline
\textbf{RF-14} & El paciente debe poder recibir \textbf{notificaciones automáticas} para registrar comidas y hábitos, para mantener constancia diaria en el uso de la aplicación. \\
\hline
\textbf{RF-16} & El nutricionista debe poder \textbf{suscribirse a planes de pago} según la cantidad de pacientes gestionados (básico, intermedio, avanzado), para ajustar la plataforma a sus necesidades. \\
\hline
\textbf{RF-17} & El nutricionista debe poder \textbf{cancelar su suscripción} en cualquier momento desde la plataforma web, para evitar cobros adicionales. \\
\hline
\textbf{RF-18} & El sistema debe \textbf{permitir pagos en línea} a través de pasarelas seguras (tarjeta de crédito/débito, billeteras digitales, transferencias), para facilitar el acceso a los planes de nutricionista. \\
\hline
\textbf{RF-19} & La \textbf{Landing Page} debe mostrar la \textbf{propuesta de valor} y rutas por segmento (médico/paciente) de forma clara. \\
\hline
\textbf{RF-20} & La Landing Page debe permitir \textbf{ver/reproducir una demo} del producto. \\
\hline
\textbf{RF-21} & La Landing Page debe incluir \textbf{formulario de contacto} con validaciones y mecanismo anti-abuso (captcha). \\
\hline
\textbf{RF-22} & La Landing Page debe permitir \textbf{compartir en redes sociales} (deep links/metatags sociales). \\
\hline
\textbf{RF-23} & La plataforma debe publicar y permitir \textbf{acceso a Políticas y Privacidad vigentes}. \\
\hline
\textbf{RF-24} & La Landing Page debe \textbf{exponer metadatos SEO} (title, description, canonical) y estructura semántica para descubrimiento. \\
\hline
\textbf{RF-25} & El \textbf{nutricionista} debe poder \textbf{registrar su cuenta} con datos profesionales mínimos (nombre, correo, contraseña). \\
\hline
\textbf{RF-26} & El usuario debe poder \textbf{recuperar/restablecer} su contraseña mediante correo con token seguro. \\
\hline
\textbf{RF-27} & El nutricionista debe poder \textbf{crear pacientes nuevos}. \\
\hline
\textbf{RF-28} & El nutricionista debe poder \textbf{editar información} de pacientes. \\
\hline
\textbf{RF-29} & El nutricionista debe poder \textbf{desactivar/eliminar} pacientes (con resguardo de integridad histórica). \\
\hline
\textbf{RF-30} & El nutricionista debe poder \textbf{buscar y filtrar} pacientes por nombre o estado. \\
\hline
\textbf{RF-31} & El nutricionista debe poder \textbf{ver la dieta diaria} y alimentos del paciente. \\
\hline
\textbf{RF-32} & El nutricionista debe poder \textbf{ver macros/calorías} del paciente por día y semana. \\
\hline
\textbf{RF-33} & El nutricionista debe poder \textbf{ver actividades} y calorías gastadas del paciente. \\
\hline
\textbf{RF-38} & El nutricionista debe poder \textbf{ver el historial de pagos}. \\
\hline
\textbf{RF-39} & El nutricionista debe poder \textbf{ver el estado de su suscripción} y la \textbf{fecha del próximo cobro}. \\
\hline
\textbf{RF-40} & El paciente debe poder \textbf{registrar/sincronizar pasos diarios} desde el dispositivo o proveedor compatible. \\
\hline
\textbf{RF-41} & La app debe mostrar el \textbf{balance diario} (calorías consumidas vs gastadas). \\
\hline
\textbf{RF-42} & El sistema debe \textbf{gestionar consentimientos} por finalidad (crear/actualizar/revocar) y \textbf{registrar evidencias} de aceptación. \\
\hline
\end{longtable}

\newpage

### Requisitos No Funcionales

\begin{longtable}{|p{1.5cm}|p{9cm}|p{4.5cm}|}
\hline
\textbf{ID} & \textbf{Requisito no funcional} & \textbf{Atributo de calidad} \\
\hline
\endfirsthead
\hline
\textbf{ID} & \textbf{Requisito no funcional} & \textbf{Atributo de calidad} \\
\hline
\endhead
\hline
\endfoot
\hline
\endlastfoot
\textbf{RNF-01} & El sistema debe \textbf{soportar} hasta 1\,000 usuarios concurrentes activos y mantener latencia $< 300$ ms en operaciones críticas (login, registro de comidas, sincronización). & Rendimiento \\
\hline
\textbf{RNF-02} & Toda comunicación de datos entre cliente, servidor y dispositivos debe realizarse mediante \textbf{HTTPS con TLS 1.3}. & Seguridad \\
\hline
\textbf{RNF-03} & El sistema debe estar disponible al menos el \textbf{99.9\%} del tiempo durante el horario 6{:}00–23{:}00 (hora Perú). & Disponibilidad \\
\hline
\textbf{RNF-04} & La interfaz móvil y web debe cargar en \textbf{$< 2$ s} en conexiones 4G o superiores (LTE, 5G o WiFi equivalente). En 3G o inferior no se garantiza este tiempo. & Rendimiento \\
\hline
\textbf{RNF-05} & Registrar \textbf{métricas de eventos críticos} (errores 4xx/5xx, fallos de autenticación, tiempo de respuesta promedio, tasa de sincronización fallida) en logs estructurados, accesibles y auditables. & Observabilidad \\
\hline
\textbf{RNF-06} & El backend debe \textbf{escalar} para absorber $+100\%$ de usuarios en picos manteniendo latencia $< 500$ ms en operaciones críticas, mediante \textbf{escalado vertical u horizontal del monolito}, \textbf{cachés}, y \textbf{pooling} eficiente de recursos. & Escalabilidad \\
\hline
\textbf{RNF-07} & Datos sensibles \textbf{cifrados en reposo} con \textbf{AES-256}; acceso regido por \textbf{deny-by-default} y controles de autorización. & Seguridad \\
\hline
\textbf{RNF-08} & \textbf{Redundancia al fallo} (failover automático) con \textbf{RPO $\leq$ 15 min} y \textbf{RTO $\leq$ 1 hora}. & Confiabilidad/Disponibilidad \\
\hline
\textbf{RNF-09} & Interfaz \textbf{accesible} cumpliendo \textbf{WCAG 2.1 AA} (contraste, navegación por teclado, texto alternativo). & Usabilidad/Accesibilidad \\
\hline
\textbf{RNF-10} & Compatibilidad con navegadores modernos (Chrome, Firefox, Edge, Safari últimas 2 versiones) y dispositivos iOS/Android con versiones \textbf{no mayores a 3 años}. & Compatibilidad \\
\hline
\textbf{RNF-11} & Backend con \textbf{arquitectura de monolito modular} (módulos bien delimitados, dependencias explícitas, límites de dominio), \textbf{documentado}, con \textbf{cobertura de pruebas unitarias $\geq$ 80\%} y \textbf{tests de contrato} entre módulos. & Mantenibilidad \\
\hline
\textbf{RNF-12} & \textbf{Backups} automáticos de la base de datos al menos 1 vez al día, con \textbf{tasa de éxito 100\%}. & Confiabilidad \\
\hline
\textbf{RNF-13} & \textbf{RBAC}: control de acceso basado en roles; impedir acceso a recursos restringidos sin permisos. & Seguridad \\
\hline
\textbf{RNF-14} & \textbf{Integridad de datos}: asegurar \textbf{0\% de duplicados} en procesos de sincronización diaria. & Confiabilidad \\
\hline
\textbf{RNF-15} & Cumplimiento de \textbf{Ley de Protección de Datos Personales (Perú)} y \textbf{GDPR}; 100\% de datos personales con consentimiento informado. & Regulatorio/Seguridad \\
\hline
\textbf{RNF-16} & \textbf{Modo oscuro/claro} con \textbf{contraste mínimo 4.5{:}1} en ambos modos. & Usabilidad \\
\hline
\textbf{RNF-17} & \textbf{Pagos/PCI}: cumplimiento \textbf{PCI DSS}; no almacenar PAN/CVV; \textbf{tokenización} con la pasarela. & Seguridad/Regulatorio \\
\hline
\textbf{RNF-18} & \textbf{Rate limiting}: límites por IP/usuario/cliente OAuth; respuestas \textbf{429} con ventana deslizante y cabeceras de cuota. & Seguridad/Rendimiento \\
\hline
\textbf{RNF-19} & \textbf{Versionado de API}: \textbf{semver}, deprecaciones con preaviso $\geq 90$ días y \textbf{2 versiones} activas soportadas. & Mantenibilidad/Evolutividad \\
\hline
\textbf{RNF-20} & \textbf{i18n y tiempo}: \texttt{es-PE} por defecto; fechas en \textbf{RFC 3339/ISO{-}8601}. & Usabilidad/Compatibilidad \\
\hline
\textbf{RNF-22} & \textbf{Calidad IA}: precisión mínima Top{-}1 $\geq$ X\% en dataset validado; latencia p95 $\leq 1.5$ s por inferencia en dispositivo medio. & Rendimiento/Exactitud \\
\hline
\textbf{RNF-26} & Contratos de API generados automáticamente con \textbf{OpenAPI 3.1} y documentación interactiva en \texttt{/docs} y \texttt{/redoc}; \textbf{esquemas Pydantic} versionados por recurso. & Mantenibilidad \\
\hline
\textbf{RNF-27} & \textbf{Validación estricta} de entrada y salida con \textbf{Pydantic} (\textit{request} y \textit{response models}); respuestas 422 coherentes y mensajes de error estandarizados. & Correctitud/Usabilidad \\
\hline
\textbf{RNF-28} & \textbf{Seguridad OAuth 2.0} con \textbf{JWT Bearer}; \textbf{scopes} por recurso; contraseñas con \textbf{bcrypt}; rotación de claves y expiración configurable. & Seguridad \\
\hline
\textbf{RNF-29} & \textbf{CORS} restrictivo por \textbf{orígenes}, \textbf{métodos} y \textbf{headers} permitidos; denegar por defecto. & Seguridad \\
\hline
\textbf{RNF-30} & \textbf{Problem Details} RFC 9457 para errores; códigos y tipos de problema consistentes; correlación mediante \textbf{X-Request-ID}. & Fiabilidad/Observabilidad \\
\hline
\textbf{RNF-31} & \textbf{ASGI} con \textbf{Uvicorn} y \textbf{uvloop}; \textbf{workers} configurables (\texttt{gunicorn + uvicorn.workers.UvicornWorker}) y \textbf{keep-alive} optimizado. & Rendimiento \\
\hline
\textbf{RNF-32} & \textbf{Rate limiting} por IP y usuario; respuestas 429 con cabeceras de cuota; protección ante fuerza bruta en \texttt{/auth}. & Seguridad/Rendimiento \\
\hline
\textbf{RNF-33} & \textbf{Compresión} \texttt{GZip}/\texttt{Brotli} y \textbf{caché HTTP} donde aplique; \textbf{ETag} o \textbf{Last-Modified} para recursos idempotentes. & Rendimiento \\
\hline
\textbf{RNF-34} & \textbf{Conexión a BD} con \textbf{pooling} y \textbf{timeouts}; transacciones por solicitud; manejo seguro de sesiones en entorno asincrónico. & Rendimiento/Confiabilidad \\
\hline
\textbf{RNF-37} & \textbf{Versionado de API por ruta} (\texttt{/v1}) y \textbf{cabeceras de deprecación}; dos versiones activas simultáneas. & Evolutividad \\
\hline
\textbf{RNF-38} & \textbf{Paginación}, \textbf{orden} y \textbf{filtros} consistentes en listados; límites y desplazamiento con validación de rangos. & Usabilidad/Rendimiento \\
\hline
\textbf{RNF-39} & \textbf{Configuración 12-factor} con \textbf{Pydantic Settings}; secretos por variables de entorno y almacén seguro. & Mantenibilidad/Seguridad \\
\hline
\textbf{RNF-41} & \textbf{Health checks} \texttt{/health} y \texttt{/ready}; verificación de dependencias críticas (BD, caché, colas). & Operabilidad \\
\hline
\textbf{RNF-42} & \textbf{Migraciones} controladas (p.ej. Alembic) con \textbf{rollbacks} y \textbf{semillas} por entorno. & Mantenibilidad \\
\hline
\textbf{RNF-43} & \textbf{Pruebas} con \texttt{pytest} y \texttt{httpx}; \textbf{pytest-asyncio} para rutas \texttt{async}; \textbf{cobertura $\geq$ 80\%}. & Calidad \\
\hline
\textbf{RNF-44} & \textbf{Seguridad de cabeceras} HTTP: \texttt{X-Content-Type-Options}, \texttt{X-Frame-Options}, \texttt{Referrer-Policy}, \texttt{Content-Security-Policy} adecuada al contexto. & Seguridad \\
\hline
\end{longtable}

\newpage

## User Stories 

En esta sección se operacionalizan los requisitos de *Foodlytics* en *User Stories* organizadas por épicas y canales (Landing Page, Web Application, Mobile Application) más un bloque técnico de plataforma. Cada historia sigue el formato \emph{Como–Quiero–Para} y se acompaña de criterios de aceptación en estilo \emph{Given–When–Then}, lo que permite verificación objetiva, estimación y planificación de sprints. La codificación (LP/WEB/MOB/T) preserva la trazabilidad con los requisitos funcionales y no funcionales definidos para la solución. De forma transversal, las historias consideran seguridad y privacidad (consentimiento, cifrado, auditoría), accesibilidad y rendimiento; además, reflejan capacidades clave del producto (registro de ingestas con IA, cálculo de macros/IMC, reportes y alertas) coherentes con la arquitectura objetivo (monolito modular) y la hoja de ruta. Esta estructura facilita priorización, cobertura de casos y evidencia de cumplimiento para la evaluación académica.

**Epics**

\begin{longtable}{|m{5cm}|m{10cm}|}
\hline
\textbf{LP-EP01 (Presentación y propuesta de valor)} &
\textbf{Como} visitante, \textbf{quiero} comprender qué problema resuelve la aplicación y cómo me beneficia, \textbf{para} decidir si me interesa continuar explorando. \\
\hline
LP-US01 & Visualización de propuesta de valor clara \\ \hline
LP-US02 & Identificación de segmento médico \\ \hline
LP-US03 & Identificación de segmento paciente \\ \hline
LP-US04 & Evidencia y testimonios de usuarios \\ \hline
LP-US05 & Ruta de producto \\ \hline

\textbf{LP-EP02 (Conversión e interacción inicial)} &
\textbf{Como} visitante interesado, \textbf{quiero} tener formas claras de contacto o demostración, \textbf{para} iniciar relación con el producto o el equipo. \\
\hline
LP-US06 & Acción principal de conversión \\ \hline
LP-US07 & Captura de interés del médico \\ \hline
LP-US08 & Captura de interés del paciente \\ \hline
LP-US09 & Información de contacto verificada \\ \hline
LP-US10 & Ver demo del producto \\ \hline
LP-US11 & Compartir en redes sociales \\ \hline

\textbf{LP-EP03 (Confianza y soporte informativo)} &
\textbf{Como} visitante, \textbf{quiero} acceder a información confiable y soporte básico, \textbf{para} sentir seguridad y claridad antes de usar la solución. \\
\hline
LP-US12 & Acceso a políticas y privacidad vigentes \\ \hline
LP-US13 & Soporte multiplataforma y rendimiento en dispositivos \\ \hline
LP-US14 & Preguntas frecuentes \\ \hline
LP-US15 & Descubrimiento por buscadores \\ \hline

\textbf{WEB-EP01 (Gestión de cuenta y autenticación)} &
\textbf{Como} nutricionista, \textbf{quiero} acceder de forma segura a la aplicación web, \textbf{para} proteger mi información y la de mis pacientes. \\
\hline
WEB-US01 & Registro de cuenta de nutricionista \\ \hline
WEB-US03 & Inicio de sesión \\ \hline
WEB-US04 & Cierre de sesión \\ \hline
WEB-US05 & Recuperación de contraseña \\ \hline
WEB-US06 & Gestión de perfil \\ \hline

\textbf{WEB-EP02 (Gestión de pacientes)} &
\textbf{Como} nutricionista, \textbf{quiero} registrar y administrar a mis pacientes, \textbf{para} poder darles seguimiento personalizado. \\
\hline
WEB-US07 & Registro de pacientes nuevos \\ \hline
WEB-US08 & Edición de información de pacientes \\ \hline
WEB-US09 & Eliminación o desactivación de pacientes \\ \hline
WEB-US10 & Búsqueda y filtrado de pacientes por nombre o estado \\ \hline

\textbf{WEB-EP03 (Visualización de dieta diaria)} &
\textbf{Como} nutricionista, \textbf{quiero} visualizar la dieta diaria de mis pacientes, \textbf{para} evaluar su consumo calórico y nutricional. \\
\hline
WEB-US11 & Visualización de alimentos consumidos en el día \\ \hline
WEB-US12 & Visualización de macros y calorías aproximadas \\ \hline
WEB-US13 & Historial diario de calorías consumidas y gastadas, con resumen semanal \\ \hline

\textbf{WEB-EP04 (Seguimiento de actividad física)} &
\textbf{Como} nutricionista, \textbf{quiero} revisar la actividad física de mis pacientes, \textbf{para} complementar el análisis de la dieta. \\
\hline
WEB-US14 & Visualización de rutinas de ejercicio registradas \\ \hline
WEB-US15 & Visualización de calorías gastadas \\ \hline

\textbf{WEB-EP05 (Asignación de rutinas y dietas)} &
\textbf{Como} nutricionista, \textbf{quiero} asignar rutinas y planes nutricionales, \textbf{para} guiar a mis pacientes en su progreso. \\
\hline
WEB-US16 & Creación de rutinas personalizadas \\ \hline
WEB-US17 & Asignación de metas de calorías y macros \\ \hline
WEB-US18 & Registro de recomendaciones específicas \\ \hline

\textbf{WEB-EP06 (Reportes y métricas)} &
\textbf{Como} nutricionista, \textbf{quiero} acceder a reportes históricos de mis pacientes, \textbf{para} evaluar progreso y ajustar planes. \\
\hline
WEB-US19 & Reporte de evolución de peso \\ \hline
WEB-US20 & Dashboard de progreso con gráficas \\ \hline
WEB-US21 & Generación de reportes descargables \\ \hline

\textbf{WEB-EP07 (Gestión de planes y pagos)} & 
\textbf{Como} nutricionista, \textbf{quiero} gestionar mi suscripción a planes de la plataforma, \textbf{para} acceder a funcionalidades avanzadas según la cantidad de pacientes que administro. \\
\hline
WEB-US22 & Selección de plan de suscripción según cantidad de pacientes \\
\hline
WEB-US23 & Pago en línea con métodos disponibles (tarjeta, billetera digital, etc.) \\
\hline
WEB-US24 & Cancelación de suscripción en cualquier momento \\
\hline
WEB-US25 & Visualización del historial de pagos \\
\hline
WEB-US26 & Ver la \textit{fecha del próximo cobro} y el estado actual de la suscripción \\
\hline

\textbf{MOB-EP01 (Gestión de cuenta y autenticación)} &
\textbf{Como} paciente, \textbf{quiero} acceder de forma segura a la app y administrar mi perfil, \textbf{para} proteger mi información y usar la aplicación con mis datos correctos. \\
\hline
MOB-US01 & Registro de usuario nuevo \\ \hline
MOB-US02 & Inicio de sesión \\ \hline
MOB-US03 & Cierre de sesión \\ \hline
MOB-US04 & Recuperación de contraseña \\ \hline
MOB-US05 & Gestión de perfil del paciente \\ \hline

\textbf{MOB-EP02 (Pantalla inicial y resumen)} &
\textbf{Como} paciente, \textbf{quiero} ver al iniciar un resumen de calorías, macros e IMC, \textbf{para} entender mi estado diario y tomar decisiones rápidas. \\
\hline
MOB-US06 & Resumen diario de calorías y macros al iniciar \\ \hline
MOB-US07 & Cálculo y visualización de IMC \\ \hline
MOB-US08 & Historial diario con resumen semanal \\ \hline

\textbf{MOB-EP03 (Registro de comidas con IA)} &
\textbf{Como} paciente, \textbf{quiero} registrar mis comidas con foto y correcciones manuales, \textbf{para} llevar un control preciso de lo que consumo y mis macros. \\
\hline
MOB-US09 & Registrar comida mediante foto con reconocimiento \\ \hline
MOB-US10 & Modificar alimentos o cantidades detectadas \\ \hline
MOB-US11 & Visualización de macros y calorías por comida registrada \\ \hline

\textbf{MOB-EP04 (Actividad física y balance)} &
\textbf{Como} paciente, \textbf{quiero} registrar mi actividad física y sincronizar pasos, \textbf{para} conocer calorías gastadas y mi balance diario con lo que como. \\
\hline
MOB-US12 & Registro de actividad física manual \\ \hline
MOB-US13 & Balance diario calorías consumidas vs gastadas \\ \hline
MOB-US14 & Registro de pasos y estimación de calorías quemadas diarios \\ \hline

\textbf{MOB-EP05 (Seguimiento de peso y objetivos)} &
\textbf{Como} paciente, \textbf{quiero} registrar mi peso y ver mi evolución, \textbf{para} ajustar mis metas y confirmar si mi plan funciona. \\
\hline
MOB-US15 & Registro y gráfico de peso \\ \hline
MOB-US16 & Ajuste de metas diarias según progreso \\ \hline
MOB-US17 & Visualización semanal de cumplimiento \\ \hline

\textbf{MOB-EP06 (Alertas y hábitos)} &
\textbf{Como} paciente, \textbf{quiero} recibir recordatorios y consejos útiles, \textbf{para} mantener constancia al registrar comidas, peso y cumplir mis metas diarias. \\
\hline
MOB-US18 & Notificaciones para registrar comidas \\ \hline
MOB-US19 & Alerta por exceso o déficit respecto a meta diaria \\ \hline
MOB-US20 & Notificaciones de consejos personalizados de nutrición y entrenamiento \\ \hline

\textbf{T-EP01 (Autenticación y gestión de cuenta técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints de autenticación y gestión de perfil, \textbf{para} asegurar que usuarios accedan de forma segura y puedan administrar sus datos correctamente. \\
\hline
TUS-01 & Registro seguro de usuario \\ \hline
TUS-02 & Inicio de sesión para usuario registrado \\ \hline
TUS-03 & Cierre de sesión seguro \\ \hline
TUS-04 & Recuperación de contraseña olvidada \\ \hline
TUS-05 & Actualización de perfil de usuario \\ \hline

\textbf{T-EP02 (Gestión de pacientes técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints CRUD para pacientes, \textbf{para} que los nutricionistas gestionen la información de sus pacientes de forma completa. \\
\hline
TUS-06 & Crear paciente nuevo \\ \hline
TUS-07 & Obtener datos de un paciente \\ \hline
TUS-08 & Actualizar datos del paciente \\ \hline
TUS-09 & Desactivar paciente o marcar como inactivo \\ \hline

\textbf{T-EP03 (Comidas y macros técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints que permitan registrar, editar y consultar comidas con cálculos de calorías y macros, \textbf{para} respaldar el seguimiento nutricional del usuario. \\
\hline
TUS-10 & Registrar registro de comida \\ \hline
TUS-11 & Corregir registro de comida existente \\ \hline
TUS-12 & Consultar consumo diario de comidas \\ \hline

\textbf{T-EP04 (Actividad física y pasos técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints que permitan registrar actividad física y pasos diarios y calcular calorías quemadas, \textbf{para} proporcionar balance energético al paciente. \\
\hline
TUS-13 & Registrar actividad física manual \\ \hline
TUS-14 & Registrar conteo de pasos diarios \\ \hline
TUS-15 & Consultar resumen diario de pasos y calorías quemadas \\ \hline

\textbf{T-EP05 (Peso, IMC y objetivos técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints para registrar peso, calcular IMC y gestionar metas nutricionales, \textbf{para} que los usuarios puedan monitorear su progreso y ajustar objetivos. \\
\hline
TUS-16 & Registrar peso del usuario \\ \hline
TUS-17 & Calcular y consultar IMC actual \\ \hline
TUS-18 & Gestionar metas de calorías y macros \\ \hline

\textbf{T-EP06 (Notificaciones y alertas técnica)} &
\textbf{Como} Developer, \textbf{quiero} endpoints que gestionen recordatorios y alertas automáticas, \textbf{para} mantener al usuario motivado y notificar desviaciones de sus metas. \\
\hline
TUS-19 & Programar recordatorios para comidas o peso \\ \hline
TUS-20 & Detectar exceso o déficit respecto a metas y generar alerta \\ \hline

\textbf{T-EP07 (Seguridad, contratos y observabilidad técnica)} &
\textbf{Como} Developer, \textbf{quiero} estandarizar contrato de API, manejo de errores, controles de seguridad y telemetría, \textbf{para} tener una plataforma confiable, medible y fácil de mantener. \\
\hline
TUS-21 & Publicación del contrato OpenAPI 3.1 \\ \hline
TUS-22 & Manejo de errores con Problem Details RFC 9457 \\ \hline
TUS-23 & Controles de autorización por recurso y propiedad \\ \hline
TUS-24 & Paginación y orden en listados de API \\ \hline
TUS-25 & Versionado estable de API \\ \hline
TUS-26 & Observabilidad con métricas, trazas y logs \\ \hline
TUS-27 & Auditoría y trazabilidad de cambios \\ \hline

\textbf{T-EP08 (Reconocimiento de alimentos por IA técnica)} &
\textbf{Como} Developer, \textbf{quiero} implementar servicio de reconocimiento de alimentos desde imágenes que estime cantidades y permita correcciones del usuario, \textbf{para} que la app móvil identifique alimentos automáticamente. \\
\hline
TUS-28 & Reconocer alimentos desde imagen subida \\ \hline
TUS-29 & Estimar cantidad de alimento detectado \\ \hline
TUS-30 & Devolver puntuaciones de confianza por alimento identificado \\ \hline
TUS-31 & Permitir al usuario corregir alimentos o cantidades mal detectadas \\ \hline
TUS-32 & Publicar catálogo mínimo de categorías de alimentos y porciones soportadas \\ \hline

\textbf{T-EP09 (Privacidad y consentimiento técnica)} &
\textbf{Como} Developer, \textbf{quiero} mecanismos de consentimiento y protección de datos, \textbf{para} usar información personal e imágenes de forma segura. \\
\hline
TUS-33 & Gestión de consentimientos por finalidad de uso \\ \hline
TUS-34 & Cifrado en tránsito y en reposo para imágenes y datos \\ \hline
TUS-35 & Limpieza de metadatos en imágenes \\ \hline
TUS-36 & Registro de uso de datos para cumplimiento y auditoría \\ \hline

\textbf{T-EP10 (Sincronización diaria en lote)} &
\textbf{Como} Developer, \textbf{quiero} sincronizar en un solo envío al final del día los datos registrados localmente, con reintentos seguros y manejo correcto de zona horaria, \textbf{para} reducir consumo de red, evitar duplicados y asegurar consistencia. \\
\hline
TUS-37 & Indicadores de estado de sincronización en cliente \\ \hline
TUS-38 & Cola local de cambios del día \\ \hline
TUS-39 & Cierre de jornada y sello de corte del día \\ \hline
TUS-40 & Envío en lote de registros del día \\ \hline
TUS-41 & Reintentos con backoff exponencial hasta confirmar recepción \\ \hline
TUS-42 & Idempotencia con claves únicas por lote \\ \hline
TUS-43 & Confirmación del backend y marcado local como enviado \\ \hline
TUS-44 & Detección y descarte de duplicados en servidor \\ \hline
TUS-45 & Timestamps en RFC 3339 y manejo de zona horaria \\ \hline
TUS-46 & Reprogramación de envío si falla el lote final \\ \hline
TUS-47 & Estado de sincronización visible para el usuario \\ \hline
TUS-48 & Parámetro de hora de corte configurable por zona \\ \hline

\textbf{T-EP12 (Integración de pagos/Suscripciones Culqi)} & 
\textbf{Como} developer, \textbf{quiero} integrar la suscripción con Culqi, webhooks y verificación del estado, \textbf{para} manejar pagos, facturación y suscripciones de nutricionistas de forma segura. \\
\hline
TUS-49 & Crear endpoint para iniciar suscripción en Culqi con plan seleccionado \\
\hline
TUS-50 & Verificar transacción / callback de Culqi para confirmar pago \\
\hline
TUS-51 & Registrar estado de suscripción del nutricionista en base al pago (activo, vencido, cancelado) \\
\hline
TUS-52 & Servicio para que el nutricionista vea fecha del próximo cobro y estado actual \\
\hline
\end{longtable}

\newpage

### *Landing Page US*

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

LP-US01 & Visualización de propuesta de valor clara &
\textbf{Como} visitante, \textbf{quiero} visualizar claramente la propuesta de valor de la aplicación, \textbf{para} comprender el problema que resuelve y cómo me beneficia. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Comprensión al primer acceso}\\
\textbf{Dado que} el visitante accede a la landing page\\
\textbf{cuando} se carga la sección principal\\
\textbf{entonces} comprende el propósito y beneficios del producto sin ambigüedad.\\[0.2em]

\textbf{Escenario 2: Mensaje complementario}\\
\textbf{Dado que} el visitante no identifica la propuesta de valor\\
\textbf{cuando} revisa el contenido expandido\\
\textbf{entonces} obtiene un mensaje aclaratorio con el problema y el beneficio clave.\\[0.2em]

\textbf{Escenario 3: Consistencia entre dispositivos}\\
\textbf{Dado que} el visitante usa móvil o escritorio\\
\textbf{cuando} visualiza la propuesta de valor\\
\textbf{entonces} el mensaje se mantiene claro y equivalente en ambos contextos.
\end{tabular}
& LP-EP01\\
\hline

LP-US02 & Identificación de segmento médico &
\textbf{Como} visitante del segmento médico, \textbf{quiero} identificar contenido dirigido a mi rol, \textbf{para} entender cómo la solución facilita mi práctica profesional. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Contenido segmentado}\\
\textbf{Dado que} el visitante pertenece al segmento médico\\
\textbf{cuando} accede a la landing page\\
\textbf{entonces} encuentra una sección con beneficios y casos de uso para profesionales.\\[0.2em]

\textbf{Escenario 2: Ampliación de información}\\
\textbf{Dado que} el visitante médico necesita más detalle\\
\textbf{cuando} solicita información extendida\\
\textbf{entonces} el sistema le ofrece un recurso con capacidades y ejemplos clínicos.\\[0.2em]

\textbf{Escenario 3: Diferenciación de perfiles}\\
\textbf{Dado que} existen varios segmentos\\
\textbf{cuando} se muestran las opciones de perfil\\
\textbf{entonces} el contenido médico se diferencia claramente del contenido para pacientes.
\end{tabular}
& LP-EP01\\
\hline

LP-US03 & Identificación de segmento paciente &
\textbf{Como} visitante paciente, \textbf{quiero} identificar rápidamente el contenido pensado para mí, \textbf{para} saber cómo me ayuda a mejorar mi nutrición y hábitos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Beneficios para pacientes}\\
\textbf{Dado que} el visitante es paciente\\
\textbf{cuando} accede a la sección correspondiente\\
\textbf{entonces} visualiza beneficios y resultados esperados para su contexto.\\[0.2em]

\textbf{Escenario 2: Expectativas y privacidad}\\
\textbf{Dado que} el visitante necesita claridad sobre datos\\
\textbf{cuando} revisa la información del segmento paciente\\
\textbf{entonces} entiende qué datos se usan y con qué finalidad.\\[0.2em]

\textbf{Escenario 3: Próximo paso claro}\\
\textbf{Dado que} el visitante está interesado\\
\textbf{cuando} busca cómo avanzar\\
\textbf{entonces} identifica el siguiente paso para informarse o dejar su interés.
\end{tabular}
& LP-EP01\\
\hline

LP-US04 & Evidencia y testimonios de usuarios &
\textbf{Como} visitante, \textbf{quiero} revisar evidencia y testimonios verificados, \textbf{para} ganar confianza en la efectividad del producto. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Testimonios disponibles}\\
\textbf{Dado que} el visitante explora la sección de evidencia\\
\textbf{cuando} consulta testimonios\\
\textbf{entonces} encuentra citas atribuidas y resultados reportados.\\[0.2em]

\textbf{Escenario 2: Control de calidad}\\
\textbf{Dado que} un testimonio no cumple criterios de publicación\\
\textbf{cuando} el sistema lo valida\\
\textbf{entonces} el testimonio no se muestra hasta ser corregido.\\[0.2em]

\textbf{Escenario 3: Evidencia cuantitativa}\\
\textbf{Dado que} el visitante busca datos objetivos\\
\textbf{cuando} revisa la evidencia\\
\textbf{entonces} identifica métricas o resultados agregados disponibles.
\end{tabular}
& LP-EP01\\
\hline

LP-US05 & Ruta de producto &
\textbf{Como} visitante, \textbf{quiero} conocer el estado actual y la evolución del producto, \textbf{para} entender qué recibo hoy y qué mejoras vienen. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Estado y próximas etapas}\\
\textbf{Dado que} el visitante consulta la ruta de producto\\
\textbf{cuando} revisa las capacidades actuales y futuras\\
\textbf{entonces} comprende qué está disponible y qué se planea liberar.\\[0.2em]

\textbf{Escenario 2: Solicitud de información}\\
\textbf{Dado que} el visitante tiene dudas sobre la ruta\\
\textbf{cuando} requiere más detalle\\
\textbf{entonces} obtiene un medio de contacto para profundizar.\\[0.2em]

\textbf{Escenario 3: Actualizaciones trazables}\\
\textbf{Dado que} existen cambios en la hoja de ruta\\
\textbf{cuando} el contenido se actualiza\\
\textbf{entonces} se muestra fecha de última actualización para trazabilidad.
\end{tabular}
& LP-EP01\\
\hline

LP-US06 & Acción principal de conversión &
\textbf{Como} visitante interesado, \textbf{quiero} iniciar una acción clara de contacto o demo, \textbf{para} comenzar la relación con el equipo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Conversión exitosa}\\
\textbf{Dado que} el visitante decide iniciar contacto\\
\textbf{cuando} completa los datos mínimos requeridos\\
\textbf{entonces} el sistema registra el interés y confirma la recepción.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} el visitante intenta convertir\\
\textbf{cuando} omite un dato obligatorio\\
\textbf{entonces} el sistema informa qué dato falta para completar el proceso.\\[0.2em]

\textbf{Escenario 3: Prevención de duplicados}\\
\textbf{Dado que} el visitante reintenta la conversión en un corto lapso\\
\textbf{cuando} los datos coinciden con un registro reciente\\
\textbf{entonces} el sistema evita duplicidad y confirma el registro previo.
\end{tabular}
& LP-EP02\\
\hline

LP-US07 & Captura de interés del médico &
\textbf{Como} visitante del segmento médico, \textbf{quiero} dejar mis datos profesionales, \textbf{para} ser contactado con información adecuada a mi práctica. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro de interés}\\
\textbf{Dado que} el visitante médico decide dejar su interés\\
\textbf{cuando} entrega sus datos profesionales mínimos\\
\textbf{entonces} el sistema registra el interés con etiqueta de segmento.\\[0.2em]

\textbf{Escenario 2: Consentimiento}\\
\textbf{Dado que} el visitante proporciona datos de contacto\\
\textbf{cuando} acepta el uso para fines informativos\\
\textbf{entonces} el sistema almacena la evidencia de consentimiento.\\[0.2em]

\textbf{Escenario 3: Confirmación}\\
\textbf{Dado que} el interés se registra\\
\textbf{cuando} el sistema envía confirmación al correo indicado\\
\textbf{entonces} el visitante recibe confirmación del registro.
\end{tabular}
& LP-EP02\\
\hline

LP-US08 & Captura de interés del paciente &
\textbf{Como} visitante paciente, \textbf{quiero} dejar mis datos de contacto, \textbf{para} recibir orientación inicial sobre el producto. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el visitante paciente desea información\\
\textbf{cuando} entrega los datos mínimos solicitados\\
\textbf{entonces} el sistema registra el interés con etiqueta de segmento.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el visitante ingresa datos con formato incorrecto\\
\textbf{cuando} intenta registrar su interés\\
\textbf{entonces} el sistema informa el dato inválido y solicita corrección.\\[0.2em]

\textbf{Escenario 3: Confirmación de registro}\\
\textbf{Dado que} el contacto queda registrado\\
\textbf{cuando} el sistema confirma la recepción\\
\textbf{entonces} el visitante conoce el siguiente paso esperado.
\end{tabular}
& LP-EP02\\
\hline

LP-US09 & Información de contacto verificada &
\textbf{Como} visitante, \textbf{quiero} verificar mi correo (y opcionalmente teléfono), \textbf{para} asegurar que la comunicación posterior sea efectiva. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Verificación de correo}\\
\textbf{Dado que} el visitante registró su interés\\
\textbf{cuando} usa el enlace de verificación recibido\\
\textbf{entonces} su contacto queda verificado.\\[0.2em]

\textbf{Escenario 2: Enlace inválido o vencido}\\
\textbf{Dado que} el visitante intenta verificar con un enlace no válido\\
\textbf{cuando} el sistema procesa el token\\
\textbf{entonces} informa la invalidez y permite solicitar otro.\\[0.2em]

\textbf{Escenario 3: Verificación telefónica opcional}\\
\textbf{Dado que} el visitante proporciona número telefónico\\
\textbf{cuando} ingresa el código de verificación\\
\textbf{entonces} el sistema marca el número como verificado.
\end{tabular}
& LP-EP02\\
\hline

LP-US10 & Ver demo del producto &
\textbf{Como} visitante, \textbf{quiero} acceder a una demostración del producto, \textbf{para} entender su funcionamiento antes de evaluar una compra. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso a la demo}\\
\textbf{Dado que} el visitante solicita ver la demo\\
\textbf{cuando} la demostración está disponible\\
\textbf{entonces} puede visualizarla sin interrupciones.\\[0.2em]

\textbf{Escenario 2: Registro de interés post-demo}\\
\textbf{Dado que} el visitante finaliza la demo\\
\textbf{cuando} desea saber más\\
\textbf{entonces} el sistema le permite registrar su interés para seguimiento.\\[0.2em]

\textbf{Escenario 3: Accesibilidad de la demo}\\
\textbf{Dado que} el visitante usa distintos dispositivos\\
\textbf{cuando} accede a la demostración\\
\textbf{entonces} puede visualizarla correctamente en móvil y escritorio.
\end{tabular}
& LP-EP02\\
\hline

LP-US11 & Compartir en redes sociales &
\textbf{Como} visitante, \textbf{quiero} compartir la landing page, \textbf{para} difundir el producto con otros interesados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Enlace compartible}\\
\textbf{Dado que} el visitante decide compartir\\
\textbf{cuando} obtiene el enlace de la página\\
\textbf{entonces} el enlace funciona y conserva título y descripción del producto.\\[0.2em]

\textbf{Escenario 2: Compatibilidad básica}\\
\textbf{Dado que} el visitante comparte en redes comunes\\
\textbf{cuando} publica el enlace\\
\textbf{entonces} la vista previa contiene nombre y resumen del producto.\\[0.2em]

\textbf{Escenario 3: Trazabilidad de campaña}\\
\textbf{Dado que} se usan parámetros de campaña\\
\textbf{cuando} el enlace compartido es visitado\\
\textbf{entonces} el acceso queda etiquetado para análisis de origen.
\end{tabular}
& LP-EP02\\
\hline

LP-US12 & Acceso a políticas y privacidad vigentes &
\textbf{Como} visitante, \textbf{quiero} acceder a políticas y privacidad actualizadas, \textbf{para} conocer el uso de mis datos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta de políticas}\\
\textbf{Dado que} el visitante desea informarse\\
\textbf{cuando} accede a políticas y privacidad\\
\textbf{entonces} puede leer contenido vigente y comprensible.\\[0.2em]

\textbf{Escenario 2: Evidencia de aceptación}\\
\textbf{Dado que} el visitante entrega datos de contacto\\
\textbf{cuando} acepta el tratamiento para fines informativos\\
\textbf{entonces} el sistema registra la aceptación con marca temporal.\\[0.2em]

\textbf{Escenario 3: Trazabilidad de cambios}\\
\textbf{Dado que} las políticas se actualizan\\
\textbf{cuando} el visitante las consulta\\
\textbf{entonces} observa la fecha de última actualización.
\end{tabular}
& LP-EP03\\
\hline

LP-US13 & Soporte multiplataforma y rendimiento &
\textbf{Como} visitante, \textbf{quiero} que la landing funcione correctamente en navegadores y móviles actuales, \textbf{para} navegar sin fricciones. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Compatibilidad esencial}\\
\textbf{Dado que} el visitante utiliza navegadores modernos\\
\textbf{cuando} accede a la landing\\
\textbf{entonces} puede navegar sin errores críticos.\\[0.2em]

\textbf{Escenario 2: Desempeño aceptable}\\
\textbf{Dado que} la red es móvil 4G promedio\\
\textbf{cuando} el visitante carga la página\\
\textbf{entonces} el contenido principal responde en menos de 2 segundos.\\[0.2em]

\textbf{Escenario 3: Degradación controlada}\\
\textbf{Dado que} el dispositivo es de recursos limitados\\
\textbf{cuando} se carga la landing\\
\textbf{entonces} la experiencia se mantiene utilizable sin fallos.
\end{tabular}
& LP-EP03\\
\hline

LP-US14 & Preguntas frecuentes &
\textbf{Como} visitante, \textbf{quiero} consultar respuestas a dudas comunes, \textbf{para} resolver preguntas rápidamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta de FAQs}\\
\textbf{Dado que} el visitante tiene una duda\\
\textbf{cuando} consulta la sección de preguntas frecuentes\\
\textbf{entonces} encuentra respuestas organizadas por tema.\\[0.2em]

\textbf{Escenario 2: Búsqueda temática}\\
\textbf{Dado que} el visitante necesita una respuesta específica\\
\textbf{cuando} revisa la categoría relacionada\\
\textbf{entonces} localiza una respuesta acorde a su consulta.\\[0.2em]

\textbf{Escenario 3: Escalamiento}\\
\textbf{Dado que} la duda no se resuelve con las FAQs\\
\textbf{cuando} solicita apoyo\\
\textbf{entonces} el sistema ofrece un medio de contacto para asistencia.
\end{tabular}
& LP-EP03\\
\hline

LP-US15 & Descubrimiento por buscadores &
\textbf{Como} visitante que busca la marca, \textbf{quiero} encontrar la landing en buscadores, \textbf{para} acceder fácilmente al sitio. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Página indexable}\\
\textbf{Dado que} los buscadores rastrean el sitio\\
\textbf{cuando} analizan la landing\\
\textbf{entonces} la página es indexable y apta para descubrimiento.\\[0.2em]

\textbf{Escenario 2: Búsqueda por nombre de marca}\\
\textbf{Dado que} el visitante busca el nombre del producto\\
\textbf{cuando} revisa resultados\\
\textbf{entonces} encuentra una referencia a la landing page.\\[0.2em]

\textbf{Escenario 3: Metadatos coherentes}\\
\textbf{Dado que} la página es compartida o listada en buscadores\\
\textbf{cuando} se muestra su vista previa\\
\textbf{entonces} aparecen título y descripción coherentes con el producto.
\end{tabular}
& LP-EP03\\
\hline

\end{longtable}

\newpage

### *Web Application US*

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

WEB-US01 & Registro de cuenta de nutricionista & \textbf{Como} nutricionista, \textbf{quiero} registrar una cuenta en la plataforma proporcionando mis datos básicos y credenciales, \textbf{para} acceder de manera segura al sistema. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el nutricionista completa el formulario de registro con datos válidos\\
\textbf{cuando} envía el formulario\\
\textbf{entonces} el sistema crea la cuenta y envía un correo de confirmación.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} el nutricionista no completa todos los campos requeridos\\
\textbf{cuando} intenta registrar la cuenta\\
\textbf{entonces} el sistema muestra mensajes de error indicando los campos faltantes.\\[0.2em]

\textbf{Escenario 3: Correo ya registrado}\\
\textbf{Dado que} el nutricionista ingresa un correo ya existente\\
\textbf{cuando} envía el formulario de registro\\
\textbf{entonces} el sistema muestra un mensaje de error indicando duplicidad.\\
\end{tabular} & WEB-EP01 \\
\hline

WEB-US03 & Inicio de sesión & \textbf{Como} nutricionista, \textbf{quiero} iniciar sesión en la plataforma con mi correo y contraseña, \textbf{para} acceder a mis pacientes y funcionalidades. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Inicio exitoso}\\
\textbf{Dado que} el nutricionista tiene una cuenta activa\\
\textbf{cuando} ingresa correo y contraseña válidos\\
\textbf{entonces} accede al dashboard principal.\\[0.2em]

\textbf{Escenario 2: Contraseña incorrecta}\\
\textbf{Dado que} el nutricionista ingresa un correo válido\\
\textbf{cuando} introduce una contraseña incorrecta\\
\textbf{entonces} el sistema muestra un mensaje de error.\\[0.2em]

\textbf{Escenario 3: Cuenta no confirmada}\\
\textbf{Dado que} el nutricionista no confirmó su correo institucional\\
\textbf{cuando} intenta iniciar sesión\\
\textbf{entonces} el sistema bloquea el acceso y solicita confirmación previa.\\
\end{tabular} & WEB-EP01 \\
\hline

WEB-US04 & Cierre de sesión & \textbf{Como} nutricionista, \textbf{quiero} cerrar sesión en cualquier momento, \textbf{para} proteger la seguridad de mi cuenta. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cierre exitoso}\\
\textbf{Dado que} el nutricionista está autenticado\\
\textbf{cuando} selecciona la opción de cerrar sesión\\
\textbf{entonces} el sistema finaliza la sesión y redirige a la pantalla de inicio.\\[0.2em]

\textbf{Escenario 2: Inactividad prolongada}\\
\textbf{Dado que} el nutricionista permanece inactivo un tiempo configurado\\
\textbf{cuando} se excede ese tiempo\\
\textbf{entonces} el sistema cierra automáticamente la sesión.\\[0.2em]

\textbf{Escenario 3: Intento de acción tras cierre}\\
\textbf{Dado que} la sesión ya fue cerrada\\
\textbf{cuando} el nutricionista intenta acceder a un recurso privado\\
\textbf{entonces} el sistema redirige a la pantalla de inicio de sesión.\\
\end{tabular} & WEB-EP01 \\
\hline

WEB-US05 & Recuperación de contraseña & \textbf{Como} nutricionista, \textbf{quiero} recuperar mi contraseña a través de un enlace seguro enviado a mi correo, \textbf{para} restablecer mi acceso a la plataforma. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Solicitud exitosa}\\
\textbf{Dado que} el nutricionista olvidó su contraseña\\
\textbf{cuando} solicita la recuperación e ingresa un correo válido\\
\textbf{entonces} el sistema envía un enlace seguro para restablecer la clave.\\[0.2em]

\textbf{Escenario 2: Correo inválido}\\
\textbf{Dado que} el nutricionista ingresa un correo inexistente\\
\textbf{cuando} solicita recuperación\\
\textbf{entonces} el sistema muestra un mensaje de error.\\[0.2em]

\textbf{Escenario 3: Enlace expirado}\\
\textbf{Dado que} el nutricionista recibe un enlace caducado\\
\textbf{cuando} intenta restablecer su contraseña\\
\textbf{entonces} el sistema indica que debe solicitar uno nuevo.\\
\end{tabular} & WEB-EP01 \\
\hline

WEB-US06 & Gestión de perfil & \textbf{Como} nutricionista, \textbf{quiero} actualizar mis datos de perfil como nombre, especialidad y contacto, \textbf{para} mantener mi información actualizada. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Actualización exitosa}\\
\textbf{Dado que} el nutricionista está autenticado\\
\textbf{cuando} edita sus datos de perfil con información válida\\
\textbf{entonces} el sistema guarda los cambios y los refleja inmediatamente.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el nutricionista ingresa datos inválidos (ejemplo: correo con formato incorrecto)\\
\textbf{cuando} intenta guardar\\
\textbf{entonces} el sistema muestra errores de validación.\\[0.2em]

\textbf{Escenario 3: Cancelación de cambios}\\
\textbf{Dado que} el nutricionista inició una edición\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no aplica los cambios y mantiene la información anterior.\\
\end{tabular} & WEB-EP01 \\
\hline

WEB-US07 & Registro de pacientes nuevos & \textbf{Como} nutricionista, \textbf{quiero} registrar pacientes con sus datos básicos, \textbf{para} darles seguimiento personalizado. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el nutricionista está autenticado\\
\textbf{cuando} completa el formulario de nuevo paciente con datos válidos\\
\textbf{entonces} el sistema guarda el paciente y lo lista en la base.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} el formulario está incompleto\\
\textbf{cuando} el nutricionista intenta guardar\\
\textbf{entonces} el sistema muestra mensajes de error.\\[0.2em]

\textbf{Escenario 3: Paciente duplicado}\\
\textbf{Dado que} se registra un paciente con DNI ya existente\\
\textbf{cuando} se envía el formulario\\
\textbf{entonces} el sistema alerta que el paciente ya existe.\\
\end{tabular} & WEB-EP02 \\
\hline

WEB-US08 & Edición de pacientes & \textbf{Como} nutricionista, \textbf{quiero} editar los datos de mis pacientes, \textbf{para} mantener la información actualizada. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Edición exitosa}\\
\textbf{Dado que} un paciente está registrado\\
\textbf{cuando} el nutricionista modifica sus datos\\
\textbf{entonces} el sistema guarda los cambios y actualiza la ficha.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el nutricionista ingresa información incorrecta\\
\textbf{cuando} intenta guardar\\
\textbf{entonces} el sistema muestra errores de validación.\\[0.2em]

\textbf{Escenario 3: Cancelación de cambios}\\
\textbf{Dado que} el nutricionista inicia la edición\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no aplica modificaciones.\\
\end{tabular} & WEB-EP02 \\
\hline

WEB-US09 & Eliminación de pacientes & \textbf{Como} nutricionista, \textbf{quiero} eliminar o desactivar pacientes, \textbf{para} gestionar únicamente a quienes atiendo activamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Eliminación exitosa}\\
\textbf{Dado que} un paciente está en la base\\
\textbf{cuando} el nutricionista lo elimina\\
\textbf{entonces} el sistema lo marca como inactivo.\\[0.2em]

\textbf{Escenario 2: Paciente inexistente}\\
\textbf{Dado que} se intenta eliminar un paciente no registrado\\
\textbf{cuando} se ejecuta la acción\\
\textbf{entonces} el sistema muestra un error.\\[0.2em]

\textbf{Escenario 3: Cancelación de eliminación}\\
\textbf{Dado que} el nutricionista inicia el proceso de eliminar\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no realiza cambios.\\
\end{tabular} & WEB-EP02 \\
\hline

WEB-US10 & Búsqueda y filtrado de pacientes & \textbf{Como} nutricionista, \textbf{quiero} buscar y filtrar pacientes por nombre o estado, \textbf{para} encontrar rápidamente la información que necesito. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Búsqueda por nombre}\\
\textbf{Dado que} el nutricionista tiene una lista de pacientes\\
\textbf{cuando} ingresa un nombre en el buscador\\
\textbf{entonces} el sistema lista los resultados coincidentes.\\[0.2em]

\textbf{Escenario 2: Filtro por estado}\\
\textbf{Dado que} existen pacientes activos e inactivos\\
\textbf{cuando} selecciona un filtro por estado\\
\textbf{entonces} el sistema muestra solo los pacientes filtrados.\\[0.2em]

\textbf{Escenario 3: Sin resultados}\\
\textbf{Dado que} no hay coincidencias con el criterio de búsqueda\\
\textbf{cuando} se ejecuta la búsqueda\\
\textbf{entonces} el sistema muestra “Sin resultados encontrados”.\\
\end{tabular} & WEB-EP02 \\
\hline

WEB-US11 & Visualización de dieta diaria & \textbf{Como} nutricionista, \textbf{quiero} ver los alimentos consumidos por mis pacientes en el día, \textbf{para} evaluar su dieta actual. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización completa}\\
\textbf{Dado que} el paciente registró alimentos en la app móvil\\
\textbf{cuando} el nutricionista abre la ficha diaria\\
\textbf{entonces} el sistema muestra todos los registros.\\[0.2em]

\textbf{Escenario 2: Sin registros}\\
\textbf{Dado que} no hay alimentos registrados en un día\\
\textbf{cuando} el nutricionista abre la ficha\\
\textbf{entonces} el sistema indica “No hay registros para este día”.\\[0.2em]

\textbf{Escenario 3: Error de sincronización}\\
\textbf{Dado que} hay un problema de sincronización\\
\textbf{cuando} el nutricionista intenta visualizar\\
\textbf{entonces} el sistema muestra un aviso de error técnico.\\
\end{tabular} & WEB-EP03 \\
\hline

WEB-US12 & Visualización de macros y calorías & \textbf{Como} nutricionista, \textbf{quiero} ver un resumen de macros y calorías aproximadas de mis pacientes, \textbf{para} evaluar su balance energético. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Resumen correcto}\\
\textbf{Dado que} el paciente tiene alimentos registrados\\
\textbf{cuando} el nutricionista consulta el resumen\\
\textbf{entonces} el sistema muestra calorías y macros calculados.\\[0.2em]

\textbf{Escenario 2: Sin datos}\\
\textbf{Dado que} el paciente no registró comidas\\
\textbf{cuando} se abre el resumen\\
\textbf{entonces} se muestra “Sin datos disponibles”.\\[0.2em]

\textbf{Escenario 3: Datos incompletos}\\
\textbf{Dado que} algunos registros carecen de calorías estimadas\\
\textbf{cuando} el nutricionista consulta\\
\textbf{entonces} el sistema advierte que los datos pueden estar incompletos.\\
\end{tabular} & WEB-EP03 \\
\hline

WEB-US13 & Historial de calorías consumidas y gastadas & \textbf{Como} nutricionista, \textbf{quiero} visualizar el historial de calorías consumidas y gastadas semanalmente, \textbf{para} hacer seguimiento a la evolución del paciente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Historial disponible}\\
\textbf{Dado que} el paciente registró información durante la semana\\
\textbf{cuando} el nutricionista consulta el historial\\
\textbf{entonces} el sistema muestra los datos en gráfico y tabla.\\[0.2em]

\textbf{Escenario 2: Semana sin registros}\\
\textbf{Dado que} el paciente no registró datos\\
\textbf{cuando} el nutricionista abre el historial\\
\textbf{entonces} el sistema indica que no hay información disponible.\\[0.2em]

\textbf{Escenario 3: Datos parciales}\\
\textbf{Dado que} el paciente registró datos solo algunos días\\
\textbf{cuando} se abre el historial\\
\textbf{entonces} el sistema muestra la información parcial con aviso.\\
\end{tabular} & WEB-EP03 \\
\hline

WEB-US14 & Visualización de rutinas de ejercicio & \textbf{Como} nutricionista, \textbf{quiero} visualizar las rutinas de ejercicio registradas por mis pacientes, \textbf{para} complementar el análisis de la dieta. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Rutinas disponibles}\\
\textbf{Dado que} el paciente ha registrado rutinas de ejercicio\\
\textbf{cuando} el nutricionista consulta su ficha\\
\textbf{entonces} el sistema muestra las rutinas con detalles de duración e intensidad.\\[0.2em]

\textbf{Escenario 2: Sin rutinas registradas}\\
\textbf{Dado que} el paciente no ha registrado ejercicios\\
\textbf{cuando} el nutricionista abre la sección de rutinas\\
\textbf{entonces} el sistema indica que no hay información disponible.\\[0.2em]

\textbf{Escenario 3: Error de sincronización}\\
\textbf{Dado que} ocurre un problema al recuperar datos de la app móvil\\
\textbf{cuando} el nutricionista consulta rutinas\\
\textbf{entonces} el sistema muestra un aviso de error técnico.\\
\end{tabular} & WEB-EP04 \\
\hline

WEB-US15 & Visualización de calorías gastadas & \textbf{Como} nutricionista, \textbf{quiero} visualizar las calorías gastadas por mis pacientes, \textbf{para} evaluar su nivel de actividad física. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cálculo exitoso}\\
\textbf{Dado que} el paciente registró actividades físicas\\
\textbf{cuando} el nutricionista abre la ficha de calorías gastadas\\
\textbf{entonces} el sistema muestra el total de calorías quemadas en el día.\\[0.2em]

\textbf{Escenario 2: Sin datos}\\
\textbf{Dado que} no hay actividades registradas\\
\textbf{cuando} se abre la ficha\\
\textbf{entonces} el sistema indica “No hay datos disponibles”.\\[0.2em]

\textbf{Escenario 3: Datos incompletos}\\
\textbf{Dado que} algunas actividades no registraron calorías estimadas\\
\textbf{cuando} el nutricionista consulta la ficha\\
\textbf{entonces} el sistema muestra los datos parciales con un aviso.\\
\end{tabular} & WEB-EP04 \\
\hline

WEB-US16 & Creación de rutinas personalizadas & \textbf{Como} nutricionista, \textbf{quiero} crear rutinas de ejercicio personalizadas para mis pacientes, \textbf{para} apoyar su progreso físico. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Creación exitosa}\\
\textbf{Dado que} el nutricionista define una rutina válida\\
\textbf{cuando} guarda la rutina\\
\textbf{entonces} el sistema la asigna al paciente seleccionado.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} el nutricionista no completa todos los campos requeridos\\
\textbf{cuando} intenta guardar la rutina\\
\textbf{entonces} el sistema muestra mensajes de error.\\[0.2em]

\textbf{Escenario 3: Cancelación de creación}\\
\textbf{Dado que} el nutricionista está creando una rutina\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no guarda los cambios.\\
\end{tabular} & WEB-EP05 \\
\hline

WEB-US17 & Asignación de metas nutricionales & \textbf{Como} nutricionista, \textbf{quiero} asignar metas de calorías y macros a mis pacientes, \textbf{para} guiar su plan alimenticio. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Asignación exitosa}\\
\textbf{Dado que} el nutricionista define valores de calorías y macros válidos\\
\textbf{cuando} guarda la meta\\
\textbf{entonces} el sistema asigna la meta al paciente.\\[0.2em]

\textbf{Escenario 2: Valores inválidos}\\
\textbf{Dado que} el nutricionista ingresa números fuera de rango\\
\textbf{cuando} intenta guardar\\
\textbf{entonces} el sistema muestra errores de validación.\\[0.2em]

\textbf{Escenario 3: Cancelación de asignación}\\
\textbf{Dado que} el nutricionista inicia la asignación de metas\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no guarda la información.\\
\end{tabular} & WEB-EP05 \\
\hline

WEB-US18 & Registro de recomendaciones específicas & \textbf{Como} nutricionista, \textbf{quiero} registrar recomendaciones personalizadas para cada paciente, \textbf{para} complementar su plan de salud. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el nutricionista ingresa recomendaciones válidas\\
\textbf{cuando} guarda la información\\
\textbf{entonces} el sistema muestra las recomendaciones en la ficha del paciente.\\[0.2em]

\textbf{Escenario 2: Campos vacíos}\\
\textbf{Dado que} no se ingresa texto en el campo de recomendaciones\\
\textbf{cuando} el nutricionista intenta guardar\\
\textbf{entonces} el sistema muestra un error.\\[0.2em]

\textbf{Escenario 3: Cancelación de registro}\\
\textbf{Dado que} el nutricionista empieza a escribir recomendaciones\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no guarda los datos.\\
\end{tabular} & WEB-EP05 \\
\hline

WEB-US19 & Reporte de evolución de peso & \textbf{Como} nutricionista, \textbf{quiero} generar reportes históricos de peso de mis pacientes, \textbf{para} evaluar su progreso en el tiempo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Reporte exitoso}\\
\textbf{Dado que} el paciente tiene registros de peso\\
\textbf{cuando} el nutricionista solicita un reporte\\
\textbf{entonces} el sistema genera y muestra el gráfico de evolución.\\[0.2em]

\textbf{Escenario 2: Sin registros}\\
\textbf{Dado que} el paciente no tiene registros de peso\\
\textbf{cuando} se intenta generar el reporte\\
\textbf{entonces} el sistema indica que no hay datos suficientes.\\[0.2em]

\textbf{Escenario 3: Exportación de reporte}\\
\textbf{Dado que} se genera un reporte de peso\\
\textbf{cuando} el nutricionista selecciona exportar\\
\textbf{entonces} el sistema descarga el reporte en PDF.\\
\end{tabular} & WEB-EP06 \\
\hline

WEB-US20 & Dashboard de progreso con gráficas & \textbf{Como} nutricionista, \textbf{quiero} acceder a un dashboard de progreso visual, \textbf{para} tener una visión rápida del desempeño de mis pacientes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización correcta}\\
\textbf{Dado que} el paciente tiene datos registrados\\
\textbf{cuando} el nutricionista accede al dashboard\\
\textbf{entonces} el sistema muestra gráficos de calorías, macros y peso.\\[0.2em]

\textbf{Escenario 2: Sin datos registrados}\\
\textbf{Dado que} no existen datos\\
\textbf{cuando} el nutricionista abre el dashboard\\
\textbf{entonces} el sistema indica que no hay información disponible.\\[0.2em]

\textbf{Escenario 3: Error en carga}\\
\textbf{Dado que} ocurre un problema en la consulta\\
\textbf{cuando} el nutricionista abre el dashboard\\
\textbf{entonces} el sistema muestra un mensaje de error técnico.\\
\end{tabular} & WEB-EP06 \\
\hline

WEB-US21 & Generación de reportes descargables & \textbf{Como} nutricionista, \textbf{quiero} generar y descargar reportes en formatos estándar, \textbf{para} compartirlos con mis pacientes o archivarlos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Descarga en PDF}\\
\textbf{Dado que} el nutricionista genera un reporte\\
\textbf{cuando} selecciona la opción de exportar en PDF\\
\textbf{entonces} el sistema descarga el archivo correctamente.\\[0.2em]

\textbf{Escenario 2: Descarga en Excel}\\
\textbf{Dado que} el nutricionista genera un reporte\\
\textbf{cuando} selecciona la opción de exportar en Excel\\
\textbf{entonces} el sistema descarga el archivo correctamente.\\[0.2em]

\textbf{Escenario 3: Error de exportación}\\
\textbf{Dado que} el sistema presenta un fallo al exportar\\
\textbf{cuando} se intenta descargar el archivo\\
\textbf{entonces} se muestra un mensaje de error.\\
\end{tabular} & WEB-EP06 \\
\hline

WEB-US22 & Selección de plan de suscripción & 
\textbf{Como} nutricionista, \textbf{quiero} seleccionar un plan de suscripción según la cantidad de pacientes que administro, \textbf{para} acceder a las funcionalidades adecuadas. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Selección exitosa}\\
\textbf{Dado que} el nutricionista accede a la sección de planes disponibles\\
\textbf{cuando} selecciona un plan válido y confirma su elección\\
\textbf{entonces} el sistema registra el plan seleccionado en su cuenta.\\[0.2em]

\textbf{Escenario 2: Plan no disponible}\\
\textbf{Dado que} el nutricionista intenta seleccionar un plan inexistente o inactivo\\
\textbf{cuando} confirma su selección\\
\textbf{entonces} el sistema muestra un mensaje de error indicando la indisponibilidad.\\[0.2em]

\textbf{Escenario 3: Cambio de plan}\\
\textbf{Dado que} el nutricionista ya tiene un plan activo\\
\textbf{cuando} selecciona un nuevo plan superior\\
\textbf{entonces} el sistema actualiza la suscripción al nuevo plan y ajusta el ciclo de pago.\\
\end{tabular} & WEB-EP07 \\
\hline

WEB-US23 & Pago en línea & 
\textbf{Como} nutricionista, \textbf{quiero} pagar en línea mi suscripción usando métodos disponibles (tarjeta, billetera digital, etc.), \textbf{para} activar o renovar mi plan. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Pago exitoso}\\
\textbf{Dado que} el nutricionista selecciona un plan válido y un método de pago disponible\\
\textbf{cuando} confirma el pago\\
\textbf{entonces} el sistema procesa la transacción y activa la suscripción.\\[0.2em]

\textbf{Escenario 2: Pago rechazado}\\
\textbf{Dado que} el nutricionista selecciona un método de pago\\
\textbf{cuando} el sistema recibe una respuesta de rechazo del proveedor de pagos\\
\textbf{entonces} el sistema muestra un mensaje de error e invita a reintentar con otro método.\\[0.2em]

\textbf{Escenario 3: Error de conexión}\\
\textbf{Dado que} el nutricionista intenta realizar un pago\\
\textbf{cuando} ocurre un error de conexión con el servicio de pagos (ej. Culqi)\\
\textbf{entonces} el sistema notifica el error y conserva el estado pendiente del pago.\\
\end{tabular} & WEB-EP07 \\
\hline

WEB-US24 & Cancelación de suscripción & 
\textbf{Como} nutricionista, \textbf{quiero} cancelar mi suscripción en cualquier momento, \textbf{para} dejar de usar funcionalidades avanzadas sin cargos posteriores. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cancelación exitosa}\\
\textbf{Dado que} el nutricionista tiene una suscripción activa\\
\textbf{cuando} solicita la cancelación desde la sección de gestión de cuenta\\
\textbf{entonces} el sistema cancela la suscripción y confirma la fecha de finalización.\\[0.2em]

\textbf{Escenario 2: Cancelación tardía}\\
\textbf{Dado que} el nutricionista cancela luego de haberse realizado el cobro del ciclo actual\\
\textbf{cuando} confirma la cancelación\\
\textbf{entonces} el sistema informa que el plan se mantendrá activo hasta el final del ciclo pagado.\\[0.2em]

\textbf{Escenario 3: Error en cancelación}\\
\textbf{Dado que} el nutricionista solicita la cancelación\\
\textbf{cuando} ocurre un error con el proveedor de pagos\\
\textbf{entonces} el sistema notifica al usuario y mantiene el estado de la suscripción sin cambios.\\
\end{tabular} & WEB-EP07 \\
\hline

WEB-US25 & Historial de pagos & 
\textbf{Como} nutricionista, \textbf{quiero} visualizar el historial de mis pagos realizados, \textbf{para} llevar control de mis transacciones y facturación. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización exitosa}\\
\textbf{Dado que} el nutricionista tiene pagos registrados en la plataforma\\
\textbf{cuando} accede a la sección de historial\\
\textbf{entonces} el sistema muestra la lista de pagos con fecha, monto y método.\\[0.2em]

\textbf{Escenario 2: Sin historial}\\
\textbf{Dado que} el nutricionista aún no ha realizado pagos\\
\textbf{cuando} accede a la sección de historial\\
\textbf{entonces} el sistema muestra un mensaje indicando “No se encontraron pagos registrados”.\\[0.2em]

\textbf{Escenario 3: Error de consulta}\\
\textbf{Dado que} el nutricionista accede a la sección de historial\\
\textbf{cuando} ocurre un error en la base de datos o en la integración con Culqi\\
\textbf{entonces} el sistema muestra un mensaje de error temporal.\\
\end{tabular} & WEB-EP07 \\
\hline

WEB-US26 & Estado de suscripción & 
\textbf{Como} nutricionista, \textbf{quiero} ver la fecha del próximo cobro y el estado actual de mi suscripción, \textbf{para} estar informado sobre mi plan activo. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de estado activo}\\
\textbf{Dado que} el nutricionista tiene una suscripción activa\\
\textbf{cuando} accede a la sección de estado de suscripción\\
\textbf{entonces} el sistema muestra la fecha del próximo cobro y el estado “Activo”.\\[0.2em]

\textbf{Escenario 2: Suscripción cancelada}\\
\textbf{Dado que} el nutricionista canceló su suscripción\\
\textbf{cuando} consulta el estado\\
\textbf{entonces} el sistema muestra el estado “Cancelada” con la fecha de finalización.\\[0.2em]

\textbf{Escenario 3: Error en la consulta de estado}\\
\textbf{Dado que} el nutricionista consulta el estado de su suscripción\\
\textbf{cuando} ocurre un error de comunicación con Culqi\\
\textbf{entonces} el sistema muestra un mensaje de error temporal indicando que intente más tarde.\\
\end{tabular} & WEB-EP07 \\
\hline
\end{longtable}

\newpage

### *Mobile Application US*

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

MOB-US01 & Registro de usuario nuevo & \textbf{Como} paciente, \textbf{quiero} registrarme en la aplicación móvil proporcionando mis datos personales, \textbf{para} crear mi cuenta y acceder a las funcionalidades. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el paciente completa todos los campos obligatorios\\
\textbf{cuando} envía el formulario de registro\\
\textbf{entonces} el sistema crea la cuenta y confirma el registro.\\[0.2em]

\textbf{Escenario 2: Campos incompletos}\\
\textbf{Dado que} el paciente deja campos obligatorios vacíos\\
\textbf{cuando} intenta registrarse\\
\textbf{entonces} el sistema muestra mensajes de error.\\[0.2em]

\textbf{Escenario 3: Correo inválido}\\
\textbf{Dado que} el paciente ingresa un correo no válido\\
\textbf{cuando} intenta registrar la cuenta\\
\textbf{entonces} el sistema muestra un mensaje de validación.\\
\end{tabular} & MOB-EP01 \\
\hline

MOB-US02 & Inicio de sesión & \textbf{Como} paciente, \textbf{quiero} iniciar sesión en la aplicación móvil con mis credenciales, \textbf{para} acceder a mi información personal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Inicio exitoso}\\
\textbf{Dado que} el paciente tiene una cuenta activa\\
\textbf{cuando} ingresa credenciales correctas\\
\textbf{entonces} accede al sistema correctamente.\\[0.2em]

\textbf{Escenario 2: Credenciales inválidas}\\
\textbf{Dado que} el paciente ingresa datos incorrectos\\
\textbf{cuando} intenta iniciar sesión\\
\textbf{entonces} el sistema muestra un error de autenticación.\\[0.2em]

\textbf{Escenario 3: Cuenta no confirmada}\\
\textbf{Dado que} la cuenta no ha sido verificada\\
\textbf{cuando} el paciente intenta iniciar sesión\\
\textbf{entonces} el sistema indica que debe confirmar primero su cuenta.\\
\end{tabular} & MOB-EP01 \\
\hline

MOB-US03 & Cierre de sesión & \textbf{Como} paciente, \textbf{quiero} cerrar mi sesión de la aplicación móvil, \textbf{para} proteger mi información personal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cierre exitoso}\\
\textbf{Dado que} el paciente está autenticado\\
\textbf{cuando} selecciona la opción de cerrar sesión\\
\textbf{entonces} el sistema cierra la sesión y redirige a la pantalla inicial.\\[0.2em]

\textbf{Escenario 2: Sesión expirada}\\
\textbf{Dado que} la sesión ha expirado automáticamente\\
\textbf{cuando} el paciente intenta interactuar\\
\textbf{entonces} el sistema redirige a inicio de sesión.\\[0.2em]

\textbf{Escenario 3: Error de red}\\
\textbf{Dado que} ocurre un fallo al cerrar sesión\\
\textbf{cuando} el paciente ejecuta la acción\\
\textbf{entonces} el sistema muestra un mensaje de error.\\
\end{tabular} & MOB-EP01 \\
\hline

MOB-US04 & Recuperación de contraseña & \textbf{Como} paciente, \textbf{quiero} recuperar mi contraseña mediante correo electrónico, \textbf{para} restablecer mi acceso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Recuperación exitosa}\\
\textbf{Dado que} el paciente solicita recuperar contraseña\\
\textbf{cuando} ingresa su correo válido\\
\textbf{entonces} el sistema envía un enlace de restablecimiento.\\[0.2em]

\textbf{Escenario 2: Correo inexistente}\\
\textbf{Dado que} el paciente ingresa un correo no registrado\\
\textbf{cuando} solicita recuperación\\
\textbf{entonces} el sistema muestra un error.\\[0.2em]

\textbf{Escenario 3: Enlace expirado}\\
\textbf{Dado que} el paciente recibe un enlace de recuperación\\
\textbf{cuando} este ha expirado\\
\textbf{entonces} el sistema muestra un mensaje de enlace inválido.\\
\end{tabular} & MOB-EP01 \\
\hline

MOB-US05 & Gestión de perfil del paciente & \textbf{Como} paciente, \textbf{quiero} gestionar mi perfil personal, \textbf{para} mantener mis datos actualizados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Actualización exitosa}\\
\textbf{Dado que} el paciente accede a su perfil\\
\textbf{cuando} actualiza datos válidos\\
\textbf{entonces} el sistema guarda los cambios correctamente.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el paciente ingresa información no válida\\
\textbf{cuando} intenta guardar\\
\textbf{entonces} el sistema muestra un error de validación.\\[0.2em]

\textbf{Escenario 3: Cancelación de edición}\\
\textbf{Dado que} el paciente modifica datos\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no guarda los cambios.\\
\end{tabular} & MOB-EP01 \\
\hline

MOB-US06 & Resumen diario de calorías y macros & \textbf{Como} paciente, \textbf{quiero} ver un resumen de calorías y macros al iniciar la aplicación, \textbf{para} tomar decisiones rápidas sobre mi dieta. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Resumen con datos completos}\\
\textbf{Dado que} el paciente ha registrado comidas\\
\textbf{cuando} abre la app\\
\textbf{entonces} se muestra un resumen de calorías y macros.\\[0.2em]

\textbf{Escenario 2: Sin datos registrados}\\
\textbf{Dado que} no hay comidas registradas\\
\textbf{cuando} el paciente abre la app\\
\textbf{entonces} se indica que aún no hay información disponible.\\[0.2em]

\textbf{Escenario 3: Error en carga de datos}\\
\textbf{Dado que} ocurre un problema al consultar el backend\\
\textbf{cuando} el paciente abre la app\\
\textbf{entonces} el sistema muestra un aviso de error.\\
\end{tabular} & MOB-EP02 \\
\hline

MOB-US07 & Cálculo y visualización de IMC & \textbf{Como} paciente, \textbf{quiero} calcular y visualizar mi IMC en la app, \textbf{para} conocer mi estado de salud general. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cálculo correcto}\\
\textbf{Dado que} el paciente registra su peso y altura\\
\textbf{cuando} solicita calcular IMC\\
\textbf{entonces} el sistema muestra el resultado correctamente.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} falta peso o altura\\
\textbf{cuando} se intenta calcular IMC\\
\textbf{entonces} el sistema muestra un mensaje de error.\\[0.2em]

\textbf{Escenario 3: Datos inválidos}\\
\textbf{Dado que} se ingresan valores fuera de rango\\
\textbf{cuando} se calcula IMC\\
\textbf{entonces} el sistema alerta que los datos no son válidos.\\
\end{tabular} & MOB-EP02 \\
\hline

MOB-US08 & Historial diario con resumen semanal & \textbf{Como} paciente, \textbf{quiero} consultar mi historial de calorías consumidas y gastadas, \textbf{para} evaluar mi progreso semanal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Historial completo}\\
\textbf{Dado que} el paciente tiene registros diarios\\
\textbf{cuando} consulta el historial\\
\textbf{entonces} el sistema muestra la información con resumen semanal.\\[0.2em]

\textbf{Escenario 2: Sin datos suficientes}\\
\textbf{Dado que} el paciente solo tiene un registro\\
\textbf{cuando} consulta el historial\\
\textbf{entonces} el sistema muestra un aviso de datos insuficientes.\\[0.2em]

\textbf{Escenario 3: Error de consulta}\\
\textbf{Dado que} ocurre un fallo técnico\\
\textbf{cuando} se consulta el historial\\
\textbf{entonces} el sistema muestra un mensaje de error.\\
\end{tabular} & MOB-EP02 \\
\hline

MOB-US09 & Registro de comida mediante foto & \textbf{Como} paciente, \textbf{quiero} registrar mis comidas mediante una foto, \textbf{para} que la app identifique alimentos automáticamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el paciente sube una foto clara de su comida\\
\textbf{cuando} la IA procesa la imagen\\
\textbf{entonces} se muestran los alimentos detectados.\\[0.2em]

\textbf{Escenario 2: Foto inválida}\\
\textbf{Dado que} la imagen es borrosa o no corresponde a alimentos\\
\textbf{cuando} se intenta procesar\\
\textbf{entonces} el sistema indica que no pudo identificar los alimentos.\\[0.2em]

\textbf{Escenario 3: Error de red}\\
\textbf{Dado que} hay un fallo en la conexión\\
\textbf{cuando} se sube la foto\\
\textbf{entonces} el sistema muestra un aviso y permite reintentar.\\
\end{tabular} & MOB-EP03 \\
\hline

MOB-US10 & Modificar alimentos o cantidades detectadas & \textbf{Como} paciente, \textbf{quiero} corregir manualmente los alimentos o cantidades detectadas por la IA, \textbf{para} tener un registro más preciso de mi consumo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Corrección exitosa}\\
\textbf{Dado que} el paciente revisa la comida detectada\\
\textbf{cuando} edita alimentos o cantidades\\
\textbf{entonces} el sistema actualiza el registro correctamente.\\[0.2em]

\textbf{Escenario 2: Eliminación de alimento}\\
\textbf{Dado que} un alimento fue detectado incorrectamente\\
\textbf{cuando} el paciente lo elimina\\
\textbf{entonces} el sistema actualiza el total de calorías y macros.\\[0.2em]

\textbf{Escenario 3: Error al guardar cambios}\\
\textbf{Dado que} el paciente corrige datos\\
\textbf{cuando} ocurre un error en la app\\
\textbf{entonces} el sistema muestra un mensaje de error y mantiene los valores anteriores.\\
\end{tabular} & MOB-EP03 \\
\hline

MOB-US11 & Visualización de macros y calorías por comida registrada & \textbf{Como} paciente, \textbf{quiero} ver el detalle de macros y calorías de cada comida registrada, \textbf{para} conocer su impacto en mi dieta diaria. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización correcta}\\
\textbf{Dado que} el paciente registró una comida\\
\textbf{cuando} consulta su detalle\\
\textbf{entonces} el sistema muestra macros y calorías exactas.\\[0.2em]

\textbf{Escenario 2: Comida sin datos completos}\\
\textbf{Dado que} una comida no tiene todos los nutrientes calculados\\
\textbf{cuando} el paciente la consulta\\
\textbf{entonces} el sistema indica qué datos no están disponibles.\\[0.2em]

\textbf{Escenario 3: Error en la carga}\\
\textbf{Dado que} ocurre un fallo de conexión\\
\textbf{cuando} el paciente abre la vista de detalle\\
\textbf{entonces} el sistema muestra un aviso de error.\\
\end{tabular} & MOB-EP03 \\
\hline

MOB-US12 & Registro de actividad física manual & \textbf{Como} paciente, \textbf{quiero} registrar manualmente mis actividades físicas, \textbf{para} calcular las calorías gastadas durante el día. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el paciente ingresa una actividad\\
\textbf{cuando} completa los datos (tipo, duración, intensidad)\\
\textbf{entonces} el sistema guarda el registro.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} se ingresan valores fuera de rango\\
\textbf{cuando} el paciente intenta registrar\\
\textbf{entonces} el sistema muestra un error de validación.\\[0.2em]

\textbf{Escenario 3: Cancelación del registro}\\
\textbf{Dado que} el paciente inició el llenado\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no guarda cambios.\\
\end{tabular} & MOB-EP04 \\
\hline

MOB-US13 & Balance diario de calorías consumidas vs gastadas & \textbf{Como} paciente, \textbf{quiero} visualizar mi balance de calorías consumidas y gastadas, \textbf{para} evaluar si cumplo mis metas nutricionales. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Balance positivo}\\
\textbf{Dado que} el paciente consumió más calorías de las gastadas\\
\textbf{cuando} consulta su balance diario\\
\textbf{entonces} el sistema indica superávit calórico.\\[0.2em]

\textbf{Escenario 2: Balance negativo}\\
\textbf{Dado que} el paciente gastó más calorías de las consumidas\\
\textbf{cuando} consulta su balance\\
\textbf{entonces} el sistema indica déficit calórico.\\[0.2em]

\textbf{Escenario 3: Balance neutro}\\
\textbf{Dado que} el paciente consumió lo mismo que gastó\\
\textbf{cuando} consulta su balance\\
\textbf{entonces} el sistema muestra que está en equilibrio.\\
\end{tabular} & MOB-EP04 \\
\hline

MOB-US14 & Registro de pasos y calorías quemadas & \textbf{Como} paciente, \textbf{quiero} sincronizar mis pasos diarios con la app, \textbf{para} conocer las calorías quemadas automáticamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Sincronización exitosa}\\
\textbf{Dado que} el paciente tiene un podómetro o sensor\\
\textbf{cuando} sincroniza la app\\
\textbf{entonces} se muestran los pasos y calorías.\\[0.2em]

\textbf{Escenario 2: Sin sensor disponible}\\
\textbf{Dado que} el dispositivo no soporta conteo de pasos\\
\textbf{cuando} el paciente intenta sincronizar\\
\textbf{entonces} el sistema indica que no es posible.\\[0.2em]

\textbf{Escenario 3: Error de conexión}\\
\textbf{Dado que} hay un problema con el sensor\\
\textbf{cuando} se intenta sincronizar\\
\textbf{entonces} la app muestra un mensaje de error.\\
\end{tabular} & MOB-EP04 \\
\hline

MOB-US15 & Registro y gráfico de peso & \textbf{Como} paciente, \textbf{quiero} registrar mi peso y visualizarlo en un gráfico, \textbf{para} seguir mi evolución en el tiempo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el paciente ingresa su peso\\
\textbf{cuando} guarda el valor\\
\textbf{entonces} el sistema lo añade al historial.\\[0.2em]

\textbf{Escenario 2: Datos fuera de rango}\\
\textbf{Dado que} el paciente ingresa un peso irreal\\
\textbf{cuando} intenta registrar\\
\textbf{entonces} el sistema muestra un mensaje de validación.\\[0.2em]

\textbf{Escenario 3: Visualización de gráfico}\\
\textbf{Dado que} hay varios registros\\
\textbf{cuando} el paciente consulta la evolución\\
\textbf{entonces} el sistema genera un gráfico de tendencia.\\
\end{tabular} & MOB-EP05 \\
\hline

MOB-US16 & Ajuste de metas diarias según progreso & \textbf{Como} paciente, \textbf{quiero} ajustar mis metas diarias de calorías y macros, \textbf{para} alinearlas a mi progreso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Ajuste exitoso}\\
\textbf{Dado que} el paciente modifica metas\\
\textbf{cuando} guarda los cambios\\
\textbf{entonces} el sistema aplica las nuevas metas.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el paciente ingresa valores fuera de rango\\
\textbf{cuando} intenta guardar\\
\textbf{entonces} el sistema muestra un mensaje de error.\\[0.2em]

\textbf{Escenario 3: Cancelación de cambios}\\
\textbf{Dado que} el paciente edita metas\\
\textbf{cuando} cancela la acción\\
\textbf{entonces} el sistema no aplica modificaciones.\\
\end{tabular} & MOB-EP05 \\
\hline

MOB-US17 & Visualización semanal de cumplimiento & \textbf{Como} paciente, \textbf{quiero} visualizar el cumplimiento de mis metas semanales, \textbf{para} confirmar si estoy alcanzando mis objetivos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cumplimiento alto}\\
\textbf{Dado que} el paciente cumplió la mayoría de metas\\
\textbf{cuando} consulta el reporte semanal\\
\textbf{entonces} el sistema indica alto nivel de cumplimiento.\\[0.2em]

\textbf{Escenario 2: Cumplimiento bajo}\\
\textbf{Dado que} el paciente no alcanzó la mayoría de metas\\
\textbf{cuando} consulta el reporte semanal\\
\textbf{entonces} el sistema indica bajo nivel de cumplimiento.\\[0.2em]

\textbf{Escenario 3: Sin datos suficientes}\\
\textbf{Dado que} hay pocos registros\\
\textbf{cuando} se consulta la semana\\
\textbf{entonces} el sistema indica que no hay datos suficientes.\\
\end{tabular} & MOB-EP05 \\
\hline

MOB-US18 & Notificaciones para registrar comidas & \textbf{Como} paciente, \textbf{quiero} recibir notificaciones para registrar mis comidas, \textbf{para} mantener constancia en mis registros diarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación programada}\\
\textbf{Dado que} el paciente configuró alertas\\
\textbf{cuando} llega la hora establecida\\
\textbf{entonces} el sistema envía una notificación.\\[0.2em]

\textbf{Escenario 2: Notificaciones desactivadas}\\
\textbf{Dado que} el paciente desactivó recordatorios\\
\textbf{cuando} llega la hora configurada\\
\textbf{entonces} no se recibe ninguna alerta.\\[0.2em]

\textbf{Escenario 3: Error de envío}\\
\textbf{Dado que} ocurre un fallo en el sistema de notificaciones\\
\textbf{cuando} se debería enviar un recordatorio\\
\textbf{entonces} no se recibe y se registra el error.\\
\end{tabular} & MOB-EP06 \\
\hline

MOB-US19 & Alerta por exceso o déficit calórico & \textbf{Como} paciente, \textbf{quiero} recibir alertas si supero o no alcanzo mis metas calóricas, \textbf{para} ajustar mi consumo diario. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Exceso calórico}\\
\textbf{Dado que} el paciente supera su meta diaria\\
\textbf{cuando} registra una comida extra\\
\textbf{entonces} el sistema envía una alerta de exceso.\\[0.2em]

\textbf{Escenario 2: Déficit calórico}\\
\textbf{Dado que} el paciente no alcanza su meta diaria\\
\textbf{cuando} termina el día\\
\textbf{entonces} el sistema envía una alerta de déficit.\\[0.2em]

\textbf{Escenario 3: Dentro del rango}\\
\textbf{Dado que} el paciente mantiene su consumo en rango\\
\textbf{cuando} llega al final del día\\
\textbf{entonces} no se envía alerta alguna.\\
\end{tabular} & MOB-EP06 \\
\hline

MOB-US20 & Notificaciones de consejos personalizados & \textbf{Como} paciente, \textbf{quiero} recibir consejos de nutrición y entrenamiento, \textbf{para} mejorar mis hábitos y cumplir mis objetivos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consejo diario enviado}\\
\textbf{Dado que} el paciente tiene activadas notificaciones\\
\textbf{cuando} llega la hora configurada\\
\textbf{entonces} el sistema envía un consejo personalizado.\\[0.2em]

\textbf{Escenario 2: Consejos desactivados}\\
\textbf{Dado que} el paciente desactiva consejos\\
\textbf{cuando} llega la hora\\
\textbf{entonces} no se recibe notificación.\\[0.2em]

\textbf{Escenario 3: Error en el envío}\\
\textbf{Dado que} ocurre un fallo en el sistema de notificaciones\\
\textbf{cuando} debía enviarse un consejo\\
\textbf{entonces} no se recibe y se registra el error.\\
\end{tabular} & MOB-EP06 \\
\hline
\end{longtable}

\newpage

### *Technical US*

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

TUS-01 & Registro seguro de usuario & \textbf{Como} Developer, \textbf{quiero} un endpoint para registrar usuarios con validaciones seguras, \textbf{para} asegurar el alta confiable de cuentas nuevas. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} se envía un POST a /users con datos válidos\\
\textbf{cuando} el sistema valida y crea el usuario\\
\textbf{entonces} devuelve 201 Created con el ID del usuario.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} se envía un POST con campos vacíos o inválidos\\
\textbf{cuando} el sistema procesa la solicitud\\
\textbf{entonces} devuelve 400 Bad Request con mensaje de error.\\[0.2em]

\textbf{Escenario 3: Usuario duplicado}\\
\textbf{Dado que} ya existe un correo en el sistema\\
\textbf{cuando} se intenta registrar nuevamente\\
\textbf{entonces} devuelve 409 Conflict indicando duplicado.\\
\end{tabular} & T-EP01 \\
\hline

TUS-02 & Inicio de sesión de usuario & \textbf{Como} Developer, \textbf{quiero} un endpoint de login con autenticación JWT, \textbf{para} permitir acceso seguro a los usuarios registrados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Login exitoso}\\
\textbf{Dado que} se envía un POST a /auth/login con credenciales válidas\\
\textbf{cuando} el sistema autentica al usuario\\
\textbf{entonces} devuelve 200 OK con un token JWT.\\[0.2em]

\textbf{Escenario 2: Credenciales inválidas}\\
\textbf{Dado que} se envía un POST con contraseña incorrecta\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 401 Unauthorized.\\[0.2em]

\textbf{Escenario 3: Usuario inactivo}\\
\textbf{Dado que} el usuario fue desactivado\\
\textbf{cuando} intenta iniciar sesión\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP01 \\
\hline

TUS-03 & Cierre de sesión seguro & \textbf{Como} Developer, \textbf{quiero} un endpoint para cerrar sesión invalidando el token, \textbf{para} proteger el acceso posterior. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Logout exitoso}\\
\textbf{Dado que} se envía un POST a /auth/logout con token válido\\
\textbf{cuando} el sistema lo invalida\\
\textbf{entonces} devuelve 200 OK confirmando cierre de sesión.\\[0.2em]

\textbf{Escenario 2: Token inválido}\\
\textbf{Dado que} se envía un token manipulado\\
\textbf{cuando} el sistema lo procesa\\
\textbf{entonces} devuelve 401 Unauthorized.\\[0.2em]

\textbf{Escenario 3: Token ya expirado}\\
\textbf{Dado que} el token ya caducó\\
\textbf{cuando} se envía la solicitud de logout\\
\textbf{entonces} devuelve 400 indicando sesión expirada.\\
\end{tabular} & T-EP01 \\
\hline

TUS-04 & Recuperación de contraseña olvidada & \textbf{Como} Developer, \textbf{quiero} un endpoint de recuperación de contraseña, \textbf{para} permitir al usuario restablecer su acceso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Solicitud válida}\\
\textbf{Dado que} se envía un POST a /auth/recover con correo válido\\
\textbf{cuando} el sistema valida la existencia del usuario\\
\textbf{entonces} envía un enlace temporal y devuelve 200 OK.\\[0.2em]

\textbf{Escenario 2: Correo no registrado}\\
\textbf{Dado que} se envía un correo inexistente\\
\textbf{cuando} el sistema lo procesa\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Token de recuperación expirado}\\
\textbf{Dado que} el usuario intenta usar un enlace caducado\\
\textbf{cuando} el sistema lo valida\\
\textbf{entonces} devuelve 410 Gone y permite solicitar otro.\\
\end{tabular} & T-EP01 \\
\hline

TUS-05 & Actualización de perfil & \textbf{Como} Developer, \textbf{quiero} un endpoint para actualizar información de perfil, \textbf{para} mantener los datos de usuario correctos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Actualización exitosa}\\
\textbf{Dado que} se envía un PUT a /users/{id} con datos válidos y token\\
\textbf{cuando} el sistema actualiza la información\\
\textbf{entonces} devuelve 200 OK con los nuevos datos.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} se envía información con formato incorrecto\\
\textbf{cuando} el sistema lo procesa\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no se envía token válido\\
\textbf{cuando} se intenta actualizar\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP01 \\
\hline

TUS-06 & Crear paciente nuevo & \textbf{Como} Developer, \textbf{quiero} un endpoint para registrar pacientes, \textbf{para} que los nutricionistas puedan dar de alta nuevos usuarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Creación exitosa}\\
\textbf{Dado que} se envía un POST a /patients con datos válidos y token de nutricionista\\
\textbf{cuando} el sistema procesa la solicitud\\
\textbf{entonces} devuelve 201 Created con el ID del paciente.\\[0.2em]

\textbf{Escenario 2: Datos faltantes}\\
\textbf{Dado que} el cuerpo de la solicitud omite campos obligatorios\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request con detalle de error.\\[0.2em]

\textbf{Escenario 3: Usuario no autorizado}\\
\textbf{Dado que} un rol distinto a nutricionista intenta crear paciente\\
\textbf{cuando} se procesa la solicitud\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP02 \\
\hline

TUS-07 & Obtener datos de un paciente & \textbf{Como} Developer, \textbf{quiero} un endpoint GET para obtener información de un paciente, \textbf{para} que el nutricionista consulte detalles individuales. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta exitosa}\\
\textbf{Dado que} se envía un GET a /patients/{id} con token válido\\
\textbf{cuando} el sistema encuentra el paciente\\
\textbf{entonces} devuelve 200 OK con los datos completos.\\[0.2em]

\textbf{Escenario 2: Paciente inexistente}\\
\textbf{Dado que} el ID no corresponde a ningún registro\\
\textbf{cuando} el sistema busca\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Sin autorización}\\
\textbf{Dado que} no se incluye token válido\\
\textbf{cuando} se realiza la solicitud\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP02 \\
\hline

TUS-08 & Actualizar datos del paciente & \textbf{Como} Developer, \textbf{quiero} un endpoint PUT/PATCH para modificar datos de paciente, \textbf{para} mantener su información actualizada. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Actualización correcta}\\
\textbf{Dado que} se envía un PUT a /patients/{id} con datos válidos y token de nutricionista\\
\textbf{cuando} el sistema actualiza la información\\
\textbf{entonces} devuelve 200 OK con los datos nuevos.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} se envían campos con formato incorrecto\\
\textbf{cuando} el sistema los valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Paciente inexistente}\\
\textbf{Dado que} se usa un ID no registrado\\
\textbf{cuando} el sistema busca\\
\textbf{entonces} devuelve 404 Not Found.\\
\end{tabular} & T-EP02 \\
\hline

TUS-09 & Desactivar paciente & \textbf{Como} Developer, \textbf{quiero} un endpoint para desactivar pacientes, \textbf{para} que el nutricionista gestione su estado. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Desactivación exitosa}\\
\textbf{Dado que} se envía un PATCH a /patients/{id}/deactivate con token válido\\
\textbf{cuando} el sistema procesa la acción\\
\textbf{entonces} devuelve 200 OK confirmando desactivación.\\[0.2em]

\textbf{Escenario 2: Paciente inexistente}\\
\textbf{Dado que} el ID no corresponde a un registro válido\\
\textbf{cuando} el sistema busca\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un rol no autorizado intenta desactivar\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP02 \\
\hline

TUS-10 & Registrar comida & \textbf{Como} Developer, \textbf{quiero} un endpoint para registrar comidas de un paciente, \textbf{para} calcular calorías y macros diarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} se envía un POST a /meals con datos válidos\\
\textbf{cuando} el sistema procesa la comida\\
\textbf{entonces} devuelve 201 Created con detalles del registro.\\[0.2em]

\textbf{Escenario 2: Datos incompletos}\\
\textbf{Dado que} faltan campos obligatorios\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario sin token}\\
\textbf{Dado que} no se incluye token de autenticación\\
\textbf{cuando} se envía la solicitud\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP03 \\
\hline

TUS-11 & Corregir comida existente & \textbf{Como} Developer, \textbf{quiero} un endpoint para modificar registros de comida, \textbf{para} ajustar errores en calorías o cantidades. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Corrección exitosa}\\
\textbf{Dado que} se envía un PUT a /meals/{id} con datos corregidos\\
\textbf{cuando} el sistema procesa la solicitud\\
\textbf{entonces} devuelve 200 OK con datos actualizados.\\[0.2em]

\textbf{Escenario 2: Registro inexistente}\\
\textbf{Dado que} el ID no corresponde a ningún registro\\
\textbf{cuando} el sistema busca\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Usuario no autorizado}\\
\textbf{Dado que} un usuario intenta editar un registro ajeno\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP03 \\
\hline

TUS-12 & Consultar comidas diarias & \textbf{Como} Developer, \textbf{quiero} un endpoint GET para consultar comidas del día, \textbf{para} mostrar al nutricionista y paciente el consumo diario. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta correcta}\\
\textbf{Dado que} se envía un GET a /meals?date=YYYY-MM-DD\\
\textbf{cuando} el sistema encuentra registros\\
\textbf{entonces} devuelve 200 OK con la lista de comidas.\\[0.2em]

\textbf{Escenario 2: Sin registros}\\
\textbf{Dado que} no existen comidas en esa fecha\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 200 OK con lista vacía.\\[0.2em]

\textbf{Escenario 3: Token inválido}\\
\textbf{Dado que} se envía un token incorrecto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP03 \\
\hline

TUS-13 & Registrar actividad física & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para registrar actividades físicas, \textbf{para} calcular calorías quemadas. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} se envía un POST a /activities con datos válidos\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 201 Created con detalles de la actividad.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} se envían valores negativos de duración o calorías\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario no autorizado}\\
\textbf{Dado que} se intenta registrar actividad sin token válido\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP04 \\
\hline

TUS-14 & Registrar pasos diarios & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para registrar pasos diarios, \textbf{para} complementar el balance energético. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro correcto}\\
\textbf{Dado que} se envía un POST a /steps con número positivo de pasos\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 201 Created con el conteo almacenado.\\[0.2em]

\textbf{Escenario 2: Número inválido}\\
\textbf{Dado que} se envían pasos negativos o en formato incorrecto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Token inválido}\\
\textbf{Dado que} se usa un token incorrecto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP04 \\
\hline

TUS-15 & Consultar resumen diario de pasos & \textbf{Como} Developer, \textbf{quiero} un endpoint GET para obtener el resumen de pasos y calorías, \textbf{para} que el usuario vea su balance energético. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta exitosa}\\
\textbf{Dado que} se envía un GET a /steps/summary?date=YYYY-MM-DD\\
\textbf{cuando} el sistema encuentra datos\\
\textbf{entonces} devuelve 200 OK con pasos y calorías quemadas.\\[0.2em]

\textbf{Escenario 2: Sin datos}\\
\textbf{Dado que} no hay registros para la fecha indicada\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 200 OK con resumen vacío.\\[0.2em]

\textbf{Escenario 3: Usuario no autorizado}\\
\textbf{Dado que} el token es inválido\\
\textbf{cuando} se realiza la consulta\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP04 \\
\hline

TUS-16 & Registrar peso del usuario & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para registrar el peso del usuario, \textbf{para} calcular métricas de progreso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro correcto}\\
\textbf{Dado que} se envía un POST a /weight con un valor positivo y token válido\\
\textbf{cuando} el sistema guarda el registro\\
\textbf{entonces} devuelve 201 Created con los datos del peso.\\[0.2em]

\textbf{Escenario 2: Valor inválido}\\
\textbf{Dado que} se envía un peso negativo o en formato incorrecto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no se incluye token válido\\
\textbf{cuando} el sistema procesa la solicitud\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP05 \\
\hline

TUS-17 & Calcular y consultar IMC & \textbf{Como} Developer, \textbf{quiero} un endpoint GET para calcular y consultar el IMC, \textbf{para} mostrar al usuario su estado de salud. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cálculo exitoso}\\
\textbf{Dado que} se envía un GET a /bmi con peso y altura válidos\\
\textbf{cuando} el sistema procesa los datos\\
\textbf{entonces} devuelve 200 OK con el valor del IMC.\\[0.2em]

\textbf{Escenario 2: Datos faltantes}\\
\textbf{Dado que} no se envía la altura en la solicitud\\
\textbf{cuando} el sistema intenta calcular\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario no autorizado}\\
\textbf{Dado que} no se incluye token válido\\
\textbf{cuando} se procesa la petición\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP05 \\
\hline

TUS-18 & Gestionar metas nutricionales & \textbf{Como} Developer, \textbf{quiero} un endpoint PUT para establecer metas de calorías y macros, \textbf{para} que el usuario tenga objetivos claros. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Metas establecidas}\\
\textbf{Dado que} se envía un PUT a /goals con calorías y macros válidos\\
\textbf{cuando} el sistema guarda la configuración\\
\textbf{entonces} devuelve 200 OK confirmando las metas.\\[0.2em]

\textbf{Escenario 2: Valores fuera de rango}\\
\textbf{Dado que} se envían calorías o macros inválidos\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un rol distinto al paciente intenta configurar metas\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP05 \\
\hline

TUS-19 & Programar recordatorios & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para programar recordatorios, \textbf{para} enviar alertas sobre comidas y peso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Programación correcta}\\
\textbf{Dado que} se envía un POST a /reminders con hora válida\\
\textbf{cuando} el sistema registra el recordatorio\\
\textbf{entonces} devuelve 201 Created con detalles.\\[0.2em]

\textbf{Escenario 2: Hora inválida}\\
\textbf{Dado que} se envía un formato de hora incorrecto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no se incluye token válido\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP06 \\
\hline

TUS-20 & Generar alertas por exceso o déficit & \textbf{Como} Developer, \textbf{quiero} un endpoint para detectar excesos o déficits calóricos, \textbf{para} notificar al usuario. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Detección correcta}\\
\textbf{Dado que} se envía un POST a /alerts con el balance diario\\
\textbf{cuando} el sistema detecta desviación\\
\textbf{entonces} devuelve 200 OK con alerta generada.\\[0.2em]

\textbf{Escenario 2: Balance dentro de rango}\\
\textbf{Dado que} el balance está dentro de la meta\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 204 No Content.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no se envía token válido\\
\textbf{cuando} se procesa la petición\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP06 \\
\hline

TUS-21 & Publicar contrato OpenAPI & \textbf{Como} Developer, \textbf{quiero} publicar el contrato OpenAPI 3.1, \textbf{para} documentar los endpoints disponibles. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso exitoso}\\
\textbf{Dado que} se envía un GET a /docs/openapi\\
\textbf{cuando} el sistema expone la documentación\\
\textbf{entonces} devuelve 200 OK con JSON OpenAPI.\\[0.2em]

\textbf{Escenario 2: Ruta inexistente}\\
\textbf{Dado que} se consulta un endpoint distinto\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no hay token válido\\
\textbf{cuando} se consulta la documentación\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP07 \\
\hline

TUS-22 & Manejo de errores con Problem Details & \textbf{Como} Developer, \textbf{quiero} que los errores usen Problem Details RFC 9457, \textbf{para} estandarizar respuestas. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Error 400}\\
\textbf{Dado que} el sistema recibe una solicitud inválida\\
\textbf{cuando} responde\\
\textbf{entonces} devuelve 400 con objeto Problem Details.\\[0.2em]

\textbf{Escenario 2: Error 404}\\
\textbf{Dado que} el recurso no existe\\
\textbf{cuando} el sistema responde\\
\textbf{entonces} devuelve 404 con Problem Details.\\[0.2em]

\textbf{Escenario 3: Error 500}\\
\textbf{Dado que} ocurre una falla interna\\
\textbf{cuando} se genera la respuesta\\
\textbf{entonces} devuelve 500 con Problem Details.\\
\end{tabular} & T-EP07 \\
\hline

TUS-23 & Controles de autorización por recurso & \textbf{Como} Developer, \textbf{quiero} implementar controles de autorización, \textbf{para} restringir acceso según rol y propiedad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso permitido}\\
\textbf{Dado que} un nutricionista consulta sus pacientes\\
\textbf{cuando} el rol coincide\\
\textbf{entonces} devuelve 200 OK.\\[0.2em]

\textbf{Escenario 2: Acceso denegado}\\
\textbf{Dado que} un usuario intenta acceder a un recurso ajeno\\
\textbf{cuando} el sistema valida permisos\\
\textbf{entonces} devuelve 403 Forbidden.\\[0.2em]

\textbf{Escenario 3: Token inválido}\\
\textbf{Dado que} no se incluye token válido\\
\textbf{cuando} se procesa la petición\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP07 \\
\hline

TUS-24 & Paginación y orden en listados & \textbf{Como} Developer, \textbf{quiero} endpoints con paginación y orden, \textbf{para} mejorar rendimiento en listados grandes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Listado con parámetros válidos}\\
\textbf{Dado que} se envía un GET a /patients?page=1\&size=10\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 200 OK con resultados paginados.\\[0.2em]

\textbf{Escenario 2: Parámetros inválidos}\\
\textbf{Dado que} se envía un valor negativo en page o size\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\[0.2em]

\textbf{Escenario 3: Sin parámetros}\\
\textbf{Dado que} no se envían parámetros de paginación\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve resultados por defecto (ej. 20 elementos).\\
\end{tabular} & T-EP07 \\
\hline

TUS-25 & Versionado de API & \textbf{Como} Developer, \textbf{quiero} implementar versionado en los endpoints, \textbf{para} garantizar compatibilidad entre clientes y backend. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso a versión específica}\\
\textbf{Dado que} se consulta GET /api/v1/patients\\
\textbf{cuando} la versión existe\\
\textbf{entonces} devuelve 200 OK con la respuesta correspondiente.\\[0.2em]

\textbf{Escenario 2: Versión inexistente}\\
\textbf{Dado que} se consulta GET /api/v3/patients\\
\textbf{cuando} la versión no está soportada\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Cliente sin especificar versión}\\
\textbf{Dado que} no se incluye prefijo de versión\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 400 Bad Request indicando versión requerida.\\
\end{tabular} & T-EP07 \\
\hline

TUS-26 & Observabilidad con métricas & \textbf{Como} Developer, \textbf{quiero} exponer métricas del sistema, \textbf{para} monitorear rendimiento y uso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso válido}\\
\textbf{Dado que} se consulta GET /metrics con token de admin\\
\textbf{cuando} el sistema responde\\
\textbf{entonces} devuelve 200 OK con métricas en formato Prometheus.\\[0.2em]

\textbf{Escenario 2: Usuario sin permisos}\\
\textbf{Dado que} un rol paciente intenta acceder a /metrics\\
\textbf{cuando} el sistema valida permisos\\
\textbf{entonces} devuelve 403 Forbidden.\\[0.2em]

\textbf{Escenario 3: Fallo interno}\\
\textbf{Dado que} ocurre un error en la recolección\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 500 Internal Server Error con Problem Details.\\
\end{tabular} & T-EP07 \\
\hline

TUS-27 & Auditoría y trazabilidad & \textbf{Como} Developer, \textbf{quiero} registrar acciones críticas en logs auditables, \textbf{para} cumplir normativas y revisar historial. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro correcto}\\
\textbf{Dado que} un nutricionista actualiza datos de paciente\\
\textbf{cuando} el sistema guarda la acción\\
\textbf{entonces} devuelve 200 OK y registra auditoría con timestamp.\\[0.2em]

\textbf{Escenario 2: Consulta de auditoría}\\
\textbf{Dado que} un admin consulta GET /audit/logs\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 200 OK con historial paginado.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un paciente intenta consultar logs\\
\textbf{cuando} el sistema valida rol\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP07 \\
\hline

TUS-28 & Reconocer alimentos desde imagen & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para subir imágenes, \textbf{para} identificar alimentos automáticamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Imagen válida}\\
\textbf{Dado que} se envía un POST a /food/recognize con foto en formato válido\\
\textbf{cuando} el sistema procesa la imagen\\
\textbf{entonces} devuelve 200 OK con lista de alimentos detectados.\\[0.2em]

\textbf{Escenario 2: Formato no soportado}\\
\textbf{Dado que} se envía imagen en formato no válido (ej. .txt)\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 415 Unsupported Media Type.\\[0.2em]

\textbf{Escenario 3: Imagen corrupta}\\
\textbf{Dado que} el archivo está dañado\\
\textbf{cuando} el sistema intenta procesarlo\\
\textbf{entonces} devuelve 422 Unprocessable Entity.\\
\end{tabular} & T-EP08 \\
\hline

TUS-29 & Estimar cantidad de alimento & \textbf{Como} Developer, \textbf{quiero} estimar gramos de alimento detectado, \textbf{para} calcular macros aproximados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Estimación exitosa}\\
\textbf{Dado que} el sistema detecta arroz en la imagen\\
\textbf{cuando} procesa el tamaño de la porción\\
\textbf{entonces} devuelve 200 OK con gramos estimados.\\[0.2em]

\textbf{Escenario 2: Sin confianza suficiente}\\
\textbf{Dado que} la IA no supera 50\% de confianza\\
\textbf{cuando} se procesa la imagen\\
\textbf{entonces} devuelve 200 OK con “porción desconocida”.\\[0.2em]

\textbf{Escenario 3: Datos faltantes}\\
\textbf{Dado que} no se incluyó categoría de referencia\\
\textbf{cuando} se procesa la estimación\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP08 \\
\hline

TUS-30 & Puntuaciones de confianza & \textbf{Como} Developer, \textbf{quiero} devolver score de confianza por alimento, \textbf{para} validar resultados al usuario. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Respuesta válida}\\
\textbf{Dado que} se detectan múltiples alimentos\\
\textbf{cuando} el sistema genera la salida\\
\textbf{entonces} devuelve 200 OK con cada alimento y su porcentaje de confianza.\\[0.2em]

\textbf{Escenario 2: IA sin resultados}\\
\textbf{Dado que} no se detecta ningún alimento\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 204 No Content.\\[0.2em]

\textbf{Escenario 3: Usuario no autenticado}\\
\textbf{Dado que} no hay token válido\\
\textbf{cuando} el sistema responde\\
\textbf{entonces} devuelve 401 Unauthorized.\\
\end{tabular} & T-EP08 \\
\hline

TUS-31 & Corrección manual de alimentos & \textbf{Como} Developer, \textbf{quiero} permitir correcciones de alimentos detectados, \textbf{para} que el usuario ajuste errores de la IA. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Corrección exitosa}\\
\textbf{Dado que} se envía un PUT a /food/corrections con ID válido\\
\textbf{cuando} el usuario actualiza nombre y cantidad\\
\textbf{entonces} devuelve 200 OK confirmando cambios.\\[0.2em]

\textbf{Escenario 2: Alimento no encontrado}\\
\textbf{Dado que} se envía un ID inexistente\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 404 Not Found.\\[0.2em]

\textbf{Escenario 3: Formato inválido}\\
\textbf{Dado que} el payload está incompleto\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP08 \\
\hline

TUS-32 & Catálogo de alimentos soportados & \textbf{Como} Developer, \textbf{quiero} publicar un catálogo de alimentos soportados, \textbf{para} guiar a la IA y al usuario en el registro. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta exitosa}\\
\textbf{Dado que} se consulta GET /food/catalog\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve 200 OK con lista de categorías y porciones.\\[0.2em]

\textbf{Escenario 2: Catálogo vacío}\\
\textbf{Dado que} no hay categorías registradas\\
\textbf{cuando} se procesa la consulta\\
\textbf{entonces} devuelve 204 No Content.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un rol no autorizado consulta /food/catalog\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP08 \\
\hline

TUS-33 & Gestión de consentimientos & \textbf{Como} Developer, \textbf{quiero} un endpoint para registrar consentimientos por finalidad de uso, \textbf{para} cumplir con normativas de privacidad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} se envía POST /consents con datos válidos\\
\textbf{cuando} el sistema guarda el consentimiento\\
\textbf{entonces} devuelve 201 Created con ID del consentimiento.\\[0.2em]

\textbf{Escenario 2: Consentimiento duplicado}\\
\textbf{Dado que} ya existe consentimiento para el mismo usuario y finalidad\\
\textbf{cuando} se intenta registrar de nuevo\\
\textbf{entonces} devuelve 409 Conflict.\\[0.2em]

\textbf{Escenario 3: Datos inválidos}\\
\textbf{Dado que} falta información en el payload\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP09 \\
\hline

TUS-34 & Cifrado en tránsito y en reposo & \textbf{Como} Developer, \textbf{quiero} que los datos estén cifrados en tránsito y reposo, \textbf{para} garantizar seguridad de la información. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Comunicación segura}\\
\textbf{Dado que} se realiza petición HTTPS\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} la conexión está cifrada con TLS.\\[0.2em]

\textbf{Escenario 2: Datos en reposo}\\
\textbf{Dado que} se guarda información sensible en BD\\
\textbf{cuando} el sistema persiste\\
\textbf{entonces} los datos quedan cifrados AES-256.\\[0.2em]

\textbf{Escenario 3: Intento de acceso inseguro}\\
\textbf{Dado que} un cliente envía HTTP sin TLS\\
\textbf{cuando} el sistema recibe\\
\textbf{entonces} devuelve 426 Upgrade Required.\\
\end{tabular} & T-EP09 \\
\hline

TUS-35 & Limpieza de metadatos en imágenes & \textbf{Como} Developer, \textbf{quiero} eliminar metadatos de imágenes, \textbf{para} proteger la privacidad de los usuarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Imagen procesada}\\
\textbf{Dado que} se sube imagen con EXIF\\
\textbf{cuando} el sistema guarda la imagen\\
\textbf{entonces} elimina metadatos antes de almacenar.\\[0.2em]

\textbf{Escenario 2: Imagen sin metadatos}\\
\textbf{Dado que} la foto no tiene EXIF\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} la guarda directamente.\\[0.2em]

\textbf{Escenario 3: Error en limpieza}\\
\textbf{Dado que} ocurre un fallo al limpiar\\
\textbf{cuando} se procesa la imagen\\
\textbf{entonces} devuelve 500 Internal Server Error.\\
\end{tabular} & T-EP09 \\
\hline

TUS-36 & Registro de uso de datos & \textbf{Como} Developer, \textbf{quiero} registrar el uso de datos sensibles, \textbf{para} auditoría y cumplimiento legal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro válido}\\
\textbf{Dado que} un nutricionista accede a datos de paciente\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} se registra en logs con timestamp.\\[0.2em]

\textbf{Escenario 2: Consulta de registros}\\
\textbf{Dado que} un admin consulta GET /data-usage\\
\textbf{cuando} el sistema responde\\
\textbf{entonces} devuelve historial auditable.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un rol paciente consulta /data-usage\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP09 \\
\hline

TUS-37 & Estado de sincronización en cliente & \textbf{Como} Developer, \textbf{quiero} mostrar indicadores de sincronización, \textbf{para} informar al usuario del progreso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Sincronización activa}\\
\textbf{Dado que} se inicia sincronización diaria\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} devuelve status=“In Progress”.\\[0.2em]

\textbf{Escenario 2: Sincronización exitosa}\\
\textbf{Dado que} se completó envío\\
\textbf{cuando} el backend confirma\\
\textbf{entonces} devuelve status=“Completed”.\\[0.2em]

\textbf{Escenario 3: Fallo de red}\\
\textbf{Dado que} no hay conexión estable\\
\textbf{cuando} el sistema intenta sincronizar\\
\textbf{entonces} devuelve status=“Failed”.\\
\end{tabular} & T-EP10 \\
\hline

TUS-38 & Cola local de cambios del día & \textbf{Como} Developer, \textbf{quiero} almacenar cambios en cola local, \textbf{para} enviarlos al backend en lote. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro en cola}\\
\textbf{Dado que} el usuario guarda comidas offline\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} agrega cambios a cola local.\\[0.2em]

\textbf{Escenario 2: Vaciar cola}\\
\textbf{Dado que} se completó sincronización\\
\textbf{cuando} se marca recibido\\
\textbf{entonces} la cola se vacía.\\[0.2em]

\textbf{Escenario 3: Error al persistir cola}\\
\textbf{Dado que} ocurre fallo en almacenamiento local\\
\textbf{cuando} se guarda cambio\\
\textbf{entonces} devuelve error al usuario.\\
\end{tabular} & T-EP10 \\
\hline

TUS-39 & Cierre de jornada & \textbf{Como} Developer, \textbf{quiero} implementar cierre de jornada con sello de corte, \textbf{para} definir datos diarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Corte exitoso}\\
\textbf{Dado que} se llega a la hora configurada\\
\textbf{cuando} el sistema procesa corte\\
\textbf{entonces} asigna sello diario.\\[0.2em]

\textbf{Escenario 2: Corte manual}\\
\textbf{Dado que} el admin ejecuta POST /cutoff\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} asigna sello inmediato.\\[0.2em]

\textbf{Escenario 3: Error en corte}\\
\textbf{Dado que} ocurre fallo en operación\\
\textbf{cuando} se ejecuta\\
\textbf{entonces} devuelve 500 Internal Server Error.\\
\end{tabular} & T-EP10 \\
\hline

TUS-40 & Envío en lote de registros & \textbf{Como} Developer, \textbf{quiero} enviar registros en lote al final del día, \textbf{para} optimizar recursos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Lote exitoso}\\
\textbf{Dado que} hay datos en cola\\
\textbf{cuando} el sistema ejecuta POST /sync/batch\\
\textbf{entonces} devuelve 200 OK confirmando recepción.\\[0.2em]

\textbf{Escenario 2: Lote duplicado}\\
\textbf{Dado que} se reenvía mismo lote\\
\textbf{cuando} el backend valida\\
\textbf{entonces} devuelve 409 Conflict.\\[0.2em]

\textbf{Escenario 3: Error de red}\\
\textbf{Dado que} no hay conexión\\
\textbf{cuando} se intenta enviar lote\\
\textbf{entonces} se reprograma envío.\\
\end{tabular} & T-EP10 \\
\hline

TUS-41 & Reintentos con backoff exponencial & \textbf{Como} Developer, \textbf{quiero} reintentos con backoff, \textbf{para} asegurar entrega de datos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Primer reintento}\\
\textbf{Dado que} el envío falla\\
\textbf{cuando} se reprograma\\
\textbf{entonces} se ejecuta en 30s.\\[0.2em]

\textbf{Escenario 2: Segundo reintento}\\
\textbf{Dado que} falla de nuevo\\
\textbf{cuando} se reprograma\\
\textbf{entonces} se ejecuta en 60s.\\[0.2em]

\textbf{Escenario 3: Éxito tras reintento}\\
\textbf{Dado que} tercer envío es exitoso\\
\textbf{cuando} el backend confirma\\
\textbf{entonces} el sistema marca lote como enviado.\\
\end{tabular} & T-EP10 \\
\hline

TUS-42 & Idempotencia en lotes & \textbf{Como} Developer, \textbf{quiero} claves únicas en cada lote, \textbf{para} evitar duplicados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Lote único}\\
\textbf{Dado que} se envía POST /sync/batch con clave X\\
\textbf{cuando} backend valida\\
\textbf{entonces} lo guarda.\\[0.2em]

\textbf{Escenario 2: Reenvío mismo lote}\\
\textbf{Dado que} se envía misma clave X\\
\textbf{cuando} backend valida\\
\textbf{entonces} devuelve 200 OK sin duplicar.\\[0.2em]

\textbf{Escenario 3: Clave inválida}\\
\textbf{Dado que} se omite clave\\
\textbf{cuando} se procesa\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP10 \\
\hline

TUS-43 & Confirmación de backend & \textbf{Como} Developer, \textbf{quiero} confirmar recepción de datos, \textbf{para} marcar localmente enviados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Confirmación exitosa}\\
\textbf{Dado que} backend recibe lote\\
\textbf{cuando} responde 200 OK\\
\textbf{entonces} cliente marca datos como enviados.\\[0.2em]

\textbf{Escenario 2: Sin confirmación}\\
\textbf{Dado que} backend no responde\\
\textbf{cuando} pasa timeout\\
\textbf{entonces} cliente mantiene datos en cola.\\[0.2em]

\textbf{Escenario 3: Error backend}\\
\textbf{Dado que} responde 500\\
\textbf{cuando} procesa lote\\
\textbf{entonces} cliente reintenta envío.\\
\end{tabular} & T-EP10 \\
\hline

TUS-44 & Descarte de duplicados & \textbf{Como} Developer, \textbf{quiero} descartar duplicados en servidor, \textbf{para} mantener integridad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Duplicado detectado}\\
\textbf{Dado que} lote tiene misma clave\\
\textbf{cuando} backend procesa\\
\textbf{entonces} ignora duplicado.\\[0.2em]

\textbf{Escenario 2: Registro único}\\
\textbf{Dado que} clave es nueva\\
\textbf{cuando} se procesa\\
\textbf{entonces} guarda datos.\\[0.2em]

\textbf{Escenario 3: Error en validación}\\
\textbf{Dado que} clave está corrupta\\
\textbf{cuando} se valida\\
\textbf{entonces} devuelve 400.\\
\end{tabular} & T-EP10 \\
\hline

TUS-45 & Manejo de timestamps & \textbf{Como} Developer, \textbf{quiero} timestamps en RFC3339, \textbf{para} asegurar consistencia temporal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Timestamp válido}\\
\textbf{Dado que} cliente envía timestamp RFC3339\\
\textbf{cuando} backend valida\\
\textbf{entonces} guarda registro.\\[0.2em]

\textbf{Escenario 2: Timestamp inválido}\\
\textbf{Dado que} cliente envía formato incorrecto\\
\textbf{cuando} backend valida\\
\textbf{entonces} devuelve 400.\\[0.2em]

\textbf{Escenario 3: Diferencia de zona}\\
\textbf{Dado que} timestamp incluye zona UTC-5\\
\textbf{cuando} backend procesa\\
\textbf{entonces} normaliza a UTC.\\
\end{tabular} & T-EP10 \\
\hline

TUS-46 & Reprogramación de envío & \textbf{Como} Developer, \textbf{quiero} reprogramar envío fallido, \textbf{para} lograr sincronización eventual. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Fallo inicial}\\
\textbf{Dado que} POST /sync falla\\
\textbf{cuando} pasa timeout\\
\textbf{entonces} sistema agenda nuevo intento.\\[0.2em]

\textbf{Escenario 2: Reintento exitoso}\\
\textbf{Dado que} backend responde 200 en segundo intento\\
\textbf{cuando} cliente reenvía\\
\textbf{entonces} marca lote como enviado.\\[0.2em]

\textbf{Escenario 3: Fallo persistente}\\
\textbf{Dado que} backend sigue respondiendo error\\
\textbf{cuando} se alcanzan 3 intentos\\
\textbf{entonces} se registra error crítico.\\
\end{tabular} & T-EP10 \\
\hline

TUS-47 & Estado visible de sincronización & \textbf{Como} Developer, \textbf{quiero} mostrar estado de sincronización, \textbf{para} dar transparencia al usuario. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Estado progresivo}\\
\textbf{Dado que} proceso está corriendo\\
\textbf{cuando} cliente consulta /sync/status\\
\textbf{entonces} devuelve “In Progress”.\\[0.2em]

\textbf{Escenario 2: Estado completado}\\
\textbf{Dado que} lote ya se envió\\
\textbf{cuando} cliente consulta /sync/status\\
\textbf{entonces} devuelve “Completed”.\\[0.2em]

\textbf{Escenario 3: Estado fallido}\\
\textbf{Dado que} envío falló\\
\textbf{cuando} cliente consulta /sync/status\\
\textbf{entonces} devuelve “Failed”.\\
\end{tabular} & T-EP10 \\ \hline
\hline

TUS-49 & Endpoint para iniciar suscripción & 
\textbf{Como} developer, \textbf{quiero} crear un endpoint que inicie una suscripción en Culqi con el plan seleccionado, \textbf{para} procesar el alta de forma segura. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Suscripción iniciada exitosamente}\\
\textbf{Dado que} el nutricionista selecciona un plan válido\\
\textbf{cuando} se realiza un POST al endpoint con el ID del plan y datos de pago\\
\textbf{entonces} el sistema responde 201 con el ID de la suscripción generada en Culqi.\\[0.2em]

\textbf{Escenario 2: Datos inválidos}\\
\textbf{Dado que} el request no contiene datos obligatorios (ej. ID de plan, token de pago)\\
\textbf{cuando} se procesa el request\\
\textbf{entonces} el sistema responde 400 indicando campos faltantes.\\[0.2em]

\textbf{Escenario 3: Error en Culqi}\\
\textbf{Dado que} el endpoint se comunica con Culqi\\
\textbf{cuando} Culqi devuelve un error en la transacción\\
\textbf{entonces} el sistema responde 502 con el detalle del fallo externo.\\
\end{tabular} & T-EP12 \\
\hline

TUS-50 & Verificación de transacción & 
\textbf{Como} developer, \textbf{quiero} verificar el callback de Culqi para confirmar el pago, \textbf{para} validar la suscripción del nutricionista. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Callback válido}\\
\textbf{Dado que} Culqi envía un webhook con firma válida\\
\textbf{cuando} el sistema recibe la notificación\\
\textbf{entonces} marca la transacción como confirmada y activa la suscripción.\\[0.2em]

\textbf{Escenario 2: Firma inválida}\\
\textbf{Dado que} Culqi envía un webhook con firma incorrecta o manipulada\\
\textbf{cuando} el sistema valida la firma\\
\textbf{entonces} descarta la notificación y responde 401.\\[0.2em]

\textbf{Escenario 3: Evento desconocido}\\
\textbf{Dado que} Culqi envía un webhook con un evento no soportado\\
\textbf{cuando} el sistema procesa el evento\\
\textbf{entonces} registra un log de advertencia y responde 200 sin cambios.\\
\end{tabular} & T-EP12 \\
\hline

TUS-51 & Registro de estado de suscripción & 
\textbf{Como} developer, \textbf{quiero} registrar el estado de la suscripción del nutricionista en base al pago (activo, vencido, cancelado), \textbf{para} mantener coherencia en la base de datos. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Activación correcta}\\
\textbf{Dado que} un pago es confirmado por Culqi\\
\textbf{cuando} el sistema procesa la transacción\\
\textbf{entonces} actualiza el estado de la suscripción a “Activo”.\\[0.2em]

\textbf{Escenario 2: Suscripción cancelada}\\
\textbf{Dado que} el nutricionista solicita la cancelación desde la plataforma\\
\textbf{cuando} el sistema procesa la orden\\
\textbf{entonces} cambia el estado de la suscripción a “Cancelado”.\\[0.2em]

\textbf{Escenario 3: Suscripción vencida}\\
\textbf{Dado que} el ciclo de pago del nutricionista expira\\
\textbf{cuando} el sistema detecta la falta de pago en la fecha de corte\\
\textbf{entonces} actualiza el estado a “Vencido”.\\
\end{tabular} & T-EP12 \\
\hline

TUS-52 & Servicio de consulta de estado & 
\textbf{Como} developer, \textbf{quiero} implementar un servicio que muestre la fecha del próximo cobro y el estado actual, \textbf{para} que el nutricionista consulte su suscripción. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta exitosa}\\
\textbf{Dado que} el nutricionista tiene una suscripción activa\\
\textbf{cuando} realiza un GET al servicio de estado\\
\textbf{entonces} el sistema devuelve 200 con el estado “Activo” y la fecha del próximo cobro.\\[0.2em]

\textbf{Escenario 2: Suscripción inexistente}\\
\textbf{Dado que} el nutricionista no posee suscripción activa\\
\textbf{cuando} realiza un GET al servicio de estado\\
\textbf{entonces} el sistema devuelve 404 indicando que no existe suscripción registrada.\\[0.2em]

\textbf{Escenario 3: Error en la consulta}\\
\textbf{Dado que} el nutricionista realiza una consulta\\
\textbf{cuando} ocurre un fallo en la base de datos o en la integración con Culqi\\
\textbf{entonces} el sistema responde 500 con un mensaje de error temporal.\\
\end{tabular} & T-EP12 \\
\hline

\end{longtable}

\newpage

## Impact Mapping  

El Impact Map es una herramienta de planificación estratégica que permite alinear los objetivos de negocio con las necesidades de los usuarios y las funcionalidades del sistema. Su propósito es asegurar que cada característica del producto contribuya de forma clara y medible al cumplimiento de un objetivo central.

A partir del objetivo principal del sistema —mejorar el seguimiento nutricional y la adherencia del paciente mediante una solución tecnológica accesible y confiable— se identifican los actores involucrados, los cambios de comportamiento esperados y las funcionalidades clave que permitirán alcanzar dicho resultado.

Este enfoque visual permite priorizar funcionalidades, evitando el desarrollo de características irrelevantes, y garantiza que cada acción dentro del sistema esté respaldada por una lógica de impacto real en la experiencia del usuario y los resultados clínicos.

A continuación, se presentan los Impact Maps para los dos segmentos principales:

**Impact Map – Segmento 1: Nutricionistas Clínicos y Deportivos**

![Artefacto creado en UXPressia](src/img/cap3/ImpactMapping1.png)

\newpage

**Impact Map – Segmento 2: Pacientes interesados en mejorar su alimentación**

![Artefacto creado en UXPressia](src/img/cap3/ImpactMapping2.png)

\newpage


## Product Backlog

Una de las técnicas más utilizadas para estimar el esfuerzo necesario para completar cada tarea es la escala de Fibonacci, la cual permite asignar puntos de historia de manera proporcional a la complejidad y tiempo requerido. 

\vspace{1em}

\begin{quote}
Como señala Smith (2020), esta escala no lineal facilita la identificación de tareas que requieren un mayor esfuerzo, lo que resulta en una planificación más precisa y eficiente.
\end{quote}

\vspace{1em}

A continuación, se presentan la tablas de nuestros *Product Backlog* para cada segmento objetivo, demostrando cómo se alinean nuestros recursos con las necesidades más urgentes de nuestros usuarios.

\begin{longtable}{|c|p{1cm}|p{3.5cm}|p{7cm}|p{1cm}|}
\hline
\# Orden & \textbf{ID} & \textbf{Título} & \textbf{Descripción} & \textbf{Story Points} \\
\hline
1 & \textbf{LP-US01} & Visualización de propuesta de valor clara & \textbf{Como} visitante, \textbf{quiero} visualizar claramente la propuesta de valor, \textbf{para} comprender qué ofrece la aplicación. & 3 \\
\hline
2 & \textbf{LP-US02} & Identificación de segmento médico & \textbf{Como} visitante, \textbf{quiero} identificar el segmento médico, \textbf{para} saber cómo la aplicación atiende sus necesidades. & 2 \\
\hline
3 & \textbf{LP-US03} & Identificación de segmento paciente & \textbf{Como} visitante, \textbf{quiero} identificar el segmento paciente, \textbf{para} entender cómo me beneficiará la solución. & 2 \\
\hline
4 & \textbf{LP-US04} & Evidencia y testimonios & \textbf{Como} visitante, \textbf{quiero} ver evidencias y testimonios, \textbf{para} confiar en la aplicación. & 2 \\
\hline
5 & \textbf{LP-US05} & Ruta de producto & \textbf{Como} visitante, \textbf{quiero} conocer la ruta de producto, \textbf{para} ver la evolución de la aplicación. & 3 \\
\hline
6 & \textbf{LP-US06} & Acción principal de conversión & \textbf{Como} visitante, \textbf{quiero} contar con un botón claro de conversión, \textbf{para} iniciar relación con el equipo. & 2 \\
\hline
7 & \textbf{LP-US07} & Captura de interés del médico & \textbf{Como} visitante médico, \textbf{quiero} registrar mi interés, \textbf{para} recibir información personalizada. & 2 \\
\hline
8 & \textbf{LP-US08} & Captura de interés del paciente & \textbf{Como} visitante paciente, \textbf{quiero} registrar mi interés, \textbf{para} recibir información útil. & 2 \\
\hline
9 & \textbf{LP-US09} & Información de contacto verificada & \textbf{Como} visitante, \textbf{quiero} acceder a información de contacto verificada, \textbf{para} comunicarme con el equipo. & 2 \\
\hline
10 & \textbf{LP-US10} & Ver demo del producto & \textbf{Como} visitante, \textbf{quiero} ver una demo del producto, \textbf{para} comprender sus funcionalidades. & 3 \\
\hline
11 & \textbf{LP-US11} & Compartir en redes sociales & \textbf{Como} visitante, \textbf{quiero} compartir el producto en redes sociales, \textbf{para} difundir la solución. & 2 \\
\hline
12 & \textbf{LP-US12} & Políticas y privacidad & \textbf{Como} visitante, \textbf{quiero} acceder a políticas y privacidad, \textbf{para} sentir confianza antes de registrarme. & 2 \\
\hline
13 & \textbf{LP-US13} & Soporte multiplataforma & \textbf{Como} visitante, \textbf{quiero} conocer la compatibilidad multiplataforma, \textbf{para} saber si funciona en mis dispositivos. & 2 \\
\hline
14 & \textbf{LP-US14} & Preguntas frecuentes & \textbf{Como} visitante, \textbf{quiero} acceder a preguntas frecuentes, \textbf{para} resolver dudas comunes. & 2 \\
\hline
15 & \textbf{LP-US15} & Descubrimiento en buscadores & \textbf{Como} visitante, \textbf{quiero} que el producto aparezca en buscadores, \textbf{para} encontrarlo fácilmente. & 2 \\
\hline
16 & \textbf{WEB-US01} & Registro de cuenta de nutricionista & \textbf{Como} nutricionista, \textbf{quiero} registrar mi cuenta, \textbf{para} acceder al sistema. & 3 \\
\hline
17 & \textbf{WEB-US03} & Inicio de sesión & \textbf{Como} nutricionista, \textbf{quiero} iniciar sesión, \textbf{para} acceder de forma segura a mi cuenta. & 3 \\
\hline
18 & \textbf{WEB-US04} & Cierre de sesión & \textbf{Como} nutricionista, \textbf{quiero} cerrar sesión, \textbf{para} proteger mis datos. & 2 \\
\hline
19 & \textbf{WEB-US05} & Recuperación de contraseña & \textbf{Como} nutricionista, \textbf{quiero} recuperar mi contraseña, \textbf{para} restablecer acceso en caso de olvido. & 3 \\
\hline
20 & \textbf{WEB-US06} & Gestión de perfil & \textbf{Como} nutricionista, \textbf{quiero} gestionar mi perfil, \textbf{para} mantener actualizada mi información. & 3 \\
\hline
21 & \textbf{WEB-US07} & Registro de pacientes nuevos & \textbf{Como} nutricionista, \textbf{quiero} registrar pacientes, \textbf{para} darles seguimiento. & 5 \\
\hline
22 & \textbf{WEB-US08} & Edición de pacientes & \textbf{Como} nutricionista, \textbf{quiero} editar la información de pacientes, \textbf{para} mantener sus datos al día. & 3 \\
\hline
23 & \textbf{WEB-US09} & Eliminación de pacientes & \textbf{Como} nutricionista, \textbf{quiero} eliminar o desactivar pacientes, \textbf{para} mantener una lista limpia. & 3 \\
\hline
24 & \textbf{WEB-US10} & Búsqueda de pacientes & \textbf{Como} nutricionista, \textbf{quiero} buscar pacientes, \textbf{para} localizarlos rápidamente. & 3 \\
\hline
25 & \textbf{WEB-US11} & Visualizar alimentos diarios & \textbf{Como} nutricionista, \textbf{quiero} ver alimentos consumidos, \textbf{para} analizar su dieta. & 3 \\
\hline
26 & \textbf{WEB-US12} & Visualización de macros & \textbf{Como} nutricionista, \textbf{quiero} ver macros y calorías, \textbf{para} evaluar la dieta. & 3 \\
\hline
27 & \textbf{WEB-US13} & Historial diario y semanal & \textbf{Como} nutricionista, \textbf{quiero} ver historial de calorías, \textbf{para} evaluar progresos semanales. & 5 \\
\hline
28 & \textbf{WEB-US14} & Rutinas de ejercicio & \textbf{Como} nutricionista, \textbf{quiero} visualizar rutinas, \textbf{para} complementar la dieta. & 3 \\
\hline
29 & \textbf{WEB-US15} & Calorías gastadas & \textbf{Como} nutricionista, \textbf{quiero} ver calorías gastadas, \textbf{para} analizar balance energético. & 3 \\
\hline
30 & \textbf{WEB-US16} & Crear rutinas & \textbf{Como} nutricionista, \textbf{quiero} crear rutinas, \textbf{para} personalizar el plan del paciente. & 5 \\
\hline
31 & \textbf{WEB-US17} & Asignar metas & \textbf{Como} nutricionista, \textbf{quiero} asignar metas de calorías y macros, \textbf{para} dar objetivos personalizados. & 3 \\
\hline
32 & \textbf{WEB-US18} & Recomendaciones & \textbf{Como} nutricionista, \textbf{quiero} registrar recomendaciones, \textbf{para} guiar al paciente. & 2 \\
\hline
33 & \textbf{WEB-US19} & Reporte de evolución de peso & \textbf{Como} nutricionista, \textbf{quiero} generar reportes de peso, \textbf{para} evaluar cambios en el tiempo. & 3 \\
\hline
34 & \textbf{WEB-US20} & Dashboard de progreso & \textbf{Como} nutricionista, \textbf{quiero} ver gráficas de progreso, \textbf{para} analizar evolución de pacientes. & 5 \\
\hline
35 & \textbf{WEB-US21} & Reportes descargables & \textbf{Como} nutricionista, \textbf{quiero} descargar reportes, \textbf{para} compartir con pacientes. & 3 \\
\hline
36 & \textbf{MOB-US01} & Registro de usuario nuevo & \textbf{Como} paciente, \textbf{quiero} registrarme en la app, \textbf{para} empezar a usarla. & 3 \\
\hline
37 & \textbf{MOB-US02} & Inicio de sesión & \textbf{Como} paciente, \textbf{quiero} iniciar sesión, \textbf{para} acceder a mis datos. & 3 \\
\hline
38 & \textbf{MOB-US03} & Cierre de sesión & \textbf{Como} paciente, \textbf{quiero} cerrar sesión, \textbf{para} proteger mis datos. & 2 \\
\hline
39 & \textbf{MOB-US04} & Recuperación de contraseña & \textbf{Como} paciente, \textbf{quiero} recuperar mi contraseña, \textbf{para} acceder en caso de olvido. & 3 \\
\hline
40 & \textbf{MOB-US05} & Gestión de perfil & \textbf{Como} paciente, \textbf{quiero} gestionar mi perfil, \textbf{para} mantener mis datos correctos. & 3 \\
\hline
41 & \textbf{MOB-US06} & Resumen diario inicial & \textbf{Como} paciente, \textbf{quiero} ver un resumen de calorías y macros, \textbf{para} controlar mi día. & 3 \\
\hline
42 & \textbf{MOB-US07} & Cálculo de IMC & \textbf{Como} paciente, \textbf{quiero} calcular mi IMC, \textbf{para} conocer mi estado físico. & 3 \\
\hline
43 & \textbf{MOB-US08} & Historial diario/semanal & \textbf{Como} paciente, \textbf{quiero} ver mi historial diario y semanal, \textbf{para} analizar mi progreso. & 5 \\
\hline
44 & \textbf{MOB-US09} & Registro de comidas con foto & \textbf{Como} paciente, \textbf{quiero} registrar mis comidas con foto, \textbf{para} facilitar el ingreso de alimentos. & 5 \\
\hline
45 & \textbf{MOB-US10} & Modificar comida registrada & \textbf{Como} paciente, \textbf{quiero} modificar alimentos detectados, \textbf{para} corregir cantidades o errores. & 3 \\
\hline
46 & \textbf{MOB-US11} & Ver macros por comida & \textbf{Como} paciente, \textbf{quiero} ver macros por comida registrada, \textbf{para} analizar el aporte individual. & 3 \\
\hline
47 & \textbf{MOB-US12} & Registro de actividad manual & \textbf{Como} paciente, \textbf{quiero} registrar actividades manualmente, \textbf{para} reflejar mi esfuerzo. & 3 \\
\hline
48 & \textbf{MOB-US13} & Balance diario & \textbf{Como} paciente, \textbf{quiero} ver el balance entre calorías consumidas y gastadas, \textbf{para} controlar mi salud. & 3 \\
\hline
49 & \textbf{MOB-US14} & Registro de pasos & \textbf{Como} paciente, \textbf{quiero} registrar mis pasos, \textbf{para} estimar calorías quemadas. & 3 \\
\hline
50 & \textbf{MOB-US15} & Registro y gráfico de peso & \textbf{Como} paciente, \textbf{quiero} registrar mi peso y ver gráficos, \textbf{para} analizar mi evolución. & 3 \\
\hline
51 & \textbf{MOB-US16} & Ajuste de metas & \textbf{Como} paciente, \textbf{quiero} ajustar mis metas, \textbf{para} mantenerme en el plan. & 3 \\
\hline
52 & \textbf{MOB-US17} & Visualización semanal & \textbf{Como} paciente, \textbf{quiero} visualizar mis resultados semanales, \textbf{para} revisar mi cumplimiento. & 3 \\
\hline
53 & \textbf{MOB-US18} & Notificaciones de comidas & \textbf{Como} paciente, \textbf{quiero} recibir notificaciones de comidas, \textbf{para} registrar con constancia. & 2 \\
\hline
54 & \textbf{MOB-US19} & Alertas de metas & \textbf{Como} paciente, \textbf{quiero} recibir alertas de exceso o déficit, \textbf{para} ajustar mi dieta. & 3 \\
\hline
55 & \textbf{MOB-US20} & Consejos personalizados & \textbf{Como} paciente, \textbf{quiero} recibir consejos personalizados, \textbf{para} mejorar mis hábitos. & 3 \\
\hline
56 & \textbf{TUS-01} & Registro seguro de usuario & \textbf{Como} developer, \textbf{quiero} implementar registro seguro, \textbf{para} garantizar la creación confiable de cuentas. & 5 \\
\hline
57 & \textbf{TUS-02} & Inicio de sesión seguro & \textbf{Como} developer, \textbf{quiero} implementar inicio de sesión seguro, \textbf{para} permitir acceso confiable a los usuarios. & 5 \\
\hline
58 & \textbf{TUS-03} & Cierre de sesión seguro & \textbf{Como} developer, \textbf{quiero} habilitar cierre de sesión seguro, \textbf{para} proteger la información del usuario. & 3 \\
\hline
59 & \textbf{TUS-04} & Recuperación de contraseña & \textbf{Como} developer, \textbf{quiero} implementar recuperación de contraseña, \textbf{para} restablecer accesos de usuarios olvidadizos. & 3 \\
\hline
60 & \textbf{TUS-05} & Actualización de perfil & \textbf{Como} developer, \textbf{quiero} permitir actualización de perfil, \textbf{para} mantener los datos de usuario actualizados. & 3 \\
\hline
61 & \textbf{TUS-06} & Crear paciente & \textbf{Como} developer, \textbf{quiero} implementar endpoint para crear paciente, \textbf{para} registrar nuevos usuarios en el sistema. & 5 \\
\hline
62 & \textbf{TUS-07} & Obtener paciente & \textbf{Como} developer, \textbf{quiero} obtener información de un paciente, \textbf{para} mostrarla al nutricionista. & 3 \\
\hline
63 & \textbf{TUS-08} & Actualizar paciente & \textbf{Como} developer, \textbf{quiero} actualizar información de un paciente, \textbf{para} mantener datos correctos. & 3 \\
\hline
64 & \textbf{TUS-09} & Desactivar paciente & \textbf{Como} developer, \textbf{quiero} desactivar pacientes, \textbf{para} mantener registros vigentes sin eliminarlos. & 3 \\
\hline
65 & \textbf{TUS-10} & Registrar comida & \textbf{Como} developer, \textbf{quiero} permitir registrar comidas, \textbf{para} guardar la dieta del usuario. & 5 \\
\hline
66 & \textbf{TUS-11} & Corregir comida & \textbf{Como} developer, \textbf{quiero} habilitar corrección de comidas, \textbf{para} ajustar datos detectados erróneamente. & 3 \\
\hline
67 & \textbf{TUS-12} & Consultar consumo diario & \textbf{Como} developer, \textbf{quiero} consultar el consumo diario, \textbf{para} mostrar resúmenes nutricionales. & 3 \\
\hline
68 & \textbf{TUS-13} & Registrar actividad física & \textbf{Como} developer, \textbf{quiero} registrar actividad física, \textbf{para} reflejar esfuerzo del usuario. & 3 \\
\hline
69 & \textbf{TUS-14} & Registrar pasos & \textbf{Como} developer, \textbf{quiero} registrar pasos diarios, \textbf{para} calcular calorías quemadas. & 3 \\
\hline
70 & \textbf{TUS-15} & Consultar resumen de pasos & \textbf{Como} developer, \textbf{quiero} consultar resumen de pasos, \textbf{para} generar balance energético. & 3 \\
\hline
71 & \textbf{TUS-16} & Registrar peso & \textbf{Como} developer, \textbf{quiero} registrar peso de usuario, \textbf{para} monitorear evolución. & 3 \\
\hline
72 & \textbf{TUS-17} & Calcular IMC & \textbf{Como} developer, \textbf{quiero} calcular y consultar IMC, \textbf{para} determinar estado de salud. & 3 \\
\hline
73 & \textbf{TUS-18} & Gestionar metas & \textbf{Como} developer, \textbf{quiero} gestionar metas de calorías y macros, \textbf{para} personalizar objetivos. & 5 \\
\hline
74 & \textbf{TUS-19} & Programar recordatorios & \textbf{Como} developer, \textbf{quiero} programar recordatorios automáticos, \textbf{para} mantener la constancia del usuario. & 3 \\
\hline
75 & \textbf{TUS-20} & Detectar exceso/déficit & \textbf{Como} developer, \textbf{quiero} detectar exceso o déficit en la dieta, \textbf{para} generar alertas. & 3 \\
\hline
76 & \textbf{TUS-21} & Publicar contrato OpenAPI & \textbf{Como} developer, \textbf{quiero} publicar contrato OpenAPI 3.1, \textbf{para} documentar la API. & 3 \\
\hline
77 & \textbf{TUS-22} & Manejo de errores estándar & \textbf{Como} developer, \textbf{quiero} usar Problem Details RFC 9457, \textbf{para} gestionar errores de forma uniforme. & 3 \\
\hline
78 & \textbf{TUS-23} & Controles de autorización & \textbf{Como} developer, \textbf{quiero} implementar autorización granular, \textbf{para} proteger recursos sensibles. & 5 \\
\hline
79 & \textbf{TUS-24} & Paginación y orden & \textbf{Como} developer, \textbf{quiero} implementar paginación y orden, \textbf{para} optimizar listados grandes. & 3 \\
\hline
80 & \textbf{TUS-25} & Versionado estable & \textbf{Como} developer, \textbf{quiero} versionar la API, \textbf{para} mantener estabilidad en cambios futuros. & 3 \\
\hline
81 & \textbf{TUS-26} & Observabilidad con métricas & \textbf{Como} developer, \textbf{quiero} habilitar métricas y trazas, \textbf{para} monitorear el sistema. & 5 \\
\hline
82 & \textbf{TUS-27} & Auditoría de cambios & \textbf{Como} developer, \textbf{quiero} auditar cambios, \textbf{para} garantizar trazabilidad de datos. & 3 \\
\hline
83 & \textbf{TUS-28} & Reconocimiento de alimentos & \textbf{Como} developer, \textbf{quiero} reconocer alimentos en imágenes, \textbf{para} identificar comidas automáticamente. & 5 \\
\hline
84 & \textbf{TUS-29} & Estimación de cantidades & \textbf{Como} developer, \textbf{quiero} estimar cantidad de alimentos, \textbf{para} calcular macros. & 5 \\
\hline
85 & \textbf{TUS-30} & Puntuaciones de confianza & \textbf{Como} developer, \textbf{quiero} devolver puntuaciones de confianza, \textbf{para} indicar certeza en detecciones. & 3 \\
\hline
86 & \textbf{TUS-31} & Corrección manual de IA & \textbf{Como} developer, \textbf{quiero} permitir corrección manual, \textbf{para} mejorar precisión del registro. & 3 \\
\hline
87 & \textbf{TUS-32} & Catálogo de alimentos & \textbf{Como} developer, \textbf{quiero} publicar catálogo de alimentos y porciones, \textbf{para} estandarizar registros. & 5 \\
\hline
88 & \textbf{TUS-33} & Gestión de consentimientos & \textbf{Como} developer, \textbf{quiero} gestionar consentimientos por finalidad, \textbf{para} cumplir con normas de privacidad. & 5 \\
\hline
89 & \textbf{TUS-34} & Cifrado en tránsito y reposo & \textbf{Como} developer, \textbf{quiero} cifrar datos en tránsito y reposo, \textbf{para} garantizar seguridad. & 5 \\
\hline
90 & \textbf{TUS-35} & Limpieza de metadatos & \textbf{Como} developer, \textbf{quiero} limpiar metadatos de imágenes, \textbf{para} proteger privacidad del usuario. & 3 \\
\hline
91 & \textbf{TUS-36} & Registro de uso de datos & \textbf{Como} developer, \textbf{quiero} registrar uso de datos, \textbf{para} cumplir con auditorías y normativas. & 3 \\
\hline
92 & \textbf{TUS-37} & Indicadores de sincronización & \textbf{Como} developer, \textbf{quiero} mostrar indicadores de sincronización, \textbf{para} informar al usuario. & 3 \\
\hline
93 & \textbf{TUS-38} & Cola local de cambios & \textbf{Como} developer, \textbf{quiero} mantener cola local de cambios, \textbf{para} asegurar persistencia antes de envío. & 5 \\
\hline
94 & \textbf{TUS-39} & Cierre de jornada & \textbf{Como} developer, \textbf{quiero} implementar cierre de jornada, \textbf{para} definir datos a sincronizar. & 3 \\
\hline
95 & \textbf{TUS-40} & Envío en lote & \textbf{Como} developer, \textbf{quiero} enviar registros en lote, \textbf{para} optimizar red y recursos. & 5 \\
\hline
96 & \textbf{TUS-41} & Reintentos automáticos & \textbf{Como} developer, \textbf{quiero} reintentos con backoff, \textbf{para} asegurar entrega de datos. & 5 \\
\hline
97 & \textbf{TUS-42} & Idempotencia en lotes & \textbf{Como} developer, \textbf{quiero} usar claves únicas en lotes, \textbf{para} evitar duplicados. & 5 \\
\hline
98 & \textbf{TUS-43} & Confirmación del backend & \textbf{Como} developer, \textbf{quiero} confirmar recepción del backend, \textbf{para} marcar datos como enviados. & 3 \\
\hline
99 & \textbf{TUS-44} & Detección de duplicados & \textbf{Como} developer, \textbf{quiero} detectar duplicados en servidor, \textbf{para} mantener integridad. & 5 \\
\hline
100 & \textbf{TUS-45} & Manejo de timestamps & \textbf{Como} developer, \textbf{quiero} usar timestamps RFC 3339 con zona horaria, \textbf{para} asegurar consistencia. & 3 \\
\hline
101 & \textbf{TUS-46} & Reprogramación de envío & \textbf{Como} developer, \textbf{quiero} reprogramar envío fallido, \textbf{para} garantizar sincronización eventual. & 5 \\
\hline
102 & \textbf{TUS-47} & Estado visible & \textbf{Como} developer, \textbf{quiero} mostrar estado de sincronización, \textbf{para} dar transparencia al usuario. & 2 \\
\hline
103 & \textbf{TUS-48} & Hora de corte configurable & \textbf{Como} developer, \textbf{quiero} configurar hora de corte por zona, \textbf{para} adaptar sincronización. & 3 \\
\hline
\end{longtable}

\newpage

# Capítulo IV: Strategic-Level Software Design  

El diseño estratégico del software es una etapa crítica que define las bases técnicas sobre las que se construirá la solución. En este capítulo, se presenta la arquitectura conceptual de FoodLytics, con el propósito de optimizar la relación entre nutricionistas y pacientes a través del seguimiento automatizado de la alimentación.

Para definir la estructura de alto nivel del sistema, se han empleado metodologías como *Attribute-Driven Design (ADD)* y *Domain-Driven Design (DDD)*. Estas permiten alinear la arquitectura técnica con los atributos de calidad clave del sistema —como precisión, usabilidad, escalabilidad y seguridad de datos— al mismo tiempo que se asegura que cada módulo responda al dominio real de la nutrición clínica y deportiva.

Finalmente, se ha utilizado el modelo C4 para representar de forma visual y jerárquica los niveles de abstracción del sistema, desde su contexto general hasta los contenedores que lo componen. Todo este marco estratégico no solo orienta el desarrollo técnico de FoodLytics, sino que también garantiza su sostenibilidad, escalabilidad y alineación con los objetivos de GMB LABS como startup de innovación en salud.

![Recurso extraído de Canva](src/img/cap4/software-design-intro.png)

\newpage

## Strategic-Level Attribute-Driven Design  

El diseño estratégico de la solución parte del enfoque Attribute-Driven Design (ADD), el cual busca alinear la arquitectura del sistema con los atributos de calidad más relevantes para los usuarios y el negocio. Este enfoque permite tomar decisiones arquitectónicas fundamentadas en los requerimientos no funcionales críticos como rendimiento, escalabilidad, disponibilidad, usabilidad y mantenibilidad, aspectos esenciales para el éxito de FoodLytics en un entorno clínico y deportivo exigente.

A continuación, se presenta el propósito del diseño, seguido por los drivers de arquitectura, escenarios de calidad esperados y sus implicancias en el diseño estructural del sistema.

### Design Purpose  

El propósito del diseño arquitectónico de FoodLytics es construir una solución tecnológica sólida, centrada en la experiencia del usuario, que permita mejorar el seguimiento nutricional entre profesionales y pacientes. La aplicación está compuesta por una arquitectura monolítica modular, que permite mantener una estructura unificada pero organizada en módulos funcionales claramente definidos.

Esta elección responde a la necesidad de facilitar el desarrollo inicial, mantener la cohesión del sistema y permitir la escalabilidad progresiva conforme evolucionen los requerimientos del negocio. Cada módulo del sistema (gestión de usuarios, reconocimiento de alimentos, cálculo nutricional, monitoreo de progreso, entre otros) está diseñado de forma desacoplada dentro del monolito, lo que permite realizar mantenimientos o mejoras sin afectar la totalidad de la aplicación.

Desde el lado del paciente, la aplicación móvil permite registrar sus comidas mediante fotografías, mientras que en el lado profesional, la plataforma web facilita el análisis del historial alimenticio, la personalización de dietas y el seguimiento del progreso. Ambos entornos se comunican con una misma base de datos y lógica de negocio, asegurando coherencia, sincronización inmediata y simplicidad operativa.

Este diseño busca garantizar atributos clave como usabilidad, mantenibilidad, escalabilidad funcional y tiempo de respuesta adecuado, en un entorno donde la precisión nutricional y la agilidad clínica son fundamentales.

### Attribute-Driven Design Inputs  

Esta sección presenta los insumos que orientan el diseño de la arquitectura de la solución, tomando como base la metodología *Attribute-Driven Design* (ADD). Los elementos descritos permiten vincular los objetivos del sistema con los atributos de calidad esperados, asegurando que las decisiones de diseño respondan a las necesidades identificadas en los segmentos objetivo.

\newpage

#### Primary Functionality (Primary User Stories)  

La funcionalidad principal de la solución se centra en los procesos que sostienen el registro, análisis y comunicación de la información nutricional y física entre pacientes y nutricionistas. Estas funcionalidades fueron seleccionadas porque representan los requisitos con mayor impacto en la arquitectura del sistema. Requieren integración entre aplicaciones móviles y web, uso de inteligencia artificial, almacenamiento seguro de datos y generación de reportes. 

Los Epics y User Stories destacados se relacionan directamente con la creación de valor para los segmentos objetivo. En el caso del paciente, se busca un registro confiable de comidas y hábitos. En el caso del nutricionista, se busca contar con herramientas de análisis y seguimiento basadas en la información recolectada. 

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

MOB-US09 & Registro de comida mediante foto & \textbf{Como} paciente, \textbf{quiero} registrar mis comidas mediante una foto, \textbf{para} que la app identifique alimentos automáticamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} el paciente sube una foto clara de su comida\\
\textbf{cuando} la IA procesa la imagen\\
\textbf{entonces} se muestran los alimentos detectados.\\[0.2em]

\textbf{Escenario 2: Foto inválida}\\
\textbf{Dado que} la imagen es borrosa o no corresponde a alimentos\\
\textbf{cuando} se intenta procesar\\
\textbf{entonces} el sistema indica que no pudo identificar los alimentos.\\[0.2em]

\textbf{Escenario 3: Error de red}\\
\textbf{Dado que} hay un fallo en la conexión\\
\textbf{cuando} se sube la foto\\
\textbf{entonces} el sistema muestra un aviso y permite reintentar.\\
\end{tabular} & MOB-EP03 \\
\hline

MOB-US13 & Balance diario de calorías consumidas vs gastadas & \textbf{Como} paciente, \textbf{quiero} visualizar mi balance de calorías consumidas y gastadas, \textbf{para} evaluar si cumplo mis metas nutricionales. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Balance positivo}\\
\textbf{Dado que} el paciente consumió más calorías de las gastadas\\
\textbf{cuando} consulta su balance diario\\
\textbf{entonces} el sistema indica superávit calórico.\\[0.2em]

\textbf{Escenario 2: Balance negativo}\\
\textbf{Dado que} el paciente gastó más calorías de las consumidas\\
\textbf{cuando} consulta su balance\\
\textbf{entonces} el sistema indica déficit calórico.\\[0.2em]

\textbf{Escenario 3: Balance neutro}\\
\textbf{Dado que} el paciente consumió lo mismo que gastó\\
\textbf{cuando} consulta su balance\\
\textbf{entonces} el sistema muestra que está en equilibrio.\\
\end{tabular} & MOB-EP04 \\
\hline

WEB-US20 & Dashboard de progreso con gráficas & \textbf{Como} nutricionista, \textbf{quiero} acceder a un dashboard de progreso visual, \textbf{para} tener una visión rápida del desempeño de mis pacientes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización correcta}\\
\textbf{Dado que} el paciente tiene datos registrados\\
\textbf{cuando} el nutricionista accede al dashboard\\
\textbf{entonces} el sistema muestra gráficos de calorías, macros y peso.\\[0.2em]

\textbf{Escenario 2: Sin datos registrados}\\
\textbf{Dado que} no existen datos\\
\textbf{cuando} el nutricionista abre el dashboard\\
\textbf{entonces} el sistema indica que no hay información disponible.\\[0.2em]

\textbf{Escenario 3: Error en carga}\\
\textbf{Dado que} ocurre un problema en la consulta\\
\textbf{cuando} el nutricionista abre el dashboard\\
\textbf{entonces} el sistema muestra un mensaje de error técnico.\\
\end{tabular} & WEB-EP06 \\
\hline

WEB-US21 & Generación de reportes descargables & \textbf{Como} nutricionista, \textbf{quiero} generar y descargar reportes en formatos estándar, \textbf{para} compartirlos con mis pacientes o archivarlos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Descarga en PDF}\\
\textbf{Dado que} el nutricionista genera un reporte\\
\textbf{cuando} selecciona la opción de exportar en PDF\\
\textbf{entonces} el sistema descarga el archivo correctamente.\\[0.2em]

\textbf{Escenario 2: Descarga en Excel}\\
\textbf{Dado que} el nutricionista genera un reporte\\
\textbf{cuando} selecciona la opción de exportar en Excel\\
\textbf{entonces} el sistema descarga el archivo correctamente.\\[0.2em]

\textbf{Escenario 3: Error de exportación}\\
\textbf{Dado que} el sistema presenta un fallo al exportar\\
\textbf{cuando} se intenta descargar el archivo\\
\textbf{entonces} se muestra un mensaje de error.\\
\end{tabular} & WEB-EP06 \\
\hline

TUS-28 & Reconocer alimentos desde imagen & \textbf{Como} Developer, \textbf{quiero} un endpoint POST para subir imágenes, \textbf{para} identificar alimentos automáticamente. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Imagen válida}\\
\textbf{Dado que} se envía un POST a /food/recognize con foto en formato válido\\
\textbf{cuando} el sistema procesa la imagen\\
\textbf{entonces} devuelve 200 OK con lista de alimentos detectados.\\[0.2em]

\textbf{Escenario 2: Formato no soportado}\\
\textbf{Dado que} se envía imagen en formato no válido (ej. .txt)\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 415 Unsupported Media Type.\\[0.2em]

\textbf{Escenario 3: Imagen corrupta}\\
\textbf{Dado que} el archivo está dañado\\
\textbf{cuando} el sistema intenta procesarlo\\
\textbf{entonces} devuelve 422 Unprocessable Entity.\\
\end{tabular} & T-EP08 \\
\hline

\end{longtable}

\newpage

#### Quality attribute Scenarios 

En esta sección se presentan los escenarios de atributos de calidad que sirven como insumo para el diseño arquitectónico. Estos escenarios permiten definir cómo debe responder el sistema ante condiciones específicas relacionadas con rendimiento, seguridad, disponibilidad, usabilidad y escalabilidad. Cada escenario se describe de manera estructurada para asegurar que pueda evaluarse con métricas claras y cuantificables. 


\renewcommand{\arraystretch}{1.2} 
\begin{small} % opcional: reduce tipografía para que entre mejor
\begin{longtable}{|
 >{\raggedright\arraybackslash}p{2.1cm}|
 >{\raggedright\arraybackslash}p{1.9cm}|
 >{\raggedright\arraybackslash}p{2.1cm}|
 >{\raggedright\arraybackslash}p{1.5cm}|
 >{\raggedright\arraybackslash}p{1.8cm}|
 >{\raggedright\arraybackslash}p{2cm}|
 >{\raggedright\arraybackslash}p{2cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Atributo}} & 
\multicolumn{1}{c|}{\textbf{Fuente}} & 
\multicolumn{1}{c|}{\textbf{Estímulo}} & 
\multicolumn{1}{c|}{\textbf{Artefacto}} & 
\multicolumn{1}{c|}{\textbf{Entorno}} & 
\multicolumn{1}{c|}{\textbf{Respuesta}} & 
\multicolumn{1}{c|}{\textbf{Medida}} \\ 
\hline

Rendimiento & Paciente & Consulta su resumen diario desde la app móvil &
Aplicación móvil y backend & Conexión 4G promedio &
El sistema procesa la solicitud y entrega los datos al usuario &
Tiempo de respuesta $<$ 2 segundos \\ 
\hline

Disponibilidad & Nutricionista & Accede al panel web en horario laboral &
Servidor backend & Sistema en operación normal &
El sistema mantiene el servicio disponible &
Uptime $\geq$ 99.9\% \\ 
\hline

Seguridad & Atacante externo & Intenta interceptar datos en tránsito &
Canal de comunicación cliente-servidor & Durante transmisión de información &
El sistema cifra toda la comunicación &
Todo tráfico bajo HTTPS TLS 1.3 \\ 
\hline

Confiabilidad & Paciente & Sincroniza su información al final del día &
Backend de sincronización & Carga concurrente de múltiples usuarios &
El sistema recibe los datos, evita duplicados y confirma recepción &
RPO $\leq$ 15 min, RTO $\leq$ 1h, cero registros duplicados \\ 
\hline

Usabilidad & Paciente & Accede con discapacidad visual &
Interfaz móvil & Uso de lector de pantalla &
La aplicación presenta contenido accesible y navegable &
Cumplimiento de WCAG 2.1 nivel AA \\ 
\hline

Escalabilidad & Sistema & Incremento de usuarios concurrentes en picos de uso &
Backend en contenedores & 10,000 usuarios conectados &
El sistema escala horizontalmente sin caídas de servicio &
Latencia $<$ 300 ms en operaciones críticas \\ 
\hline

Observabilidad & Administrador & Se produce un error en el cálculo del IMC &
Servicio de cálculo & Producción &
El sistema registra el error y genera alerta en monitoreo &
Evento registrado en logs estructurados y alerta en $<$ 1 min \\ 
\hline

\end{longtable}
\end{small}


\newpage


#### Constraints

Aquí se detallan las restricciones que no son negociables y que guían la construcción de la solución. Estas restricciones provienen del negocio, de requerimientos legales y de la propia estrategia técnica. Su cumplimiento garantiza que el sistema sea seguro, confiable, portable y alineado con las regulaciones aplicables. 
A continuación, se presentan los constraints representados como Technical Stories, donde cada uno ocupa una fila con su respectiva descripción, criterios de aceptación y relación con las épicas técnicas

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{TUS ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline

TUS-33 & Gestión de consentimientos & \textbf{Como} Developer, \textbf{quiero} un endpoint para registrar consentimientos por finalidad de uso, \textbf{para} cumplir con normativas de privacidad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} se envía POST /consents con datos válidos\\
\textbf{cuando} el sistema guarda el consentimiento\\
\textbf{entonces} devuelve 201 Created con ID del consentimiento.\\[0.2em]

\textbf{Escenario 2: Consentimiento duplicado}\\
\textbf{Dado que} ya existe consentimiento para el mismo usuario y finalidad\\
\textbf{cuando} se intenta registrar de nuevo\\
\textbf{entonces} devuelve 409 Conflict.\\[0.2em]

\textbf{Escenario 3: Datos inválidos}\\
\textbf{Dado que} falta información en el payload\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP09 \\
\hline

TUS-34 & Cifrado en tránsito y en reposo & \textbf{Como} Developer, \textbf{quiero} que los datos estén cifrados en tránsito y reposo, \textbf{para} garantizar seguridad de la información. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Comunicación segura}\\
\textbf{Dado que} se realiza petición HTTPS\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} la conexión está cifrada con TLS.\\[0.2em]

\textbf{Escenario 2: Datos en reposo}\\
\textbf{Dado que} se guarda información sensible en BD\\
\textbf{cuando} el sistema persiste\\
\textbf{entonces} los datos quedan cifrados AES-256.\\[0.2em]

\textbf{Escenario 3: Intento de acceso inseguro}\\
\textbf{Dado que} un cliente envía HTTP sin TLS\\
\textbf{cuando} el sistema recibe\\
\textbf{entonces} devuelve 426 Upgrade Required.\\
\end{tabular} & T-EP09 \\
\hline

TUS-35 & Limpieza de metadatos en imágenes & \textbf{Como} Developer, \textbf{quiero} eliminar metadatos de imágenes, \textbf{para} proteger la privacidad de los usuarios. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Imagen procesada}\\
\textbf{Dado que} se sube imagen con EXIF\\
\textbf{cuando} el sistema guarda la imagen\\
\textbf{entonces} elimina metadatos antes de almacenar.\\[0.2em]

\textbf{Escenario 2: Imagen sin metadatos}\\
\textbf{Dado que} la foto no tiene EXIF\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} la guarda directamente.\\[0.2em]

\textbf{Escenario 3: Error en limpieza}\\
\textbf{Dado que} ocurre un fallo al limpiar\\
\textbf{cuando} se procesa la imagen\\
\textbf{entonces} devuelve 500 Internal Server Error.\\
\end{tabular} & T-EP09 \\
\hline

TUS-36 & Registro de uso de datos & \textbf{Como} Developer, \textbf{quiero} registrar el uso de datos sensibles, \textbf{para} auditoría y cumplimiento legal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro válido}\\
\textbf{Dado que} un nutricionista accede a datos de paciente\\
\textbf{cuando} el sistema procesa\\
\textbf{entonces} se registra en logs con timestamp.\\[0.2em]

\textbf{Escenario 2: Consulta de registros}\\
\textbf{Dado que} un admin consulta GET /data-usage\\
\textbf{cuando} el sistema responde\\
\textbf{entonces} devuelve historial auditable.\\[0.2em]

\textbf{Escenario 3: Usuario sin permisos}\\
\textbf{Dado que} un rol paciente consulta /data-usage\\
\textbf{cuando} el sistema valida\\
\textbf{entonces} devuelve 403 Forbidden.\\
\end{tabular} & T-EP09 \\
\hline

TUS-42 & Idempotencia en lotes & \textbf{Como} Developer, \textbf{quiero} claves únicas en cada lote, \textbf{para} evitar duplicados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Lote único}\\
\textbf{Dado que} se envía POST /sync/batch con clave X\\
\textbf{cuando} backend valida\\
\textbf{entonces} lo guarda.\\[0.2em]

\textbf{Escenario 2: Reenvío mismo lote}\\
\textbf{Dado que} se envía misma clave X\\
\textbf{cuando} backend valida\\
\textbf{entonces} devuelve 200 OK sin duplicar.\\[0.2em]

\textbf{Escenario 3: Clave inválida}\\
\textbf{Dado que} se omite clave\\
\textbf{cuando} se procesa\\
\textbf{entonces} devuelve 400 Bad Request.\\
\end{tabular} & T-EP10 \\
\hline

TUS-43 & Confirmación de backend & \textbf{Como} Developer, \textbf{quiero} confirmar recepción de datos, \textbf{para} marcar localmente enviados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Confirmación exitosa}\\
\textbf{Dado que} backend recibe lote\\
\textbf{cuando} responde 200 OK\\
\textbf{entonces} cliente marca datos como enviados.\\[0.2em]

\textbf{Escenario 2: Sin confirmación}\\
\textbf{Dado que} backend no responde\\
\textbf{cuando} pasa timeout\\
\textbf{entonces} cliente mantiene datos en cola.\\[0.2em]

\textbf{Escenario 3: Error backend}\\
\textbf{Dado que} responde 500\\
\textbf{cuando} procesa lote\\
\textbf{entonces} cliente reintenta envío.\\
\end{tabular} & T-EP10 \\
\hline

TUS-44 & Descarte de duplicados & \textbf{Como} Developer, \textbf{quiero} descartar duplicados en servidor, \textbf{para} mantener integridad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Duplicado detectado}\\
\textbf{Dado que} lote tiene misma clave\\
\textbf{cuando} backend procesa\\
\textbf{entonces} ignora duplicado.\\[0.2em]

\textbf{Escenario 2: Registro único}\\
\textbf{Dado que} clave es nueva\\
\textbf{cuando} se procesa\\
\textbf{entonces} guarda datos.\\[0.2em]

\textbf{Escenario 3: Error en validación}\\
\textbf{Dado que} clave está corrupta\\
\textbf{cuando} se valida\\
\textbf{entonces} devuelve 400.\\
\end{tabular} & T-EP10 \\
\hline

TUS-45 & Manejo de timestamps & \textbf{Como} Developer, \textbf{quiero} timestamps en RFC3339, \textbf{para} asegurar consistencia temporal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Timestamp válido}\\
\textbf{Dado que} cliente envía timestamp RFC3339\\
\textbf{cuando} backend valida\\
\textbf{entonces} guarda registro.\\[0.2em]

\textbf{Escenario 2: Timestamp inválido}\\
\textbf{Dado que} cliente envía formato incorrecto\\
\textbf{cuando} backend valida\\
\textbf{entonces} devuelve 400.\\[0.2em]

\textbf{Escenario 3: Diferencia de zona}\\
\textbf{Dado que} timestamp incluye zona UTC-5\\
\textbf{cuando} backend procesa\\
\textbf{entonces} normaliza a UTC.\\
\end{tabular} & T-EP10 \\
\hline

\end{longtable}

\newpage

### Architectural Drivers Backlog 

En esta sección se consolidan los drivers arquitectónicos priorizados por el equipo. El backlog incluye drivers funcionales, atributos de calidad y restricciones. Cada driver se clasifica considerando su importancia para los stakeholders y el nivel de complejidad técnica que implica su implementación. Este backlog sirve como base para la toma de decisiones de diseño. 

\begin{longtable}{|p{1.5cm}|p{3cm}|p{4cm}|p{3cm}|p{3cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Driver ID}} &
\multicolumn{1}{c|}{\textbf{Título de Driver}} &
\multicolumn{1}{c|}{\textbf{Descripción}} &
\multicolumn{1}{p{3cm}|}{\centering\textbf{Importancia para los Stakeholders}\par} &
\multicolumn{1}{p{3cm}|}{\centering\textbf{Impacto en Architecture Technical Complexity}\par} \\
\hline

FD-01 & Registro de comidas con foto e IA & 
Permitir al paciente registrar sus comidas mediante fotos y reconocimiento automático de alimentos. & 
High & High \\ 
\hline

FD-02 & Dashboard nutricionista & 
Proporcionar al nutricionista un panel con métricas de calorías, macros y peso del paciente. & 
High & Medium \\ 
\hline

FD-03 & Generación de reportes descargables & 
Permitir al nutricionista exportar reportes en PDF y Excel para seguimiento clínico. & 
Medium & Medium \\ 
\hline

QAD-01 & Rendimiento en consultas críticas & 
Garantizar que operaciones principales respondan en menos de 2 segundos en conexión 4G. & 
High & High \\ 
\hline

QAD-02 & Disponibilidad del sistema & 
Asegurar que el sistema mantenga un uptime $\geq$ 99.9\% durante horario laboral. & 
High & High \\ 
\hline

QAD-03 & Seguridad de la información & 
Asegurar cifrado en tránsito con TLS 1.3 y en reposo con AES-256. & 
High & High \\ 
\hline

QAD-04 & Escalabilidad horizontal & 
El backend debe escalar horizontalmente para soportar hasta 10,000 usuarios concurrentes. & 
High & High \\ 
\hline

QAD-05 & Usabilidad accesible & 
La interfaz debe cumplir con WCAG 2.1 nivel AA y ser intuitiva en móviles y navegadores modernos. & 
Medium & Medium \\ 
\hline

QAD-06 & Observabilidad y monitoreo & 
El sistema debe registrar métricas, logs y errores con trazabilidad. & 
Medium & Medium \\ 
\hline

CST-01 & Cumplimiento normativo de datos & 
Cumplir con la Ley de Protección de Datos Personales (Perú) y GDPR. & 
High & High \\ 
\hline

CST-02 & Consentimiento explícito & 
Registrar y auditar consentimientos de pacientes y nutricionistas antes de procesar sus datos. & 
High & Medium \\ 
\hline

CST-03 & Sincronización diaria en lote & 
Procesar datos en un único envío con reintentos seguros y control de duplicados. & 
High & High \\ 
\hline

\end{longtable}

\newpage

### Architectural Design Decisions 

Aquí se resume el proceso seguido para la toma de decisiones de diseño arquitectónico. El equipo documentó las iteraciones del *Quality Attribute Workshop*, los drivers considerados y los patrones candidatos evaluados. Para cada decisión se registraron pros y contras de los patrones discutidos, lo que permitió seleccionar la opción más adecuada para responder a los objetivos del sistema. 



\begingroup
\setlength{\tabcolsep}{3pt}
\begin{longtable}{|p{1.2cm}|p{2.5cm}|p{1.8cm}|p{1.8cm}|p{1.9cm}|p{1.8cm}|p{1.9cm}|p{1.8cm}|}
\hline
\multicolumn{1}{|p{1.2cm}|}{\centering\textbf{Driver ID}\par} &
\multicolumn{1}{p{2.8cm}|}{\centering\textbf{Título de Driver}\par} &
\multicolumn{2}{p{3.6cm}|}{\centering\textbf{Pattern 1}\par} &
\multicolumn{2}{p{3.6cm}|}{\centering\textbf{Pattern 2}\par} &
\multicolumn{2}{p{3.6cm}|}{\centering\textbf{Pattern 3}\par} \\ \hline
\multicolumn{2}{|c|}{} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Pro}\par} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Con}\par} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Pro}\par} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Con}\par} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Pro}\par} &
\multicolumn{1}{p{1.8cm}|}{\centering\textbf{Con}\par} \\ \hline
\endfirsthead




\multirow{2}{*}{\centering QAD-01} &
\multirow{2}{2.8cm}{\centering Rendimiento\\en consultas\\críticas} &
\multicolumn{2}{p{3.6cm}|}{\centering Cache distribuida\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Base de datos relacional optimizada\par} &
\multicolumn{2}{p{3.6cm}|}{\centering CQRS\par} \\ \cline{3-8}
& &
\multicolumn{1}{p{1.8cm}|}{\centering Reduce latencia en consultas repetitivas\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Complejidad en sincronización de datos\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Modelo conocido, soporte transaccional\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Latencia mayor con alta concurrencia\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Separa lectura y escritura, mejora performance\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Mayor complejidad de desarrollo\par} \\ \hline


\multirow{2}{*}{\centering QAD-01} &
\multirow{2}{2.8cm}{\centering Disponibilidad\\del sistema} &
\multicolumn{2}{p{3.6cm}|}{\centering Replicación activa-activa\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Replicación activa-pasiva\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Kubernetes con autoescalado\par} \\ \cline{3-8}
& &
\multicolumn{1}{p{1.8cm}|}{\centering Alta tolerancia a fallos\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Costos altos de infraestructura\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Menor costo, configuración más simple\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Mayor tiempo de failover\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Orquesta- ción robusta, resiliencia\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Curva de aprendizaje alta\par} \\ \hline


\multirow{2}{*}{\centering QAD-01} &
\multirow{2}{2.8cm}{\centering Seguridad\\de la información} &
\multicolumn{2}{p{3.6cm}|}{\centering OAuth 2.0 + JWT\par} &
\multicolumn{2}{p{3.6cm}|}{\centering API Key simple\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Identity Provider externo\par} \\ \cline{3-8}
& &
\multicolumn{1}{p{1.8cm}|}{\centering Estándar reconocido, soporta RBAC\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Requiere configuración cuidadosa\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Implementa- ción rápida\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Seguridad limitada, no escalable\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Gestión centralizada, cumplimiento normativo\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Dependen- cia de terceros\par} \\ \hline


\multirow{2}{*}{\centering QAD-01} &
\multirow{2}{2.8cm}{\centering Escalabilidad\\horizontal} &
\multicolumn{2}{p{3.6cm}|}{\centering Microservicios\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Modular monolítico\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Event-driven architecture\par} \\ \cline{3-8}
& &
\multicolumn{1}{p{1.8cm}|}{\centering Escalan independientemente, fáciles de desplegar\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Mayor complejidad operativa\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Sencillo en etapas tempranas, fácil de mantener\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Escalabilidad limitada\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Maneja alta concurrencia y picos de carga\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Difícil de probar y depurar\par} \\ \hline


\multirow{2}{*}{\centering QAD-01} &
\multirow{2}{2.8cm}{\centering Sincronización\\diaria en lote} &
\multicolumn{2}{p{3.6cm}|}{\centering Cola de mensajes (Kafka, RabbitMQ)\par} &
\multicolumn{2}{p{3.6cm}|}{\centering API REST directa\par} &
\multicolumn{2}{p{3.6cm}|}{\centering Almacenamiento local en cliente\par} \\ \cline{3-8}
& &
\multicolumn{1}{p{1.8cm}|}{\centering Alta confiabilidad, soporta reintentos\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Dependen- cia tecnológica nueva\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Simplicidad de implementación\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Riesgo de pérdida en fallos de red\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Garantiza reintento sin conexión\par} &
\multicolumn{1}{p{1.8cm}|}{\centering Lógica adicional en cliente\par} \\ \hline

\end{longtable}
\endgroup


\newpage


### Quality Attribute Scenario Refinements  

Al finalizar el Quality Attribute Workshop, el equipo priorizó los escenarios de atributos de calidad que tienen mayor impacto en la arquitectura. Las decisiones se enfocaron en garantizar rendimiento, seguridad, disponibilidad y escalabilidad, ya que estos atributos representan los factores críticos para la experiencia de usuario y el cumplimiento de los objetivos del negocio. A continuación se presenta la versión refinada de los escenarios priorizados, ordenados según su relevancia para los stakeholders y la complejidad técnica de su implementación. 

\begin{longtable}{|p{4cm}|p{4cm}|p{7cm}|}
\hline
\multicolumn{3}{|c|}{\textbf{Scenario Refinement for Scenario 1}} \\ \hline
\textbf{Scenario(s):} & \multicolumn{2}{p{11cm}|}{Consulta de resumen diario en la aplicación móvil.} \\ \hline
\textbf{Business Goals:} & \multicolumn{2}{p{11cm}|}{Asegurar que los pacientes accedan a su información nutricional de manera rápida y confiable.} \\ \hline
\textbf{Relevant Quality Attributes:} & \multicolumn{2}{p{11cm}|}{Rendimiento, usabilidad.} \\ \hline

\multirow{6}{*}{\textbf{Scenario Components}} 
& \textbf{Stimulus:} & El paciente solicita su resumen diario de calorías y nutrientes. \\ \cline{2-3}
& \textbf{Stimulus Source:} & Paciente \\ \cline{2-3}
& \textbf{Scenario Components Environment:} & Conexión móvil promedio (4G). \\ \cline{2-3}
& \textbf{Artifact (if Known):} & Backend y aplicación móvil. \\ \cline{2-3}
& \textbf{Response:} & El sistema procesa la solicitud y entrega el resumen en pantalla. \\ \cline{2-3}
& \textbf{Response Measure:} & Tiempo de respuesta $<$ 2 segundos. \\ \hline

\textbf{Questions:} & \multicolumn{2}{p{11cm}|}{¿Cómo se comporta el sistema en condiciones de baja conectividad?} \\ \hline
\textbf{Issues:} & \multicolumn{2}{p{11cm}|}{Posible necesidad de caché local en el dispositivo.} \\ \hline
\end{longtable}

\newpage

\begin{longtable}{|p{4cm}|p{4cm}|p{7cm}|}
\hline
\multicolumn{3}{|c|}{\textbf{Scenario Refinement for Scenario 2}} \\ \hline
\textbf{Scenario(s):} & \multicolumn{2}{p{11cm}|}{Acceso de nutricionista al dashboard web.} \\ \hline
\textbf{Business Goals:} & \multicolumn{2}{p{11cm}|}{Garantizar que los nutricionistas cuenten con datos confiables y actualizados para la toma de decisiones.} \\ \hline
\textbf{Relevant Quality Attributes:} & \multicolumn{2}{p{11cm}|}{Disponibilidad, confiabilidad.} \\ \hline

\multirow{6}{*}{\textbf{Scenario Components}} 
& \textbf{Stimulus:} & El nutricionista accede al panel web en horario laboral. \\ \cline{2-3}
& \textbf{Stimulus Source:} & Nutricionista \\ \cline{2-3}
& \textbf{Scenario Components Environment:} & Producción, alta concurrencia de usuarios. \\ \cline{2-3}
& \textbf{Artifact (if Known):} & Servidor backend y aplicación web. \\ \cline{2-3}
& \textbf{Response:} & El sistema mantiene la disponibilidad del servicio y muestra datos completos. \\ \cline{2-3}
& \textbf{Response Measure:} & Uptime $\geq$ 99.9\%. \\ \hline

\textbf{Questions:} & \multicolumn{2}{p{11cm}|}{¿Qué pasa si ocurre un fallo en el servidor principal?} \\ \hline
\textbf{Issues:} & \multicolumn{2}{p{11cm}|}{Se requiere replicación activa.} \\ \hline
\end{longtable}

\newpage

\begin{longtable}{|p{4cm}|p{4cm}|p{7cm}|}
\hline
\multicolumn{3}{|c|}{\textbf{Scenario Refinement for Scenario 3}} \\ \hline
\textbf{Scenario(s):} & \multicolumn{2}{p{11cm}|}{Envío de datos diarios desde la aplicación móvil.} \\ \hline
\textbf{Business Goals:} & \multicolumn{2}{p{11cm}|}{Garantizar que la información registrada por el paciente se sincronice correctamente sin pérdida de datos.} \\ \hline
\textbf{Relevant Quality Attributes:} & \multicolumn{2}{p{11cm}|}{Confiabilidad, seguridad.} \\ \hline

\multirow{6}{*}{\textbf{Scenario Components}} 
& \textbf{Stimulus:} & El paciente sincroniza su información de comidas y peso al final del día. \\ \cline{2-3}
& \textbf{Stimulus Source:} & Paciente \\ \cline{2-3}
& \textbf{Scenario Components Environment:} & Dispositivo móvil con conexión intermitente a internet. \\ \cline{2-3}
& \textbf{Artifact (if Known):} & Aplicación móvil y backend de sincronización. \\ \cline{2-3}
& \textbf{Response:} & El sistema almacena la información, descarta duplicados y confirma recepción. \\ \cline{2-3}
& \textbf{Response Measure:} & RPO $\leq$ 15 minutos y cero duplicados registrados. \\ \hline

\textbf{Questions:} & \multicolumn{2}{p{11cm}|}{¿Qué ocurre si la red se corta durante el envío?} \\ \hline
\textbf{Issues:} & \multicolumn{2}{p{11cm}|}{Necesidad de mecanismos de reintento y almacenamiento local temporal.} \\ \hline
\end{longtable}

\newpage

\begin{longtable}{|p{4cm}|p{4cm}|p{7cm}|}
\hline
\multicolumn{3}{|c|}{\textbf{Scenario Refinement for Scenario 4}} \\ \hline
\textbf{Scenario(s):} & \multicolumn{2}{p{11cm}|}{Protección de datos personales durante la transmisión.} \\ \hline
\textbf{Business Goals:} & \multicolumn{2}{p{11cm}|}{Cumplir con regulaciones de protección de datos y generar confianza en los usuarios.} \\ \hline
\textbf{Relevant Quality Attributes:} & \multicolumn{2}{p{11cm}|}{Seguridad.} \\ \hline

\multirow{6}{*}{\textbf{Scenario Components}} 
& \textbf{Stimulus:} & Un atacante externo intenta interceptar datos transmitidos entre cliente y servidor. \\ \cline{2-3}
& \textbf{Stimulus Source:} & Atacante externo \\ \cline{2-3}
& \textbf{Scenario Components Environment:} & Transmisión de datos en producción. \\ \cline{2-3}
& \textbf{Artifact (if Known):} & Canal de comunicación entre cliente y servidor. \\ \cline{2-3}
& \textbf{Response:} & El sistema cifra toda la comunicación y rechaza conexiones inseguras. \\ \cline{2-3}
& \textbf{Response Measure:} & 100\% del tráfico bajo HTTPS TLS 1.3. \\ \hline

\textbf{Questions:} & \multicolumn{2}{p{11cm}|}{¿Cómo se gestionan certificados caducados o no confiables?} \\ \hline
\textbf{Issues:} & \multicolumn{2}{p{11cm}|}{Riesgo de fallas si no se renuevan certificados a tiempo.} \\ \hline
\end{longtable}

\newpage

\begin{longtable}{|p{4cm}|p{4cm}|p{7cm}|}
\hline
\multicolumn{3}{|c|}{\textbf{Scenario Refinement for Scenario 5}} \\ \hline
\textbf{Scenario(s):} & \multicolumn{2}{p{11cm}|}{Escalamiento del sistema en picos de carga.} \\ \hline
\textbf{Business Goals:} & \multicolumn{2}{p{11cm}|}{Mantener la disponibilidad y el rendimiento durante momentos de alta concurrencia.} \\ \hline
\textbf{Relevant Quality Attributes:} & \multicolumn{2}{p{11cm}|}{Escalabilidad, rendimiento.} \\ \hline

\multirow{6}{*}{\textbf{Scenario Components}} 
& \textbf{Stimulus:} & 10,000 usuarios se conectan de forma concurrente en un periodo de alta demanda. \\ \cline{2-3}
& \textbf{Stimulus Source:} & Sistema (usuarios concurrentes). \\ \cline{2-3}
& \textbf{Scenario Components Environment:} & Producción con picos de uso. \\ \cline{2-3}
& \textbf{Artifact (if Known):} & Backend desplegado en contenedores. \\ \cline{2-3}
& \textbf{Response:} & El sistema escala horizontalmente sin degradación del servicio. \\ \cline{2-3}
& \textbf{Response Measure:} & Latencia $<$ 300 ms en operaciones críticas. \\ \hline

\textbf{Questions:} & \multicolumn{2}{p{11cm}|}{¿El costo de infraestructura escala proporcionalmente con la demanda?} \\ \hline
\textbf{Issues:} & \multicolumn{2}{p{11cm}|}{Riesgo de sobrecostos si no se optimiza el autoescalado.} \\ \hline
\end{longtable}

\newpage

## Strategic-Level Domain-Driven Design  

### EventStorming

La sesión de Event Storming permitió mapear de manera colaborativa el flujo completo de la aplicación de seguimiento nutricional, identificando los eventos clave, los actores involucrados y las interacciones entre ellos. Se definieron los procesos pr incipales: Onboarding del Paciente, Análisis de Datos Nutricionales mediante IA, Seguimiento y Registro de Comidas, Notificaciones y Feedback al Paciente, y el Dashboard para Paciente. 

En cada proceso se visualizaron los eventos disparadores, los comandos, los servicios implicados y las métricas que alimentan el análisis nutricional, facilitando la detección de dependencias, la definición de bounded contexts y la comprensión integral del dominio para guiar el diseño de la solución. 


![Recurso realizado en Miro - EventStorming](src\img\cap4\Event Storming.png)

\newpage

### Candidate Context Discovery 

La sesión de Candidate Context Discovery permitió descomponer el dominio de Foodlytics en bounded contexts claramente diferenciados a partir del EventStorming. Para ello se aplicaron las técnicas de start-with-value y look-for-pivotal-events, priorizando los puntos del proceso con mayor valor para el negocio y los eventos que generan transiciones críticas entre flujos.

**Candidate bounded contexts propuestos (ordenados por valor)**

1) Food Tracking (Registro de Comidas) — valor alto: permite seguimiento continuo. 
2) Nutrition Analysis (Motor IA/ML) — valor alto: entrega insights automáticos. 
3) Clinician Dashboard (Panel Nutricionista) — valor alto: facilita decisiones clínicas. 
4) User & Access (Autenticación/Consentimiento) — valor crítico para seguridad y cuenta. 
5) Reports & Analytics — valor medio: reportes semanales/mensuales y métricas. 
6) Risk Prediction (IA de riesgos) — valor medio/alto: predicciones de hipertensión/diabetes. 
7) Media Storage (Imágenes) — soporte técnico para fotos. 

\newpage

**Detalle de bounded contexts dilimitados en la sesión**

1. **Contexto de Identity and Access Management**

  - **Límite:** Abarca desde el registro y autenticación de usuarios hasta la gestión de sesiones y recuperación de credenciales.

  - **Eventos clave:** Registro de usuario, verificación de correo electrónico, inicio de sesión, restablecimiento de contraseña, cierre de sesión.

  - **Justificación:** Este bounded context centraliza la seguridad y el control de acceso de los usuarios, asegurando la integridad de las credenciales y la protección de datos sensibles. Su independencia garantiza un manejo coherente de la identidad a través de los demás módulos del sistema.

![EventStorming - Bounded Context Identity and Access Management](src/img/cap4/Event Storming 1.png)

\newpage

2. **Contexto de Diet Tracking**

  - **Límite:** Incluye el registro de comidas, seguimiento de peso, cálculo automático de balance calórico y evaluación del progreso nutricional del paciente.

  - **Eventos clave:** Registro de comida, actualización de macros, registro de peso diario, generación de historial y dashboard de progreso.

  - **Justificación:** Este bounded context permite al paciente monitorear su alimentación y evolución física mediante datos procesados en tiempo real, lo que facilita al nutricionista el seguimiento personalizado del plan dietético.

![EventStorming - Bounded Context Diet Tracking](src/img/cap4/Event Storming 2.png)

\newpage

3. **Contexto de Payments**

  - **Límite:** Abarca la gestión de pagos, validación de suscripciones y control de servicios activos del nutricionista.

  - **Eventos clave:** Inicio de pago, confirmación de transacción, reembolso, generación de comprobante y reporte mensual de ingresos.

  - **Justificación:** Este bounded context permite la administración financiera del sistema, garantizando que los servicios de los nutricionistas se mantengan activos según el estado de sus pagos y suscripciones.

![EventStorming - Bounded Context Payments](src/img/cap4/Event Storming 3.png)

\newpage

4. **Contexto de Profile**

  - **Límite:** Cubre la actualización de datos personales, objetivos, preferencias y configuración de idioma o tema de los usuarios.

  - **Eventos clave:** Actualización de perfil, modificación de objetivo, validación de datos, notificación de cambios al nutricionista.

  - **Justificación:** Este bounded context permite mantener la información personal y los objetivos del usuario actualizados, asegurando coherencia con los planes nutricionales y facilitando la personalización de la experiencia.

![EventStorming - Bounded Context Profile](src/img/cap4/Event Storming 4.png)

\newpage

5. **Contexto de Coaching**

  - **Límite:** Abarca la creación de planes nutricionales y rutinas de ejercicios, el seguimiento semanal del progreso y la generación de reportes.

  - **Eventos clave:** Creación de plan, evaluación de progreso semanal, ajuste de calorías, exportación de reporte PDF.

  - **Justificación:** Este bounded context define la interacción directa entre el nutricionista y el paciente mediante planes personalizados, asegurando un acompañamiento estructurado y medible.

![EventStorming - Bounded Context Coaching](src/img/cap4/Event Storming 5.png)

\newpage

6. **Contexto de Notifications**

  - **Límite:** Cubre la gestión y envío de recordatorios, notificaciones automáticas y alertas críticas.

  - **Eventos clave:** Programación de notificación, envío de push o correo, confirmación de entrega, cancelación o lectura.

  - **Justificación:** Este bounded context mantiene la comunicación activa entre el sistema y los usuarios, reforzando la adherencia a los planes nutricionales y garantizando la entrega oportuna de información importante.

![EventStorming - Bounded Context Notifications](src/img/cap4/Event Storming 6.png)

\newpage

7. **Contexto de Recognition (IA de reconocimiento de alimentos)**

  - **Límite:** Abarca la detección automática de alimentos mediante visión computacional, el cálculo de calorías estimadas y la corrección manual de los resultados.

  - **Eventos clave:** Carga de imagen, ejecución del reconocimiento, detección de alimentos, ajuste manual, actualización de base de datos.

  - **Justificación:** Este bounded context incorpora inteligencia artificial para simplificar el registro de comidas del paciente, mejorando la precisión y reduciendo el tiempo de registro en el seguimiento dietético.

![EventStorming - Bounded Context Recognition (IA de reconocimiento de alimentos)](src/img/cap4/Event Storming 7.png)

La identificación de estos bounded contexts permitió reducir complejidad, delimitar responsabilidades y sentar las bases para un diseño modular escalable de la solución.

\newpage

### Domain Message Flows Modeling

Para esta sección nuestro objetivo fue visualizar cómo los bounded contexts colaboran (mensajes, eventos y solicitudes sincrónicas) para soportar los casos de uso clave. Se aplicó Domain Storytelling para describir interacciones humanas y técnicas

- **Historia A — Registrar comida y análisis automático**

1. **Paciente** toma una foto y presiona **RegistrarComida** en la app.

2. **App Móvil** envía el **command** `RegistrarComida` a **Food Tracking**.

3. **Food Tracking** guarda metadatos y **emite** `FotoSubida`.

4. **Media Storage** persiste la imagen y **emite** `FotoAlmacenada`.

5. Una **política (saga)** *On FotoAlmacenada* invoca `AnalizarFoto` en **Nutrition Analysis** (asíncrono).

6. **Nutrition Analysis** procesa la imagen, calcula nutrientes y **emite** `ComidaAnalizada`.

7. **Food Tracking** actualiza el registro y **emite** `ComidaRegistradaConAnalisis`.

8. **Notifications** consume el evento y, si aplica, envía **AlertaPaciente**.

9. **Clinician Dashboard** consume `ComidaRegistradaConAnalisis` y actualiza la vista del nutricionista.

![Historia A - Registrar comida y análisis automático](src/img/cap4/A.png)


- **Historia B — Nutricionista ajusta el plan y comunica cambios**

1. **Nutricionista** abre **Clinician Dashboard** y **consulta** histórico (query al read-model propio).

2. El profesional registra un **command** `AjustarPlanNutricional` en **Clinician Dashboard**, que delega a **Nutrition Analysis** (validaciones) / **Food Tracking** (persistencia del plan activo).

3. **Food Tracking** **emite** `PlanNutricionalActualizado`.

4. **Notifications** consume el evento y envía **MensajeCambioDePlan** al **Paciente**.

5. **Patient App** refresca la vista vía **query** (read-model) al **Clinician Dashboard**.

![Historia B - Nutricionista ajusta el plan y comunica cambios](src/img/cap4/B.png)


\newpage


- **Historia C — Recordatorios y adherencia**

1. Un **job** en **Notifications** detecta comidas pendientes y **emite** `RecordatorioComidaProgramado`.

2. **Notifications** envía **push** al **Paciente**.

3. Si el paciente no registra, se **reintenta**; si persiste, **Notifications** **emite** `AdherenciaBajaDetectada`.

4. **Clinician Dashboard** consume el evento y marca al paciente en **riesgo de baja adherencia**.

![Historia C - Recordatorios y adherencia](src/img/cap4/C.png)

\newpage

### Bounded Context Canvases 

La elaboración de los Bounded Context Canvases permitió plasmar en detalle el diseño de los contextos delimitados previamente en la sesión de Candidate Context Discovery. Cada canvas recoge los criterios esenciales de diseño para asegurar que los bounded contexts aporten valor, mantengan independencia y reduzcan complejidad en la solución.

**Canvas 1 — Food Tracking (Registro de Comidas)**

![1: Food Tracking (Registro de Comidas)](src/img/cap4/Bounded Context Canvases 1.png)

**Canvas 2 — Nutrition Analysis (Motor IA/ML)**

![2: Nutrition Analysis (Motor IA/ML)](src/img/cap4/Bounded Context Canvases 2.png)

**Canvas 3 — Clinician Dashboard**

![3: Clinician Dashboard](src/img/cap4/Bounded Context Canvases 3.png)

**Canvas 4 — User & Access (Autenticación y Consentimiento)**

![4: User & Access (Autenticación y Consentimiento)](src/img/cap4/Bounded Context Canvases 4.png)

**Canvas 5 — Notifications & Reminders**

![5: Notifications & Reminders](src/img/cap4/Bounded Context Canvases 5.png)

\newpage

### Context Mapping 

El proceso de Context Mapping permitió representar las relaciones estructurales y los contratos de integración entre los bounded contexts definidos en Foodlytics. Mientras que los Bounded Context Canvases detallan cada contexto de manera aislada, el context map ofrece una visión sistémica de cómo colaboran e intercambian información dentro de los límites de la solución.

- Para su elaboración se aplicaron preguntas de exploración sugeridas en Domain-Driven Design, como:

  - ¿Qué pasa si un capability se mueve a otro bounded context?

  - ¿Qué ocurre si un contexto debe actuar como proveedor (supplier) de otro que depende de sus datos?

  - ¿Qué patrones de integración reducen duplicidad y aseguran consistencia entre contextos?

A partir de este análisis se identificaron y aplicaron distintos patrones de relación entre contextos:

  - Customer/Supplier, en la interacción de Food Tracking con Nutrition Analysis y User & Access.

  - Shared Service, para la gestión común de imágenes a través de Media Storage.

  - Event-Driven Consistency, en la propagación de eventos como ComidaAnalizada o ComidaRegistrada.

  - Conformist / ACL, en la relación del Clinician Dashboard al consumir reportes y proyecciones de otros contextos.

![Context Mapping](src/img/cap4/Context mapping.png)

El context map resultante proporciona un marco claro para comprender las dependencias y flujos de datos entre módulos, facilita la identificación de puntos críticos de acoplamiento y sirve como guía práctica para la posterior implementación técnica de integraciones entre microservicios.

\newpage

## Software Architecture 

### Software Architecture System Landscape Diagram

En este caso, se optó por un monolito modular con arquitectura en capas y principios de DDD para mantener cohesión interna, claridad en los dominios de negocio y simplicidad operativa en las primeras fases del proyecto. Al mismo tiempo, se decidió integrar servicios externos desplegados en la nube, como Culqi para el procesamiento seguro de pagos, Auth0 para la autenticación y gestión de identidades, y un servicio de detección de imágenes para enriquecer las funcionalidades. 

![System Landscape Diagram ](src/img/cap4/Emergentes-Landscape.png)

\newpage

### Software Architecture Context Level Diagrams  

La primera imagen muestra cómo los pacientes y nutricionistas interactúan con Foodlytics. El paciente registra su consumo y recibe un cálculo aproximado de calorías, mientras que el nutricionista accede a la misma plataforma para hacer seguimiento. Foodlytics se integra con un servicio externo de autenticación (Auth0) que gestiona accesos y con un servicio de IA (GPT4) que procesa imágenes de alimentos. Las fotos enviadas no se almacenan, solo se procesan para devolver información nutricional. El sistema actúa como punto central de interacción entre usuarios y servicios externos. 

![C4 - System context diagram ](src/img/cap4/Emergentes-Contexto.drawio.png)

\newpage

### Software Architecture Container Level Diagrams  

La segunda imagen describe la arquitectura por contenedores de Foodlytics. Los usuarios acceden a través de una aplicación móvil y una aplicación web, que se conectan con una landing page que redirige según el perfil. La API en Flask recibe datos, envía imágenes al servicio de IA y maneja autenticación con Auth0. La base de datos en Postgres guarda perfiles e históricos pero no imágenes. El servicio externo de IA procesa las fotos y devuelve calorías y macros. Cada contenedor cumple un rol definido y se conecta con los demás para mantener el flujo de información. 

![C4 - Container diagram ](src/img/cap4/Emergentes-Contenedores.drawio.png)

Al tener una arquitectura monolítica, las instrucciones del docente fue incluir los datos adicionales de los bounded contexts a modo de componentes 

![C4 - Component diagram ](src/img/cap4/Emergentes-Componentes.drawio.png)

El diagrama muestra la arquitectura de Foodlytics dividida en bounded contexts y componentes conectados. Los actores son paciente y nutricionista, quienes acceden por aplicación web y móvil. El sistema usa un servicio externo de autenticación (Auth0) y un servicio externo de IA para procesar imágenes de comida. 

En la API se agrupan los módulos: autenticación, perfil, actividad física, dashboard, notificaciones, seguimiento de pacientes y procesamiento de imágenes. Cada módulo gestiona funciones específicas y se comunica con los bounded contexts que necesita. Los anti corruption layers permiten el intercambio de datos entre bounded contexts, por ejemplo, entre gestión de pacientes y dashboard o entre gestión de dieta y reconocimiento de alimentos. 

El almacenamiento está en Foodlytics DB con soporte de un ORM, que guarda información de pacientes, perfiles, notificaciones e históricos de actividad, sin almacenar imágenes. El flujo principal es que el paciente registra comidas o actividad, la información se procesa con IA o se guarda en la base, y el nutricionista accede al dashboard para seguimiento. 

\newpage

### Software Architecture Deployment Diagrams

![Software Architecture Deployment Diagrams](src/img/cap4/Diagrama despliegue emergentes.drawio.png)

El diagrama muestra la arquitectura de despliegue de la solución, donde la aplicación móvil desarrollada en React Native y publicada en App Store y Play Store se conecta mediante una API al servidor de Hostinger, que aloja un backend monolítico en Python Flask encargado de procesar las solicitudes, ejecutar comandos SQL y comunicarse con la base de datos PostgreSQL desplegada en Railway. En el mismo servidor se encuentra el frontend web en Angular, que interactúa con la API a través de HTTPS/JSON, mientras que la Landing Page informativa se aloja de forma independiente en GitHub Pages usando React, permitiendo así que las aplicaciones móviles y web compartan los mismos servicios centralizados y se garantice consistencia de datos y escalabilidad. 

\newpage

# Capítulo V: Tactical-Level Software Design  

## Bounded Context: Image Recognition

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto AI Recognition}\label{tab:ai-recognition-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{DailyIntake} & Representa el conjunto de comidas registradas por el usuario en un día. Contiene los datos nutricionales totales y la lista de ítems reconocidos por IA.\\
Entity & \code{MealItem} & Representa una comida individual detectada en una imagen. Incluye nombre del alimento, calorías, proteínas, carbohidratos y grasas.\\
Entity & \code{RecognitionRequest} & Modela una solicitud de análisis enviada al servicio de IA. Guarda metadatos como fecha, usuario, estado y referencia al archivo procesado.\\
Value Object & \code{NutritionFacts} & Agrupa los valores nutricionales (calorías, proteínas, carbohidratos, grasas) estimados por IA.\\
Value Object & \code{ImageMetadata} & Contiene información técnica de la imagen, resolución, formato, tamaño y hash de archivo.\\
Enum & \code{RecognitionStatus} & \code{\{PENDING, PROCESSING, COMPLETED, FAILED\}}.\\
Domain Event & \code{RecognitionCompletedEvent} & Se emite cuando una imagen ha sido procesada exitosamente por el servicio de IA.\\
Domain Event & \code{RecognitionFailedEvent} & Se emite cuando la solicitud de reconocimiento falla por error de red o servicio.\\
\bottomrule
\end{tabularx}

### Interface Layer 

\begin{tabularx}{\textwidth}{L{0.22\textwidth}L{0.28\textwidth}Y}
\caption{Elementos de la capa Interface del contexto AI Recognition}\label{tab:ai-recognition-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Controller & \code{RecognitionController} & Expone endpoints REST para subir imágenes y obtener resultados de reconocimiento.\\
Resource & \code{RecognitionRequestResource} & Representa la solicitud de análisis enviada por el usuario.\\
Resource & \code{MealItemResource} & Representa los alimentos detectados y sus datos nutricionales.\\
Resource & \code{DailyIntakeResource} & Representa el resumen diario de ingesta alimenticia, listo para exposición vía API.\\
Transform & \code{RecognitionTransform} & Convierte entidades del dominio a recursos API.\\
Adapter (ACL) & \code{StorageClientAdapter} & Cliente para subir y recuperar imágenes desde el servicio de almacenamiento en la nube.\\
Adapter (ACL) & \code{AIModelClientAdapter} & Cliente para comunicarse con el motor de reconocimiento basado en IA.\\
\bottomrule
\end{tabularx}

### Application Layer  

\begin{tabularx}{\textwidth}{L{0.23\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Application del contexto AI Recognition}\label{tab:ai-recognition-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Command & \code{CreateRecognitionRequestCommand} & Solicitud para registrar una nueva imagen a analizar.\\
Command & \code{ProcessRecognitionResultCommand} & Instrucción para actualizar los resultados del análisis de IA.\\
Service & \code{RecognitionCommandService} & Gestiona el flujo de creación y actualización de solicitudes de reconocimiento.\\
Service & \code{RecognitionQueryService} & Permite consultar resultados de reconocimiento por usuario o fecha.\\
Event Handler & \code{RecognitionCompletedEventHandler} & Escucha \code{RecognitionCompletedEvent} para actualizar agregados y notificar a otros contextos.\\
Repository Interface & \code{RecognitionRepository} & Define las operaciones para persistir solicitudes e ítems de comida.\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Infrastructure del contexto AI Recognition}\label{tab:ai-recognition-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Repository Implementation & \code{SQLAlchemyRecognitionRepository} & Implementa \code{RecognitionRepository} usando SQLAlchemy.\\
ORM Model & \code{RecognitionRequestModel} & Mapea la entidad \code{RecognitionRequest} a la base de datos PostgreSQL.\\
ORM Model & \code{MealItemModel} & Mapea la entidad \code{MealItem} y sus atributos nutricionales.\\
ORM Model & \code{DailyIntakeModel} & Entidad ORM para el agregado \code{DailyIntake}.\\
External Client & \code{AIModelClient} & Cliente HTTP/gRPC para comunicarse con el servicio de reconocimiento IA.\\
External Client & \code{StorageClient} & Cliente para manejo de imágenes en la nube.\\
Unit of Work & \code{SQLAlchemyUnitOfWork} & Coordina transacciones en operaciones de reconocimiento.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Image Recognition (Component Level Diagram)](src/img/cap5/Recognition/Componente.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Image Recognition (Layer Class Diagram)](src/img/cap5/Recognition/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Image Recognition (Database Design Diagram)](src\img\cap5\Recognition\ERD _ recognition.png)

## Bounded Context: Diet Tracking 

### Domain Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Aggregate Root & \code{DietTrackingRecord} & Representa el seguimiento diario de la dieta y progreso físico de un usuario. Contiene los resultados de comparación entre el \code{DailyIntake} actual y el del día anterior. \\
\addlinespace
Aggregate (externo) & \code{DailyIntake} & Agregado raíz del contexto \code{AI Recognition}. Contiene los datos nutricionales del día (calorías, macros, etc.). \\
\addlinespace
Value Object & \code{NutrientComparison} & Diferencia entre nutrientes (calorías, proteínas, carbohidratos y grasas) de dos \code{DailyIntake} consecutivos. \\
\addlinespace
Value Object & \code{WeightComparison} & Diferencia entre el peso actual y el del día anterior. \\
\addlinespace
Value Object & \code{ProgressTrend} & Resultado del análisis conjunto de nutrientes y peso. \\
\addlinespace
Enum & \code{ProgressStatus} & \code{\{IMPROVED, DECLINED, STABLE\}}. \\
\bottomrule
\end{tabularx}
\end{table}

### Interface Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Aggregate Root & \code{DietTrackingRecord} & Representa el seguimiento diario de la dieta y progreso físico de un usuario. Contiene los resultados de comparación entre el \code{DailyIntake} actual y el del día anterior. \\
\addlinespace
Aggregate (externo) & \code{DailyIntake} & Agregado raíz del contexto \code{AI Recognition}. Contiene los datos nutricionales del día (calorías, macros, etc.). \\
\addlinespace
Value Object & \code{NutrientComparison} & Diferencia entre nutrientes (calorías, proteínas, carbohidratos y grasas) de dos \code{DailyIntake} consecutivos. \\
\addlinespace
Value Object & \code{WeightComparison} & Diferencia entre el peso actual y el del día anterior. \\
\addlinespace
Value Object & \code{ProgressTrend} & Resultado del análisis conjunto de nutrientes y peso. \\
\addlinespace
Enum & \code{ProgressStatus} & \code{\{IMPROVED, DECLINED, STABLE\}}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.22\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Command & \code{GenerateDietTrackingRecordCommand} & Instrucción para crear un nuevo registro diario y comparar con el anterior. \\
\addlinespace
Command & \code{EvaluateProgressCommand} & Evalúa el progreso del día y genera un evento si hubo mejora. \\
\addlinespace
Service & \code{GenerateDietTrackingRecordService} & Caso de uso principal. Obtiene datos desde \code{Recognition} y \code{Profile}, crea el \code{DietTrackingRecord}, evalúa progreso y publica eventos. \\
\addlinespace
Service & \code{GetProgressService} & Consulta el historial de progreso del usuario. \\
\addlinespace
Event & \code{ProgressImprovedEvent} & Evento de dominio emitido cuando el progreso del usuario mejora. \\
\addlinespace
Event Handler & \code{ProgressImprovedEventHandler} & Escucha \code{ProgressImprovedEvent} y genera una notificación en el contexto \code{Notifications}. \\
\addlinespace
Repository Interface & \code{DietTrackingRepository} & Abstracción de acceso a registros \code{DietTrackingRecord}. \\
\addlinespace
ACL Adapter & \code{NotificationClientAdapter} & Cliente para enviar notificaciones al contexto \code{Notifications}. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.28\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Repository Implementation & \code{SQLDietTrackingRepository} & Implementación concreta de \code{DietTrackingRepository} usando SQLAlchemy (o equivalente ORM). \\
\addlinespace
Repository Interface (del dominio) & \code{DietTrackingRepository} & Define operaciones como \code{save}, \code{find\_by\_user\_and\_date}, \code{find\_latest\_by\_user}. \\
\addlinespace
Event Publisher & \code{DomainEventPublisher} & Publica eventos de dominio dentro del sistema. \\
\addlinespace
Event Subscriber & \code{EventBusSubscriber} & Escucha eventos desde otros contextos si fuera necesario (no principal aquí). \\
\addlinespace
Mapper / ORM Model & \code{DietTrackingModel} & Entidad ORM equivalente a \code{DietTrackingRecord}. \\
\addlinespace
Unit of Work & \code{SQLAlchemyUnitOfWork} & Coordina transacciones de repositorios durante operaciones complejas. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Diet Tracking (Component Level Diagram)](src/img/cap5/Diet Tracking/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Diet Tracking (Layer Class Diagram)](src/img/cap5/Diet Tracking/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Diet Tracking (Database Design Diagram)](src/img/cap5/Diet Tracking/ERD.png)

## Bounded Context: Notification

### Domain Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.25\textwidth} Y}
\toprule
\textbf{Nombre} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{Notification} & Entity (Aggregate Root) & Representa una notificación interna dirigida a un usuario (paciente o nutricionista). Contiene el estado y métodos de dominio como \code{mark\_as\_read()}. \\
\addlinespace
\code{NotificationStatus} & Enum & Define los estados posibles de una notificación: \code{UNREAD}, \code{READ}. \\
\addlinespace
\code{NotificationRepository} & Interface (ABC) & Define las operaciones del repositorio: \code{save()}, \code{find\_by\_recipient()}, \code{find\_unread()}. No conoce la implementación. \\
\bottomrule
\end{tabularx}
\end{table}

### Interface Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Interface del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{NotificationController} & Flask Controller / Blueprint & Expone los endpoints REST del bounded context (\code{/notifications}, \code{/notifications/read}). Interactúa con los \code{CommandHandlers} y \code{QueryHandlers}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer 

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.33\textwidth} L{0.27\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{CreateNotificationCommand} & Command (Value Object) & Encapsula los datos necesarios para crear una notificación (\code{recipient\_id}, \code{title}, \code{message}). \\
\addlinespace
\code{MarkNotificationAsReadCommand} & Command (Value Object) & Contiene el identificador de la notificación a marcar como leída. \\
\addlinespace
\code{NotificationCommandHandler} & Application Service & Orquesta la ejecución de los comandos: crea notificaciones o actualiza su estado. Se comunica con \code{NotificationRepository}. \\
\addlinespace
\code{GetNotificationsQuery (opcional)} & Query & Permite solicitar las notificaciones de un usuario. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.33\textwidth} L{0.27\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{SqlAlchemyNotificationRepository} & Repository Implementation & Implementa \code{NotificationRepository} usando SQLAlchemy. Ejecuta persistencia y consultas en PostgreSQL. \\
\addlinespace
\code{NotificationModel (opcional)} & ORM Entity & Mapeo de la tabla \code{notifications} en la base de datos. \\
\addlinespace
\code{Unit of Work} & \code{SQLAlchemyUnitOfWork} & Coordina transacciones de repositorios durante operaciones complejas. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Notifications (Component Level Diagram)](src/img/cap5/Notifications/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Notifications (Layer Class Diagram)](src/img/cap5/Notifications/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Notifications (Database Design Diagram )](src/img/cap5/Notifications/ERD.png)

## Bounded Context: Payments

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\caption{Elementos del dominio del contexto Payments}\label{tab:payments-domain} \\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
\endfirsthead

\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
\endhead

\midrule
\multicolumn{3}{r}{\small Continúa en la siguiente página} \\
\endfoot

\bottomrule
\endlastfoot

Aggregate Root & \code{Payment} & Representa un cobro único realizado por un paciente. Atributos: \code{paymentId}, \code{amount} (\code{Money}), \code{status} \code{\{INITIATED, AUTHORIZED, CAPTURED, FAILED, REFUNDED\}}, \code{methodToken}, \code{customerId}, \code{externalTxnId}, \code{failureReason}, \code{occurredAt}. \\
Aggregate Root & \code{Subscription} & Representa una suscripción de un nutricionista. Atributos: \code{subscriptionId}, \code{planId}, \code{customerId}, \code{status} \code{\{ACTIVE, PAST\_DUE, CANCELED\}}, \code{currentPeriodStart}, \code{currentPeriodEnd}, \code{externalSubId}. \\
Value Object & \code{Money} & \code{currency}, \code{value}. Monto monetario con su moneda. \\
Value Object & \code{IdempotencyKey} & Identificador único para evitar cobros duplicados. \\
Value Object & \code{ExternalTxnId} & ID de transacción en \code{Culqi}. \\
Enum & \code{PaymentStatus} & \code{\{INITIATED, AUTHORIZED, CAPTURED, FAILED, REFUNDED\}}. \\
Enum & \code{SubscriptionStatus} & \code{\{ACTIVE, PAST\_DUE, CANCELED\}}. \\
Domain Event & \code{PaymentCaptured} & Emite un evento cuando un pago se confirma. \\
Domain Event & \code{SubscriptionRenewed} & Emite un evento cuando una suscripción se renueva automáticamente. \\
\end{tabularx}

### Interface Layer 

\begin{table}[H]
\centering
\caption{Elementos de la capa Interface del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.23\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Controller & \code{PaymentsController} & Endpoints: \code{/api/payments/charge}, \code{/api/payments/refund}, \code{/api/payments/\{paymentId\}}. \\
\addlinespace
Controller & \code{SubscriptionsController} & Endpoints: \code{/api/payments/subscriptions}, \code{/api/payments/subscriptions/\{id\}}. \\
\addlinespace
Controller & \code{CulqiWebhookController} & Endpoint \code{/api/payments/webhooks/culqi}. Verifica firma HMAC y traduce eventos \code{charge.*} y \code{subscription.*}. \\
\addlinespace
Resource & \code{CreateChargeResource} & Estructura para crear un cobro. \\
\addlinespace
Resource & \code{CreateSubscriptionResource} & Estructura para iniciar una suscripción. \\
\addlinespace
Resource & \code{RefundResource} & Datos para procesar un reembolso. \\
\addlinespace
Resource & \code{PaymentResource} & Representación API del agregado \code{Payment}. \\
\addlinespace
Resource & \code{SubscriptionResource} & Representación API del agregado \code{Subscription}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Command Service & \code{PaymentCommandService} & Métodos: \code{initiateCharge(cmd)}, \code{refund(cmd)}. Gestiona el flujo completo del pago y publica eventos. \\
\addlinespace
Command Service & \code{SubscriptionCommandService} & Métodos: \code{start(cmd)}, \code{cancel(cmd)}. Gestiona creación y cancelación de suscripciones. \\
\addlinespace
Query Service & \code{PaymentQueryService} & Consulta pagos por ID o cliente. \\
\addlinespace
Query Service & \code{SubscriptionQueryService} & Consulta suscripciones activas o por plan. \\
\addlinespace
Event Handler & \code{CulqiWebhookHandler} & Procesa eventos asíncronos desde \code{Culqi} y actualiza los agregados. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Repository Implementation & \code{SQLPaymentRepository} & Implementa \code{PaymentRepositoryPort} con SQLAlchemy. \\
\addlinespace
Repository Implementation & \code{SQLSubscriptionRepository} & Implementa \code{SubscriptionRepositoryPort} con SQLAlchemy. \\
\addlinespace
External Client & \code{CulqiClient} & Gestiona cobros, reembolsos y suscripciones vía API \code{Culqi}. \\
\addlinespace
Utility & \code{CulqiWebhookSignatureVerifier} & Verifica la firma HMAC del webhook de \code{Culqi}. \\
\addlinespace
ORM Model & \code{PaymentModel} & Entidad ORM para \code{Payment}. \\
\addlinespace
ORM Model & \code{SubscriptionModel} & Entidad ORM para \code{Subscription}. \\
\addlinespace
Unit of Work & \code{SQLAlchemyUnitOfWork} & Maneja transacciones y persistencia atómica. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Payments (Component Level Diagram)](src\img\cap5\Payments\Foodlytics - Payment Module C4.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Payments (Layer Class Diagram)](src\img\cap5\Payments\Foodlytics - Payment Module Domain Class Diagram.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Payments (Database Design Diagram )](src\img\cap5\Payments\Foodlytics - Payment Module Database.png)

## Bounded Context: Identity and Access Management 

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto IAM}\label{tab:iam-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{User} & Entidad principal que representa a cualquier persona que interactúa con el sistema. Gestiona la identidad y la autenticación.\\
Aggregate Root & \code{Patient} & Representa a un cliente que recibe asesoramiento nutricional. Es la raíz que agrupa sus métricas, dieta, comidas y objetivos.\\
Aggregate Root & \code{Nutritionist} & Representa al profesional que provee el servicio. Es la raíz que agrupa a sus pacientes asignados y las dietas que crea.\\
Entity & \code{Profile} & Contiene la información personal y de contacto común tanto para pacientes como para nutricionistas.\\
Entity & \code{Diet} & Representa un plan nutricional específico creado por un nutricionista para un paciente.\\
Entity & \code{Meal} & Representa una comida específica registrada por un paciente, con su desglose de macronutrientes.\\
Entity & \code{PatientMetrics} & Almacena un resumen del progreso del paciente en un período determinado, como peso, calorías y adherencia.\\
Entity & \code{Schedule} & Define el calendario de seguimiento del paciente, incluyendo las fechas de inicio y fin del plan.\\
Entity & \code{Goal} & Define los objetivos diarios y finales del paciente dentro de un \code{Schedule}, como las calorías o el peso objetivo.\\
Value Object & \code{Notification} & Representa un mensaje o alerta enviado a un usuario dentro del sistema.\\
\bottomrule
\end{tabularx}

### Interface Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Interface del contexto IAM}\label{tab:iam-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
API Controller & \code{AuthController} & Gestiona las solicitudes de registro e inicio de sesión, interactuando con el proveedor de identidad externo Google. \\
API Controller & \code{PatientController} & Expone endpoints para que la aplicación móvil gestione los datos del paciente, registre comidas, consulte su dieta y vea su progreso. \\
API Controller & \code{NutritionistController} & Expone endpoints para que la aplicación web gestione el dashboard, la lista de pacientes, cree dietas y vea las métricas de sus clientes. \\
API Controller & \code{MealTrackingController} & Procesa las solicitudes de registro de comidas, incluyendo la recepción de imágenes para el análisis de IA. \\
User Interface & Aplicación móvil (cliente) & Interfaz para el paciente, desarrollada en Flutter o React Native. Permite la interacción con la API. \\
User Interface & Aplicación web (nutricionista) & Interfaz para el nutricionista, desarrollada en React o Angular. Permite la interacción con la API. \\
\bottomrule
\end{tabularx}

### Application Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Application del contexto IAM}\label{tab:iam-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Application Service & \code{PatientManagementService} & Orquesta los casos de uso relacionados con la gestión de pacientes, como la asignación de un nutricionista y la actualización de datos personales.\\
Application Service & \code{DietService} & Maneja la lógica de creación, asignación y actualización de dietas por parte de los nutricionistas.\\
Application Service & \code{MealTrackingService} & Coordina el proceso de registro de una comida, desde la recepción de datos hasta la comunicación con el servicio de IA y el cálculo de macronutrientes.\\
Application Service & \code{DashboardService} & Procesa y agrega los datos necesarios para construir los dashboards tanto del paciente como del nutricionista.\\
Application Service & \code{NotificationService} & Gestiona la creación y el envío de notificaciones a los usuarios según las acciones que ocurren en el sistema (por ejemplo, nueva dieta asignada).\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Infrastructure del contexto IAM}\label{tab:iam-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Database & \code{FoodlyticsDB (PostgreSQL)} & Sistema de base de datos relacional que proporciona persistencia a todas las entidades del dominio.\\
ORM Framework & \code{SQLAlchemy} & Abstrae la comunicación con la base de datos \code{PostgreSQL}, mapeando las entidades del dominio a tablas.\\
External Service & \code{Google Identity Service} & Proveedor de identidad externo utilizado para la autenticación y autorización de usuarios (\code{OAuth 2.0}).\\
External Service & \code{AI Food Recognition API} & Servicio externo de IA que recibe imágenes de comidas y devuelve información sobre alimentos y macronutrientes.\\
File Storage & \code{Cloud Storage (e.g., S3/GCS)} & Servicio para almacenar archivos subidos por los usuarios, como imágenes de perfil o fotos de comidas.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Identity and Access Management (Component Level Diagram)](src/img/cap5/Iam/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Identity and Access Management (Layer Class Diagram)](src/img/cap5/Iam/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Identity and Access Management (Database Design Diagram )](src/img/cap5/Iam/BD.png)

## Bounded Context: Profile

### Domain Layer 

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto Profile}\label{tab:profile-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{Profile} & Representa la información personal de un usuario dentro del sistema. Es el punto central de este contexto. Contiene datos como nombre, género, contacto y fechas de registro.\\
Entity (referencia externa) & \code{User} & Entidad referenciada desde el contexto \code{IAM (Identity Access Management)}. Relación lógica mediante \code{user\_id}. No se persiste aquí.\\
\bottomrule
\end{tabularx}

### Interface Layer  

\begin{tabularx}{\textwidth}{L{0.18\textwidth}L{0.27\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Interface del contexto Profile}\label{tab:profile-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Controller & \code{ProfileController} & Expone endpoints REST para crear, obtener y actualizar perfiles de usuario. & Se comunica con los servicios de la capa de aplicación.\\
Resource & \code{ProfileResource} & Representa los datos de un perfil en las respuestas HTTP. & Generado desde la entidad \code{Profile}.\\
Transform & \code{ProfileTransform} & Convierte entre la entidad \code{Profile} y su \code{ProfileResource}. & Evita exponer directamente la capa de dominio.\\
\bottomrule
\end{tabularx}

### Application Layer 

\begin{tabularx}{\textwidth}{L{0.18\textwidth}L{0.25\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Application del contexto Profile}\label{tab:profile-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Command & \code{CreateProfileCommand} & Solicitud para registrar un nuevo perfil asociado a un usuario. & Contiene \code{user\_id}, \code{first\_name}, \code{last\_name}, \code{gender}, \code{contact\_phone}.\\
Command & \code{UpdateProfileCommand} & Solicitud para modificar los datos personales de un perfil existente. & Contiene campos opcionales de actualización.\\
Query & \code{GetProfileByUserIdQuery} & Permite recuperar el perfil asociado a un usuario. & Devuelve un objeto \code{Profile}.\\
Service & \code{ProfileCommandService} & Gestiona operaciones de creación y actualización de perfiles. & Aplica reglas de negocio básicas antes de persistir.\\
Service & \code{ProfileQueryService} & Gestiona la lectura de perfiles desde el repositorio. & Se usa en consultas \code{GET}.\\
Repository Interface & \code{ProfileRepository} & Abstracción para la persistencia de entidades \code{Profile}. & Implementado en la capa de infraestructura.\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.20\textwidth}L{0.28\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Infrastructure del contexto Profile}\label{tab:profile-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Repository Implementation & \code{SQLAlchemyProfileRepository} & Implementación concreta del repositorio de perfiles con SQLAlchemy. & Gestiona operaciones CRUD sobre la tabla \code{profile}.\\
ORM Model & \code{ProfileModel} & Mapea la entidad de dominio \code{Profile} a la base de datos \code{PostgreSQL}. & Define columnas y restricciones (\code{id}, \code{user\_id}, \code{first\_name}, etc.).\\
Database Table & \code{profile} & Tabla persistente que almacena los datos de perfil. & Campos: \code{id}, \code{user\_id}, \code{first\_name}, \code{last\_name}, \code{gender}, \code{contact\_phone}, \code{updated\_at}, \code{created\_at}.\\
ACL Adapter & \code{UserClientAdapter} & Conector hacia el contexto \code{IAM} para validar existencia del usuario (\code{user\_id}). & Se invoca antes de crear un perfil.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Profile (Component Level Diagram)](src\img\cap5\Profile\Emergentes-Profile.drawio.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Profile (Layer Class Diagram)](src/img/cap5/Profile/CLASES.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Profile (Database Design Diagram )](src/img/cap5/Profile/ERD.png)

# Capítulo VI: Solution UX Design  

## Style Guidelines  
### General Style Guidelines  
### Web, Mobile & Devices Style Guidelines  

## Information Architecture  
### Labeling Systems  
### Searching Systems  
### SEO Tags and Meta Tags  
### Navigation Systems  

## Landing Page UI Design  
### Landing Page Wireframe  
### Landing Page Mock-up  

## Applications UX/UI Design  
### Applications Wireframes  
### Applications Wireflow Diagrams  


# **Conclusiones** 

En primer lugar, se concluye que el análisis de mercado evidenció de manera clara la necesidad de una solución digital de nutrición adaptada al contexto peruano, lo que refuerza la pertinencia del desarrollo de Foodlytics y la validez de la propuesta de valor planteada. Este hallazgo permitió confirmar que la problemática identificada no solo es real, sino que constituye una oportunidad estratégica para introducir un producto innovador en el sector salud digital.

Asimismo, la integración de inteligencia artificial con una base de datos culturalmente adaptada a los alimentos peruanos representa un diferenciador competitivo frente a aplicaciones globales. Esta característica, además de responder a las necesidades locales, fortalece la propuesta frente a la competencia al ofrecer una experiencia personalizada y alineada con la realidad gastronómica del país.

Por otro lado, las entrevistas realizadas a nutricionistas y pacientes validaron los principales pain points detectados, como la baja adherencia a los planes nutricionales, los registros manuales poco confiables y la falta de retroalimentación constante. De esta manera, se corroboró que los usuarios potenciales reconocen valor en una aplicación que resuelva estas limitaciones mediante el registro automático de comidas.

Del mismo modo, la aplicación del proceso Lean UX permitió estructurar hipótesis verificables que orientaron la solución hacia resultados medibles. Esta metodología se consolidó como un enfoque fundamental para asegurar que la propuesta no solo sea técnicamente viable, sino también relevante y sostenible para los usuarios finales.

Además, el uso de EventStorming y Context Mapping facilitó la comprensión compartida de los procesos centrales, aportando claridad en la definición de los bounded contexts y en la futura arquitectura del sistema. Esta práctica contribuyó a generar un diseño inicial más robusto y coherente con las necesidades identificadas.

En esa misma línea, la definición de drivers de calidad y restricciones técnicas estableció una base sólida para las decisiones arquitectónicas, priorizando criterios como escalabilidad, facilidad de uso y precisión en los cálculos. Esto permitirá que la solución evolucione de manera ordenada y confiable en fases posteriores.

De igual forma, el análisis competitivo demostró que las soluciones existentes carecen de un enfoque cultural y de una interacción efectiva entre especialista y paciente, lo cual abre una brecha de mercado que Foodlytics puede cubrir. Este diagnóstico orientó estrategias de diferenciación y posicionamiento que consolidan la relevancia del proyecto.

Asimismo, la estructuración del backlog y de las user stories permitió traducir los hallazgos de la investigación en requerimientos funcionales y no funcionales concretos. Esta trazabilidad asegura que la propuesta de valor inicial se vea reflejada en el diseño y la implementación futura de la solución tecnológica.

Por otra parte, el trabajo colaborativo del equipo, evidenciado en el uso del tablero Kanban y en el registro de versiones, garantizó una distribución equitativa de responsabilidades y la culminación exitosa del entregable. Este aspecto demostró la capacidad de gestión y organización en el cumplimiento de los objetivos propuestos.

Finalmente, la comunicación oral y escrita del grupo se consolidó como un componente esencial para transmitir tanto la visión estratégica como los aspectos técnicos del proyecto, alcanzando el Student Outcome ABET-EAC 3. En conclusión, la TB1 permitió sentar bases estratégicas, técnicas y metodológicas sólidas que aseguran la viabilidad del proyecto y posicionan a Foodlytics como una propuesta innovadora y culturalmente pertinente para la salud digital en el Perú.

\newpage


# **Recomendaciones.**  

En primer lugar, comprendimos la importancia de ampliar la validación con usuarios a través de entrevistas y pruebas piloto que involucren segmentos más diversos, como adultos mayores y pacientes en zonas rurales, ya que esto permitirá asegurar que la solución tenga un alcance inclusivo y no se limite únicamente a un público urbano joven. Asimismo, reconocimos que la base de datos de alimentos debe enriquecerse con una representación más amplia de la gastronomía nacional, incorporando platos de la costa, sierra y selva, lo cual incrementará la pertinencia cultural de la aplicación y reforzará su valor frente a soluciones globales.

Por otro lado, asumimos la necesidad de optimizar el modelo de inteligencia artificial mediante un entrenamiento continuo con datasets validados por especialistas, de modo que se reduzcan errores en el reconocimiento de porciones y se garantice la confiabilidad de los cálculos nutricionales. Del mismo modo, vimos relevante diseñar mecanismos de retroalimentación que permitan a los usuarios ajustar sus registros, generando un ciclo de mejora continua que enriquezca tanto la experiencia del paciente como la precisión de la herramienta.

Además, entendimos que la protección de datos personales debe ser un eje central del proyecto, por lo que aplicaremos protocolos alineados a la normativa nacional e internacional, garantizando privacidad, seguridad y confianza en el uso de la aplicación. Igualmente, identificamos que los nutricionistas requieren flexibilidad en el uso de la herramienta, por lo que se recomienda implementar dashboards personalizables y reportes adaptados a diferentes contextos clínicos.

En esa misma línea, reconocimos que el fortalecimiento de alianzas estratégicas con universidades, clínicas y asociaciones profesionales será clave para validar la solución en entornos reales y acelerar su adopción en el mercado. También vimos necesario planificar la escalabilidad de la arquitectura, asegurando que la aplicación soporte un crecimiento sostenido sin comprometer la experiencia de usuario.

Finalmente, concluimos que debemos integrar elementos de gamificación, notificaciones inteligentes y recompensas digitales como estrategias de motivación para mejorar la adherencia de los pacientes. Asimismo, nos comprometemos a monitorear constantemente indicadores clave de desempeño como la retención de usuarios, la satisfacción de pacientes y la adopción por parte de especialistas, ya que estos servirán como guía para implementar ajustes ágiles y mantener la mejora continua del proyecto.

\newpage

# **Referencias Bibliográficas**

\begingroup
\setlength\parindent{-0.5cm} 
\setlength\leftskip{0.5cm}  
\setlength\parskip{0.2cm}    

Appvizer. (2023, 17 de marzo). Método 5W: definición, ejemplos concretos y ventajas. Appvizer. \url{https://www.appvizer.es/revista/organizacion-planificacion/gestion-proyectos/5w-definicion-ejemplos-concretos-y-ventajas-metodo-5-w}

Benyon, D. (2014). \textit{Designing interactive systems: A comprehensive guide to HCI, UX \& interaction design} (3rd ed.). Pearson Education.

Brown, T. (2009). \textit{Change by design: How design thinking creates new alternatives for business and society}. Harvard Business Press.

Colegio de Nutricionistas del Perú. (2023). \textit{Informe estadístico de profesionales colegiados}. CNP. \url{https://www.cnp.org.p}

Cutipa-Coro. (2024). Estudio bibliométrico sobre marketing digital y posicionamiento en la industria de laboratorios clínicos. \textit{Revista Veritas de Difusão Científica}. \url{https://revistaveritas.org/index.php/veritas/article/view/155}

Hermoza Arámbulo, R. D., Matellini Mosca, B. M., Rosales Rojas, A. J., \& Noriega Ruiz, V. H. (2017). Adherencia a terapia médica nutricional en pacientes con diabetes mellitus tipo 2, de un hospital nacional de nivel III en Lima, Perú [Artículo]. \textit{Revista Médica Herediana, 28}(3), 150–156.

Huerta Álvarez, R. A., Villalobos Vivanco, S. R., Vidal Huamán, F. G., \& Palomino Quispe, L. P. (2024). Estado nutricional y consumo de alimentos ultraprocesados en adultos de Lima – Perú. \textit{Nutrición Clínica y Dietética Hospitalaria, 44}(2), 137–144.

Instituto Nacional de Estadística e Informática. (2023). \textit{Encuesta Demográfica y de Salud Familiar 2023}. INEI. \url{https://www.inei.gob.pe}

Instituto Nacional de Salud. (2023). \textit{Abordaje nutricional para la prevención y control del sobrepeso y la obesidad tipo I} [Documento técnico]. Lima, Perú: INS.

Lean UX. (s.f.). In O’Reilly. \url{https://www.oreilly.com/library/view/lean-ux-3rd/9781098116293/ch06.html}

Ministerio de Salud. (2022). \textit{Plan nacional de prevención y control del sobrepeso, obesidad y diabetes mellitus tipo 2, 2022-2030 (RM 158-2022-MINSA)}. Biblioteca Virtual en Salud. \url{https://bvs.minsa.gob.pe/local/covid/boletin/RM-158-2022-MINSA.pdf}

Ministerio de Salud. (2023). \textit{Abordaje nutricional para la prevención y control del sobrepeso y la obesidad tipo I}. Instituto Nacional de Salud. \url{https://alimentacionsaludable.ins.gob.pe/sites/default/files/2023-04/ABORDAJE%20NUTRICIONAL%20PARA%20LA%20PREVENCI%C3%93N%20Y%20CONTROL%20DEL%20SOBREPESO%20Y%20LA%20OBESIDAD%20TIPO%20I.pdf}

Ministerio de Salud. (2023). \textit{Nutricionistas advierten que 7 de cada 10 peruanos sufre de exceso de peso} [Nota de prensa]. Lima, Perú: Ministerio de Salud.

Ministerio de Salud. (2025, 18 de enero). Semana de Oro del Perú 2025: el 62 \% de la población peruana mayor de 15 años tiene exceso de peso. Gobierno del Perú. \url{https://www.gob.pe/institucion/minsa/noticias/1210470-semana-de-oro-del-peru-2025-el-62-de-la-poblacion-peruana-mayor-de-15-anos-tiene-exceso-de-peso}

Munive Yachachi, Y. A. (2023). \textit{Adherencia al tratamiento dietético y estado nutricional en pacientes adultos con enfermedad renal crónica terminal en un hospital nacional, Lima} [Tesis de maestría, Universidad Nacional Mayor de San Marcos]. UNMSM-Tesis.

Observatorio Peruano para el Desarrollo. (s.f.). \textit{Incremento del sobrepeso y la obesidad}. observatorio.ceplan.gob.pe.

Valdárrago De la Mata, F. O. (2024). \textit{Reducción del exceso de peso en población peruana: cifras en Lima Metropolitana y Callao} [Tesis de maestría, Universidad Nacional Federico Villarreal]. Repositorio UNFV.

\endgroup
