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

## Solution Implementation  
### Sprint n 
#### Sprint Planning n  
#### Sprint Backlog n  
#### Development Evidence for Sprint Review  
#### Testing Suite Evidence for Sprint Review  
#### Execution Evidence for Sprint Review  
#### Services Documentation Evidence for Sprint Review  
#### Software Deployment Evidence for Sprint Review  
#### Team Collaboration Insights during Sprint  

## Validation Interviews  

este no va 

### Diseño de Entrevistas 

este no va 

### Registro de Entrevistas  

este no va 

### Evaluaciones según heurísticas 

este no va 

## Video About-the-Product  

este no va 
