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
  tb1 & 15/09/2025 & Poma Espinoza, Gustavo  & Desarrollé el diseño de entrevistas, el registro de resultados y su análisis. Apoyé en el modelado de dominios (EventStorming y Context Mapping). \\
  \hline
  tb1 & 25/09/2025 & Del Castillo Bueno, Daniel Mateo & Redacté contenidos sobre decisiones técnicas y arquitectónicas, escenarios de calidad, restricciones y drivers de diseño. También apoyé en el backlog arquitectónico. \\
  \hline
  tb1 & 25/09/2025 & Ramos Rios, Belén del Rocio & Integré los apartados del documento en LaTeX, asegurando uniformidad y coherencia entre secciones. Coordiné la presentación final del entregable. \\
  \hline
  tb1 & 25/09/2025 & Vilchez Rios, Mateo Alejandro & Redacté antecedentes, problemática y objetivos. Elaboré User Stories y el Product Backlog, definiendo requerimientos del sistema. \\
  \hline
  tp & 30/09/2025 & Zavala Quedena, Gonzalo Andre & Tactical-Level Software Design of Payments. \\
  \hline
  tp & 30/09/2025 & Poma Espinoza, Gustavo  & Tactical-Level Software Design of IAM. \\
  \hline
  tp & 02/10/2025 & Del Castillo Bueno, Daniel Mateo & Tactical-Level Software Design of Diet Tracking, Profile, Notifications and Image Recognition. \\
  \hline
  tp & 05/10/2025 & Ramos Rios, Belén del Rocio & Solution UX Design of Landing Page and Mobile Application. \\
  \hline
  tp & 10/10/2025 & Vilchez Rios, Mateo Alejandro & Solution UX Design of Web Application. \\
  \hline
  tb2 & 20/11/2025 & Zavala Quedena, Gonzalo Andre & Product Implementation, Validation and Deployment. Participé en Solution Implementation y en la elaboración del Video About-the-Product. \\
  \hline
  tb2 & 20/11/2025 & Poma Espinoza, Gustavo & Product Implementation, Validation and Deployment. Contribuí en Solution Implementation y en el Video About-the-Product. \\
  \hline
  tb2 & 20/11/2025 & Del Castillo Bueno, Daniel Mateo & Product Implementation, Validation and Deployment. Colaboré en Solution Implementation y en la creación del Video About-the-Product. \\
  \hline
  tb2 & 20/11/2025 & Ramos Rios, Belén del Rocio & Applications UX/UI Design y Applications Prototyping. Participé en Product Implementation, Validation and Deployment. Apoyé en Solution Implementation y en el Video About-the-Product. \\
  \hline
  tb2 & 20/11/2025 & Vilchez Rios, Mateo Alejandro & Applications UX/UI Design y Applications Prototyping. Contribuí en Product Implementation, Validation and Deployment. Participé en Solution Implementation y en el Video About-the-Product. \\
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

**Entregable TP:**

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

\newpage

**Entregable TB2:**

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/GMB-Labs/GMB_Labs-Report/pulse)
:::


**Tablero Kanban:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/1)](src/img/cap1/insights-kanban-todo.png){ width=85% }

**Kanban List:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/2)](src/img/cap1/insights-kanban-list.png){ width=85% }

\newpage

**Traffic Map - Mobile App:**

![Organización GMB Labs, imagen extraída de Github[URL](https://github.com/GMB-Labs/Foodlytics-Mobile-Application/graphs/traffic)](src/img/cap1/mobileapp.png){ width=85% }

**Traffic Map - Web App:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/GMB-Labs/Foodlytics-Web-Application/graphs/traffic)](src/img/cap1/webApp.png){ width=85% }

**Traffic Map - Backend App:**

![Organización GMB Labs, imagen extraída de Github[URL](https://github.com/GMB-Labs/foodlytics-api/graphs/traffic) ](src/img/cap1/backend.png){ width=85% }

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

El diseño de experiencia de usuario de Foodlytics conecta la funcionalidad técnica del sistema con una interacción visual clara y significativa. Esta etapa busca garantizar que cada punto de contacto entre el usuario y el producto refleje precisión, accesibilidad y coherencia. El enfoque se basa en los hallazgos obtenidos en la fase de análisis de requisitos y needfinding, donde su propósito es optimizar la comprensión de datos nutricionales, reducir el esfuerzo cognitivo del usuario y facilitar la toma de decisiones informadas.

## Style Guidelines  

![Artefacto creado en Figma](src/img/cap6/Style_Guidelines.png)

Los lineamientos de estilo definen la identidad visual y el lenguaje gráfico que guían todas las interfaces de Foodlytics. Su propósito es mantener coherencia entre la aplicación web, la app móvil y los materiales de comunicación asociados, asegurando una experiencia homogénea sin importar el punto de acceso.

El sistema de diseño se apoya en principios de accesibilidad (WCAG 2.1 AA) y en una estructura modular que permite escalar y adaptar la interfaz a nuevos contextos o dispositivos. Su aplicación garantiza que tanto nutricionistas como pacientes interactúen con una interfaz clara, moderna y alineada con los valores de precisión, salud y bienestar que caracterizan a Foodlytics.

\newpage

### General Style Guidelines

En el diseño de productos digitales, la estética cumple una función estratégica: orientar la interacción, transmitir confianza y reducir la carga cognitiva del usuario. Un lenguaje visual bien estructurado, con criterios definidos sobre identidad, color, tipografía y tono comunicacional, permite que la experiencia sea clara, coherente y funcional.

\vspace{1em}

\begin{quote}
Norman (2024) señala que un diseño visual efectivo no se basa en adornos, sino en la capacidad de guiar al usuario sin distraerlo. La simplicidad no implica ausencia de intención, sino precisión en cada elemento que conforma la interfaz.
\end{quote}

\vspace{1em}

Bajo este enfoque, el sistema visual de *Foodlytics* se diseña para conectar tres dimensiones: la funcionalidad técnica del software, la comprensión de datos nutricionales y la sensación de control que el usuario busca al gestionar su bienestar. El objetivo es construir una identidad visual flexible y consistente que mantenga la misma lógica en la web, la app móvil y el material de comunicación.

\vspace{2em}

**Branding:**

*Foodlytics* es una solución tecnológica desarrollada por GMB Labs que integra inteligencia artificial y nutrición digital para optimizar la alimentación de los pacientes y facilitar el trabajo de los profesionales de la salud.
Su identidad visual refleja bienestar, precisión y confianza, valores esenciales en el ámbito de la nutrición y la tecnología médica. La plataforma busca simplificar el análisis de información nutricional mediante una experiencia visual clara, accesible y basada en datos.

Cada elemento del branding (colores, tipografía y estilo visual) fue diseñado para reforzar la misión de *Foodlytics*: ayudar a las personas a comprender mejor su alimentación, promoviendo hábitos sostenibles a través de una interfaz intuitiva y coherente en todos los entornos digitales.

\newpage

**Logotipo:**

El logotipo de *Foodlytics* fue creado para representar visualmente la unión entre alimentación y tecnología. Su símbolo principal integra un tenedor dentro de la letra “F”, lo que genera una identidad distintiva y funcional que resume el propósito de la marca: conectar la comida (*food*) con el análisis de datos (*analytics*).

El color verde menta transmite frescura, salud y equilibrio, mientras que la tipografía redondeada refuerza la accesibilidad y la claridad de la marca. El diseño mantiene proporciones equilibradas que aseguran una lectura nítida en diferentes dispositivos y tamaños.

Además, se han definido variantes del logotipo para asegurar su correcta visibilidad en diferentes fondos y dispositivos, sin perder coherencia ni legibilidad en entornos web y móviles.

![Artefacto creado en Figma](src/img/cap6/LogosFoodlytics.png)

\newpage

**Iconografía de la Aplicación**

La iconografía de Foodlytics se fundamenta en el uso del símbolo principal de la marca —la “F” con forma de tenedor— como ícono distintivo dentro de la aplicación móvil y web. Este elemento sintetiza la esencia del producto: la unión entre alimentación y análisis de datos.

Su diseño minimalista y geométrico permite mantener claridad visual en diferentes tamaños, garantizando reconocimiento inmediato en pantallas reducidas o interfaces densas en información. El ícono fue optimizado para conservar legibilidad en versiones claras y oscuras, con bordes suaves y proporciones equilibradas que refuerzan la identidad moderna y accesible de la marca.

Además, se definieron variantes monocromáticas y de contorno adaptables a distintos fondos, optimizadas para su uso en interfaces, favicons, aplicaciones móviles y material promocional. Estas versiones aseguran coherencia visual en todo el ecosistema digital de *Foodlytics*, manteniendo un estilo consistente, profesional y alineado con el enfoque de salud y tecnología del producto.

El uso del ícono en la aplicación móvil se centra en su función como elemento principal de reconocimiento. Aparece en la pantalla de inicio y en el sistema de notificaciones, consolidando la presencia de la marca en los dispositivos del usuario.

![Artefacto creado en Figma](src/img/cap6/Icon_App.png)

\newpage

**Paleta de colores**

La paleta de colores está estructurada en tres grupos principales: los colores de marca, los colores de estado y los colores de texto. Esta clasificación permite mantener una coherencia visual sólida, adaptando el uso del color según su función en la experiencia del usuario y en la identidad de la marca. Cada tono ha sido seleccionado para equilibrar accesibilidad, contraste y armonía visual, garantizando una lectura clara en todos los dispositivos y contextos de uso.

\vspace{2em}

1) **Brand Colors**

  La paleta cromática fue diseñada para reflejar los valores fundamentales del producto: bienestar, precisión y equilibrio. Cada color cumple una función específica dentro del sistema visual, reforzando la identidad tecnológica y accesible de la marca.

  Los tonos principales se basan en verdes menta y turquesa, que transmiten frescura y vitalidad, características asociadas a la alimentación saludable y a la innovación digital. Los colores secundarios complementan esta gama aportando flexibilidad visual y contraste en distintas interfaces, asegurando legibilidad y coherencia tanto en entornos claros como oscuros.

  El uso intencional del color contribuye a la experiencia del usuario al guiar la atención hacia elementos interactivos y datos relevantes. En interfaces nutricionales, estos matices generan una sensación de orden, limpieza y confianza, aspectos esenciales en productos que procesan información de salud.

\newpage

- **Colores Principales (*Primary Colors*)**

  Estos colores son la base del sistema visual y se aplican en la interfaz principal, botones de acción y componentes destacados de la aplicación web y móvil.
    
  - **Verde Menta (#2FCBAC):** Color principal de marca. Representa equilibrio, bienestar y claridad. Se utiliza en elementos de acción, gráficos y botones principales.
  
  - **Turquesa Claro (#50D9BE):** Acento complementario que aporta dinamismo y sensación de frescura.
  
  - **Aqua Suave (#74E3CD):** Tono auxiliar que suaviza transiciones y fondos secundarios.
  
  - **Verde Pastel (#99ECDC):** Empleado en componentes informativos o de retroalimentación, aporta ligereza visual.

 ![Artefacto creado en Figma](src/img/cap6/BrandColors1.png)

\newpage

- **Colores Secundarios (*Secondary Colors*)**

  Los tonos secundarios amplían la paleta para aplicaciones contextuales, gráficos, dashboards y fondos de contraste. Mantienen armonía con los colores primarios y permiten flexibilidad en entornos digitales y materiales promocionales.
    
  - **Verde Esmeralda (#40BF82):** Color principal de marca. Representa equilibrio, bienestar y claridad. Se utiliza en elementos de acción, gráficos y botones principales.
  
  - **Verde Suave (#60CD99):** Usado en componentes neutrales y áreas de información.
  
  - **Verde Desaturado (#82D9B0)** Complementa el verde principal en interfaces minimalistas o de baja carga visual.
  
  - **Verde Claro (#A4E5C6):** Aplicado en fondos suaves, tarjetas informativas y espacios de descanso visual.
  
  ![Artefacto creado en Figma](src/img/cap6/BrandColors2.png)

\newpage

2) **State Colors**

La paleta de colores de estado en Foodlytics está diseñada para comunicar de forma inmediata el tipo y la relevancia de cada mensaje dentro del sistema. Estos tonos se aplican en notificaciones, alertas, validaciones y reportes nutricionales, guiando la atención del usuario y mejorando la comprensión visual de la información.

Cada color transmite un significado específico que refuerza la claridad del contenido y facilita la toma de decisiones. Su uso coherente en toda la interfaz garantiza una comunicación visual unificada, manteniendo el equilibrio entre funcionalidad y estética.

\vspace{1em}

- **Colores de Estado (*State Colors*)**
    
  - **Info Color (#1D88FE):** Representa información general, consejos o recordatorios no críticos. Se utiliza en mensajes informativos, tooltips y alertas suaves relacionadas con el progreso o cambios recientes en los hábitos alimenticios.
  
  - **Error Color (#FF5A65):** Indica errores, inconsistencias o acciones que requieren corrección. Se aplica en validaciones de formularios, advertencias de datos incompletos y notificaciones sobre fallos en el registro de alimentos o sincronización.
  
  - **Success Color (#05C168):** Señala acciones completadas o resultados favorables, como la correcta detección de un alimento o el cumplimiento de metas nutricionales. Transmite sensación de logro y confianza.
  
  - **Warning Color (#FDB52A):** Alerta sobre situaciones que requieren atención, pero no representan error. Se usa para notificar excesos calóricos, desequilibrios de macros o posibles inconsistencias detectadas por la IA.
  
  \vspace{1em}

  ![Artefacto creado en Figma](src/img/cap6/StateColors.png)

\newpage

3) **TextColors**

El sistema de color para texto asegura legibilidad y jerarquía en todas las interfaces. Los tonos seleccionados funcionan sobre fondos claros y mantienen contraste conforme a WCAG 2.1 AA en tamaños estándar.

\vspace{1em}

- **Colores de Estado (*State Colors*)**
    
  - **Negro Intenso (#0F0A0A):** Color principal para títulos, encabezados y métricas. Aporta fuerza visual y alta legibilidad.
  
  - **Gris Oscuro (#262424):** Usado en subtítulos, etiquetas o texto secundario. Ofrece equilibrio visual sin distraer.
  
  - **Gris Neutro (#231C1C):** Ideal para párrafos y descripciones extensas. Mantiene una lectura cómoda y fluida.
  
  - **Gris Profundo (#1B1111):** Se emplea en componentes densos o sobre fondos claros para resaltar contraste.

  - **Gris Claro (#A7A7A7):** Utilizado en placeholders, estados deshabilitados o notas informativas.

\vspace{1em}

  ![Artefacto creado en Figma](src/img/cap6/TextColors.png)

\newpage

**Tipografía**

La identidad tipográfica de Foodlytics ha sido cuidadosamente definida para garantizar legibilidad, jerarquía visual y consistencia en todas sus plataformas: landing page, aplicación web y aplicación móvil. Se emplean diferentes fuentes según el entorno, adaptadas a las necesidades visuales y funcionales de cada interfaz.

\vspace{1em}

1. ***Landing Page***

- ***Outfit* (Google Fonts)**
  
  - Pesos utilizados: *Black, Bold, Medium, Regular, Light*
  
  Outfit es la tipografía principal de la landing page de Foodlytics. Su estructura geométrica y alto contraste visual facilitan la lectura de títulos y subtítulos, destacando mensajes clave y llamados a la acción. Los pesos más gruesos (Bold y Black) se aplican en secciones hero y encabezados principales, mientras que las variantes Medium y Regular aportan equilibrio en textos de apoyo y descripciones.

  ![Artefacto creado en Figma](src/img/cap6/Typography_Outfit_landingWeb.png)

\newpage

- ***Inter* (Google Fonts)**
  
  - Peso utilizado: *Light, Regular, Medium, Bold*
  
  Inter se utiliza en elementos secundarios de la landing page, como botones, badges y texto de soporte. Su diseño optimizado para pantallas mejora la lectura en tamaños pequeños y asegura consistencia con la interfaz de la aplicación. La combinación de ambas familias crea una jerarquía clara entre los mensajes informativos y los interactivos.

  ![Artefacto creado en Figma](src/img/cap6/Typography_Inter_landing.png)

- **Niveles Tipográficos Definidos:**

  - **Títulos principales (Hero, secciones):** *Outfit — Bold / Black *(700–900)

  - **Subtítulos y encabezados secundarios:** *Outfit — Medium* (500)

  - **Párrafos y texto descriptivo:** *Inter — Regular* (400)

  - **Detalles o etiquetas (badges, botones, inputs):** *Inter — Medium* (500)

  - **Texto de soporte o notas técnicas:** *Inter — Light* (300)

\newpage

2. **Aplicación Web**

- ***Outfit* (Google Fonts)**
  
  - Peso utilizado: *Bold, Medium, Regular* 
  
  *Outfit* es la fuente principal empleada en la interfaz web. Su estructura sencilla y bien espaciada la hace ideal para entornos digitales centrados en la usabilidad. El peso Bold se asigna a títulos, Medium a subtítulos y elementos intermedios, y Regular al contenido general del sistema.

  ![Artefacto creado en Figma](src/img/cap6/Typography_Outfit_landingWeb.png)

- ***Roboto* (Google Fonts)**
  
  - Peso utilizado: *Light, Regular, Regular* 
  
  *Roboto* se emplea como fuente de apoyo dentro de componentes técnicos del sistema, especialmente en interfaces construidas con Angular Material. Su lectura sencilla y proporciones neutras mejoran la integración con controles interactivos, inputs y menús contextuales.

  ![Artefacto creado en Figma](src/img/cap6/Typography_Roboto.png)

- ***Material Symbols Outlined***
  
  - Sistema de íconos oficial de Google Material.
  
  Este set tipográfico se utiliza para representar íconos en botones, paneles y menús de navegación, manteniendo un lenguaje visual coherente con la estética general del sistema.

  ![Artefacto creado en Figma](src/img/cap6/material.png)

\newpage

3. **Aplicación Movil**

- ***Poppins* (Google Fonts)**
  
  - Peso utilizado: *Bold, Medium, Regular*
  
   *Poppins* es la tipografía principal de la app móvil. Su diseño geométrico y moderno contribuye a una interfaz clara y coherente. La versión Bold se utiliza para títulos y acciones clave, aportando énfasis visual. Medium se aplica en subtítulos y encabezados secundarios, manteniendo una jerarquía visual sólida. Y regular es ideal para el cuerpo del texto, asegurando una lectura fluida y accesible.

  ![Artefacto creado en Figma](src/img/cap6/Typography_Poppins_app.png)

\newpage

**Tonos de Comunicación**

El tono de comunicación combina cercanía, claridad y profesionalismo. Está diseñado para transmitir confianza a nutricionistas y empatía a pacientes, reflejando el equilibrio entre tecnología de precisión y acompañamiento humano. Cada mensaje busca orientar, educar y motivar sin imponer, manteniendo siempre una voz accesible y optimista.

El lenguaje se mantiene respetuoso, amigable y claro, evitando tecnicismos innecesarios y priorizando explicaciones simples que fomenten la comprensión de los datos nutricionales. El objetivo es lograr que el usuario perciba la aplicación como una herramienta confiable, moderna y fácil de usar, que simplifica su gestión diaria sin perder calidez.

- **Neutral y Profesional:** El discurso conserva rigor informativo, especialmente en reportes o métricas.

- **Amigable y Cercano:** Se emplea un tono positivo, empático y alentador en mensajes de interacción o recordatorios.

- **Respetuoso y Cortés:** La comunicación mantiene cortesía y cuidado en notificaciones o recomendaciones alimentarias.

- **Entusiasta y Claro:** El tono celebra los logros del usuario, reforzando el sentido de progreso sin exagerar.

![Artefacto creado en Figma](src/img/cap6/ToneOfVoice.png)

\vspace{1em}

**Eslogan**

El eslogan de *Foodlytics* sintetiza la esencia de la marca y su propuesta de valor: simplificar la nutrición mediante el uso inteligente de la tecnología. Expresa el propósito central del producto y guía la experiencia de usuario bajo tres principios: claridad, bienestar y accesibilidad.

![Artefacto creado en Figma](src/img/cap6/Eslogan.png)

Este mensaje transmite precisión y empatía. Refleja una herramienta que transforma la gestión nutricional en una experiencia intuitiva, visual y práctica. El eslogan conecta con ambos públicos del sistema —pacientes y nutricionistas— al enfatizar la simplicidad sin perder el enfoque técnico.

\newpage

### Web, Mobile & Devices Style Guidelines

![Artefacto creado en Figma](src/img/cap6/cover.png)

Esta sección presenta la aplicación de los lineamientos visuales de Foodlytics dentro de cada entorno digital del sistema. A partir de los principios definidos en las guías generales de estilo, se detalla cómo se implementan los componentes visuales, la estructura de grillas, los formularios y los elementos interactivos en las plataformas web y móvil.

El objetivo es asegurar una experiencia coherente, accesible y fluida para los dos perfiles principales del sistema: nutricionistas y pacientes. Cada componente fue diseñado para optimizar la interpretación de datos y facilitar la toma de decisiones dentro de su contexto de uso.

La versión web prioriza la claridad en la presentación de información analítica y la eficiencia en la navegación entre módulos, mientras que la aplicación móvil enfatiza la simplicidad, el seguimiento visual y la interacción rápida. Ambas mantienen una identidad unificada, sustentada en una jerarquía visual clara, tipografía legible y colores consistentes con la marca.

1. **Sistema de Grillas (*Grid System*)**

- **Propósito**

  El sistema de grillas es el esqueleto visual que estructura toda la experiencia de usuario en Foodlytics. Su función es establecer un orden lógico y armónico en la disposición de los elementos en pantalla, garantizando legibilidad y consistencia visual entre las diferentes plataformas.

  Una grilla flexible y adaptativa permite que el contenido se ajuste a múltiples dispositivos sin perder claridad ni equilibrio visual. En un sistema como Foodlytics —que abarca interfaces analíticas para nutricionistas y entornos móviles para pacientes—, contar con una grilla bien definida es esencial para mantener una experiencia coherente, accesible y profesional en todos los contextos de uso.

- **Justificación de las decisiones de diseño**

  Para definir las resoluciones y el número de columnas se tomaron como referencia los siguientes criterios:

  - Estándares de diseño responsive ampliamente adoptados, como los establecidos por Material Design y Bootstrap (12 columnas para escritorio, reducción progresiva para móviles).

  - Análisis de los dispositivos más utilizados por los perfiles de usuario de Foodlytics, obtenidos a partir de las entrevistas y cuestionarios aplicados durante la fase de investigación. En estos se identificó que los nutricionistas emplean principalmente computadoras portátiles y tablets para análisis y reportes, mientras que los pacientes acceden mediante smartphones para registrar alimentos y visualizar su progreso.

  - **Escenarios de uso específicos:**

    - La interfaz del nutricionista debe mostrar métricas, reportes y gráficos con jerarquía y claridad visual.  

    - La interfaz del paciente debe priorizar accesibilidad, fluidez y simplicidad, facilitando la interacción rápida en dispositivos móviles.

    - La aplicación web debe soportar visualización avanzada de datos, edición de información y generación de informes.

- **Configuración técnica adoptada**

  A continuación, se muestra una tabla con las configuraciones técnicas definidas para cada tipo de plataforma:

\begin{longtable}{|c|c|c|c|c|}
\hline
\textbf{Plataforma} & \textbf{Resolución} & \textbf{Columnas} & \textbf{Gutter (px)} & \textbf{Ancho de columna (px)} \\
\hline
\endfirsthead
\hline
\textbf{Plataforma} & \textbf{Resolución} & \textbf{Columnas} & \textbf{Gutter (px)} & \textbf{Ancho de columna (px)} \\
\hline
\endhead
Web HD & 1440 $\times$ 1024 & 12 & 30 & 65 \\
\hline
Web Estándar & 1024 $\times$ 1024 & 12 & 30 & 50 \\
\hline
Tablet & 768 $\times$ 1024 & 6 & 30 & 88 \\
\hline
Smartphone & 320 $\times$ 1024 & 2 & 30 & 130 \\
\hline
\end{longtable}

Estas configuraciones permiten distribuir el contenido de manera eficiente y visualmente equilibrada en cada dispositivo, manteniendo coherencia entre vistas y facilitando la adaptación de componentes reutilizables.

\newpage

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):** Implementa una estructura modular basada en 12 columnas para soportar paneles analíticos, tablas y formularios extensos. El objetivo es maximizar el uso del espacio manteniendo claridad y jerarquía visual.


  - **App Móvil (Pacientes):** Emplea una grilla de 2 columnas centrada en cards informativas y botones amplios. Está diseñada para favorecer la lectura rápida, la interacción táctil y la navegación lineal.

  - **Tablet (Vista híbrida):** Mantiene un punto intermedio entre el diseño web y móvil, combinando estructura analítica con disposición táctil.


  - **Dashboard Administrativo:** Usa una grilla adaptable para manejar reportes, métricas y visualización de progreso, conservando uniformidad con la interfaz principal.

![Artefacto creado en Figma](src/img/cap6/Grid.png)

\newpage

2. **Botones y Enlaces (*Buttons & Links*)**

- **Propósito**

  Los botones y enlaces son los principales puntos de interacción dentro de Foodlytics. Representan acciones esenciales del usuario como registrar alimentos, generar reportes, actualizar métricas o acceder a información nutricional. Su diseño debe comunicar de forma clara su propósito, manteniendo coherencia visual y accesibilidad en todos los dispositivos.

  Un botón bien diseñado no solo invita a la acción, sino que también guía al usuario en su flujo dentro del sistema. En Foodlytics, donde conviven perfiles con diferentes niveles de experiencia tecnológica (pacientes y nutricionistas), los botones deben ser comprensibles, táctiles y fácilmente reconocibles, manteniendo consistencia visual entre la aplicación web y móvil.

- **Criterios de diseño evaluados para definir los botones**

  Las decisiones de diseño se basaron en principios de usabilidad, pruebas con usuarios y lineamientos de accesibilidad digital:

  - **Jerarquía visual clara:** e establecieron tres tipos de botones según su nivel de prioridad: **Primario** (acción principal), **Secundario** (acciones complementarias) y **Ghost** (acciones informativas o menos frecuentes).

  - **Tamaños escalables:** Se definieron tres tamaños (*Small, Medium y Large*) que se adaptan al contexto de uso, desde paneles analíticos hasta pantallas táctiles.

  - **Estados de interacción definidos:** Cada botón presenta variaciones visuales para *hover, focus, active y disabled*, ofreciendo retroalimentación inmediata y mejorando la percepción de control del usuario.

  - **Compatibilidad responsive:** Los botones están diseñados bajo el sistema de grillas, ajustando sus proporciones y espaciado según el ancho de pantalla.

  - **Tipografía, relleno y espaciado:** Se emplea Outfit en la versión web y Poppins en la app móvil. Los tamaños de fuente y padding se ajustan para lograr equilibrio visual y comodidad táctil.

- **Configuración técnica adoptada**

\begin{longtable}{|c|c|c|c|}
\hline
\textbf{Tamaño} & \textbf{Padding vertical} & \textbf{Padding horizontal} & \textbf{Font size} \\
\hline
\endfirsthead
\hline
\textbf{Tamaño} & \textbf{Padding vertical} & \textbf{Padding horizontal} & \textbf{Font size} \\
\hline
\endhead
Small & 12 px & 24 px & 14 px \\
\hline
Medium & 14 px & 32 px & 16 px \\
\hline
Large & 16 px & 48 px & 18 px \\
\hline
\end{longtable}

\newpage

- **Tipos de botón:**

  - **Primario:** Alto contraste. Se usa para las acciones principales, como “Guardar progreso”, “Analizar datos” o “Confirmar registro”.
  - **Secundario:** Tonalidad neutra. Se aplica a acciones complementarias o informativas, como “Ver historial” o “Editar plan”.
  - **Ghost:** Sin fondo, con borde o texto de color de marca. Se reserva para acciones menos frecuentes o navegación ligera.

- **Estados definidos y su función en la experiencia del usuario:**

  - **Default:** Estado base del botón, visible y disponible para ser presionado.
  - **Hover:** Aplica principalmente en interfaces web. El color se intensifica para indicar interactividad.
  - **Active:** Estado momentáneo cuando el botón es presionado. Brinda retroalimentación inmediata.
  - **Focus:** Indica que el botón fue seleccionado por teclado. Mejora la navegación accesible y la usabilidad en formularios.
  - **Disabled:** Estado inactivo o no disponible. Aparece atenuado para evitar confusiones y guiar al usuario sobre las condiciones necesarias antes de ejecutar una acción.

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):**  Los botones se aplican en dashboards, formularios y tablas de control. Predomina el tamaño Medium por su precisión con mouse. El botón Primario se reserva para tareas clave como “Generar reporte”, “Guardar plan nutricional” o “Actualizar base de datos”. Los estados hover y focus refuerzan la experiencia de escritorio.

  - **App Móvil (Pacientes):**  Se priorizan los tamaños Large y Medium con iconos y etiquetas claras, optimizados para interacción táctil. Ejemplos: “Registrar comida”, “Ver progreso” o “Actualizar metas”. Los estados active y disabled facilitan la comprensión del flujo en pantallas pequeñas.


  - **Tablet (Modo híbrido):**  Combina elementos de ambas interfaces, priorizando botones medianos y espacios amplios. Ideal para nutricionistas en consulta o revisión de planes en campo.

![Artefacto creado en Figma](src/img/cap6/Button_Link.png)

\newpage

3. **Campos de Entrada (*Input Fields*)**

- **Propósito**

  Los campos de entrada son los principales puntos de interacción entre el usuario y Foodlytics. A través de ellos se recopila información esencial para el funcionamiento del sistema, como datos de usuario, alimentos consumidos, objetivos nutricionales, observaciones o configuraciones de cuenta.

  En un entorno como Foodlytics —que conecta nutricionistas y pacientes dentro de una misma plataforma—, el diseño claro y accesible de los campos garantiza que los datos se ingresen de forma correcta y fluida. Un campo bien estructurado mejora la precisión de la información, reduce errores y optimiza la experiencia general.

  Por el contrario, un input mal diseñado puede generar frustración, confusión o errores de validación. Por ello, cada campo debe comunicar visualmente su propósito, su estado y su contexto, reforzando la confianza del usuario en cada interacción.

- **Criterios de diseño evaluados para definir los campos de entrada**

  - **Claridad visual y jerarquía de información:** Se definieron distintos tipos de campos (con etiqueta, con ícono, con texto de ayuda, etc.) para que el usuario entienda de forma inmediata qué tipo de dato debe ingresar.

  - **Retroalimentación inmediata:** Cada campo comunica visualmente su estado (activo, completo, con error o deshabilitado), brindando seguridad y reduciendo la carga cognitiva.

  - **Compatibilidad con dispositivos táctiles y de escritorio:** Los tamaños, márgenes y alturas fueron diseñados para interacción precisa con mouse o tacto.

  - **Soporte para validaciones visuales:** Colores, íconos y mensajes de asistencia guían al usuario sin interrumpir el flujo de uso.

  - **Uso mínimo e intencional:** Solo se muestran los campos estrictamente necesarios en cada flujo, reduciendo distracciones y mejorando la eficiencia.

- **Tipos de campo definidos**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Tipo} & \textbf{Uso previsto} \\
\hline
\endfirsthead
\hline
\textbf{Tipo} & \textbf{Uso previsto} \\
\hline
\endhead
Texto simple & Entradas básicas como nombre, correo, peso o meta calórica. \\
\hline
Ícono a la derecha & Permite ejecutar acciones contextuales (ej. mostrar/ocultar contraseña o activar búsqueda de alimentos). \\
\hline
Etiquetado & Refuerza el propósito del campo mediante texto flotante o persistente sobre el borde superior. \\
\hline
Texto asistivo & Muestra reglas de validación, tips nutricionales o mensajes de ayuda sobre formato o unidades. \\
\hline
Redimensionable & Se usa para comentarios o anotaciones personalizadas dentro del registro diario. \\
\hline
\end{longtable}

- **Estados definidos y su propósito**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Estado} & \textbf{Función} \\
\hline
\endfirsthead
\hline
\textbf{Estado} & \textbf{Función} \\
\hline
\endhead
Normal & Campo vacío, disponible para recibir datos. Indica su propósito de manera visual y clara. \\
Focus & Se activa al seleccionar el campo. Resalta el borde con el color de marca para guiar la atención del usuario. \\
\hline
Error (Status color) & Indica información incorrecta o faltante. Aplica color rojo y texto auxiliar con mensaje descriptivo. \\
\hline
Disabled & Campo deshabilitado o bloqueado. Útil para datos autogenerados por el sistema o configuraciones avanzadas. \\
\hline
\end{longtable}

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):** Los campos se emplean en formularios para crear y editar planes nutricionales, registrar pacientes, ingresar métricas y configurar objetivos. Incorporan etiquetas flotantes, validaciones en tiempo real y mensajes de ayuda.

  - **App Móvil (Pacientes):** Inputs simples, con íconos y etiquetas persistentes. Se utilizan para actualizar peso, ingresar alimentos o modificar datos personales. Los campos deben ser amplios, táctiles y legibles para uso rápido diario.

  - **Tablet (Versión híbrida):** Combina campos tipo formulario y campos táctiles, permitiendo ingreso rápido de datos y revisión de información en tiempo real durante consultas presenciales.

![Artefacto creado en Figma](src/img/cap6/Input_fields.png)

\newpage

4. **Diálogos Emergentes (*Dialogs*)**

- **Propósito**

  Los diálogos emergentes en *Foodlytics* cumplen la función de interrumpir momentáneamente el flujo de navegación para llamar la atención del usuario sobre acciones relevantes, confirmaciones críticas o mensajes informativos del sistema.

  En un entorno centrado en la gestión nutricional, donde las acciones pueden implicar la modificación de planes, eliminación de datos o confirmación de registros, los diálogos aseguran que las decisiones sean conscientes y verificadas antes de ejecutarse.

  También contribuyen a simplificar las interfaces principales, mostrando información o formularios específicos solo cuando es necesario, evitando sobrecargar las pantallas con elementos permanentes.

- **Criterios de diseño evaluados para definir los diálogos**

  - **Claridad y enfoque:** Cada diálogo debe transmitir un mensaje directo, con jerarquía visual clara. Se recomienda incluir un título, un cuerpo conciso y las acciones principales.

  - **Accesibilidad visual y jerarquía de botones:** Los botones mantienen un orden lógico (acción principal a la derecha) y usan el color de marca para guiar la atención.

  - **Compatibilidad responsive:** Los diálogos se adaptan automáticamente a diferentes tamaños de pantalla, garantizando usabilidad en computadoras, tablets y smartphones.

  - **Tamaños escalables:** Se definen cinco tamaños (de XS a XL) según el nivel de complejidad de la acción o cantidad de información que contienen.

  - **Retroalimentación inmediata:** Cada acción dentro de un diálogo genera una respuesta visual o una notificación que confirma su ejecución, reforzando la sensación de control del usuario.

- **Tamaños disponibles**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Tamaño} & \textbf{Uso seleccionado} \\
\hline
\endfirsthead
\hline
\textbf{Tamaño} & \textbf{Uso seleccionado} \\
\hline
\endhead
XS & Confirmaciones simples o mensajes informativos (ej. “Cambios guardados correctamente”). \\
\hline
SM & Acciones rápidas o formularios mínimos (ej. “¿Deseas eliminar este registro?”). \\
\hline
MD & Diálogos estándar con campos de validación o selección (ej. “Editar datos del paciente”). \\
\hline
LG & Formularios con múltiples acciones o configuración avanzada (ej. “Actualizar plan nutricional”). \\
\hline
XL & Visualización de reportes o datos analíticos (ej. “Detalle de progreso semanal”). \\
\hline
\end{longtable}

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):** Se utilizan para confirmar acciones administrativas como guardar, eliminar o editar datos de pacientes y planes alimentarios. También aparecen en procesos de generación de reportes o sincronización con IA. Deben ocupar como máximo el 80% del viewport y presentar las acciones principales con jerarquía visual clara: “Guardar”, “Cancelar” o “Eliminar”.

  - **App Móvil (Pacientes):** Se activan al registrar alimentos, confirmar cambios de datos o mostrar alertas automáticas de progreso. Los diálogos se diseñan con tipografía legible y botones grandes, centrados en la facilidad de lectura y acción táctil inmediata.

  - Ademas, el sistema de IA puede generar eventos automáticos que activen diálogos informativos dentro del entorno web o móvil, como notificaciones de detección de alimentos o ajustes automáticos en el plan nutricional.

![Artefacto creado en Figma](src/img/cap6/Dialog.png)

\newpage

5. **Pestañas de Navegación (*Tabs*)**

- **Propósito**

  Las pestañas de navegación son un componente clave dentro de la interfaz de *Foodlytics* para organizar contenido jerárquico o categorizado sin sobrecargar la pantalla. Permiten que el usuario acceda rápidamente a diferentes secciones relacionadas dentro de una misma vista, manteniendo el contexto y la continuidad de la información.

  En el entorno de *Foodlytics*, donde los usuarios (nutricionistas y pacientes) interactúan con múltiples módulos —como progreso, reportes, historial de comidas y configuración—, las tabs facilitan una navegación ordenada, fluida y visualmente coherente, mejorando la usabilidad general del sistema.

- **Criterios de diseño para definir las tabs**

  - **Eficiencia de navegación:** Las tabs permiten explorar contenido agrupado sin abandonar la vista actual, optimizando la experiencia en módulos con información recurrente.

  - **Adaptabilidad:** Se definieron versiones horizontales y verticales para ajustarse a las necesidades de cada plataforma.

  - **Escenarios de movilidad:** En la app del paciente, se priorizan tabs scrollables para presentar varias secciones sin saturar el espacio visual.

  - **Visibilidad del estado activo:** Cada tab resalta el estado seleccionado mediante un subrayado con el color de marca y un cambio de tipografía o peso visual.

  - **Patrones consistentes con Angular/Daxa y Material Design:** El diseño de tabs sigue las pautas de Angular Material, asegurando coherencia en comportamiento, accesibilidad y animaciones.

- **Variantes disponibles**

\begin{longtable}{|c|c|p{9cm}|}
\hline
\textbf{Orientación} & \textbf{Tipos} & \textbf{Características principales} \\
\hline
\endfirsthead
\hline
\textbf{Orientación} & \textbf{Tipos} & \textbf{Características principales} \\
\hline
\endhead
Horizontal & Standard & 2–4 pestañas visibles, sin scroll. \\
\hline
Horizontal & Scrollable & Permite desplazamiento si hay muchas secciones. \\
\hline
Horizontal & Full Width & Las tabs se ajustan al ancho total del contenedor. \\
\hline
Vertical & Standard & Organización tipo menú lateral, ideal para configuración. \\
\hline
Vertical & Scrollable & Utilizado cuando hay múltiples categorías anidadas. \\
\hline
Vertical & Full Height & Ocupa toda la altura disponible del contenedor. \\
\hline
\end{longtable}

\newpage

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):** Las tabs se emplean para organizar secciones de reportes, historial de pacientes, seguimiento de progreso y configuración de planes. En dashboards se usa el modo horizontal standard, mientras que en paneles de ajustes o administración se utiliza la versión vertical standard para mejorar la orientación.

  - **App Móvil (Pacientes):** Las pestañas permiten cambiar entre secciones como “Inicio | Registro | Reportes | Perfil”. Se utiliza el modo scrollable horizontal para garantizar accesibilidad sin saturar la pantalla. El estado activo se destaca con el color principal de marca (#2FCBAC) y un ícono representativo por categoría.

![Artefacto creado en Figma](src/img/cap6/Tabs.png)

\newpage

6. **Rutas de Navegación (*Breadcrumbs*)**

- **Propósito**

  Las rutas de navegación (*breadcrumbs*) son un patrón de interfaz esencial para mantener la orientación del usuario dentro de estructuras jerárquicas. Permiten visualizar la ubicación actual dentro del sistema y facilitan el retorno a niveles previos sin depender de menús extensos o múltiples clics.

  En la aplicación web de Foodlytics, donde los nutricionistas pueden acceder a diferentes capas de información (por ejemplo, Panel > Pacientes > Juan Pérez > Historial > Reporte semanal), este componente ayuda a mantener claridad en la estructura y a reducir la carga cognitiva, especialmente al gestionar grandes volúmenes de datos.

- **Criterios de diseño y elección**

  - **Jerarquía visual clara:** Cada nivel se separa mediante íconos de flecha o barra inclinada, acompañados por estilos tipográficos diferenciados. El último nivel (ubicación actual) se resalta con un color más intenso o sin enlace, indicando la vista activa.

  - **Adaptabilidad:** En pantallas reducidas o rutas largas, las secciones intermedias se colapsan automáticamente con puntos suspensivos (“...”), preservando la limpieza visual sin perder información contextual.

  - **Consistencia visual:** Los *breadcrumbs* utilizan la tipografía Outfit y los colores de texto secundarios del sistema (#262424 y \#2FCBAC para el enlace activo). Se integran visualmente en los encabezados de módulo y barras superiores del dashboard.

  - **Íconos contextuales:** Se pueden incluir íconos representativos según la sección (por ejemplo, un ícono de usuario junto a “Paciente”, o un ícono de gráfico junto a “Reporte semanal”), mejorando la comprensión visual y la experiencia de navegación.

  - **Accesibilidad:** Cada *breadcrumb* actúa como enlace interactivo con soporte completo para lectores de pantalla y navegación mediante teclado, asegurando accesibilidad conforme a las pautas WCAG 2.1.

\newpage

- **Aplicación por plataforma**

\begin{longtable}{|c|p{11cm}|}
\hline
\textbf{Plataforma} & \textbf{Uso y propósito} \\
\hline
\endfirsthead
\hline
\textbf{Plataforma} & \textbf{Uso y propósito} \\
\hline
\endhead
Web App (Nutricionistas) & Elemento fundamental en vistas jerárquicas del dashboard, especialmente en la gestión de pacientes, análisis de reportes y configuración de planes alimentarios. Mejora la orientación y reduce pasos innecesarios. \\
\hline
App Móvil (Pacientes) & Uso mínimo, ya que la navegación se mantiene superficial e intuitiva mediante tabs y cards. Se reserva para vistas donde el usuario profundiza en reportes o historial detallado. \\
\hline
Tablet (Versión híbrida) & Emplea el mismo patrón que la aplicación web, adaptando el espaciado y tipografía para mejorar la visibilidad táctil y lectura en orientación horizontal. \\
\hline
IA / Backend & No aplica, dado que el sistema de inteligencia artificial no presenta navegación visual jerárquica. \\
\hline
\end{longtable}

![Artefacto creado en Figma](src/img/cap6/Breadcrumbs.png)

\newpage

6. **Notificaciones y Alertas (Notifications & Alerts)**

- **Propósito**

  Las notificaciones y alertas en Foodlytics informan al usuario sobre el resultado de sus acciones o sobre eventos relevantes del sistema. Su objetivo es comunicar mensajes de estado de forma clara, inmediata y no intrusiva, mejorando la percepción de control y confianza dentro de la plataforma.

  Estos elementos son esenciales en procesos donde la retroalimentación visual es determinante, como el registro de alimentos, la validación de datos nutricionales o la generación de reportes. Las notificaciones permiten confirmar acciones exitosas, advertir sobre posibles errores o guiar al usuario hacia la corrección de un flujo.

- **Criterios de diseño y elección**

  - **Claridad visual:** Cada tipo de notificación se asocia a un color y un ícono específico, facilitando la comprensión rápida del mensaje.

  - **Proporcionalidad:** Las alertas están diseñadas para ocupar el espacio justo, sin bloquear la vista principal ni interrumpir tareas en curso.

  - **Jerarquía de información:** Se prioriza el título en negrita, seguido de un texto corto y directo que describe el evento.

  - **Retroalimentación inmediata:** Se utilizan animaciones suaves y tiempos de aparición controlados (3–5 segundos) para reforzar la acción del usuario sin sobrecargar la interfaz.

  - **Consistencia visual::** odas las notificaciones mantienen la misma estructura tipográfica (Outfit en web, Poppins en móvil) y los colores definidos en la paleta de State Colors.

- **Tipos de notificación y uso recomendado**

\begin{longtable}{|c|c|p{8cm}|}
\hline
\textbf{Tipo} & \textbf{Color} & \textbf{Uso recomendado} \\
\hline
\endfirsthead
\hline
\textbf{Tipo} & \textbf{Color} & \textbf{Uso recomendado} \\
\hline
\endhead
Success & \#05C168 & Confirma acciones completadas con éxito, como guardar un registro o generar un reporte. \\
\hline
Info & \#1D88FE & Comunica información general, actualizaciones o recordatorios no críticos. \\
\hline
Warning & \#FDB52A & Advierte sobre acciones que podrían requerir revisión, como datos incompletos o configuraciones pendientes. \\
\hline
Error & \#FF5A65 & Indica errores en formularios, fallas de conexión o acciones no permitidas. \\
\hline
\end{longtable}

\newpage

- **Aplicación por plataforma**

  - **Aplicación Web (Nutricionistas):** Las notificaciones se usan para confirmar operaciones en dashboards, edición de planes y análisis de datos. Se presentan en la parte superior derecha del panel o dentro del contenedor activo, sin bloquear la vista principal.

  - **App Móvil (Pacientes):** Se activan tras registrar comidas, modificar metas o recibir advertencias de progreso. Se prioriza la visibilidad táctil, con notificaciones centradas o flotantes en la parte inferior, acompañadas de íconos y colores de alto contraste.

![Artefacto creado en Figma](src/img/cap6/Notifications.png)

\newpage

## Information Architecture  

![Artefacto creado en Canva](src/img/cap6/InformationArchitecture.png)

La arquitectura de la información (AI) en Foodlytics define cómo se organiza, estructura y presenta el contenido dentro de la solución digital. Su propósito es facilitar que los usuarios encuentren lo que necesitan de manera intuitiva, reduciendo el esfuerzo cognitivo y mejorando la eficiencia de uso.

\begin{quote}
Morville y Rosenfeld (2023) sostienen que una arquitectura de información eficaz debe “equilibrar las necesidades del usuario con los objetivos del producto, proporcionando rutas claras, contextos consistentes y una estructura que promueva el descubrimiento sin confusión”.
\end{quote}

\vspace{1em}

Durante el desarrollo de Foodlytics, se diseñaron tres arquitecturas de información diferenciadas, alineadas con los objetivos funcionales de cada entorno: Landing Page, Aplicación Web para Nutricionistas y Aplicación Móvil para Pacientes. Todas comparten los principios de jerarquía clara, coherencia visual y accesibilidad transversal definidos en las guías de estilo del producto.

A continuación se presentan los mapas generales de arquitectura de información correspondientes a cada tipo de usuario:

**Arquitectura de Información – Plataforma Web para Nutricionistas**

La versión web está orientada a los profesionales de la salud que gestionan la información de múltiples pacientes. La jerarquía prioriza el acceso rápido a los módulos analíticos, tareas y gestión personalizada.

- **Objetivo:** Facilitar el trabajo analítico y la toma de decisiones mediante una navegación por módulos bien definidos.

- **Características:** Grillas de datos, filtros avanzados, secciones de exportación y dashboards dinámicos.

![Artefacto creado en Figma](src/img/cap6/AppNutricionistas.png)

\newpage

**Arquitectura de Información – App Móvil para Pacientes**

La aplicación móvil fue diseñada con una estructura lineal que permite al paciente registrar información de manera rápida y visualizar su progreso diario.

- **Objetivo:** Permitir al usuario realizar acciones rápidas (registrar comidas, peso o actividad) y acceder fácilmente a métricas y reportes.

- **Características:** Navegación inferior por tabs, campos de registro simplificados e integración con IA para detección visual de alimentos.

![Artefacto creado en Figma](src/img/cap6/AppPacientes.png)

\newpage

**Arquitectura de Información – Landing Page**

La arquitectura de la landing page cumple una función informativa y promocional. Está diseñada para presentar el producto, detallar beneficios y facilitar la conversión de visitantes en usuarios.

- **Objetivo:** Transmitir la propuesta de valor de manera clara y motivar la descarga de la aplicación.

- **Características:** Jerarquía de información simple, secciones breves con scroll continuo y puntos de acción destacados.

![Artefacto creado en Figma](src/img/cap6/Landing_Page.png)


Las secciones siguientes profundizan en los sistemas implementados para organización, etiquetado, navegación y búsqueda, así como en los elementos de SEO (Search Engine Optimization) y ASO (App Store Optimization) que fortalecen la visibilidad del producto.

\newpage

### Organization Systems

**Propósito**

La arquitectura organizativa en *Foodlytics* permite estructurar la información de manera que los usuarios accedan rápida y eficientemente a los contenidos más relevantes, según su perfil y propósito de uso.

Según Morville y Rosenfeld (2023), “los sistemas de organización son esenciales para transformar el caos en claridad, facilitando que los usuarios comprendan la lógica detrás del contenido digital”.

En el caso de *Foodlytics*, se han definido tres sistemas de organización principales, adaptados a las necesidades de los nutricionistas, pacientes y usuarios informativos de la landing page.

- **Organización para Pacientes (App móvil)**

  La aplicación móvil está diseñada para mostrar la información más relevante sobre el progreso diario del paciente, manteniendo un flujo jerárquico y secuencial en la navegación. El contenido prioriza la simplicidad y la inmediatez, permitiendo registrar alimentos, visualizar métricas y acceder al historial en pocos pasos.

\begin{longtable}{|p{3cm}|p{4.5cm}|p{3.5cm}|p{5cm}|}
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Inicio & Jerárquico visual & Cronológica & Presenta el resumen diario del paciente con calorías consumidas, macros e IMC actual. \\
\hline
Registro de comidas & Secuencial (paso a paso) & Por tópico (tiempo de comida) & Flujo guiado para registrar desayuno, almuerzo, cena o snack con opción de foto o ingreso manual. \\
\hline
Actividad física & Jerárquico visual & Cronológica & Organiza actividades por tipo y fecha, mostrando progreso semanal y cumplimiento de metas. \\
\hline
Historial & Lista jerárquica ordenada & Cronológica & Permite consultar registros pasados de comidas, peso o actividad, organizados por días o semanas. \\
\hline
Perfil del paciente & Modular & Por tópico & Contiene datos personales, preferencias y configuraciones de notificaciones. \\
\hline
\end{longtable}

- **Organización para Nutricionistas (Aplicación Web)**

  La aplicación web para nutricionistas emplea una estructura modular y jerárquica. Cada módulo responde a una categoría funcional (pacientes, reportes, tareas o configuración), facilitando el análisis de información y la administración eficiente de los datos.

\begin{longtable}{|p{3cm}|p{3.5cm}|p{3.5cm}|p{4.5cm}|}
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Dashboard & Jerárquico (panel con KPIs) & Por tópico & Muestra métricas clave como evolución de pacientes, progreso y cumplimiento de metas nutricionales. \\
\hline
Gestión de pacientes & Visual matricial & Por audiencia & Agrupa a los pacientes por tipo de plan o nivel de avance. Permite filtrado por nombre o estado. \\
\hline
Reportes y métricas & Jerárquico + secuencial & Cronológica / temática & Organiza reportes por fechas o indicadores (peso, calorías, balance nutricional). \\
\hline
Tareas y recordatorios & Secuencial (flujo Kanban) & Por estado & Permite gestionar tareas en estados “Por hacer”, “En progreso” y “Hecho”. \\
\hline
Configuración & Modular & Por tópico & Centraliza funciones de exportación, idioma, notificaciones y autenticación (Auth0). \\
\hline
\end{longtable}

- **Organización en la Landing Page (Sitio informativo)**

  La landing page de Foodlytics está diseñada para guiar al visitante a través de un flujo informativo que presenta la propuesta de valor, los beneficios del sistema y los enlaces de descarga. La organización sigue un orden secuencial con énfasis en las llamadas a la acción (CTAs).

\begin{longtable}{|p{3cm}|p{4cm}|p{3.5cm}|p{5cm}|}
\hline
\textbf{Tópico} & \textbf{Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Menú principal & Jerárquico visual horizontal & Por audiencia & Pacientes, Nutricionistas y Nosotros. Cada ruta presenta secciones propias con información adaptada. \\
\hline
Flujo de contenido & Secuencial (scroll vertical guiado) & Por tópico & Presenta beneficios, funcionamiento, características y testimonios en un recorrido continuo. \\
\hline
Call to Action (CTA) & Jerárquico visual final & Ninguna & Botones destacados de “Descargar App” o “Ver demo” al final de cada sección. \\
\hline
Contacto & Modular & Por audiencia & Canaliza consultas hacia el equipo de nutricionistas o el soporte técnico. \\
\hline
\end{longtable}

Esta organización garantiza que cada tipo de usuario —nutricionista, paciente o visitante informativo— pueda acceder a la información que necesita de forma clara, eficiente y sin fricción. La coherencia entre los tres sistemas refuerza la identidad digital de *Foodlytics*, mejora la comprensión del contenido y facilita la navegación en todo su ecosistema digital.

\newpage

### Labeling Systems

- **Propósito**

  Los sistemas de etiquetado son fundamentales para la claridad, coherencia y navegación dentro de un producto digital. Una nomenclatura precisa y uniforme permite que los usuarios comprendan de inmediato qué acciones pueden realizar, qué tipo de información están observando y cómo desplazarse por el sistema sin confusión.

  En *Foodlytics*, las etiquetas se desarrollaron bajo tres principios principales: simplicidad, consistencia y significado contextual. Cada palabra o ícono fue elegido con el fin de guiar a los usuarios (nutricionistas, pacientes o visitantes de la web) hacia sus objetivos de manera intuitiva y eficiente, reduciendo la carga cognitiva y favoreciendo una experiencia coherente entre plataformas.

- **App móvil – Pacientes**

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endhead
Inicio & Pantalla principal donde el usuario visualiza su resumen diario con calorías consumidas, metas alcanzadas, y alertas generadas por el sistema. \\
\hline
Comidas & Sección donde el paciente registra sus alimentos, clasificados por desayuno, almuerzo, cena o snack. Incluye opción de reconocimiento por foto o registro manual. \\
\hline
Actividad & Módulo que permite registrar peso, calorías quemadas o ejercicio físico, además de mostrar métricas semanales de actividad. \\
\hline
Historial & Vista consolidada que organiza los registros anteriores (alimentación, peso y actividad) por día o semana. Facilita el seguimiento a largo plazo. \\
\hline
Perfil & Sección donde el usuario puede actualizar datos personales, preferencias de idioma, notificaciones y privacidad. \\
\hline
\end{longtable}

- **Aplicación Web – Nutricionistas**

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endhead
Dashboard & Vista general del sistema con métricas agregadas, gráficos comparativos y panel de progreso por paciente. \\
\hline
Pacientes & Módulo donde se gestionan los perfiles individuales de los usuarios. Permite buscar, editar, eliminar o visualizar el historial nutricional. \\
\hline
Reportes & Sección destinada a generar informes automáticos en PDF o Excel. Incluye exportaciones filtradas por fechas, indicadores o tipo de plan. \\
\hline
Tareas & Panel de control tipo Kanban donde se gestionan pendientes y recordatorios asociados a pacientes o análisis de datos. \\
\hline
Configuración & Espacio de personalización del sistema: idioma, temas de color, notificaciones y credenciales seguras mediante Auth0. \\
\hline
\end{longtable}

- **Landing Page – Público general**

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endhead
Pacientes & Sección informativa orientada al usuario final. Presenta beneficios de la app, ejemplos visuales y acceso al botón de descarga. \\
\hline
Nutricionistas & Espacio dedicado a los profesionales. Explica las herramientas analíticas de la plataforma y su impacto en la gestión nutricional. \\
\hline
Nosotros & Contiene la descripción institucional de GMB Labs, los valores del proyecto y un enlace de contacto general. \\
\hline
Demo / Descargar app & Botón principal de acción (CTA) que redirige al enlace de descarga o visualización de la versión de prueba. \\
\hline
Preguntas frecuentes & Sección de soporte básico que responde dudas comunes sobre uso, registro, privacidad y compatibilidad. \\
\hline
\end{longtable}

El sistema de etiquetado de Foodlytics se construyó sobre una lógica semántica clara, evitando redundancias y tecnicismos innecesarios. Cada etiqueta se probó en flujos de navegación reales para garantizar que fuera comprensible para ambos perfiles de usuario. Esto contribuye a una experiencia más accesible y homogénea en todo el ecosistema digital del producto.

\newpage

### Searching Systems  

- **Propósito**

  Los sistemas de búsqueda en productos digitales permiten al usuario navegar entre grandes volúmenes de información de forma eficiente, reduciendo la fricción y optimizando el tiempo de interacción.

  En Foodlytics, la búsqueda activa está implementada principalmente en la plataforma web de nutricionistas, donde se gestionan múltiples perfiles, reportes y métricas. En cambio, la aplicación móvil para pacientes presenta información ya personalizada y filtrada automáticamente, evitando la necesidad de búsquedas manuales.

**Filtros y herramientas de búsqueda en la Web App**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Filtro / Función} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Filtro / Función} & \textbf{Definición} \\
\hline
\endhead
Nombre del paciente & Permite localizar rápidamente a un paciente específico mediante la entrada parcial o completa del nombre. \\
\hline
Correo electrónico o ID de usuario & Filtra pacientes registrados por correo o identificador único asignado por el sistema. \\
\hline
Estado del plan nutricional & Permite visualizar únicamente a los pacientes con planes activos, en revisión o finalizados. \\
\hline
Fecha de registro / actualización & Filtra según la fecha de creación del paciente o la última modificación de su plan. \\
\hline
Indicador de progreso & Muestra pacientes con progreso superior o inferior a un umbral definido (ej. +10\% o –5\%). \\
\hline
Tipo de reporte generado & Filtra informes nutricionales, calóricos o antropométricos según categoría. \\
\hline
Intervalo temporal & Permite consultar métricas específicas por rango de fechas (última semana, mes, trimestre). \\
\hline
Búsqueda avanzada combinada & Combina varios criterios (ej. paciente + fecha + tipo de plan) para obtener resultados más precisos. \\
\hline
\end{longtable}

- **Diseño de resultados y experiencia de búsqueda**

  - Los resultados se ordenan por nombre o fecha de actualización, según el contexto del módulo.
  - Los campos de búsqueda incluyen autocompletado inteligente que sugiere coincidencias parciales.
  - Cada resultado permite acceso directo al perfil del paciente, reporte o tarea asociada.
  - Los resultados se muestran en tablas interactivas o tarjetas con métricas resumidas, optimizando la lectura visual.

**App móvil – Pacientes**

En la aplicación móvil, el sistema no requiere un buscador manual, ya que el contenido se muestra automáticamente filtrado por perfil. El usuario solo accede a sus propios datos y métricas, con vistas separadas según el tipo de información.

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Característica} & \textbf{Función} \\
\hline
\endfirsthead
\hline
\textbf{Característica} & \textbf{Función} \\
\hline
\endhead
Vista personalizada por paciente & Cada usuario visualiza únicamente sus datos nutricionales, objetivos y progreso diario. \\
\hline
Historial por fecha & Los registros de comidas, peso o actividad se organizan automáticamente por orden cronológico. \\
\hline
Métricas destacadas & Se muestran valores resumidos como calorías, macros y porcentaje de cumplimiento diario. \\
\hline
Alertas contextuales & El sistema prioriza notificaciones relevantes según comportamiento alimentario o nivel de actividad. \\
\hline
\end{longtable}

Esta combinación de sistemas garantiza que tanto nutricionistas como pacientes puedan acceder de forma ágil a la información más relevante, manteniendo la coherencia visual y funcional en todo el ecosistema Foodlytics. La búsqueda avanzada en la web y la presentación automatizada en la app móvil contribuyen a mejorar la eficiencia, precisión y satisfacción del usuario.

\newpage

### SEO Tags, Meta Tags y ASO Elements 

- **Propósito**

  En la plataforma *Foodlytics*, los SEO Tags y Meta Tags desempeñan un papel esencial para mejorar la visibilidad digital y garantizar que tanto los usuarios potenciales como los profesionales de la salud puedan encontrar el producto fácilmente a través de motores de búsqueda y tiendas de aplicaciones.

  Aunque *Foodlytics* cuenta con una aplicación web y una aplicación móvil, la landing page es el principal punto de entrada y posicionamiento orgánico, por lo que ha sido optimizada con etiquetas cuidadosamente estructuradas para maximizar el alcance y reforzar la identidad de marca de GMB Labs.

- **SEO Tags**

  Los SEO Tags ayudan a mejorar el posicionamiento orgánico de la landing page de *Foodlytics* en motores de búsqueda como Google, optimizando el descubrimiento del producto por parte de nutricionistas, pacientes y profesionales del bienestar.
  A continuación se presentan ejemplos aplicados:

  - **Title Tag**  
    Define el título mostrado en los resultados de búsqueda.

    ```html
    <title>Foodlytics - Nutrición Inteligente Basada en Datos</title>
    ```

  - **Meta Description**  
    Proporciona un resumen claro y atractivo del contenido de la página.

    ```html
    <meta name="description" content="Foodlytics es una plataforma de análisis nutricional inteligente que conecta a nutricionistas y pacientes para optimizar planes alimentarios con datos y métricas en tiempo real." />
    ```

  - **Header Tags**  
    Establecen jerarquías semánticas dentro del contenido de la landing page.

    ```html
      <h1>Tu nutrición, más inteligente cada día</h1>
      <h2>Datos, métricas y progreso en tiempo real</h2>
      <h3>Optimiza tu salud con tecnología nutricional</h3>
    ```

- **Meta Tags**

  Los Meta Tags transmiten información técnica a los navegadores y motores de búsqueda, mejorando la accesibilidad, el rendimiento y el SEO técnico de la página. Algunos de los implementados en *Foodlytics* son:

  - **Charset Meta Tag**

    ```html
    <meta charset="UTF-8">
    ```

  - **Viewport Meta Tag**

    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```

  - **Robots Meta Tag**

    ```html
    <meta name="robots" content="index, follow">
    ```

  - **Canonical Tag**

    ```html
    <link rel="canonical" href="https://foodlytics.com">
    ```

- **Landing Page SEO Tags (para la aplicación móvil)**

  Además de las etiquetas básicas, Foodlytics emplea SEO tags específicos diseñados para destacar la aplicación móvil en resultados de búsqueda, fomentando su descarga directa:

  ```html
    <title>Foodlytics | Tu Nutrición Simplificada con IA</title>
    <meta name="description" content="Foodlytics te permite registrar, analizar y optimizar tu nutrición con inteligencia artificial. Ideal para nutricionistas y pacientes. Disponible en Android e iOS.">
    <meta name="keywords" content="app nutrición, seguimiento nutricional, dieta inteligente, inteligencia artificial, control de macros, salud digital">
    <meta name="author" content="GMB Labs">
    <link rel="canonical" href="https://foodlytics.app/">
    ```

- **App Store Optimization (ASO)**

    Para mejorar la visibilidad de la aplicación en Google Play y App Store, Foodlytics aplica una estrategia de ASO (App Store Optimization) que incluye la optimización de títulos, descripciones y palabras clave específicas del sector nutricional.

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Elemento} & \textbf{Valor propuesto} \\
\hline
\endfirsthead
\hline
\textbf{Elemento} & \textbf{Valor propuesto} \\
\hline
\endhead
App Title & Foodlytics: Nutrición Inteligente Basada en Datos \\
\hline
App Subtitle & Seguimiento nutricional con inteligencia artificial \\
\hline
App Description & Con Foodlytics, los nutricionistas pueden crear y monitorear planes personalizados mientras los pacientes registran su alimentación y progreso con datos en tiempo real. Incluye análisis automáticos de macros, alertas de hábitos y reportes exportables en PDF. Ideal para una nutrición moderna y basada en evidencia. \\
\hline
Keywords & app nutrición, seguimiento alimenticio, IA nutricional, control de macros, salud digital, dieta personalizada \\
\hline
Developer & GMB Labs \\
\hline
Categoría & Salud y Bienestar / Nutrición \\
\hline
URL descarga Android & \url{https://play.google.com/store/apps/details?id=com.foodlytics}
 \\
\hline
URL descarga iOS & \url{https://apps.apple.com/app/foodlytics/id987654321}
 \\
\hline
\end{longtable}

El uso estratégico de SEO Tags y Meta Tags en Foodlytics potencia el posicionamiento de la marca en buscadores y redes sociales, asegurando una primera impresión profesional y coherente con la identidad visual del producto.
Asimismo, las prácticas de ASO garantizan un mejor rendimiento en las tiendas de aplicaciones, aumentando la tasa de descarga y fortaleciendo la presencia digital del ecosistema Foodlytics.

\newpage

### Navigation Systems

- **Propósito**

Los sistemas de navegación son el conjunto de elementos y patrones que permiten al usuario desplazarse de forma lógica, intuitiva y eficiente dentro de una interfaz digital. Una navegación bien diseñada no solo facilita el acceso a la información, sino que también refuerza la sensación de control y orientación dentro del sistema.

Como afirma Garrett (2011), “la navegación efectiva proporciona al usuario una sensación de lugar, dirección y control dentro de un producto digital”.

En Foodlytics, los sistemas de navegación se adaptan al contexto de uso y tipo de usuario. En la aplicación móvil, se prioriza la simplicidad y el flujo lineal, mientras que en la plataforma web se optimiza la exploración de información analítica y la gestión de pacientes. Ambos mantienen coherencia visual con la guía de estilo general y con los principios de accesibilidad definidos para el producto.

**App móvil – Pacientes**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Menú inferior (tab bar) & Contiene accesos directos a: Inicio, Comidas, Actividad, Historial y Perfil. Visible en toda la aplicación. \\
\hline
Navegación jerárquica & Desde cada sección principal se puede acceder a pantallas secundarias (por ejemplo, ver detalle de comida registrada o progreso semanal). \\
\hline
Retroalimentación visual & Íconos activos cambian de color al seleccionarse (verde menta \#2FCBAC). Se incluyen notificaciones visibles en el ícono de “Perfil” para alertas de progreso o recordatorios. \\
\hline
Navegación simplificada & El diseño prioriza la experiencia rápida y directa. Solo se muestran funciones esenciales: registrar, visualizar y revisar métricas. \\
\hline
Gestos táctiles & Permite desplazamiento lateral entre secciones y cierre de formularios mediante “swipe down”. \\
\hline
\end{longtable}

**Aplicación Web – Nutricionistas**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Menú lateral persistente & Acceso permanente a módulos principales: Dashboard, Pacientes, Reportes, Tareas y Configuración. Se mantiene fijo en todas las vistas. \\
\hline
Submenús plegables & Permite desplegar subcategorías (por ejemplo, “Reportes → Individuales / Comparativos / Exportaciones”). \\
\hline
Navegación contextual & Acciones como “Editar paciente”, “Generar reporte” o “Agregar recordatorio” aparecen junto a los datos relevantes. \\
\hline
Navegación matricial & Distribución tipo grid utilizada en listados de pacientes y paneles de progreso. Facilita la lectura de múltiples registros simultáneamente. \\
\hline
Accesos rápidos & Botones flotantes o destacados dentro del dashboard para tareas frecuentes como “Añadir paciente” o “Generar informe semanal”. \\
\hline
Breadcrumbs (rutas jerárquicas) & Indican la ubicación actual dentro del sistema (por ejemplo: Dashboard > Pacientes > Juan Pérez > Reporte mensual). \\
\hline
\end{longtable}

**Landing Page – Público general**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Navbar superior fijo & Incluye enlaces a secciones: Pacientes, Nutricionistas, Nosotros y Descargar App. Permanece visible al hacer scroll. \\
\hline
Scroll guiado (anclajes) & Permite desplazarse entre secciones mediante anclas internas (“\#pacientes”, “\#nutricionistas”, etc.). \\
\hline
Botones de llamada a la acción (CTA) & Elementos de navegación destacados en color de marca (\#2FCBAC), ubicados en secciones clave. Ejemplo: “Probar ahora” o “Ver demo”. \\
\hline
Navegación jerárquica visual & Los encabezados (H1–H3) organizan el contenido según su relevancia informativa. \\
\hline
Footer navegable & Contiene accesos secundarios a políticas de privacidad, contacto y redes sociales oficiales de Foodlytics. \\
\hline
\end{longtable}

La arquitectura de navegación de integra una experiencia consistente entre plataformas. Mientras la versión móvil prioriza la inmediatez, fluidez y accesibilidad táctil, la versión web enfatiza control, gestión de datos y análisis avanzado. Ambos entornos comparten un mismo lenguaje visual y estructura cognitiva, asegurando una experiencia coherente y predecible para todos los usuarios.

\newpage

## Landing Page UI Design  


::: warn
Para acceder a la landing page desplegada, haga click en la [URL](https://foodlytics-landingpage.vercel.app/)
:::


El diseño de la interfaz de usuario de la landing page de Foodlytics se desarrolló con un enfoque centrado en el usuario, priorizando la claridad, accesibilidad y jerarquía visual. Su objetivo principal es comunicar de forma inmediata el valor del producto a los dos segmentos clave: nutricionistas y pacientes. La estructura se diseñó para guiar al visitante desde la comprensión del problema hasta la acción de conversión, integrando elementos visuales coherentes con la identidad de la marca.

La landing presenta una distribución modular con secciones diferenciadas: propuesta de valor, beneficios por segmento, testimonios, demo del producto y formulario de contacto. Cada bloque fue diseñado bajo principios de diseño limpio y legible, utilizando espacios amplios, contrastes de color bien definidos y una tipografía moderna que refuerza la confianza y profesionalismo del producto.

El proceso de diseño se desarrolló en Figma, siguiendo una línea de coherencia visual con la aplicación web y móvil. Se construyeron wireframes de baja fidelidad para definir la arquitectura y el flujo de información, los cuales sirvieron de base para los mockups de alta fidelidad que reflejan la versión visual final.

::: warn
Para acceder a los wireframes de la landing page, haga click en la [URL](https://www.figma.com/design/Q2iA0fbCJIkimHlBRaP9T4/Landing-and-Mobile?node-id=0-1&t=asNFuL2nqvhc6N6W-1)
:::

Este proceso permitió validar la disposición de elementos, la legibilidad y la efectividad de los llamados a la acción antes de su implementación técnica. El resultado es una landing page funcional, persuasiva y alineada con la estrategia de comunicación de GMB Labs.

\newpage

### Landing Page Wireframe 

Los wireframes de la landing page definen la estructura general de la interfaz, mostrando la disposición jerárquica de los componentes principales: encabezado con CTA, secciones informativas para cada público objetivo, galería de evidencias y pie de página con políticas y contacto. Este esquema permitió asegurar la coherencia entre los objetivos de negocio y la experiencia del usuario antes del desarrollo visual.

**Landing Page Wireframe - Pacientes**

En el caso del segmento paciente, la experiencia se enfoca en mostrar los beneficios inmediatos del uso de la app: reconocimiento de alimentos por IA, registro rápido de comidas, seguimiento de peso y evolución en tiempo real.

![Figma GMBLabs Wireframe](src/img/cap6/LandingPage-PacientesW.png)


**Landing Page Wireframe - Nutricionistas**

En el segmento nutricionista, el contenido resalta el valor profesional del sistema: visualización de métricas de pacientes, panel de seguimiento y generación de reportes automáticos. Ambos flujos comparten una arquitectura coherente, diseñada para mantener consistencia entre versiones web y móvil.

![Figma GMBLabs Wireframe](src/img/cap6/LandingPage-PacientesW.png)

\newpage

### Landing Page Mock-up  

Los mockups incorporan la identidad visual definitiva del producto. Se aplicaron sombras sutiles, bordes redondeados y fotografías en tonos naturales para generar cercanía. Los botones principales, como “Solicitar demo” y “Ver más”, se presentan en verde menta con contraste sobre fondo blanco, reforzando la acción principal de conversión.

**Landing Page Mock-up - Pacientes**

![Figma GMBLabs Wireframe](src/img/cap6/LandingPage-PacientesM.png)


**Landing Page Mock-up - Nutricionistas**

![Figma GMBLabs Wireframe](src/img/cap6/LandingPage-NutricionistasM.png)

\newpage

## Applications UX/UI Design  

El diseño UX/UI de las aplicaciones de Foodlytics se desarrolló bajo los principios de simplicidad, consistencia y enfoque en el usuario final. Cada interfaz fue concebida para ofrecer una experiencia fluida y coherente entre las distintas plataformas que integran el ecosistema del producto: aplicación móvil para pacientes y aplicación web para nutricionistas.

El objetivo principal fue garantizar que cada segmento de usuario encuentre la información y las acciones relevantes en el menor número de pasos posible. Para lograrlo, se definió un sistema visual común que mantiene la identidad de marca en colores, tipografía, iconografía y tono comunicacional. Este sistema permite una transición natural entre dispositivos y asegura accesibilidad en distintos contextos de uso.

El diseño se construyó de forma iterativa, combinando la arquitectura de información con los hallazgos del proceso de needfinding. Esto permitió que las decisiones visuales respondan a comportamientos reales de los usuarios, priorizando la claridad en las tareas frecuentes, la legibilidad en pantallas pequeñas y la reducción de fricción en procesos clave como el registro de comidas o el seguimiento de métricas.

La experiencia de Foodlytics busca transmitir confianza, inmediatez y control, reflejando el propósito central del producto: hacer que la nutrición digital sea más precisa, personalizada y accesible.

\newpage


### Applications Wireframes

Los wireframes de las aplicaciones de Foodlytics representan la estructura funcional y jerárquica de las pantallas principales antes del desarrollo visual. Su propósito fue validar los flujos de interacción, la disposición de los elementos y la coherencia de la navegación en cada versión del producto.

Durante esta etapa, se definieron las secciones base y los componentes reutilizables de la interfaz, como menús, tarjetas de datos, botones de acción y paneles de progreso. Cada wireframe se diseñó siguiendo el principio de “una tarea por pantalla”, buscando minimizar la carga cognitiva y mantener la atención del usuario en un solo objetivo a la vez.


#### *Web Application*

Los wireframes de la aplicación web de Foodlytics definen la estructura base del entorno profesional dirigido a nutricionistas. Este canal fue diseñado para optimizar la gestión de pacientes, la visualización de métricas y la generación de reportes, manteniendo una interfaz limpia y centrada en la productividad.

Cada pantalla fue organizada en torno a flujos de trabajo frecuentes del usuario, con el objetivo de reducir pasos innecesarios y facilitar la toma de decisiones clínicas basadas en datos. Las vistas principales comprenden

- **Sign In:** pantalla de acceso con validación segura y opción de recuperación de credenciales.

- **Dashboard:** vista general con indicadores clave de rendimiento, calorías promedio, progreso de pacientes y notificaciones recientes.

- **Patients:** listado con filtros por nombre, estado y objetivos, permitiendo acceder a la ficha individual de cada usuario.

- **Overview:** resumen detallado de la evolución de un paciente, incluyendo peso, calorías consumidas y balance energético semanal.

- **Calendar:** planificación de sesiones y recordatorios, con vista por semana y mes.

- **Kanban Board:** tablero visual para el seguimiento de tareas clínicas y nutricionales, organizado por estados (Pendiente, En curso, Completado).


![Artefacto creado en Figma - Web Application (Sign In)](src\img\cap6\web-wireframes\SignIn.pdf)

![Artefacto creado en Figma - Web Application (Dashboard)](src\img\cap6\web-wireframes\Dashboard.pdf)

![Artefacto creado en Figma - Web Application (Patients)](src\img\cap6\web-wireframes\Patients.pdf)

![Artefacto creado en Figma - Web Application (Overview)](src\img\cap6\web-wireframes\Overview.pdf)

![Artefacto creado en Figma - Web Application (Calendar)](src\img\cap6\web-wireframes\Calendar.pdf)

![Artefacto creado en Figma - Web Application (Kanban Board)](src\img\cap6\web-wireframes\KanbanBoard.pdf)


#### *Mobile Application Wireframes*

Los wireframes de la aplicación móvil de Foodlytics representan la estructura base de la experiencia del paciente. La interfaz se diseñó priorizando simplicidad, navegación táctil y claridad visual, permitiendo registrar y monitorear información nutricional en tiempo real. Cada grupo de pantallas se centra en una función principal, optimizando el flujo de interacción para reducir fricción y reforzar el sentido de progreso.

1. **Calcular IMC (Onboarding Nutricional)**
Permite recopilar los datos iniciales del usuario para calcular su Índice de Masa Corporal y definir sus metas diarias de calorías, proteínas, carbohidratos y grasas. Incluye preguntas sobre edad, género, altura, peso actual, peso objetivo y nivel de actividad. El resultado genera un plan calórico automático que se actualiza conforme al progreso del usuario.

![Artefacto creado en Figma - Mobile Application (Onboarding Nutricional)](src\img\cap6\CalcularIMC.png)

2. **Pantalla Principal (Dashboard del Paciente)**
Funciona como el punto de entrada a la aplicación. Muestra un resumen de calorías consumidas, quemadas y restantes, el IMC actual, los macronutrientes diarios y el registro de comidas del día. También incluye notificaciones contextuales que orientan al usuario en sus primeras acciones dentro de la app.

![Artefacto creado en Figma - Mobile Application (Dashboard del Paciente)](src\img\cap6\Pantallaprincipal.png)

3. **Registro de Comidas**
Integra el flujo de captura y análisis de alimentos mediante visión artificial. El usuario enfoca su plato, la IA detecta los alimentos y calcula su composición nutricional. Luego, puede editar cantidades, asignar la comida (desayuno, almuerzo o cena) y guardar el registro. Este flujo reduce el tiempo de registro manual y mejora la precisión calórica.

![Artefacto creado en Figma - Mobile Application (Registro de Comidas)](src\img\cap6\ComidasRegistradas.png)

4. **Actividad y Progreso**
Permite registrar y visualizar datos relacionados con la actividad física. Las pantallas muestran calorías quemadas, duración de ejercicios y estadísticas de progreso semanal. Se incluyen gráficos de evolución del peso, cumplimiento de metas y adherencia al plan.

![Artefacto creado en Figma - Mobile Application (Actividad y Progreso)](src\img\cap6\Actividad.png)


5. **Acciones Rápidas**
Facilita accesos directos desde cualquier parte de la app. El usuario puede registrar comida, peso, actividad o metas desde un panel emergente. Este diseño mejora la eficiencia y mantiene la continuidad del flujo principal sin necesidad de regresar a la pantalla inicial.

![Artefacto creado en Figma - Mobile Application (Acciones Rápidas)](src\img\cap6\AccionesRapidas.png)

6. **Registrar Actividad**
Permite ingresar actividades físicas específicas indicando tipo, duración e intensidad. El sistema calcula las calorías quemadas y muestra una confirmación al completar el registro. Este flujo mantiene coherencia con la vista de progreso semanal.

![Artefacto creado en Figma - Mobile Application (Registrar Actividad)](src\img\cap6\ractividad.png)


7. **Registrar Peso**
El usuario puede actualizar su peso actual, ver la diferencia con su meta y el progreso acumulado. Los datos se reflejan automáticamente en los gráficos del panel de progreso y en las metas nutricionales diarias.

![Artefacto creado en Figma - Mobile Application (Registrar Peso)](src\img\cap6\rpeso.png)


8. **Perfil y Configuración de Cuenta**
Reúne los apartados de datos personales, objetivos, idioma, notificaciones, privacidad y control de datos. Cada subpantalla está organizada bajo el principio de claridad y jerarquía visual, garantizando que el usuario entienda el propósito de cada opción sin sobrecarga cognitiva.

![Artefacto creado en Figma - Mobile Application (Perfil y Configuración de Cuenta)](src\img\cap6\Perfil.png)


9. **Pantallas de Autenticación (Carga, Login, Registro y Recuperación)**
Incluyen el flujo de inicio de sesión y registro de nuevos usuarios. Se prioriza la legibilidad y el acceso rápido, con formularios simplificados y validaciones visuales claras. La pantalla de carga refuerza la identidad visual de Foodlytics y anticipa la experiencia personalizada del sistema.

![Artefacto creado en Figma - Mobile Application (Pantallas de Autenticación)](src\img\cap6\Inicio.png)

Todos los wireframes fueron elaborados en Figma, siguiendo la cuadrícula de diseño adaptativo y el sistema de componentes de Foodlytics. La estructura garantiza coherencia visual con la aplicación web, manteniendo la misma lógica de colores, tipografía y jerarquía.


### Applications Wireflow Diagrams 

Los wireflows combinan pantallas clave con sus transiciones para mostrar, de forma compacta, cómo navega el usuario y qué decisiones toma en cada paso. Sirven como puente entre la arquitectura de información y los prototipos, ayudando a validar el flujo antes de diseñar visualmente.

#### *Web Wireflow Diagrams*

Este diagrama resume los recorridos principales de la aplicación web, destacando puntos de entrada, decisiones y resultados esperados en cada módulo.

![Artefacto creado en Figma - Flujo Principal](src\img\cap6\flow\Flow.pdf)

Describe el acceso seguro del usuario: ingreso de credenciales, manejo de errores, recuperación de contraseña y redirección a la vista inicial tras un inicio de sesión exitoso.

![Artefacto creado en Figma - Flujo Inicio de Sesion](src\img\cap6\flow\FlowSignIn.pdf)

Cubre la gestión de pacientes: búsqueda y filtros, alta y edición, desactivación con resguardo histórico, y navegación al detalle para revisar dieta, actividad y métricas.

![Artefacto creado en Figma - Flujo Pacientes](src\img\cap6\flow\FlowPatients.pdf)

Expone la planificación temporal: visualización por semana y mes.

![Artefacto creado en Figma - Flujo Calendario](src\img\cap6\flow\FlowCalendar.pdf)

Muestra el tablero de tareas del nutricionista: creación y edición rápida, cambio de estado por arrastre, vistas por paciente o categoría, y confirmaciones ligeras.

![Artefacto creado en Figma - Flujo Kanban Board](src\img\cap6\flow\FlowKanban.pdf)


#### *Mobile Wireflow Diagrams*

Los wireflows de la aplicación móvil de Foodlytics representan los recorridos de usuario dentro del sistema, desde la autenticación hasta la gestión completa de sus hábitos alimenticios y progreso físico.
Cada diagrama muestra la secuencia de pantallas, decisiones y puntos de interacción que permiten al paciente registrar su información nutricional, monitorear su salud y personalizar su experiencia.
Los flujos fueron diseñados en Figma, manteniendo consistencia visual con la interfaz final, y priorizando la simplicidad en la navegación táctil.


**Wireflow Diagram 1: Inicio de Sesión**

- **User Goal**

  El usuario desea acceder a la aplicación móvil o crear una cuenta nueva para iniciar el seguimiento nutricional personalizado.

- **Task Flow (Flujo de tareas del usuario)**

  1. Abre la aplicación y visualiza la pantalla de carga con el logo de Foodlytics.
  2. Accede a la pantalla de inicio de sesión e ingresa su correo electrónico y contraseña.
  3. Si olvida su contraseña, selecciona la opción “Recuperar contraseña” y recibe un enlace por correo.
  4. En caso de no tener cuenta, elige “Registrarse” e ingresa los datos requeridos (nombre, correo, contraseña).
  5. Una vez validada la información, el sistema redirige al flujo de configuración inicial del usuario (cálculo del IMC).


**Wireflow Diagram 2: Cálculo de IMC y Configuración Inicial**

- **User Goal**

  El usuario desea registrar su información básica (edad, género, altura, peso y nivel de actividad) para obtener su plan calórico personalizado.

- **Task Flow (Flujo de tareas del usuario)**

  1. Luego del registro, la app guía al usuario por una secuencia de pantallas que recopilan sus datos físicos.
  2. Ingresar edad, género, altura y peso actual.
  3. Definir el peso objetivo y seleccionar el nivel de actividad física semanal.
  4. El sistema calcula automáticamente el IMC y muestra las metas diarias personalizadas (calorías, proteínas, carbohidratos y grasas).
  5. Al finalizar, el usuario accede al panel principal con sus objetivos establecidos.

![Artefacto creado en Figma](src/img/cap6/WD_i.png)

\newpage

**Wireflow Diagram 3: Registro de Comidas mediante IA**

- **User Goal**

  El usuario desea registrar sus comidas diarias tomando una foto y dejar que la IA de Foodlytics identifique los alimentos y calcule los valores nutricionales.

- **Task Flow (Flujo de tareas del usuario)**

  1. Desde la pantalla principal, selecciona la sección “Comidas”.
  2. Enfoca el plato con la cámara del dispositivo.
  3. El sistema analiza la imagen e identifica los alimentos detectados.
  4. Se muestra un resumen nutricional con calorías, proteínas, carbohidratos y grasas.
  5. El usuario puede ajustar cantidades, clasificar el registro (desayuno, almuerzo o cena) y guardar los datos.
  6. La comida registrada se agrega automáticamente al resumen del día.


![Artefacto creado en Figma](src/img/cap6/WD_c.png)

**Wireflow Diagram 4: Acciones Rápidas**

- **User Goal**

  El usuario desea acceder rápidamente a las funciones principales (registrar comida, peso, actividad o nueva meta) desde cualquier pantalla de la aplicación.

- **Task Flow (Flujo de tareas del usuario)**

  1. Desde la barra inferior, selecciona el ícono “+” para abrir el menú de acciones rápidas
  2. Elige entre las opciones: Registrar comida, Registrar actividad, Registrar peso o Nueva meta.
  3. El sistema redirige directamente al flujo correspondiente según la acción seleccionada.
  4. Al completar la acción, el usuario vuelve automáticamente al dashboard principal.

![Artefacto creado en Figma](src/img/cap6/WD_ar.png)


**Wireflow Diagram 5: Registro de Actividad y Peso**

- **User Goal**

  El usuario desea registrar sus actividades físicas y peso actual para actualizar su progreso y mantener sus métricas al día.

- **Task Flow (Flujo de tareas del usuario)**

  1. Desde el menú inferior, selecciona “Actividad”.
  2. Ingresa el tipo de ejercicio, duración e intensidad.
  3. El sistema calcula las calorías quemadas y muestra una confirmación visual.
  4. En la opción “Progreso”, el usuario actualiza su peso y visualiza la evolución de los últimos días.
  5. Los datos actualizados se reflejan automáticamente en los gráficos y metas diarias.

![Artefacto creado en Figma](src/img/cap6/WD_registrar.png)

**Wireflow Diagram 6: Perfil y Configuración del Usuario**

- **User Goal**

  El usuario desea gestionar su información personal, idioma, notificaciones, políticas de privacidad y control de datos dentro de la aplicación.

- **Task Flow (Flujo de tareas del usuario)**

  1. Desde la barra inferior, selecciona “Perfil”.
  2. Accede a los apartados de datos personales, objetivos y nivel de actividad.
  3. Configura preferencias como idioma, notificaciones o alertas.
  4. Consulta los términos, políticas de privacidad y opciones de eliminación o exportación de datos.
  5. Puede regresar a la pantalla principal en cualquier momento manteniendo los cambios guardados.

![Artefacto creado en Figma](src/img/cap6/WD_Cp.png)



### Applications Mock-ups 

::: box
**Mobile Applications Mock-ups**
:::

En esta sección se presentan los mockups de la aplicación móvil de Foodlytics. Estas pantallas muestran las funciones principales del producto y reflejan el diseño final propuesto para la experiencia del paciente. Todas las interfaces mantienen consistencia visual, accesibilidad y claridad en la interacción.

![Artefacto creado en Figma - Mobile Application (Inicio)](src/img/cap6/mockups/Inicio.png)

![Artefacto creado en Figma - Mobile Application (Calcular IMC)](src/img/cap6/mockups/CalcularIMC.png)

![Artefacto creado en Figma - Mobile Application (Pantalla principal nuevo paciente)](src/img/cap6/mockups/Pantallaprincipal.png)

![Artefacto creado en Figma - Mobile Application (Comidas registradas)](src/img/cap6/mockups/ComidasRegistradas.png)

![Artefacto creado en Figma - Mobile Application (Bottom Navigation)](src/img/cap6/mockups/BottomNav.png)

![Artefacto creado en Figma - Mobile Application (Actividad y Progreso)](src/img/cap6/mockups/Actividad.png)

![Artefacto creado en Figma - Mobile Application (Perfil)](src/img/cap6/mockups/Perfil.png)

![Artefacto creado en Figma - Mobile Application (Acciones rápidas)](src/img/cap6/mockups/AccionesRapidas.png)

\newpage

::: box
**Web Applications Mock-ups**
:::

En esta sección se presentan los mockups de la aplicación web de Foodlytics. Estas pantallas muestran las funciones principales para profesionales de la salud, incluyendo la gestión de pacientes, el tablero general, el calendario, el control de notificaciones y la administración de la cuenta.

![Artefacto creado en Figma - Web Application (Login y Registro)](src/img/cap6/web-mockups/login_register.png)

![Artefacto creado en Figma - Web Application (Dashboard)](src/img/cap6/web-mockups/Dashboard.png)

![Artefacto creado en Figma - Web Application (Pacientes)](src/img/cap6/web-mockups/Pacientes.png)

![Artefacto creado en Figma - Web Application (DetallePacientes)](src/img/cap6/web-mockups/DetallePaciente.png)


![Artefacto creado en Figma - Web Application (Notificaciones)](src/img/cap6/web-mockups/Notificaciones.png)

![Artefacto creado en Figma - Web Application (Perfil)](src/img/cap6/web-mockups/Perfil.png)

![Artefacto creado en Figma - Web Application (Suscripciones)](src/img/cap6/web-mockups/Suscripciones.png)

![Artefacto creado en Figma - Web Application (Configuración)](src/img/cap6/web-mockups/Configuración.png)

![Artefacto creado en Figma - Web Application (FAQ)](src/img/cap6/web-mockups/faqs.png)

\newpage

### Applications User Flow Diagrams  

::: box
**Mobile Applications User Flow Diagrams**
:::

En esta sección se presentan los flujos de usuario diseñados para la aplicación móvil de Foodlytics. El objetivo es describir, paso a paso, cómo la persona usuaria interactúa con la app para registrar sus datos, monitorear su alimentación, actividad física y peso, y gestionar la configuración de su cuenta.

Cada diagrama resume rutas típicas, alternativas y escenarios excepcionales, respetando las reglas de negocio definidas en la arquitectura de Foodlytics, como la creación de registros únicamente para la fecha de hoy y el uso de acciones rápidas para acceder a funciones clave.

\newpage

::: info
**Inicio de sesión y creación de cuenta**
:::

**User Goal**  
La persona usuaria desea acceder a Foodlytics e iniciar sesión o crear una cuenta para comenzar a monitorear su información.

Este flujo inicia con la pantalla de carga de Foodlytics y dirige a la pantalla de inicio de sesión. La persona puede ingresar correo y contraseña, recuperar contraseña mediante enlace al correo o acceder al registro si aún no tiene cuenta.

En el registro se completan nombre, correo y contraseña. Cuando el sistema valida los datos, redirige al onboarding. La condición de éxito es llegar a la primera pantalla de configuración inicial sin errores.

::: info
**Configuración inicial de perfil y metas (Onboarding)**
:::

**User Goal**  
Registrar datos físicos y nivel de actividad para que Foodlytics calcule IMC y metas nutricionales diarias.

El onboarding se ejecuta al ingresar por primera vez. Incluye pasos secuenciales: fecha de nacimiento, género, altura, peso actual, peso objetivo y nivel de actividad física.

Cada pantalla captura un dato específico. Al finalizar, la app calcula IMC y metas de calorías. Cuando la persona confirma, se marca el onboarding como completado y se redirige a la pantalla principal.


![Artefacto creado en Figma](src/img/cap6/userflowMobile/WD_i.png)

\newpage

::: info
**Registro de comida mediante cámara e IA**
:::

**User Goal**  
Registrar una comida de hoy usando la cámara para que la IA identifique alimentos y calcule macronutrientes.

El flujo inicia en la pestaña Comidas. Si la fecha es hoy, el botón Agregar comida está disponible. Al seleccionarlo, la app abre la cámara con el parámetro dateISO y, si corresponde, mealType.

Después de tomar la foto se muestra Analizando tu comida mientras la IA detecta alimentos y porciones. La vista de Alimentos Detectados permite ajustar cantidades, eliminar alimentos o seleccionar tipo de comida si no se definió al inicio.

Al confirmar se ejecuta saveMeal, que valida que la fecha sea hoy. Si es correcto se registra la comida y se vuelve a la vista de comidas del día.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WD_comidasRegistradas.png)

\newpage

::: info
**Visualización y detalle de comidas registradas**
:::

**User Goal**  
Revisar comidas registradas y ver aportes nutricionales por día.

En la pestaña Comidas se puede navegar por el calendario. Si la fecha no es hoy, la interfaz funciona en modo lectura.

Cada comida muestra calorías y macronutrientes. Al seleccionarla se abre una pantalla con detalles de calorías totales, proteínas, carbohidratos, grasas y lista de alimentos registrados.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WD_comidasRegistradas.png)




\newpage

::: info
**Registro de actividad física y actualización de estadísticas**
:::

**User Goal**  
Registrar actividad física de hoy para actualizar calorías quemadas y estadísticas.

El flujo inicia desde Actividad o desde Registrar Actividad. La persona selecciona tipo de actividad, duración e intensidad.

Cambiar tipo de actividad muestra una lista de actividades con calorías por minuto. Al elegir una, se regresa al modal con el cálculo actualizado.

Al confirmar se ejecuta saveActivity con validación de fecha. Si es correcto se actualiza el tablero con calorías quemadas, tiempo total y racha semanal.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WB_registrarActvidiad_Peso.png)



\newpage

::: info
**Registro de peso y seguimiento de progreso**
:::

**User Goal**  
Registrar peso actual de hoy para actualizar historial y progreso.

El flujo inicia desde Progreso o desde Acciones rápidas. La persona ingresa peso actual, revisa peso anterior y la diferencia con su meta.

saveWeight valida que sea la fecha de hoy. Luego actualiza el peso actual y agrega una entrada al historial. También actualiza gráficos y cumplimiento semanal.

Si se abre desde una fecha pasada, solo se muestra el historial sin opciones de creación.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WB_registrarActvidiad_Peso.png)



\newpage

::: info
**Acciones rápidas desde el botón flotante**
:::

**User Goal**  
Acceder rápido a funciones clave sin navegar por cada pestaña.

Al presionar el botón flotante más se muestra un menú con Registrar comida, Registrar actividad, Registrar peso y Nueva meta.

Cada opción abre el flujo correspondiente mediante rutas modales. La aplicación asegura que dateISO sea igual a hoy cuando la acción lo requiere.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WD_accionesRapidas.png)


\newpage

::: info
**Gestión de cuenta, notificaciones y privacidad**
:::

**User Goal**  
Configurar datos personales, idioma, notificaciones y privacidad.

![Artefacto creado en Figma](src/img/cap6/userflowMobile/WD_Cuenta.png)

Desde Perfil se muestran datos personales, metas y preferencias.  
En Notificaciones se configuran recordatorios y alertas.  
En Idioma se selecciona idioma preferido.  
En Privacidad se gestionan opciones de datos, exportación y eliminación de información.

También se puede cambiar contraseña y revisar Términos y Condiciones y la Política de Privacidad.

\newpage

::: box
**Web Applications User Flow Diagrams**
:::

Los wireflows muestran visualmente la navegación entre las pantallas principales de la aplicación web de Foodlytics. Estos diagramas combinan las vistas de cada módulo con las conexiones funcionales que sigue la persona usuaria para cumplir tareas clave como autenticación, gestión de pacientes, revisión del calendario, seguimiento de actividades y administración de configuraciones del sistema. Los siguientes flujos permiten comprender la estructura lógica de la plataforma antes del desarrollo final.

\newpage

::: info
**Inicio de sesión y autenticación**
:::

![Inicio de sesión – Foodlytics Web](src/img/cap6/userflowWeb/FlujoInicioSesion.png)

Este wireflow representa el flujo completo de acceso a la plataforma. La persona usuaria inicia en la pantalla de bienvenida, donde puede ingresar con su correo y contraseña. También puede autenticarse mediante servicios externos o registrarse si no tiene cuenta.

Cuando el login es exitoso, el sistema redirige al dashboard principal. Este flujo busca asegurar un acceso rápido y coherente con la estructura general del sistema.

\newpage

::: info
**Página principal y navegación general**
:::

![Dashboard – Foodlytics Web](src/img/cap6/userflowWeb/FlujoPrincipal.png)

Este wireflow muestra el recorrido inicial de la persona usuaria dentro del dashboard. Desde esta vista central puede acceder a los módulos del sistema como pacientes, calendario, kanban board, actividades, notificaciones, suscripciones y configuraciones.

El objetivo de este flujo es presentar un control general de la plataforma con indicadores visuales, tablas de proyectos o pacientes, y accesos directos a funcionalidades clave.

\newpage

::: info
**Gestión de calendario**
:::

![Calendario – Foodlytics Web](src/img/cap6/userflowWeb/FlujoCalendario.png)

Este wireflow representa la navegación desde el dashboard hacia el módulo de calendario. En esta vista la persona usuaria revisa eventos por mes, consulta el panel lateral con la agenda diaria y visualiza citas programadas.

El flujo también considera acciones como agregar eventos o revisar actividades por fecha, lo que facilita la planificación y organización de sesiones o tareas relacionadas con los pacientes.

\newpage

::: info
**Kanban Board**
:::

![Kanban Board – Foodlytics Web](src/img/cap6/userflowWeb/FlujoKanbanBoard.png)

Este diagrama muestra el acceso al tablero kanban desde el dashboard. La persona usuaria visualiza las tareas distribuidas en columnas como To Do, In Progress, To Review y Completed.

El wireflow destaca la navegación entre tarjetas, la actualización del estado de cada tarea y la revisión de detalles específicos, permitiendo un seguimiento visual del progreso del trabajo.

\newpage

::: info
**Gestión de pacientes**
:::

![Pacientes – Foodlytics Web](src/img/cap6/userflowWeb/FlujoPacientes.png)

Este wireflow detalla la navegación entre el listado de pacientes y la vista de información individual. Desde el dashboard se accede al listado completo donde se puede consultar información personal, historial y estado actual de cada paciente.

Al seleccionar un paciente, el sistema muestra una vista detallada con métricas como peso, altura, calorías diarias, distribución de macronutrientes, evolución semanal y actividades registradas. Este flujo asegura que la información clínica sea accesible y clara.

\newpage

::: info
**Configuración de la cuenta y ajustes administrativos**
:::

![Configuración – Foodlytics Web](src/img/cap6/userflowWeb/FlujoConfiguracion.png)

Este wireflow agrupa todas las rutas relacionadas con la administración de la cuenta de usuario. Incluye vistas como cambio de contraseña, edición de perfil, política de privacidad y términos y condiciones.

El flujo parte desde el dashboard hacia la sección de configuraciones, permitiendo a la persona usuaria mantener control sobre su información, revisar políticas y gestionar sus preferencias para una mayor transparencia.

\newpage

## Applications Prototyping  

::: box
**Mobile Applications Prototyping**
:::

Esta sección presenta los prototipos interactivos desarrollados para la aplicación móvil de Foodlytics. Estos prototipos permiten simular la experiencia real de navegación, alineada con los User Flow Diagrams previamente definidos. Su construcción se realizó en Figma, donde se diseñaron las pantallas clave y se configuraron interacciones que replican el comportamiento esperado dentro de la aplicación final.

![Mobile Applications Prototyping](src/img/cap6/mobile-prototyping.png)

**Diseño e interacción**

El prototipado se basa en una arquitectura centrada en la claridad y eficiencia. La navegación principal utiliza una barra inferior persistente que agrupa las secciones más relevantes: Inicio, Comidas, Actividad y Perfil. Este enfoque permite que la persona usuaria acceda de manera rápida a los registros de comida, actividades físicas, peso y configuraciones personales.

Las interacciones diseñadas en Figma replican acciones reales como toques, gestos de desplazamiento, apertura de modales y transiciones entre pantallas. Esto permitió validar desde etapas tempranas si los flujos eran intuitivos y si la carga visual era adecuada para un uso diario.

**Compatibilidad entre plataformas**

Aunque los prototipos se construyeron inicialmente sobre frames de iOS para lograr una visualización más precisa, todas las decisiones de diseño fueron tomadas considerando la implementación multiplataforma con React Native y Expo. Esto asegura consistencia en iOS y Android, con variaciones mínimas como:

- Ajustes automáticos de paddings y alturas según sistema operativo.  
- Estilos de navegación superiores adecuados para cada plataforma.  
- Igualdad en tipografías, colores, componentes y jerarquía visual.

Dado que Expo unifica el comportamiento base, el prototipo es compartido para ambas plataformas. La experiencia final es equivalente en iOS y Android, manteniendo coherencia en flujos, estructura y elementos interactivos.

::: warn
Para acceder al prototipo interactivo en Figma, haga click en la [URL](https://www.figma.com/proto/ngBMJ7Uk6oelUsci7tuoc3/Mobile?node-id=94-241&t=ocWEuJh4SnNMLHnx-1&starting-point-node-id=94%3A221)
:::

::: warn
Para ver la demo en Microsoft Stream, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202211212_upc_edu_pe/IQAMyR01JuzrSIVEofg1E_NxAa0shRE-SbIjUmG9RYNFNdw?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=Wn20g1)
:::

![Shared Prototyping](src/img/cap6/shared-proto.png)

::: box
**Web Applications Prototyping**
:::

::: warn
Para visualizar el video del prototipo de la aplicación,  haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202211212_upc_edu_pe/IQDxC1_aXX_FR5o3kRvy9oOgAQWgS2xRqsIUeYUw1mLO4wc?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=r2cdl7)
:::

![Captura de Microsoft Stream](src/img/cap6/web-application-prototyping-video.png)

\newpage

# Capítulo VII: Product Implementation, Validation & Deployment  

## Software Configuration Management  

En esta sección se definen las bases para coordinar y controlar todos los elementos que forman Foodlytics, desde el entorno de desarrollo hasta el despliegue en producción. Incluye la configuración del entorno de trabajo, donde se fijan las versiones mínimas de IDE, SDK, librerías y contenedores que aseguran entornos estables y reproducibles. También incorpora el control de versiones mediante un modelo de ramas, políticas de merge y flujos de pull request que facilitan la colaboración y evitan conflictos. Se establece la guía de estilo y las convenciones de código, con linters y formateadores que mantienen el orden y la legibilidad del proyecto. Finalmente, se define la configuración de despliegue, usando pipelines de CI/CD y scripts parametrizados que automatizan la provisión y actualización de los entornos de staging y producción.

Este enfoque integral de la Gestión de Configuración de Software garantiza que cada cambio de Foodlytics quede registrado, validado y desplegado siguiendo un flujo de trabajo claro y trazable. Esto mejora la estabilidad del sistema, aporta transparencia al equipo y acelera la entrega de nuevas funcionalidades para nutricionistas y pacientes.

![Imagen extraída de Google](src/img/cap7/cap7.png)

\newpage

### Software Development Environment Configuration 

En esta sección se detallan los productos de software que el equipo usará durante todo el ciclo de vida de Foodlytics. Para cada herramienta se indica su nombre, su propósito dentro del proyecto y la forma de acceso, ya sea por la ruta de un servicio SaaS o por el enlace de descarga para instalación local. Se incluyen las fases de gestión de proyectos, gestión de requisitos, diseño UX/UI, desarrollo, pruebas, despliegue y documentación. Esto permite mantener un conjunto de herramientas alineado con las restricciones y estándares definidos para el sistema, y asegura un flujo de trabajo ordenado y consistente para nutricionistas y pacientes.

**UxPresia**  

Nos ayudará a capturar y priorizar requerimientos mediante mapas de historias de usuario, tableros de retrospectivas y definición de flujos de trabajo colaborativos.

![Imagen extraída de Canva](src/img/cap7/uxpressia-logo.png)

\newpage

::: norm
Comunicación y Almacenamiento
:::

**Discord**  

Nos ayudará a coordinar comunicación asíncrona y en tiempo real con canales temáticos, integrando notificaciones de repositorios y pipelines.

![Imagen extraída de Canva](src/img/cap7/discord-logo.png)

**Google Drive**  

Nos ayudará a centralizar y compartir recursos estáticos (imágenes, documentos de diseño, exportaciones) con control de versiones automático.

![Imagen extraída de Canva](src/img/cap7/drive-logo.png)

\newpage

::: norm
Diseño UX/UI y Modelado
:::

**Figma**  

Nos ayudará a prototipar y validar interfaces interactivas, facilitando la colaboración en diseño de pantallas móviles y web.

![Imagen extraída de Canva](src/img/cap7/figma-logo.png)

**Mermaid**  

Nos ayudará a generar diagramas (flujo, secuencia, entidad-relación) directamente desde texto, manteniendo la documentación arquitectónica actualizada.

![Imagen extraída de Canva](src/img/cap7/mermaid-logo.png)

**DeepWiki**  

Nos permitirá generar diagramas desde texto y mantener la documentación técnica actualizada.

![Imagen extraída de Canva](src/img/cap7/deepwiki-logo.png){ width=75% }

\newpage

**Structurizr**  

Nos ayudará a crear modelos C4 de arquitectura de software, exportables para compartir vistas de contexto, contenedores y componentes.

![Imagen extraída de Canva](src/img/cap7/Structurizr-logo.png)

::: norm
Entornos de Desarrollo e IDEs
:::

**WebStorm**  

Nos ayudará a desarrollar el front-end con herramientas avanzadas de refactor, debug y pruebas de JavaScript/TypeScript.

![Imagen extraída de Canva](src/img/cap7/webstorm-logo.png)

\newpage

**Pycharm IDEA**  

Nos ayudará a programar el backend en Python y ofrece integración con herramientas de construcción y soporte de debugging para acelerar el desarrollo.

![Imagen extraída de Google](src/img/cap7/pycharm-logo.png){ width=35% }

**Visual Studio Code**  

Nos ayudará a editar scripts, archivos de configuración y pequeños microservicios con su vasta biblioteca de extensiones.

![Imagen extraída de Canva](src/img/cap7/vsc-logo.png)

\newpage

**Fast API**  

Nos ayudará a estructurar y exponer servicios RESTful en Python, con arranque rápido, sintaxis clara y soporte integrado para validación y seguridad.

![Imagen extraída de Google](src/img/cap7/fastapi-logo.png){ width=45% }

\newpage

**Angular**  

Nos ayudará a construir la aplicación web de gestión con componentes modulables, inyección de dependencias y rutinas de pruebas.

![Imagen extraída de Canva](src/img/cap7/angular-logo.png)

**React**  

React permitirá desarrollar la landing page y los dashboards web. React Native se usará para la aplicación móvil con la misma base de componentes y flujo de trabajo.

![Imagen extraída de Canva](src/img/cap7/react-logo.png)

\newpage

::: norm
Servicios Externos
:::

**Auth0**  

Permitirá manejar autenticación y autorización externa con un flujo seguro para usuarios web y móviles.

![Imagen extraída de Google](src/img/cap7/auth0-logo.png){ width=45% }

**Culqi**  

Permitirá procesar pagos y validar transacciones de forma integrada en el backend y la app web.

![Imagen extraída de Google](src/img/cap7/culqi-logo.png){ width=45% }

\newpage

### Source Code Management  

En esta subsección de Source Code Management se establecerá el esquema de organización que usará el equipo para dar seguimiento a todas las modificaciones del código fuente de Foodlytics. GitHub será la plataforma de control de versiones. Se registrará la URL de cada repositorio correspondiente a la landing page, los servicios backend y las aplicaciones web y móvil. En el caso del backend, el repositorio incluirá el proyecto principal junto con los archivos de pruebas unitarias y de integración.

El workflow seguirá el modelo GitFlow. Además de la rama principal, se creará una rama de desarrollo. Cada funcionalidad o corrección tendrá un branch propio con la convención feature/. También se definirán ramas de liberación con release/ y de corrección urgente con hotfix/. Para el versionado se usará Semantic Versioning. Para los mensajes de commit se aplicará el estándar Conventional Commits. Esto asegura claridad y trazabilidad en cada cambio del proyecto.

\vspace{0.4cm}

![Artefacto creado con Mermaid](src/img/cap7/gitflow.png)

\newpage

### Source Code Style Guide & Conventions  

Para el desarrollo de Foodlytics, cada solución del sistema, como la landing page, la aplicación web, la aplicación móvil y los servicios backend, cuenta con su propio stack tecnológico, conjunto de herramientas, convenciones de idioma y estrategia de pruebas. A continuación se detalla cada una.

::: box  
**Landing Page**  
:::

- **Tecnologías**  

  - *React + Vite* con *HTML5*, *CSS3* y *JavaScript (ES6+)*.  

  - Librerías de estilo: *Tailwind CSS* y componentes de *shadcn/ui*.  

- **Herramientas**  

  - IDE: *Visual Studio Code* / *WebStorm*.  

  - Control de versiones: *Git* y *GitHub* (repositorio `Foodlytics-LandingPage`).  

  - Diseño visual y prototipos: *Figma*.  

  - Despliegue: *Vercel* con previews automáticas por Pull Request.  

- **Convenciones de idioma**  

  - Código y comentarios en **inglés**.  

  - Implementación de *i18n* para soporte de español.  

- **Pruebas y documentación**  

  - Pruebas de integración y E2E en *Playwright* con escenarios escritos en *Gherkin*.  

  - Documentación de componentes en *Storybook*.  

![Recurso extraido de Canva](src/img/cap7/landing-banner.png)

\newpage

::: box  
**Web Application (Nutritionist Application)**  
:::

- **Tecnologías**  

  - *Angular* con SSR en modo standalone (TypeScript, RxJS, Angular CLI).  
  
  - Componentes modulares y formularios reactivos.  

- **Herramientas**  

  - IDE: *WebStorm*.  
  
  - Control de versiones: *Git* y *GitHub* (repositorio `Foodlytics-Web-Application`).
    
  - Diseño: *UIzard* para wireframes y flujos de usuario.  
  
  - Linting y formateo: *ESLint* y *Prettier* integrados al desarrollo.  
  
  - QA y pruebas: *Karma* para tests E2E.  
     
  - Hosting: Render con soporte integrado para SSR y previews por Pull Request.  

- **Convenciones de idioma**  

  - Código y mensajes en **inglés**.  

- **Pruebas y documentación**  

  - Historias de usuario escritas en *Gherkin* dentro del repositorio.  
  
  - Documentación de API REST consultadas mediante *Swagger UI*.  

![Recurso extraído de Canva](src/img/cap7/web-app-banner.png)

\newpage

::: box  
**Mobile Application (Patients Application)**  
:::

- **Tecnologías**  

  - *React Native* con *Expo Go* para iOS y Android.  
  
  - Librerías para *navegación*, *cámara*, *notificaciones push* y acceso a sensores.  

- **Herramientas**  

  - IDE: *WebStorm*.  
  
  - Control de versiones: *Git* y *GitHub* (repositorio `Foodlytics-Mobile-Application`).  
  
  - Diseño de pantallas: *Figma* con prototipos interactivos.  
  
  - Emulación y pruebas: *Expo Go*, *Android Emulator* y *iOS Simulator*.  

- **Convenciones de idioma**  

  - Código y recursos en *inglés*.  
  
  - Soporte multilenguaje mediante librerías *i18n* para React Native.  

- **Pruebas y documentación**  

  - Tests unitarios con *Jest* y *React Native Testing Library*. 
   
  - Escenarios de usuario escritos en *Gherkin*.
  
  - Documentación de flujos en *Mermaid* dentro del README.  

![Recurso extraído de Canva](src/img/cap7/mobile-app-banner.png)

\newpage

::: box  
**Web Services (API)**  
:::

- **Tecnologías**  

  - *FastAPI* para el desarrollo de servicios RESTful en Python. 
   
  - Autenticación externa con *Auth0* usando *JWT*.  
  
  - Procesamiento de pagos con *Culqi API*.  

  - Persistencia: *PostgreSQL* con migraciones gestionadas por *Alembic*.
  
  - Tareas programadas y operaciones asíncronas usando *Background Tasks* de FastAPI.  

- **Herramientas**  

  - IDE: *PyCharm IDEA* / *Visual Studio Code*.  

  - Control de versiones: *Git* y *GitHub* (repositorio `foodlytics-api`).  

  - Contenedores: *Docker* + *Docker Compose* para entornos locales.  

  - Documentación de API: *Swagger UI* generada automáticamente por FastAPI.  

  - Pruebas: *pytest* para unitarias e integración.  

  - Orquestación CI/CD: *GitHub Actions* con pipelines definidas en workflows.  

  - Monitoreo: *Prometheus* + *Grafana* para métricas del backend.  

- **Convenciones de idioma**  

  - Código, variables y documentación interna en *inglés*.  

- **Pruebas y documentación**  

  - Pruebas unitarias, de integración y escenarios en *Gherkin* vinculados a historias de usuario. 
 
  - Diagramas C4 en *Structurizr* y diagramas de secuencia en *Mermaid*.  

![Recurso extraído de Canva](src/img/cap7/web-service-banner.png)

::: box  
**Convenciones de Commits**  
:::

Adoptamos **Conventional Commits v1.0.0**:
```text
<type>[scope opt]: <short description>
```
- **type:** feat, fix, docs, style, refactor, test, chore  

- **scope:** componente o módulo afectado  

- **description:** resumen breve y claro  

::: box  
**Versionado Semántico**  
:::

Seguimos **Semantic Versioning 2.0.0 (X.Y.Z)**:  

- **X (Major):** cambios incompatibles  

- **Y (Minor):** nuevas funcionalidades compatibles  

- **Z (Patch):** correcciones menores  

Las ramas y tags se nombran así:  

- Feature branches: `feature/<short-description>`  

- Release branches: `release/vX.Y.0`  

- Hotfix branches: `hotfix/vX.Y.Z`

\newpage

### Software Deployment Configuration  

Esta sección describe la configuración de despliegue utilizada para cada componente de la solución digital: Landing Page, Web Services y Aplicacion Web Frontend. A partir del código fuente en los repositorios, se detallan los pasos necesarios para su correcta publicación en entornos de desarrollo y producción.

::: warn
Para acceder al flujo de trabajo, haga click a la [URL](https://github.com/orgs/GMB-Labs/repositories)
:::

::: warn
Para acceder a la documentación del *API*, haga click a la [URL](https://deepwiki.com/GMB-Labs/foodlytics-api)
:::

::: warn
Para acceder a la documentación del *Web Application*, haga click a la [URL](https://deepwiki.com/GMB-Labs/Foodlytics-Web-Application)
:::

::: warn
Para acceder a la documentación del *Mobile Application*, haga click a la [URL](https://deepwiki.com/GMB-Labs/Foodlytics-Mobile-Application)
:::

## Solution Implementation  

### Sprint 1

El Sprint 1 marcó el inicio formal del desarrollo de Foodlytics y permitió establecer las bases técnicas y organizativas del proyecto. En esta etapa se avanzó en casi toda la documentación central, desde los primeros capítulos hasta el Capítulo 7, lo que ayudó a definir con claridad el alcance, la arquitectura y el funcionamiento general del sistema. También se completó una parte importante de la aplicación, incluyendo la estructura inicial del backend, la preparación del entorno técnico y la construcción de la landing page.

Durante el sprint se definieron las tecnologías principales, los repositorios, el estilo de desarrollo y la estructura modular del proyecto. El equipo trabajó de forma coordinada, con tareas distribuidas y roles claros, lo que facilitó avanzar de manera consistente hacia el Sprint Goal. Este primer ciclo dejó una base sólida para las siguientes iteraciones tanto en documentación como en implementación.

\newpage

#### Sprint Planning 1

\begin{tabularx}{\textwidth}{p{5cm}X}
\caption{Sprint Planning – Sprint 1}\label{tab:sprint1-planning}\\
\toprule
\textbf{Sprint Planning Background} & \\ 
\midrule

\textbf{Sprint} & Sprint 1 \\
\textbf{Date} & 10/11/2025 \\
\textbf{Time} & 21:00 \\
\textbf{Location} & Discord Virtual Meeting \\
\textbf{Prepared By} & Ramos Rios, Belen del Rocio \\
\textbf{Attendees (to planning meeting)} & Del Castillo Bueno, Daniel Mateo; Poma Espinoza, Gustavo; Vilchez Rios, Mateo Alejandro; Zavala Quedena, Gonzalo Andre \\
\textbf{Sprint 1 Review Summary} & Implementación de los 7 capítulos, Requirements Specification y primer Sprint de implementación \\
\textbf{Sprint 1 Retrospective Summary} & El trabajo se realizó a tiempo, y cada integrante terminó lo asignado. También se trabajó en equipo cuando el proyecto lo requería \\
\textbf{Sprint Goal \& User Stories} & Implementar la landing page, avanzar una parte del backend y definir las tecnologías base \\
\textbf{Sprint 1 Velocity} & 1 Sprint cada semana \\
\textbf{Sum of Story Points} & 195 \\
\bottomrule
\end{tabularx}

\newpage

#### Sprint Backlog 1 

\begin{tabularx}{\textwidth}{|c|p{1.4cm}|p{3.8cm}|X|c|}
\hline
\# Orden & \textbf{ID} & \textbf{Título} & \textbf{Descripción} & \textbf{Story Points} \\
\hline
1  & \textbf{LP-US01} & Visualización de propuesta de valor clara & Como visitante, quiero visualizar claramente la propuesta de valor, para comprender qué ofrece la aplicación. & 3 \\
\hline
2  & \textbf{LP-US02} & Identificación de segmento médico & Como visitante, quiero identificar el segmento médico, para saber cómo la aplicación atiende sus necesidades. & 2 \\
\hline
3  & \textbf{LP-US03} & Identificación de segmento paciente & Como visitante, quiero identificar el segmento paciente, para entender cómo me beneficiará la solución. & 2 \\
\hline
4  & \textbf{LP-US04} & Evidencia y testimonios & Como visitante, quiero ver evidencias y testimonios, para confiar en la aplicación. & 2 \\
\hline
5  & \textbf{LP-US05} & Ruta de producto & Como visitante, quiero conocer la ruta de producto, para ver la evolución de la aplicación. & 3 \\
\hline
6  & \textbf{LP-US06} & Acción principal de conversión & Como visitante, quiero contar con un botón claro de conversión, para iniciar relación con el equipo. & 2 \\
\hline
7  & \textbf{LP-US07} & Captura de interés del médico & Como visitante médico, quiero registrar mi interés, para recibir información personalizada. & 2 \\
\hline
8  & \textbf{LP-US08} & Captura de interés del paciente & Como visitante paciente, quiero registrar mi interés, para recibir información útil. & 2 \\
\hline
9  & \textbf{LP-US09} & Información de contacto verificada & Como visitante, quiero acceder a información de contacto verificada, para comunicarme con el equipo. & 2 \\
\hline
10 & \textbf{LP-US10} & Ver demo del producto & Como visitante, quiero ver una demo del producto, para comprender sus funcionalidades. & 3 \\
\hline
11 & \textbf{LP-US11} & Compartir en redes sociales & Como visitante, quiero compartir el producto en redes sociales, para difundir la solución. & 2 \\
\hline
12 & \textbf{LP-US12} & Políticas y privacidad & Como visitante, quiero acceder a políticas y privacidad, para sentir confianza antes de registrarme. & 2 \\
\hline
13 & \textbf{LP-US13} & Soporte multiplataforma & Como visitante, quiero conocer la compatibilidad multiplataforma, para saber si funciona en mis dispositivos. & 2 \\
\hline
14 & \textbf{LP-US14} & Preguntas frecuentes & Como visitante, quiero acceder a preguntas frecuentes, para resolver dudas comunes. & 2 \\
\hline
15 & \textbf{LP-US15} & Descubrimiento en buscadores & Como visitante, quiero que el producto aparezca en buscadores, para encontrarlo fácilmente. & 2 \\
\hline
16 & \textbf{WEB-US01} & Registro de cuenta de nutricionista & Como nutricionista, quiero registrar mi cuenta, para acceder al sistema. & 3 \\
\hline
17 & \textbf{WEB-US03} & Inicio de sesión & Como nutricionista, quiero iniciar sesión, para acceder de forma segura a mi cuenta. & 3 \\
\hline
18 & \textbf{WEB-US04} & Cierre de sesión & Como nutricionista, quiero cerrar sesión, para proteger mis datos. & 2 \\
\hline
19 & \textbf{WEB-US05} & Recuperación de contraseña & Como nutricionista, quiero recuperar mi contraseña, para restablecer acceso en caso de olvido. & 3 \\
\hline
20 & \textbf{MOB-US01} & Registro de usuario nuevo & Como paciente, quiero registrarme en la app, para empezar a usarla. & 3 \\
\hline
21 & \textbf{MOB-US02} & Inicio de sesión & Como paciente, quiero iniciar sesión, para acceder a mis datos. & 3 \\
\hline
22 & \textbf{MOB-US03} & Cierre de sesión & Como paciente, quiero cerrar sesión, para proteger mis datos. & 2 \\
\hline
23 & \textbf{MOB-US07} & Cálculo de IMC & Como paciente, quiero calcular mi IMC, para conocer mi estado físico. & 3 \\
\hline
24 & \textbf{MOB-US09} & Registro de comidas con foto & Como paciente, quiero registrar mis comidas con foto, para facilitar el ingreso de alimentos. & 5 \\
\hline
25 & \textbf{MOB-US10} & Modificar comida registrada & Como paciente, quiero modificar alimentos detectados, para corregir cantidades o errores. & 3 \\
\hline
26 & \textbf{MOB-US11} & Ver macros por comida & Como paciente, quiero ver macros por comida registrada, para analizar el aporte individual. & 3 \\
\hline
27 & \textbf{TUS-01} & Registro seguro de usuario & Como developer, quiero implementar registro seguro, para garantizar la creación confiable de cuentas. & 5 \\
\hline
28 & \textbf{TUS-02} & Inicio de sesión seguro & Como developer, quiero implementar inicio de sesión seguro, para permitir acceso confiable a los usuarios. & 5 \\
\hline
29 & \textbf{TUS-03} & Cierre de sesión seguro & Como developer, quiero habilitar cierre de sesión seguro, para proteger la información del usuario. & 3 \\
\hline
30 & \textbf{TUS-04} & Recuperación de contraseña & Como developer, quiero implementar recuperación de contraseña, para restablecer accesos de usuarios olvidadizos. & 3 \\
\hline
31 & \textbf{TUS-05} & Actualización de perfil & Como developer, quiero permitir actualización de perfil, para mantener los datos de usuario actualizados. & 3 \\
\hline
32 & \textbf{TUS-06} & Crear paciente & Como developer, quiero implementar endpoint para crear paciente, para registrar nuevos usuarios en el sistema. & 5 \\
\hline
33 & \textbf{TUS-07} & Obtener paciente & Como developer, quiero obtener información de un paciente, para mostrarla al nutricionista. & 3 \\
\hline
34 & \textbf{TUS-08} & Actualizar paciente & Como developer, quiero actualizar información de un paciente, para mantener datos correctos. & 3 \\
\hline
35 & \textbf{TUS-09} & Desactivar paciente & Como developer, quiero desactivar pacientes, para mantener registros vigentes sin eliminarlos. & 3 \\
\hline
36 & \textbf{TUS-10} & Registrar comida & Como developer, quiero permitir registrar comidas, para guardar la dieta del usuario. & 5 \\
\hline
37 & \textbf{TUS-11} & Corregir comida & Como developer, quiero habilitar corrección de comidas, para ajustar datos detectados erróneamente. & 3 \\
\hline
38 & \textbf{TUS-12} & Consultar consumo diario & Como developer, quiero consultar el consumo diario, para mostrar resúmenes nutricionales. & 3 \\
\hline
39 & \textbf{TUS-13} & Registrar actividad física & Como developer, quiero registrar actividad física, para reflejar esfuerzo del usuario. & 3 \\
\hline
40 & \textbf{TUS-14} & Registrar pasos & Como developer, quiero registrar pasos diarios, para calcular calorías quemadas. & 3 \\
\hline
41 & \textbf{TUS-15} & Consultar resumen de pasos & Como developer, quiero consultar resumen de pasos, para generar balance energético. & 3 \\
\hline
42 & \textbf{TUS-16} & Registrar peso & Como developer, quiero registrar peso de usuario, para monitorear evolución. & 3 \\
\hline
43 & \textbf{TUS-17} & Calcular IMC & Como developer, quiero calcular y consultar IMC, para determinar estado de salud. & 3 \\
\hline
44 & \textbf{TUS-18} & Gestionar metas & Como developer, quiero gestionar metas de calorías y macros, para personalizar objetivos. & 5 \\
\hline
45 & \textbf{TUS-19} & Programar recordatorios & Como developer, quiero programar recordatorios automáticos, para mantener la constancia del usuario. & 3 \\
\hline
46 & \textbf{TUS-20} & Detectar exceso o déficit & Como developer, quiero detectar exceso o déficit en la dieta, para generar alertas. & 3 \\
\hline
47 & \textbf{TUS-21} & Publicar contrato OpenAPI & Como developer, quiero publicar contrato OpenAPI 3.1, para documentar la API. & 3 \\
\hline
48 & \textbf{TUS-22} & Manejo de errores estándar & Como developer, quiero usar Problem Details RFC 9457, para gestionar errores de forma uniforme. & 3 \\
\hline
49 & \textbf{TUS-23} & Controles de autorización & Como developer, quiero implementar autorización granular, para proteger recursos sensibles. & 5 \\
\hline
50 & \textbf{TUS-24} & Paginación y orden & Como developer, quiero implementar paginación y orden, para optimizar listados grandes. & 3 \\
\hline
51 & \textbf{TUS-25} & Versionado estable & Como developer, quiero versionar la API, para mantener estabilidad en cambios futuros. & 3 \\
\hline
52 & \textbf{TUS-26} & Observabilidad con métricas & Como developer, quiero habilitar métricas y trazas, para monitorear el sistema. & 5 \\
\hline
53 & \textbf{TUS-27} & Auditoría de cambios & Como developer, quiero auditar cambios, para garantizar trazabilidad de datos. & 3 \\
\hline
54 & \textbf{TUS-28} & Reconocimiento de alimentos & Como developer, quiero reconocer alimentos en imágenes, para identificar comidas automáticamente. & 5 \\
\hline
55 & \textbf{TUS-29} & Estimación de cantidades & Como developer, quiero estimar cantidad de alimentos, para calcular macros. & 5 \\
\hline
56 & \textbf{TUS-30} & Puntuaciones de confianza & Como developer, quiero devolver puntuaciones de confianza, para indicar certeza en detecciones. & 3 \\
\hline
57 & \textbf{TUS-31} & Corrección manual de IA & Como developer, quiero permitir corrección manual, para mejorar precisión del registro. & 3 \\
\hline
58 & \textbf{TUS-32} & Catálogo de alimentos & Como developer, quiero publicar catálogo de alimentos y porciones, para estandarizar registros. & 5 \\
\hline
59 & \textbf{TUS-33} & Gestión de consentimientos & Como developer, quiero gestionar consentimientos por finalidad, para cumplir con normas de privacidad. & 5 \\
\hline
60 & \textbf{TUS-34} & Cifrado en tránsito y reposo & Como developer, quiero cifrar datos en tránsito y reposo, para garantizar seguridad. & 5 \\
\hline
61 & \textbf{TUS-35} & Limpieza de metadatos & Como developer, quiero limpiar metadatos de imágenes, para proteger privacidad del usuario. & 3 \\
\hline
\end{tabularx}

#### Development Evidence for Sprint Review  

En esta sección se presentan las evidencias técnicas del desarrollo realizado durante el Sprint, mostrando de manera verificable el trabajo implementado en los diferentes componentes del sistema. Se incluyen capturas de los commits ejecutados en la aplicación web, la aplicación móvil y los servicios de backend, junto con los avances correspondientes en la landing page y la documentación técnica generada. Estas evidencias permiten validar la construcción interna de las funcionalidades comprometidas, reflejando la evolución del código, la estructura del proyecto y las integraciones realizadas durante este Sprint.

::: norm
*API*
:::

![Recurso extraído de Github](src/img/cap7/dev-1.jpeg)

::: norm
*Mobile Application*
:::

![Recurso extraído de Github](src/img/cap7/dev-2.jpeg)

::: norm
*Web Application*
:::

![Recurso extraído de Github](src/img/cap7/dev-3.jpeg)

::: norm
*Landing Page*
:::

![Recurso extraído de Github](src/img/cap7/dev-4.jpeg)


#### Testing Suite Evidence for Sprint Review 

El equipo consolidó la evidencia de pruebas generada durante el Sprint mediante los escenarios definidos en Gherkin. Estos casos validan el comportamiento esperado de las funcionalidades desarrolladas y permiten verificar que cada historia cumple sus criterios de aceptación. A continuación se registran los enlaces y archivos correspondientes a la Testing Suite del Sprint.

```gherkin

US: LP-US01 – Visualización de propuesta de valor clara

Feature: Visualización de propuesta de valor clara
  As a visitante
  I want to visualizar claramente la propuesta de valor de la aplicación
  So that comprendo el problema que resuelve y cómo me beneficia

  Scenario: Comprensión al primer acceso
    Given que el visitante accede a la landing page
    When se carga la sección principal
    Then el visitante comprende el propósito y beneficios del producto sin ambigüedad

  Scenario: Mensaje complementario
    Given que el visitante no identifica claramente la propuesta de valor
    When revisa el contenido expandido o sección de detalle
    Then obtiene un mensaje aclaratorio con el problema y el beneficio clave

  Scenario: Consistencia entre dispositivos
    Given que el visitante usa la landing page desde móvil o escritorio
    When visualiza la propuesta de valor
    Then el mensaje se mantiene claro y equivalente en ambos contextos

```

```gherkin

US: LP-US02 – Identificación de segmento médico

Feature: Identificación de segmento médico
  As a visitante del segmento médico
  I want to identificar contenido dirigido a mi rol
  So that entiendo cómo la solución facilita mi práctica profesional

  Scenario: Contenido segmentado para médicos
    Given que el visitante pertenece al segmento médico
    When accede a la landing page
    Then encuentra una sección con beneficios y casos de uso para profesionales de la salud

  Scenario: Ampliación de información clínica
    Given que el visitante médico necesita más detalle
    When solicita información extendida sobre el producto
    Then el sistema ofrece un recurso con capacidades y ejemplos clínicos

  Scenario: Diferenciación de perfiles
    Given que existen varios segmentos de usuarios
    When se muestran las opciones o secciones por perfil
    Then el contenido médico se diferencia claramente del contenido para pacientes

```

```gherkin

US: LP-US03 – Identificación de segmento paciente

Feature: Identificación de segmento paciente
  As a visitante paciente
  I want to identificar rápidamente el contenido pensado para mí
  So that sé cómo me ayuda a mejorar mi nutrición y hábitos

  Scenario: Visualización de beneficios para pacientes
    Given que el visitante es paciente
    When accede a la sección correspondiente en la landing
    Then visualiza beneficios y resultados esperados para su contexto

  Scenario: Expectativas y privacidad del paciente
    Given que el visitante necesita claridad sobre el uso de datos
    When revisa la información del segmento paciente
    Then entiende qué datos se usan y con qué finalidad

  Scenario: Próximo paso claro para el paciente
    Given que el visitante está interesado en el producto
    When busca cómo avanzar desde la sección de paciente
    Then identifica el siguiente paso para informarse o dejar su interés

```

```gherkin

US: LP-US04 – Evidencia y testimonios de usuarios

Feature: Evidencia y testimonios de usuarios
  As a visitante
  I want to revisar evidencia y testimonios verificados
  So that gano confianza en la efectividad del producto

  Scenario: Testimonios visibles
    Given que el visitante explora la sección de evidencia
    When consulta los testimonios disponibles
    Then encuentra citas atribuidas y resultados reportados

  Scenario: Control de calidad de testimonios
    Given que un testimonio no cumple criterios de publicación
    When el sistema lo valida para mostrarlo en la landing
    Then el testimonio no se muestra hasta ser corregido o validado

  Scenario: Evidencia cuantitativa disponible
    Given que el visitante busca datos objetivos
    When revisa la evidencia presentada
    Then identifica métricas o resultados agregados disponibles del producto

```

```gherkin

US: LP-US05 – Ruta de producto

Feature: Ruta de producto
  As a visitante
  I want to conocer el estado actual y la evolución del producto
  So that entiendo qué recibo hoy y qué mejoras vienen

  Scenario: Estado actual y próximas etapas
    Given que el visitante consulta la ruta de producto
    When revisa las capacidades actuales y futuras
    Then comprende qué está disponible y qué se planea liberar

  Scenario: Solicitud de información adicional sobre roadmap
    Given que el visitante tiene dudas sobre la ruta de producto
    When requiere más detalle desde la sección de roadmap
    Then obtiene un medio de contacto para profundizar sus preguntas

  Scenario: Actualizaciones trazables de la hoja de ruta
    Given que existen cambios en la hoja de ruta
    When el contenido se actualiza en la landing
    Then se muestra la fecha de última actualización de la ruta de producto

```

```gherkin

US: LP-US06 – Acción principal de conversión

Feature: Acción principal de conversión
  As a visitante interesado
  I want to iniciar una acción clara de contacto o demo
  So that comienzo la relación con el equipo

  Scenario: Conversión exitosa
    Given que el visitante decide iniciar contacto
    When completa los datos mínimos requeridos en el formulario de conversión
    Then el sistema registra el interés y muestra un mensaje de confirmación

  Scenario: Datos incompletos en conversión
    Given que el visitante intenta convertir
    When omite un dato obligatorio del formulario
    Then el sistema informa qué dato falta para completar el proceso

  Scenario: Prevención de registros duplicados
    Given que el visitante reintenta la conversión en un corto lapso
    When los datos coinciden con un registro reciente de interés
    Then el sistema evita la duplicidad y confirma el registro previo

```

```gherkin

US: WEB-US01 – Registro de cuenta de nutricionista

Feature: Registro de cuenta de nutricionista
  As a nutricionista
  I want to registrar una cuenta en la plataforma
  So that accedo de manera segura al sistema

  Scenario: Registro exitoso de nutricionista
    Given que el nutricionista completa el formulario de registro con datos válidos
    When envía el formulario de registro
    Then el sistema crea la cuenta y envía un correo de confirmación

  Scenario: Registro con datos incompletos
    Given que el nutricionista no completa todos los campos requeridos
    When intenta registrar la cuenta
    Then el sistema muestra mensajes de error indicando los campos faltantes

  Scenario: Registro con correo ya registrado
    Given que el nutricionista ingresa un correo ya existente en la plataforma
    When envía el formulario de registro
    Then el sistema muestra un mensaje de error indicando duplicidad de correo

```

```gherkin

US: WEB-US03 – Inicio de sesión de nutricionista

Feature: Inicio de sesión de nutricionista
  As a nutricionista
  I want to iniciar sesión en la plataforma con mi correo y contraseña
  So that accedo a mis pacientes y funcionalidades

  Scenario: Inicio de sesión exitoso
    Given que el nutricionista tiene una cuenta activa y confirmada
    When ingresa correo y contraseña válidos
    Then accede al dashboard principal de la aplicación web

  Scenario: Contraseña incorrecta en login
    Given que el nutricionista ingresa un correo válido
    When introduce una contraseña incorrecta
    Then el sistema muestra un mensaje de error de credenciales inválidas

  Scenario: Cuenta no confirmada
    Given que el nutricionista no confirmó su correo institucional
    When intenta iniciar sesión con sus credenciales
    Then el sistema bloquea el acceso y solicita confirmación previa del correo

```

```gherkin

US: WEB-US04 – Cierre de sesión (web)

Feature: Cierre de sesión de nutricionista
  As a nutricionista
  I want to cerrar sesión en cualquier momento
  So that protejo la seguridad de mi cuenta

  Scenario: Cierre de sesión manual exitoso
    Given que el nutricionista está autenticado en la aplicación web
    When selecciona la opción de cerrar sesión
    Then el sistema finaliza la sesión y redirige a la pantalla de inicio

  Scenario: Cierre de sesión por inactividad
    Given que el nutricionista permanece inactivo por un tiempo configurado
    When se excede ese tiempo de inactividad
    Then el sistema cierra automáticamente la sesión y solicita login nuevamente

  Scenario: Intento de acceso tras cierre de sesión
    Given que la sesión del nutricionista ya fue cerrada
    When intenta acceder a un recurso privado
    Then el sistema redirige a la pantalla de inicio de sesión

```

```gherkin

US: WEB-US05 – Recuperación de contraseña (web)

Feature: Recuperación de contraseña de nutricionista
  As a nutricionista
  I want to recuperar mi contraseña mediante un enlace seguro
  So that restablezco mi acceso a la plataforma

  Scenario: Solicitud de recuperación exitosa
    Given que el nutricionista olvidó su contraseña
    When solicita la recuperación e ingresa un correo válido
    Then el sistema envía un enlace seguro para restablecer la clave

  Scenario: Recuperación con correo inválido
    Given que el nutricionista ingresa un correo inexistente o no registrado
    When solicita la recuperación de contraseña
    Then el sistema muestra un mensaje de error indicando que el correo no existe

  Scenario: Uso de enlace de recuperación expirado
    Given que el nutricionista recibe un enlace caducado
    When intenta restablecer su contraseña usando ese enlace
    Then el sistema indica que el enlace expiró y debe solicitar uno nuevo

```

```gherkin

US: WEB-US06 – Gestión de perfil del nutricionista

Feature: Gestión de perfil del nutricionista
  As a nutricionista
  I want to actualizar mis datos de perfil
  So that mantengo mi información profesional actualizada

  Scenario: Actualización exitosa de perfil
    Given que el nutricionista está autenticado
    When edita sus datos de perfil con información válida
    Then el sistema guarda los cambios y los refleja inmediatamente

  Scenario: Gestión de perfil con datos inválidos
    Given que el nutricionista ingresa datos con formato incorrecto
    When intenta guardar los cambios en su perfil
    Then el sistema muestra errores de validación indicando los campos inválidos

  Scenario: Cancelación de cambios en el perfil
    Given que el nutricionista inició una edición de su perfil
    When cancela la acción antes de guardar
    Then el sistema no aplica cambios y mantiene la información anterior

```

```gherkin

US: MOB-US01 – Registro de usuario nuevo (móvil)

Feature: Registro de paciente en la aplicación móvil
  As a paciente
  I want to registrarme en la aplicación móvil proporcionando mis datos personales
  So that creo mi cuenta y accedo a las funcionalidades

  Scenario: Registro móvil exitoso
    Given que el paciente completa todos los campos obligatorios del formulario móvil
    When envía el formulario de registro
    Then el sistema crea la cuenta y confirma el registro en la app

  Scenario: Registro con campos incompletos
    Given que el paciente deja campos obligatorios vacíos
    When intenta registrarse desde la app
    Then el sistema muestra mensajes de error indicando los campos pendientes

  Scenario: Registro con correo inválido
    Given que el paciente ingresa un correo con formato no válido
    When intenta registrar la cuenta
    Then el sistema muestra un mensaje de validación de correo inválido

```

```gherkin

US: MOB-US02 – Inicio de sesión (móvil)

Feature: Inicio de sesión del paciente en la app móvil
  As a paciente
  I want to iniciar sesión con mis credenciales
  So that accedo a mi información personal

  Scenario: Inicio de sesión móvil exitoso
    Given que el paciente tiene una cuenta activa
    When ingresa credenciales correctas en la app
    Then accede correctamente a la pantalla inicial de la aplicación

  Scenario: Inicio con credenciales inválidas
    Given que el paciente ingresa correo o contraseña incorrectos
    When intenta iniciar sesión
    Then el sistema muestra un error de autenticación

  Scenario: Cuenta no confirmada en móvil
    Given que la cuenta del paciente no ha sido verificada
    When intenta iniciar sesión en la app
    Then el sistema indica que debe confirmar su cuenta antes de acceder

```

```gherkin

US: MOB-US03 – Cierre de sesión (móvil)

Feature: Cierre de sesión del paciente en la app móvil
  As a paciente
  I want to cerrar mi sesión de la aplicación móvil
  So that protejo mi información personal

  Scenario: Cierre de sesión móvil exitoso
    Given que el paciente está autenticado en la app
    When selecciona la opción de cerrar sesión
    Then el sistema cierra la sesión y redirige a la pantalla inicial o de login

  Scenario: Sesión expirada automáticamente
    Given que la sesión del paciente ha expirado por inactividad o tiempo máximo
    When el paciente intenta interactuar con una sección privada
    Then el sistema redirige a la pantalla de inicio de sesión

  Scenario: Error al cerrar sesión
    Given que ocurre un fallo de red o del servidor al cerrar sesión
    When el paciente ejecuta la acción de logout
    Then el sistema muestra un mensaje de error informando que lo intente de nuevo

```

```gherkin

US: MOB-US04 – Recuperación de contraseña (móvil)

Feature: Recuperación de contraseña del paciente en app móvil
  As a paciente
  I want to recuperar mi contraseña mediante correo electrónico
  So that restablezco mi acceso a la app

  Scenario: Recuperación móvil exitosa
    Given que el paciente solicita recuperar su contraseña
    When ingresa su correo válido en la app
    Then el sistema envía un enlace de restablecimiento al correo indicado

  Scenario: Recuperación con correo inexistente
    Given que el paciente ingresa un correo no registrado
    When solicita la recuperación de contraseña
    Then el sistema muestra un mensaje de error indicando que el correo no existe

  Scenario: Uso de enlace de recuperación expirado en móvil
    Given que el paciente recibe un enlace de recuperación
    When intenta usarlo después de su tiempo de validez
    Then el sistema muestra un mensaje indicando que el enlace es inválido o expiró

```

```gherkin

US: MOB-US05 – Gestión de perfil del paciente

Feature: Gestión de perfil del paciente en app móvil
  As a paciente
  I want to gestionar y actualizar mi perfil personal
  So that mantengo mis datos actualizados

  Scenario: Actualización de perfil móvil exitosa
    Given que el paciente accede a su sección de perfil
    When actualiza datos válidos (por ejemplo nombre, edad, altura)
    Then el sistema guarda los cambios correctamente y los muestra actualizados

  Scenario: Actualización con datos inválidos
    Given que el paciente ingresa información con formato no válido
    When intenta guardar los cambios en su perfil
    Then el sistema muestra un error de validación indicando los campos con problemas

  Scenario: Cancelación de edición de perfil
    Given que el paciente modifica datos en su perfil
    When cancela la acción sin guardar
    Then el sistema descarta los cambios y mantiene la información anterior

```

```gherkin

US: TUS-01 – Registro seguro de usuario (API)

Feature: Endpoint de registro seguro de usuario
  As a Developer
  I want to exponer un endpoint para registrar usuarios con validaciones seguras
  So that aseguro el alta confiable de cuentas nuevas

  Scenario: Registro API exitoso
    Given que se envía un POST a "/users" con datos de usuario válidos
    When el sistema valida la información y crea el usuario
    Then devuelve respuesta 201 Created con el ID del usuario creado

  Scenario: Registro API con datos inválidos
    Given que se envía un POST a "/users" con campos vacíos o inválidos
    When el sistema procesa la solicitud
    Then devuelve 400 Bad Request con un objeto de error que describe los problemas

  Scenario: Registro API con usuario duplicado
    Given que ya existe un usuario con el mismo correo en el sistema
    When se intenta registrar nuevamente con ese correo
    Then el endpoint devuelve 409 Conflict indicando que el usuario ya existe

```

```gherkin

US: TUS-02 – Inicio de sesión de usuario (API)

Feature: Endpoint de inicio de sesión con JWT
  As a Developer
  I want to disponer de un endpoint de login con autenticación JWT
  So that permito acceso seguro a los usuarios registrados

  Scenario: Login API exitoso
    Given que se envía un POST a "/auth/login" con credenciales válidas
    When el sistema autentica al usuario correctamente
    Then devuelve 200 OK con un token JWT válido en la respuesta

  Scenario: Login API con credenciales inválidas
    Given que se envía un POST a "/auth/login" con contraseña incorrecta
    When el sistema valida las credenciales
    Then devuelve 401 Unauthorized sin token

  Scenario: Login API con usuario inactivo
    Given que el usuario fue desactivado en el sistema
    When intenta iniciar sesión mediante "/auth/login"
    Then el endpoint devuelve 403 Forbidden

```

```gherkin

US: TUS-03 – Cierre de sesión seguro (API)

Feature: Endpoint de cierre de sesión seguro
  As a Developer
  I want to contar con un endpoint para cerrar sesión invalidando el token
  So that protejo el acceso posterior del usuario

  Scenario: Logout API exitoso
    Given que se envía un POST a "/auth/logout" con un token válido
    When el sistema invalida el token de acceso
    Then devuelve 200 OK confirmando el cierre de sesión

  Scenario: Logout API con token inválido
    Given que se envía un POST a "/auth/logout" con un token manipulado o incorrecto
    When el sistema procesa la solicitud
    Then devuelve 401 Unauthorized

  Scenario: Logout API con token expirado
    Given que el token de acceso ya caducó
    When se envía la solicitud de logout al endpoint
    Then el sistema devuelve 400 Bad Request indicando que la sesión ya expiró

```

```gherkin

US: TUS-04 – Recuperación de contraseña olvidada (API)

Feature: Endpoint de recuperación de contraseña
  As a Developer
  I want to ofrecer un endpoint de recuperación de contraseña
  So that el usuario pueda restablecer su acceso

  Scenario: Solicitud de recuperación válida
    Given que se envía un POST a "/auth/recover" con un correo registrado
    When el sistema valida la existencia del usuario
    Then envía un enlace temporal de restablecimiento y devuelve 200 OK

  Scenario: Recuperación con correo no registrado
    Given que se envía un POST a "/auth/recover" con un correo inexistente
    When el sistema procesa la solicitud
    Then devuelve 404 Not Found

  Scenario: Uso de token de recuperación expirado
    Given que el usuario intenta usar un enlace de recuperación caducado
    When el sistema valida el token asociado
    Then devuelve 410 Gone y permite solicitar un nuevo enlace

```

```gherkin

US: TUS-05 – Actualización de perfil de usuario (API)

Feature: Endpoint de actualización de perfil de usuario
  As a Developer
  I want to disponer de un endpoint para actualizar información de perfil
  So that mantengo los datos de usuario correctos

  Scenario: Actualización de perfil API exitosa
    Given que se envía un PUT a "/users/{id}" con datos válidos y un token válido
    When el sistema actualiza la información del usuario
    Then devuelve 200 OK con los datos actualizados en el cuerpo de la respuesta

  Scenario: Actualización de perfil con datos inválidos
    Given que se envía un PUT a "/users/{id}" con información en formato incorrecto
    When el sistema valida los datos
    Then devuelve 400 Bad Request con detalles del error

  Scenario: Actualización de perfil sin autenticación
    Given que no se incluye un token válido en la solicitud a "/users/{id}"
    When se intenta actualizar la información del usuario
    Then el sistema devuelve 401 Unauthorized

```

#### Execution Evidence for Sprint Review  

En esta sección se presentan las evidencias de ejecución correspondientes al Sprint, mostrando el sistema funcionando en su entorno real. Se incluyen capturas del despliegue de la landing page, la aplicación web y los servicios de backend, junto con una vista de la aplicación móvil en operación. Estas imágenes permiten validar visualmente las funcionalidades implementadas, confirmando la correcta navegación, interacción y disponibilidad de los módulos desarrollados durante este Sprint.

::: norm
*API*
:::

![Recurso extraído de Github](src/img/cap7/exe-2.jpeg)

::: norm
*Mobile Application*
:::

![Recurso extraído de Github](src/img/cap7/exe-4.jpeg)

::: norm
*Web Application*
:::

![Recurso extraído de Github](src/img/cap7/exe-3.jpeg)

::: norm
*Landing Page*
:::

![Recurso extraído de Github](src/img/cap7/exe-1.jpeg)

#### Services Documentation Evidence for Sprint Review  

Durante este Sprint se avanzó en la documentación formal de los Web Services de Foodlytics mediante el contrato OpenAPI expuesto en Swagger UI. Esta documentación permite validar que los endpoints desarrollados cumplen con los criterios funcionales establecidos y que cada ruta incluye su verbo HTTP, parámetros de entrada, esquema de request, estructura de response y códigos de estado. Como parte de la evidencia, se registran los endpoints documentados en este Sprint, junto con la interacción visual en Swagger utilizando datos de prueba. También se incluyen los enlaces al despliegue de la documentación y los commits asociados a la actualización del contrato OpenAPI.

::: warn
Para acceder al repositorio, haga click a la [URL](https://github.com/GMB-Labs/foodlytics-api)
:::

::: warn
Para acceder al despliegue del *API*, haga click a la [URL](https://foodlytics-api-production.up.railway.app/docs#/)
:::


![Recurso extraído de Swagger](src/img/cap7/api-1.jpeg)

![Recurso extraído de Swagger](src/img/cap7/api-2.jpeg)

![Recurso extraído de Swagger](src/img/cap7/api-3.jpeg)


#### Software Deployment Evidence for Sprint Review 

El equipo registró la evidencia de despliegue correspondiente al Sprint, mostrando los entornos configurados y las versiones publicadas de cada componente. A continuación se presentan los enlaces directos a los despliegues realizados durante el Sprint.

::: warn
Para acceder al despliegue del *API*, haga click a la [URL](https://foodlytics-api-production.up.railway.app/docs#/)
:::

::: warn
Para acceder al despliegue de la *Web Application*, haga click a la [URL](https://foodlytics.onrender.com)
:::

::: warn
Para acceder al despliegue del *LandinPage*, haga click a la [URL](https://foodlytics-eight.vercel.app/pacientes#hero)
:::

#### Team Collaboration Insights during Sprint  

Durante este Sprint el equipo trabajó de forma coordinada en los distintos componentes del proyecto, distribuyendo tareas según las responsabilidades definidas y manteniendo un flujo constante de colaboración. Cada integrante participó en la implementación de la landing page, los servicios de backend y las aplicaciones web y móvil, contribuyendo con commits, revisiones y mejoras continuas. En esta sección se presentan las capturas de los analíticos de GitHub, junto con la evidencia de actividad en los repositorios, lo que permite validar la participación efectiva de todos los miembros y la integración del trabajo realizado durante el Sprint.

::: norm
*API*
:::

![Recurso extraído de Github](src/img/cap7/git-api-1.jpeg)

![Recurso extraído de Github](src/img/cap7/git-api-2.jpeg)


![Recurso extraído de Github](src/img/cap7/git-api-3.jpeg)


::: norm
*Mobile Application*
:::

![Recurso extraído de Github](src/img/cap7/git-mob-1.jpeg)

![Recurso extraído de Github](src/img/cap7/git-mob-2.jpeg)

![Recurso extraído de Github](src/img/cap7/git-mob-3.jpeg)


::: norm
*Web Application*
:::

![Recurso extraído de Github](src/img/cap7/git-web-1.jpeg)

![Recurso extraído de Github](src/img/cap7/git-web-2.jpeg)


![Recurso extraído de Github](src/img/cap7/git-web-3.jpeg)


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