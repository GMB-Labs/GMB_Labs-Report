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
\textbf{Tópico} & \ textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
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

- **Filtros y herramientas de búsqueda en la Web App**

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
Indicador de progreso & Muestra pacientes con progreso superior o inferior a un umbral definido (ej. +10% o –5%). \\
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


- **App móvil – Pacientes**

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



- **App móvil – Pacientes**

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
Retroalimentación visual & Íconos activos cambian de color al seleccionarse (verde menta #2FCBAC). Se incluyen notificaciones visibles en el ícono de “Perfil” para alertas de progreso o recordatorios. \\
\hline
Navegación simplificada & El diseño prioriza la experiencia rápida y directa. Solo se muestran funciones esenciales: registrar, visualizar y revisar métricas. \\
\hline
Gestos táctiles & Permite desplazamiento lateral entre secciones y cierre de formularios mediante “swipe down”. \\
\hline
\end{longtable}


- **Aplicación Web – Nutricionistas**

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



- **Landing Page – Público general**

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
Scroll guiado (anclajes) & Permite desplazarse entre secciones mediante anclas internas (“#pacientes”, “#nutricionistas”, etc.). \\
\hline
Botones de llamada a la acción (CTA) & Elementos de navegación destacados en color de marca (#2FCBAC), ubicados en secciones clave. Ejemplo: “Probar ahora” o “Ver demo”. \\
\hline
Navegación jerárquica visual & Los encabezados (H1–H3) organizan el contenido según su relevancia informativa. \\
\hline
Footer navegable & Contiene accesos secundarios a políticas de privacidad, contacto y redes sociales oficiales de Foodlytics. \\
\hline
\end{longtable}


La arquitectura de navegación de integra una experiencia consistente entre plataformas. Mientras la versión móvil prioriza la inmediatez, fluidez y accesibilidad táctil, la versión web enfatiza control, gestión de datos y análisis avanzado.
Ambos entornos comparten un mismo lenguaje visual y estructura cognitiva, asegurando una experiencia coherente y predecible para todos los usuarios.

\newpage



## Landing Page UI Design  

### Landing Page Wireframe 

### Landing Page Mock-up  


## Applications UX/UI Design  

### Applications Wireframes  

### Applications Wireflow Diagrams  




### Applications Mock-ups  

este no va 

### Applications User Flow Diagrams  

este no va 

## Applications Prototyping  

este no va 
