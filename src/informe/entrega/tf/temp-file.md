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
  tf & 01/12/2025 & Vilchez Rios, Mateo Alejandro & Elaboré Sprint Planning 2, Sprint Backlog 2 y el apartado de Lenguaje Ubicuo en el DDD estratégico. Contribuí en la redacción de contenidos clave para Solution Implementation y contribuí en Testing Suite y Execution Evidence. \\
  \hline
  tf & 01/12/2025 & Zavala Quedena, Gonzalo Andre & Participé en Team Collaboration Insights y en la grabación del Video About the Team. \\
  \hline
  tf & 01/12/2025 & Poma Espinoza, Gustavo & Participé en Team Collaboration Insights y en el Video About the Team. \\
  \hline
  tf & 01/12/2025 & Del Castillo Bueno, Daniel Mateo & Aporté en Development Evidence, Testing Suite, Execution Evidence, Services Documentation y Software Deployment. Participé en Team Collaboration Insights y en el Video About the Team. \\
  \hline
  tf & 01/12/2025 & Ramos Rios, Belén del Rocio & Redacté la sección completa de Validation Interviews que incluye Diseño de Entrevistas, Registro de Entrevistas y Evaluaciones según heurísticas. Participé en Development Evidence, Execution Evidence y el Video About the Team. \\
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


**Entregable TF:**

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/GMB-Labs/GMB_Labs-Report/pulse)
:::


**Tablero Kanban:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/1)](src/img/cap1/insights-kanban-todo.png){ width=85% }

**Kanban List:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/orgs/GMB-Labs/projects/1/views/2)](src/img/cap1/insights-kanban-list.png){ width=85% }

\newpage

**Traffic Map - Mobile App:**

![Organización GMB Labs, imagen extraída de Github[URL](https://github.com/GMB-Labs/Foodlytics-Mobile-Application/graphs/traffic)](src/img/cap1/mobileTF.png){ width=85% }

**Traffic Map - Web App:**

![Organización GMB Labs, imagen extraída de Github [URL](https://github.com/GMB-Labs/Foodlytics-Web-Application/graphs/traffic)](src/img/cap1/webTF.png){ width=85% }

**Traffic Map - Backend App:**

![Organización GMB Labs, imagen extraída de Github[URL](https://github.com/GMB-Labs/foodlytics-api/graphs/traffic) ](src/img/cap1/backTF.png){ width=85% }

***Student Outcome***

El curso contribuye al cumplimiento del ***Student Outcome ABET:*** *ABET-EAC - Student Outcome 3*

* **Criterio:** *Capacidad de comunicarse efectivamente con un rango de audiencias. En el siguiente cuadro se describe las acciones realizadas y enunciados de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro del ABET – EAC - Student Outcome 3.*.

En el siguiente cuadro se describe las acciones realizadas y enunciadas de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro de ***ABET - EAC - Student Outcome 3.***

\newpage

**TB1**

\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead

\parbox[t]{4cm}{
\textit{Comunica oralmente sus ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco del desarrollo de un proyecto en ingeniería.}
}
&
\parbox[t]{6cm}{
\textbf{TB1:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Presenté los resultados del análisis de mercado y la propuesta de valor.\\
\textbf{Poma Espinoza, Gustavo}\\
Expliqué hallazgos de investigación y su impacto en requisitos y arquitectura.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Exposé decisiones técnicas y de diseño.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Presenté avances y alcances de la propuesta.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Coordiné la presentación global del proyecto.
}
&
\parbox[t]{5cm}{
\textbf{TB1:}\\
La comunicación oral permitió validar la propuesta con diferentes públicos, reduciendo ambigüedades y facilitando retroalimentación útil.
}
\\
\hline

\parbox[t]{4cm}{
\textit{Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco del desarrollo de un proyecto en ingeniería.}
}
&
\parbox[t]{6cm}{
\textbf{TB1:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Redacté análisis de mercado y ventajas competitivas.\\
\textbf{Poma Espinoza, Gustavo}\\
Documenté hallazgos de entrevistas y su interpretación.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Justifiqué criterios técnicos y de diseño.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Describí la propuesta y sus objetivos.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Integré el documento en LaTeX con uniformidad.
}
&
\parbox[t]{5cm}{
\textbf{TB1:}\\
La documentación escrita consolidó resultados con claridad, permitiendo evaluaciones desde perfiles académicos y técnicos.
}
\\
\hline
\end{longtable}

\newpage

**TP**
\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead

\parbox[t]{4cm}{
\textit{Comunica oralmente sus ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos.}
}
&
\parbox[t]{6cm}{
\textbf{TP:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Expuse el \textit{Tactical Level Software Design} del módulo de pagos.\\
\textbf{Poma Espinoza, Gustavo}\\
Presenté flujos y contratos del diseño táctico del IAM.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Comuniqué riesgos y decisiones técnicas del diseño táctico.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Exposé criterios y pantallas del \textit{Solution UX Design}.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Aseguré coherencia narrativa en la exposición del grupo.
}
&
\parbox[t]{5cm}{
\textbf{TP:}\\
Las exposiciones del diseño táctico y UX facilitaron la comprensión para perfiles técnicos y no técnicos.
}
\\
\hline

\parbox[t]{4cm}{
\textit{Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos.}
}
&
\parbox[t]{6cm}{
\textbf{TP:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Documenté el diseño táctico.\\
\textbf{Poma Espinoza, Gustavo}\\
Redacté contratos y flujos con trazabilidad.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Documenté riesgos y decisiones técnicas.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Estandaricé criterios del \textit{Solution UX Design}.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Unifiqué estilo y claridad del diseño UX.
}
&
\parbox[t]{5cm}{
\textbf{TP:}\\
Los documentos escritos aseguraron claridad técnica y trazabilidad durante el diseño táctico y UX.
}
\\
\hline
\end{longtable}

\newpage

**TB2**
\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead

\parbox[t]{4cm}{
\textit{Comunica oralmente ideas y resultados con objetividad a público de diferentes especialidades y niveles jerárquicos.}
}
&
\parbox[t]{6cm}{
\textbf{TB2:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Presenté avances de \textit{Product Implementation} y validación.\\
\textbf{Poma Espinoza, Gustavo}\\
Expliqué resultados de implementación y despliegue.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Mostré decisiones finales de integración técnica.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Expuse el diseño y prototipado de aplicaciones.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Presenté prototipos y flujos UX.
}
&
\parbox[t]{5cm}{
\textbf{TB2:}\\
La comunicación oral permitió presentar el estado del producto e integrar observaciones de diseño e implementación.
}
\\
\hline

\parbox[t]{4cm}{
\textit{Comunica en forma escrita ideas y/o resultados con objetividad a diferentes perfiles.}
}
&
\parbox[t]{6cm}{
\textbf{TB2:}\\
\textbf{Zavala Quedena, Gonzalo Andre}\\
Redacté documentación de implementación y despliegue.\\
\textbf{Poma Espinoza, Gustavo}\\
Documenté validación e integración técnica.\\
\textbf{Del Castillo Bueno, Daniel Mateo}\\
Escribí evidencias de integración y despliegue.\\
\textbf{Ramos Ríos, Belén del Rocío}\\
Documenté diseño, prototipos y validación.\\
\textbf{Vilchez Ríos, Mateo Alejandro}\\
Redacté apartados de UX/UI y prototipos.
}
&
\parbox[t]{5cm}{
\textbf{TB2:}\\
Los documentos escritos mostraron precisión técnica y claridad en el avance del producto.
}
\\
\hline
\end{longtable}


**TF**

\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} &
\multicolumn{1}{c|}{\textbf{Acciones Realizadas}} &
\multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead

\parbox[t]{4cm}{
\textit{Comunica oralmente ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco de un sprint final y etapa de validación.}
}
&
\parbox[t]{6cm}{
\textbf{TF:} \\
\textbf{Zavala Quedena, Gonzalo Andre} \\
Presenté evidencias de desarrollo, Testing Suite, ejecución de servicios y despliegue. Participé en la exposición del Video About the Team. \\

\textbf{Poma Espinoza, Gustavo} \\
Expliqué resultados de implementación técnica y Contribuí en el Video About the Team. \\

\textbf{Del Castillo Bueno, Daniel Mateo} \\
Comuniqué decisiones de integración técnica, evidencias de ejecución y criterios aplicados para asegurar consistencia entre arquitectura y despliegue. Participé en la exposición del video del equipo. \\

\textbf{Ramos Ríos, Belén del Rocío} \\
Presenté el proceso completo de Validation Interviews, explicando diseño, registro y evaluación heurística. Expuse los hallazgos UX más relevantes. Participé en el Video About the Team. \\

\textbf{Vilchez Ríos, Mateo Alejandro} \\
Exposé Sprint Planning 2, Sprint Backlog 2 y la organización general de Solution Implementation. Expliqué cómo se gestionaron los entregables del sprint final. \\
}
&
\parbox[t]{5cm}{
\textbf{TF:} \\
Como grupo concluimos que la comunicación oral permitió cerrar el proyecto mostrando un entendimiento común del producto final, su arquitectura y su experiencia de usuario. Las presentaciones integraron aspectos técnicos, funcionales y de validación, fortaleciendo la coherencia general del entregable y permitiendo demostrar el funcionamiento del sistema ante diferentes perfiles.
}
\\
\hline


\parbox[t]{4cm}{
\textit{Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerárquicos, en el marco de un proyecto de ingeniería.}
}
&
\parbox[t]{6cm}{
\textbf{TF:} \\
\textbf{Zavala Quedena, Gonzalo Andre} \\
Documenté Development Evidence, Testing Suite, Execution Evidence, Services Documentation y Software Deployment. Estructuré evidencia técnica del sprint final. \\

\textbf{Poma Espinoza, Gustavo} \\
Redacté integración técnica, pruebas y evidencias de despliegue. Ordené resultados de funcionamiento del backend con claridad y trazabilidad. \\

\textbf{Del Castillo Bueno, Daniel Mateo} \\
Elaboré documentación técnica sobre servicios, pruebas de ejecución y funcionamiento final, explicando decisiones técnicas del sprint. \\

\textbf{Ramos Ríos, Belén del Rocío} \\
Redacté la sección completa de Validation Interviews, incluyendo diseño, registro y evaluación según heurísticas. Integré evidencia creciente en Solution Implementation. \\

\textbf{Vilchez Ríos, Mateo Alejandro} \\
Redacté Sprint Planning 2, Sprint Backlog 2, el Lenguaje Ubicuo y apartados clave de Solution Implementation. Ordené la estructura del documento del TF. \\
}
&
\parbox[t]{5cm}{
\textbf{TF:} \\
Concluimos que la documentación escrita permitió consolidar de forma precisa y ordenada los entregables del sprint final. Las secciones reflejan claridad técnica, trazabilidad de decisiones y una comunicación efectiva para audiencias con distintos niveles de conocimiento. El documento final evidencia la madurez del producto y el rigor aplicado en su desarrollo.
}
\\
\hline

\end{longtable}

# Capítulo VII: Product Implementation, Validation & Deployment  

## Software Configuration Management  
### Software Development Environment Configuration  
### Source Code Management  
### Source Code Style Guide & Conventions  
### Software Deployment Configuration  

## Solution Implementation  
### Sprint 2
#### Sprint Planning 2 
#### Sprint Backlog 2
#### Development Evidence for Sprint Review  
#### Testing Suite Evidence for Sprint Review  
#### Execution Evidence for Sprint Review  
#### Services Documentation Evidence for Sprint Review  
#### Software Deployment Evidence for Sprint Review  
#### Team Collaboration Insights during Sprint  

## Validation Interviews  
### Diseño de Entrevistas  
### Registro de Entrevistas  
### Evaluaciones según heurísticas  
