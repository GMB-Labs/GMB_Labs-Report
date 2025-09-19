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

# Capítulo II: Requirements Elicitation & Analysis  

## Competidores

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### Análisis competitivo  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### Estrategias y tácticas frente a competidores  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

## Entrevistas  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### Diseño de entrevistas  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### Registro de entrevistas 

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.


### Análisis de entrevistas

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

## Needfinding

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.


### User Personas

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.


### User Task Matrix

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### Empathy Mapping  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

### As-is Scenario Mapping

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.  

### Ubiquitous Language

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.