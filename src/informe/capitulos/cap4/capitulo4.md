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

#### Primary Functionality (Primary User Stories)  

#### Quality attribute Scenarios 

#### Constraints. 6/40 V1.0  

### Architectural Drivers Backlog 

### Architectural Design Decisions 

### Quality Attribute Scenario Refinements  

## Strategic-Level Domain-Driven Design  

### EventStorming

### Candidate Context Discovery 

### Domain Message Flows Modeling

### Bounded Context Canvases 

### Context Mapping 

## Software Architecture 

### Software Architecture System Landscape Diagram

### Software Architecture Context Level Diagrams  

### Software Architecture Container Level Diagrams  

### Software Architecture Deployment Diagrams