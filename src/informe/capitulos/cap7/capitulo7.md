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

\newpage

### Sprint 2

El Sprint 2 representó la fase final del desarrollo de Foodlytics y estuvo enfocado en completar, integrar y validar todos los módulos del sistema tanto a nivel técnico como documental. En esta iteración se culminaron los últimos capítulos del informe, se perfeccionó la arquitectura definida en el Sprint 1 y se finalizaron los componentes restantes de la aplicación: backend, web app, mobile app y landing page. Todo esto permitió consolidar una versión funcional, coherente y alineada con los objetivos del proyecto.

Durante este sprint se implementaron las funcionalidades críticas, se integraron los servicios expuestos por la API, se documentaron los endpoints con OpenAPI, y se realizaron pruebas de funcionamiento, navegación y despliegue. Asimismo, se ajustaron los flujos del sistema, se mejoró la experiencia de usuario y se completó la documentación técnica y académica requerida para el entregable final.

El equipo trabajó de forma continua y coordinada, afinando detalles, resolviendo dependencias entre módulos y asegurando que cada componente estuviera correctamente acoplado. Gracias a la organización, el uso de repositorios independientes y la definición clara de responsabilidades, el Sprint 2 permitió entregar un producto completo y estable. Esta iteración marcó el cierre del proyecto con una solución implementada, documentada y lista para ser presentada.

\newpage

#### Sprint Planning 2  

\begin{tabularx}{\textwidth}{p{5cm}X}
\caption{Sprint Planning – Sprint 2}\label{tab:sprint2-planning}\\
\toprule
\textbf{Sprint Planning Background} & \\ 
\midrule

\textbf{Sprint} & Sprint 2 \\
\textbf{Date} & 02/12/2025 \\
\textbf{Time} & 21:00 \\
\textbf{Location} & Discord Virtual Meeting \\
\textbf{Prepared By} & Ramos Rios, Belen del Rocio \\
\textbf{Attendees (to planning meeting)} & Del Castillo Bueno, Daniel Mateo; Poma Espinoza, Gustavo; Vilchez Rios, Mateo Alejandro; Zavala Quedena, Gonzalo Andre \\
\textbf{Sprint 2 Review Summary} & Culminación de la documentación restante, integración completa del backend, web y mobile app, y finalización de la landing page. Se consolidó una versión funcional del sistema \\
\textbf{Sprint 2 Retrospective Summary} & El equipo trabajó de forma ordenada y coordinada. Se completaron las tareas críticas, se integraron todos los módulos y se resolvieron dependencias sin retrasos \\
\textbf{Sprint Goal \& User Stories} & Completar la implementación total del sistema, integrar los módulos, documentar los servicios y cerrar los entregables finales \\
\textbf{Sprint 2 Velocity} & 1 Sprint cada semana \\
\textbf{Sum of Story Points} & 145 \\
\bottomrule
\end{tabularx}

\newpage

#### Sprint Backlog 2 

\begin{tabularx}{\textwidth}{|c|p{1.4cm}|p{3.8cm}|X|c|}
\hline
\# Orden & \textbf{ID} & \textbf{Título} & \textbf{Descripción} & \textbf{Story Points} \\
\hline
1  & \textbf{WEB-US06} & Gestión de perfil & Como nutricionista, quiero gestionar mi perfil, para mantener actualizada mi información. & 3 \\
\hline
2  & \textbf{WEB-US07} & Registro de pacientes nuevos & Como nutricionista, quiero registrar pacientes, para darles seguimiento. & 5 \\
\hline
3  & \textbf{WEB-US08} & Edición de pacientes & Como nutricionista, quiero editar la información de pacientes, para mantener sus datos al día. & 3 \\
\hline
4  & \textbf{WEB-US09} & Eliminación de pacientes & Como nutricionista, quiero eliminar o desactivar pacientes, para mantener una lista limpia. & 3 \\
\hline
5  & \textbf{WEB-US10} & Búsqueda de pacientes & Como nutricionista, quiero buscar pacientes, para localizarlos rápidamente. & 3 \\
\hline
6  & \textbf{WEB-US11} & Visualizar alimentos diarios & Como nutricionista, quiero ver alimentos consumidos, para analizar su dieta. & 3 \\
\hline
7  & \textbf{WEB-US12} & Visualización de macros & Como nutricionista, quiero ver macros y calorías, para evaluar la dieta. & 3 \\
\hline
8  & \textbf{WEB-US13} & Historial diario y semanal & Como nutricionista, quiero ver historial de calorías, para evaluar progresos semanales. & 5 \\
\hline
9  & \textbf{WEB-US14} & Rutinas de ejercicio & Como nutricionista, quiero visualizar rutinas, para complementar la dieta. & 3 \\
\hline
10 & \textbf{WEB-US15} & Calorías gastadas & Como nutricionista, quiero ver calorías gastadas, para analizar balance energético. & 3 \\
\hline
11 & \textbf{WEB-US16} & Crear rutinas & Como nutricionista, quiero crear rutinas, para personalizar el plan del paciente. & 5 \\
\hline
12 & \textbf{WEB-US17} & Asignar metas & Como nutricionista, quiero asignar metas de calorías y macros, para dar objetivos personalizados. & 3 \\
\hline
13 & \textbf{WEB-US18} & Recomendaciones & Como nutricionista, quiero registrar recomendaciones, para guiar al paciente. & 2 \\
\hline
14 & \textbf{WEB-US19} & Reporte de evolución de peso & Como nutricionista, quiero generar reportes de peso, para evaluar cambios en el tiempo. & 3 \\
\hline
15 & \textbf{WEB-US20} & Dashboard de progreso & Como nutricionista, quiero ver gráficas de progreso, para analizar evolución de pacientes. & 5 \\
\hline
16 & \textbf{WEB-US21} & Reportes descargables & Como nutricionista, quiero descargar reportes, para compartir con pacientes. & 3 \\
\hline
17 & \textbf{MOB-US04} & Recuperación de contraseña & Como paciente, quiero recuperar mi contraseña, para acceder en caso de olvido. & 3 \\
\hline
18 & \textbf{MOB-US05} & Gestión de perfil & Como paciente, quiero gestionar mi perfil, para mantener mis datos correctos. & 3 \\
\hline
19 & \textbf{MOB-US06} & Resumen diario inicial & Como paciente, quiero ver un resumen de calorías y macros, para controlar mi día. & 3 \\
\hline
20 & \textbf{MOB-US08} & Historial diario/semanal & Como paciente, quiero ver mi historial diario y semanal, para analizar mi progreso. & 5 \\
\hline
21 & \textbf{MOB-US12} & Registro de actividad manual & Como paciente, quiero registrar actividades manualmente, para reflejar mi esfuerzo. & 3 \\
\hline
22 & \textbf{MOB-US13} & Balance diario & Como paciente, quiero ver el balance entre calorías consumidas y gastadas, para controlar mi salud. & 3 \\
\hline
23 & \textbf{MOB-US14} & Registro de pasos & Como paciente, quiero registrar mis pasos, para estimar calorías quemadas. & 3 \\
\hline
24 & \textbf{MOB-US15} & Registro y gráfico de peso & Como paciente, quiero registrar mi peso y ver gráficos, para analizar mi evolución. & 3 \\
\hline
25 & \textbf{MOB-US16} & Ajuste de metas & Como paciente, quiero ajustar mis metas, para mantenerme en el plan. & 3 \\
\hline
26 & \textbf{MOB-US17} & Visualización semanal & Como paciente, quiero visualizar mis resultados semanales, para revisar mi cumplimiento. & 3 \\
\hline
27 & \textbf{MOB-US18} & Notificaciones de comidas & Como paciente, quiero recibir notificaciones de comidas, para registrar con constancia. & 2 \\
\hline
28 & \textbf{MOB-US19} & Alertas de metas & Como paciente, quiero recibir alertas de exceso o déficit, para ajustar mi dieta. & 3 \\
\hline
29 & \textbf{MOB-US20} & Consejos personalizados & Como paciente, quiero recibir consejos personalizados, para mejorar mis hábitos. & 3 \\
\hline
30 & \textbf{TUS-36} & Registro de uso de datos & Como developer, quiero registrar uso de datos, para cumplir con auditorías y normativas. & 3 \\
\hline
31 & \textbf{TUS-37} & Indicadores de sincronización & Como developer, quiero mostrar indicadores de sincronización, para informar al usuario. & 3 \\
\hline
32 & \textbf{TUS-38} & Cola local de cambios & Como developer, quiero mantener cola local de cambios, para asegurar persistencia antes de envío. & 5 \\
\hline
33 & \textbf{TUS-39} & Cierre de jornada & Como developer, quiero implementar cierre de jornada, para definir datos a sincronizar. & 3 \\
\hline
34 & \textbf{TUS-40} & Envío en lote & Como developer, quiero enviar registros en lote, para optimizar red y recursos. & 5 \\
\hline
35 & \textbf{TUS-41} & Reintentos automáticos & Como developer, quiero reintentos con backoff, para asegurar entrega de datos. & 5 \\
\hline
36 & \textbf{TUS-42} & Idempotencia en lotes & Como developer, quiero usar claves únicas en lotes, para evitar duplicados. & 5 \\
\hline
37 & \textbf{TUS-43} & Confirmación del backend & Como developer, quiero confirmar recepción del backend, para marcar datos como enviados. & 3 \\
\hline
38 & \textbf{TUS-44} & Detección de duplicados & Como developer, quiero detectar duplicados en servidor, para mantener integridad. & 5 \\
\hline
39 & \textbf{TUS-45} & Manejo de timestamps & Como developer, quiero usar timestamps RFC 3339 con zona horaria, para asegurar consistencia. & 3 \\
\hline
40 & \textbf{TUS-46} & Reprogramación de envío & Como developer, quiero reprogramar envío fallido, para garantizar sincronización eventual. & 5 \\
\hline
41 & \textbf{TUS-47} & Estado visible & Como developer, quiero mostrar estado de sincronización, para dar transparencia al usuario. & 2 \\
\hline
42 & \textbf{TUS-48} & Hora de corte configurable & Como developer, quiero configurar hora de corte por zona, para adaptar sincronización. & 3 \\
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

US: TUS-31 – Manual AI Correction

Feature: Manual correction of AI-detected food items
  As a user
  I want to manually correct detected food items
  So that I can adjust inaccurate detections

  Scenario: Correcting a detected item
    Given the AI has detected a food item incorrectly
    When the user edits the detected food
    Then the system updates the item with the corrected information

  Scenario: Viewing AI confidence values
    Given the system displays confidence scores for detections
    When the user reviews the detected items
    Then the user can decide whether manual correction is needed

  Scenario: Persisting corrected values
    Given the user modifies a detected food item
    When the user confirms the correction
    Then the corrected values are stored and override the original detection

```

```gherkin

US: TUS-32 – Food Catalog

Feature: Food catalog and standardized portions
  As a user
  I want to access a catalog of foods and portion sizes
  So that my food registration is consistent and accurate

  Scenario: Browsing the food catalog
    Given the user opens the food catalog
    When the system loads all available foods
    Then the user sees standardized food names and portions

  Scenario: Selecting a food item
    Given the user is browsing the catalog
    When the user selects a food item
    Then the system displays its portion details and nutritional values

  Scenario: Searching the catalog
    Given the user wants to find a food item
    When the user enters a search term
    Then the system shows matching foods instantly

```

```gherkin

US: TUS-33 – Consent Management

Feature: Management of user consent
  As a user
  I want to manage consent for each data processing purpose
  So that I can control how my data is used

  Scenario: Granting consent
    Given the user is on the consent settings page
    When the user enables a consent toggle
    Then the system registers the granted consent

  Scenario: Revoking consent
    Given the user previously granted consent
    When the user disables the consent toggle
    Then the system revokes the consent and updates preferences

  Scenario: Viewing consent history
    Given the system stores consent changes
    When the user opens consent logs
    Then the user sees timestamps and actions performed

```

```gherkin

US: TUS-34 – Data Encryption

Feature: Data encryption at rest and in transit
  As a system
  I want to encrypt data
  So that user information remains protected

  Scenario: Encrypting data at rest
    Given the server stores user information
    When the data is saved
    Then the system encrypts it using the configured encryption standard

  Scenario: Encrypting data in transit
    Given a user sends a request to the server
    When the request travels through the network
    Then the communication is encrypted using HTTPS/TLS

  Scenario: Rejecting unencrypted requests
    Given an incoming request is not encrypted
    When the server receives the request
    Then the system rejects it with a security error

```

```gherkin

US: TUS-35 – Metadata Cleaning

Feature: Removal of sensitive image metadata
  As a user
  I want the app to remove metadata from images
  So that my privacy is protected

  Scenario: Cleaning metadata on upload
    Given the user uploads an image
    When the system processes the file
    Then all sensitive metadata is removed automatically

  Scenario: Verifying metadata removal
    Given the system cleans metadata
    When the user views file details
    Then no location or device information is present

  Scenario: Rejecting unsupported formats
    Given the user uploads an unsupported image type
    When the system detects incompatible metadata
    Then the upload is rejected with a proper explanation

```

```gherkin

US: TUS-36 – Data Usage Logging

Feature: Logging of data usage
  As a system
  I want to track all data access operations
  So that I can support auditing and compliance

  Scenario: Logging read operations
    Given the system retrieves user data
    When an authorized user requests the information
    Then the system logs the access with timestamp and user ID

  Scenario: Logging write operations
    Given the system updates user data
    When a data modification occurs
    Then the system records the change event

  Scenario: Viewing usage logs
    Given logs exist in the system
    When an admin requests the audit records
    Then the system displays the usage history

```

```gherkin

US: TUS-37 – Sync Indicators

Feature: Display of synchronization indicators
  As a user
  I want to see the sync status of my data
  So that I know whether my information is successfully saved

  Scenario: Showing pending sync indicator
    Given changes have not yet been sent to the server
    When the user views the UI
    Then a “pending sync” indicator is displayed

  Scenario: Showing successful sync
    Given the system has synced all data
    When the user opens the app
    Then a “synced” indicator appears

  Scenario: Showing sync failure
    Given a sync error occurred
    When the user checks the app
    Then an error indicator appears with retry options

```

```gherkin

US: TUS-38 – Local Change Queue

Feature: Local queue for offline changes
  As a user
  I want the app to queue my changes locally
  So that my data is not lost when I am offline

  Scenario: Queueing offline changes
    Given the user has no internet connection
    When the user registers food or activity
    Then the system saves the change in a local queue

  Scenario: Processing queued changes
    Given the user regains internet connection
    When the system detects connectivity
    Then queued changes are sent automatically

  Scenario: Viewing queued items
    Given the user has pending changes
    When the user opens the sync status screen
    Then the system shows all queued operations

```

```gherkin

US: TUS-39 – Daily Closing

Feature: Daily closing process
  As a system
  I want to define daily cut-off rules
  So that user data is synchronized in controlled batches

  Scenario: Triggering daily closing
    Given the cut-off time is reached
    When the system evaluates pending records
    Then all changes are marked for synchronization

  Scenario: Generating closing summary
    Given the system completes the daily closing
    When the user views the summary
    Then the system shows processed items and pending ones

  Scenario: Adjusting cut-off rules
    Given the admin wants to change the cut-off time
    When the admin updates the configuration
    Then the system applies the new rules immediately

```

```gherkin

US: TUS-40 – Batch Sending

Feature: Batch sending of records
  As a system
  I want to send data in batches
  So that network usage is optimized

  Scenario: Sending a batch
    Given the system has a batch of pending data
    When the batch is ready
    Then the server receives the entire batch in a single request

  Scenario: Handling large batches
    Given the batch size exceeds the limit
    When the system processes it
    Then the system splits the batch into smaller valid chunks

  Scenario: Confirming batch delivery
    Given the server receives a batch
    When the system gets the confirmation
    Then all items in that batch are marked as delivered

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

\newpage

## Validation Interviews  

Las entrevistas de validación constituyen una herramienta cualitativa fundamental en la evaluación temprana de productos digitales, ya que permiten recopilar información directa y contextualizada sobre la experiencia de uso desde la perspectiva de los usuarios finales. En el presente proyecto, se llevaron a cabo entrevistas semiestructuradas con individuos representativos de los segmentos objetivo de la solución *Foodlytics*, con el propósito de validar su adecuación funcional, facilidad de uso y grado de satisfacción percibida.

Estas entrevistas se diseñaron cuidadosamente para cubrir los principales puntos de contacto del sistema, incluyendo:

* La **landing page**, orientada a captar pacientes y profesionales interesados, comunicando claramente el valor nutricional y clínico de la herramienta.
* El **dashboard del nutricionista**, que centraliza el historial alimentario, la evolución de peso y los reportes nutricionales para la toma de decisiones.
* La **aplicación móvil del paciente**, enfocada en el registro de comidas mediante fotos, el cálculo de calorías y macros y la visualización del progreso diario.

Durante las sesiones, se solicitó a los participantes que ejecuten tareas específicas previamente definidas por el equipo, como registrar una comida mediante fotografía, revisar el resumen nutricional diario, explorar el panel clínico o navegar por la landing page para comprender la propuesta de valor. Al mismo tiempo, se documentaron sus reacciones espontáneas y comentarios verbales siguiendo la técnica *think aloud*, lo que permitió identificar puntos de fricción, dudas y oportunidades de mejora relacionadas con la claridad visual, la precisión de los cálculos y la interacción entre paciente y nutricionista.

::: warn
Para acceder al video de las entrevistas, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202211212_upc_edu_pe/EUSHZe96_IJCpJ01PldFNykBAJ6ZEiuDjDqJJdvSMM-YyA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=YFJYGO)
:::

![Recurso extraído de Canva](src/img/cap2/entrevistas-introduccion.png)

\newpage
### Diseño de Entrevistas 

Las entrevistas de validación fueron diseñadas considerando las necesidades, contextos de uso y tareas más importantes para cada segmento objetivo del proyecto. A cada entrevistado se le presentó un conjunto de escenarios y se le asignaron tareas concretas vinculadas con los user flows principales definidos para Foodlytics.

::: box
**Segmento Objetivo 1:** Nutricionistas y médicos del deporte
:::

**Interfaces validadas:**

* Dashboard web del especialista  
* Landing page informativa  
* Vista del historial de comidas y métricas del paciente

**Objetivo:**  
Validar si la plataforma facilita el seguimiento nutricional, si la interfaz es clara para la toma de decisiones y si la información presentada es suficiente para ajustar planes y evaluar la adherencia del paciente.

**User Flows Evaluados y Preguntas de Validación:**


1) **Landing Page**

  - **Objetivo:** Ver si la página comunica con claridad la propuesta de valor de Foodlytics para profesionales de nutrición.

  - **Preguntas:**
    - ¿La información presentada te permitió entender la solución?  
    - ¿El mensaje de valor es claro para tu práctica profesional?  
    - ¿Qué agregarías o cambiarías para que te interese adoptar esta herramienta?


2) **User Flow 1: Ingreso al sistema del especialista**

  - **Objetivo:** Confirmar que el inicio de sesión sea claro, seguro y rápido.

  - **Preguntas:**
    - ¿El proceso de inicio de sesión fue fácil y entendible?  
    - ¿La interfaz te generó confianza para ingresar tus datos?  
    - ¿Qué mejorarías para agilizar este paso?


3) **User Flow 2: Revisión del panel clínico**

  - **Objetivo:** Validar si el panel presenta datos relevantes para evaluar a un paciente en poco tiempo.

  - **Preguntas:**
    - ¿La organización del panel es clara para tu trabajo diario?  
    - ¿Puedes identificar fácilmente calorías ingeridas, distribución de macros y evolución del peso?  
    - ¿La información presentada es suficiente para ajustar un plan nutricional?  
    - ¿Qué dato adicional te sería útil ver aquí?


4) **User Flow 3: Revisión del historial de comidas**

  - **Objetivo:** Evaluar si los registros generados por la app del paciente son comprensibles y confiables.

  - **Preguntas:**
    - ¿Pudiste entender rápidamente qué comió el paciente cada día?  
    - ¿Te resulta útil ver fotos, cantidades y correcciones manuales?  
    - ¿La información es suficiente para medir adherencia?  
    - ¿Qué formato preferirías para revisar esta información?


5) **User Flow 4: Generación y revisión de reportes**

  - **Objetivo:** Comprobar si los reportes permiten evaluar progreso nutricional con facilidad.

  - **Preguntas:**
    - ¿Los reportes fueron fáciles de interpretar?  
    - ¿Son útiles para consultas presenciales o virtuales?  
    - ¿Preferirías recibir reportes automáticos por correo?  
    - ¿Hay información innecesaria o falta algún dato clave?


6) **User Flow 5: Ajuste del plan nutricional**

  - **Objetivo:** Validar la claridad del flujo para actualizar metas y recomendaciones.

  - **Preguntas:**
    - ¿El proceso para ajustar metas y recomendaciones fue claro?  
    - ¿Te parece útil que los cambios se sincronicen de inmediato con el paciente?  
    - ¿Qué nivel de personalización esperas en este módulo?  

\newpage

::: box
**Segmento Objetivo 2:** Pacientes jóvenes y adultos que buscan mejorar su alimentación
:::

**Interfaces validadas:**

* Aplicación móvil del paciente  
* Landing page  
* Vista de reportes y progreso dentro de la app

**Objetivo:**  
Validar que los pacientes puedan registrar comidas con facilidad, entender su progreso y mantener motivación mediante la aplicación móvil.

**User Flows Evaluados y Preguntas de Validación:**


1) **Landing Page**

  - **Objetivo:** Ver si la página comunica confianza e interés para usar la app.

  - **Preguntas:**
    - ¿La landing page te ayudó a entender qué hace Foodlytics?  
    - ¿Confiaste en la solución después de leerla?  
    - ¿Qué agregarías para motivarte a probar la app?


2) **User Flow 1: Registro e inicio de sesión**

  - **Objetivo:** Verificar que el registro sea simple para usuarios con distintos niveles tecnológicos.

  - **Preguntas:**
    - ¿El registro e inicio de sesión fueron fáciles de realizar?  
    - ¿Hubo pasos confusos o innecesarios?  
    - ¿Te sentiste seguro al ingresar tus datos personales?  
    - ¿Qué mejorarías en este flujo?


3) **User Flow 2: Registro de comida mediante foto**

  - **Objetivo:** Evaluar la facilidad de usar la cámara, entender resultados y corregir cantidades.

  - **Preguntas:**
    - ¿Te resultó sencillo tomar la foto y registrar tu comida?  
    - ¿La app reconoció bien el alimento?  
    - ¿El ajuste manual de cantidades fue claro?  
    - ¿Usarías esta función todos los días?


4) **User Flow 3: Visualización del resumen nutricional del día**

  - **Objetivo:** Validar si los pacientes entienden su progreso diario.

  - **Preguntas:**
    - ¿La pantalla te permitió entender cuántas calorías consumiste y cómo están distribuidos tus macros?  
    - ¿Te pareció útil ver un indicador de cumplimiento diario?  
    - ¿Agregarías alguna métrica más?  


5) **User Flow 4: Revisión del historial de comidas y evolución**

  - **Objetivo:** Confirmar si el historial es fácil de navegar y motiva al usuario.

  - **Preguntas:**
    - ¿Pudiste encontrar rápidamente tu historial de comidas?  
    - ¿Te ayuda a visualizar tu progreso semanal o mensual?  
    - ¿Qué información extra agregarías para motivarte más?  


6) **User Flow 5: Recepción de notificaciones**

  - **Objetivo:** Validar si las alertas son claras, oportunas y útiles para mantener hábitos.

  - **Preguntas:**
    - ¿Las notificaciones te parecieron útiles para recordarte registrar comidas o controlar metas?  
    - ¿Te gustaría personalizar horarios y frecuencia?  
    - ¿Hay algún tipo de alerta adicional que te gustaría recibir?


7) **User Flow 6: Consulta del perfil y metas**

  - **Objetivo:** Evaluar si el usuario entiende sus metas nutricionales y puede modificarlas.

  - **Preguntas:**
    - ¿Fue fácil encontrar tu perfil y tus metas nutricionales?  
    - ¿Entendiste cómo están calculadas las metas?  
    - ¿Qué cambiarías para que este módulo sea más claro?  

\newpage

### Registro de Entrevistas  

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

Luisa Fernanda Gutiérrez Herrera, nutricionista especializada en nutrición clínica con mención en oncología, validó la experiencia de uso a través del dashboard profesional, la aplicación móvil diseñada para pacientes y la landing page de Foodlytics. Desde el inicio comentó que uno de los problemas más frecuentes en su trabajo es la falta de registros confiables por parte de los pacientes, ya que la mayoría anota sus comidas de forma desordenada o no recuerda las cantidades consumidas. Por ello, consideró que una herramienta como Foodlytics podría cubrir una necesidad clara en el seguimiento clínico y facilitar la toma de decisiones durante las consultas.

Respecto a la landing page, mencionó que comunica de forma clara la propuesta de valor, sobre todo al mostrar funciones como el reconocimiento automático de alimentos, la sincronización con el nutricionista y el análisis de calorías y macronutrientes. Señaló que incluir casos reales o ejemplos visuales del funcionamiento del sistema podría aumentar la confianza del profesional y del paciente, especialmente en contextos clínicos en los que la precisión es importante.

Durante la revisión de la aplicación móvil del paciente, destacó que el flujo de registro mediante fotografía es una solución útil para mejorar la adherencia. Comentó que sus pacientes suelen tener dificultades para estimar cantidades, por lo que valoró que la app permita corregir la porción detectada por la IA. También sugirió que la app podría incluir recordatorios configurables, ya que muchos pacientes olvidan registrar sus comidas durante el día.

Al validar el dashboard profesional, mencionó que le resultó intuitivo y alineado con las tareas que realiza en consulta. Resaltó la importancia de visualizar rápidamente calorías ingeridas, distribución de macronutrientes, horarios de comida y tendencias semanales. Consideró que ver la información del paciente distribuida por día y semana facilita identificar patrones como saltos de comidas, excesos nocturnos o desbalances marcados en proteínas o carbohidratos. Sugirió añadir una vista de progreso clínico para los pacientes que requieren un monitoreo más estricto, como aquellos en tratamiento oncológico.

En cuanto a la sección de reportes, indicó que serían útiles para respaldar las consultas, sobre todo en centros donde se solicitan informes periódicos. Comentó que sería ideal contar con una opción para exportar los reportes en PDF con formato estándar. También mencionó que la sincronización en tiempo real entre el registro del paciente y el panel del nutricionista genera una ventaja competitiva frente a sistemas tradicionales basados en mensajes o fotografías enviadas por WhatsApp.

Finalmente, Luisa afirmó que la solución presentada responde a una necesidad real dentro de la práctica nutricional. Considera que Foodlytics reduce la improvisación en consulta, mejora la precisión del seguimiento y fortalece la comunicación entre paciente y profesional. Señaló que, de mantenerse una interfaz clara y una experiencia sencilla para el usuario, estaría dispuesta a recomendar la herramienta a sus pacientes y a integrarla como apoyo rutinario en sus consultas.


![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS11.png)

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

Gianella Rodríguez, nutricionista especializada en recomposición corporal y nutrición deportiva, evaluó la experiencia de uso del dashboard profesional, la aplicación móvil para pacientes y la landing page de Foodlytics. Desde el inicio comentó que uno de los principales problemas en su práctica diaria es que sus pacientes no registran sus comidas de forma constante o lo hacen con información incompleta, lo que dificulta analizar el progreso real. Por ello, consideró que una herramienta como Foodlytics solucionaría un vacío importante en la adherencia nutricional y en la calidad del seguimiento que puede ofrecer.

Durante la revisión de la landing page, mencionó que la propuesta de valor es clara, especialmente al explicar el reconocimiento de alimentos mediante foto y el cálculo automático de calorías y macronutrientes. Señaló que agregar ejemplos visuales de comidas reales reconocidas por el sistema y testimonios de otros profesionales aumentaría la confianza y credibilidad de la herramienta. También comentó que la estructura de la página facilita entender el funcionamiento general sin necesidad de investigar demasiado.

En la validación de la aplicación móvil del paciente, destacó que el proceso de registro mediante fotografía es su funcionalidad favorita, ya que reduce la fricción en el hábito de registrar comidas. Explicó que sus pacientes suelen comer fuera de casa y muchas veces olvidan anotar detalles, por lo que una app que detecte automáticamente el alimento y permita editar las porciones resolvería uno de los problemas más frecuentes en sus consultas. Añadió que sería útil contar con recordatorios configurables para incentivar la constancia en el registro diario.

Al revisar el dashboard profesional, señaló que la organización visual le resultó intuitiva, especialmente la vista donde se presentan calorías totales, distribución de macronutrientes y comparaciones contra las metas del plan nutricional. Comentó que esta estructura facilita analizar rápidamente patrones alimentarios, como exceso de carbohidratos o baja ingesta de proteínas en días de entrenamiento. También sugirió incluir gráficos comparativos semanales y mensuales para evaluar el progreso de forma más amplia y evitar depender de registros manuales o fotografías enviadas por WhatsApp.

Sobre la sección de reportes, indicó que le parecen útiles para respaldar consultas de seguimiento. Comentó que sería ideal que los reportes puedan descargarse o exportarse, ya que algunos pacientes requieren documentación periódica para entrenadores o preparadores físicos. Además, valoró que la sincronización en tiempo real entre la app del paciente y el dashboard haga más eficiente la consulta y permita al profesional enfocarse en recomendaciones claras basadas en datos objetivos.

Gianella concluyó que Foodlytics representa una herramienta valiosa para contextos deportivos, donde el control de calorías y macronutrientes es determinante para el rendimiento. Afirmó que la solución reduce el tiempo dedicado a reconstruir la información alimentaria del paciente y aumenta la precisión de los planes nutricionales. También mencionó que recomendaría la aplicación a sus pacientes siempre que la experiencia siga siendo simple, rápida y visualmente clara.

![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS12.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Graciela del Rocío Alza \\ \hline
\textbf{Edad}                 & 32 años \\ \hline
\textbf{Ubicación geográfica} & Trujillo, Perú \\ \hline
\textbf{Cargo}                & Licenciada en Nutrición, especialista en nutrición clínica y dietoterapia \\ \hline
\textbf{Tiempo de entrevista} & 00:00 - 11:03 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Graciela del Rocío Alza, nutricionista con experiencia en nutrición clínica y dietoterapia, evaluó el dashboard profesional, la aplicación móvil del paciente y la landing page de Foodlytics. Desde el inicio comentó que una de las dificultades más frecuentes en su trabajo es que los pacientes no registran sus comidas de manera completa ni ordenada. Explicó que esta falta de información afecta su capacidad para analizar patrones alimentarios reales, especialmente en pacientes con condiciones clínicas que requieren seguimiento estricto como diabetes, hipertensión o enfermedades gastrointestinales.

Durante la revisión de la landing page, destacó que la descripción del sistema es clara y directa, especialmente en lo que respecta al reconocimiento de alimentos y a la sincronización entre paciente y nutricionista. Mencionó que agregar ejemplos visuales del análisis nutricional o casos de uso podría ayudar a transmitir mejor el potencial clínico de la herramienta. También señaló que incluir información sobre privacidad y manejo de datos aumentaría la confianza del profesional.

Al validar la aplicación móvil, comentó que el proceso de registro mediante fotografía facilita la constancia en el seguimiento nutricional, ya que reduce el tiempo que el paciente invierte en describir lo que comió. Señaló que sus pacientes suelen tener dificultades para estimar porciones, por lo que valoró que la app permita modificar cantidades detectadas por la inteligencia artificial. Sugirió que se añadan recordatorios configurables para pacientes que deben cumplir horarios estrictos de ingesta, como los que están bajo dietoterapia.

En la evaluación del dashboard profesional, mencionó que la distribución de la información es clara y que puede identificar rápidamente calorías consumidas, macros, horarios de comida y frecuencia de registros. Comentó que la posibilidad de revisar tendencias semanales y visualizar desbalances recurrentes ayudaría a personalizar planes nutricionales con mayor precisión. También señaló que sería útil incluir una vista temporal más detallada para pacientes que deben controlar horarios, como aquellos que siguen dietas fraccionadas.

Respecto a la sección de reportes, afirmó que serían útiles para consultas presenciales y virtuales. Explicó que algunos centros donde trabaja solicitan documentación periódica, por lo que valoró la idea de descargar o exportar reportes en formatos estándar. También comentó que la sincronización automática entre la app del paciente y el panel profesional permitiría reducir el tiempo de consulta y concentrarse en intervenciones más efectivas.

Graciela concluyó que Foodlytics representa una solución de apoyo tanto para el paciente como para el nutricionista, ya que mejora la calidad del seguimiento y permite trabajar con datos más confiables. Considera que la herramienta tiene potencial clínico real, siempre que mantenga una interfaz clara, un registro rápido y opciones que se adapten a pacientes con distintas necesidades nutricionales.


![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS13.png)

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Carlos Sánchez \\ \hline
\textbf{Edad}                 & 22 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Estudiante de Ingeniería en la UPC \\ \hline
\textbf{Tiempo de entrevista} & 25:45 - 30:25 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Carlos Sánchez, joven adulto que combina estudios universitarios y trabajo a tiempo parcial, evaluó la aplicación móvil de Foodlytics, la landing page y las funciones de monitoreo nutricional. Desde el inicio comentó que ha intentado mejorar su alimentación en varias ocasiones, pero siempre abandona el registro de comidas porque le resulta tedioso anotar todo lo que consume. Explicó que suele comer fuera de casa y que esto dificulta aún más llevar un control adecuado, ya que no siempre conoce las cantidades o ingredientes exactos de sus platos.

Al revisar la landing page, mencionó que entendió con claridad la propuesta de valor del sistema, especialmente la función de reconocimiento de alimentos mediante foto. Comentó que esta característica le llamó la atención porque reduce el tiempo de registro, que para él es el principal obstáculo para mantener un hábito sostenido. Señaló que sería útil incluir ejemplos reales del antes y después del registro o una demostración breve de cómo la IA procesa la imagen, para generar más confianza en nuevos usuarios.

Durante la validación de la aplicación móvil, destacó que el flujo de registro por fotografía le resultó fácil y rápido. Afirmó que, si la herramienta realmente identifica los alimentos con precisión, sería la primera app que podría usar de manera constante, ya que no necesitaría escribir ni buscar elementos manualmente. También valoró la opción de corregir porciones, ya que muchas veces recibe platos de diferentes tamaños y le sería imposible estimarlos sin apoyo visual.

Sobre la pantalla de resumen nutricional diario, comentó que le pareció clara y motivadora. Explicó que le ayuda ver su consumo de calorías y macros de forma visual, porque así entiende rápidamente si está cumpliendo lo recomendado por su nutricionista. También mencionó que agradecería que la app muestre insights simples, como días en los que suele excederse o momentos del día donde consume más carbohidratos.

En cuanto al historial de comidas, le pareció útil para ver su progreso semanal o mensual. Dijo que usaría esta sección para entender si está mejorando sus hábitos o si está repitiendo patrones que afectan sus objetivos físicos. Consideró que sería útil incluir un indicador de constancia para motivarlo a registrar sus comidas todos los días.

Finalmente, Carlos comentó que las notificaciones discre­tas serían útiles para recordarle registrar comidas, ya que suele olvidarlo cuando está ocupado. Concluyó afirmando que Foodlytics es una solución práctica para personas con rutinas aceleradas, siempre que mantenga una experiencia rápida y simple. Indicó que estaría dispuesto a usar la app a largo plazo si el proceso de registro continúa siendo tan ágil como lo observado en la validación.

![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS21.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Elizabeth Quedina \\ \hline
\textbf{Edad}                 & 59 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Contadora \\ \hline
\textbf{Tiempo de entrevista} & 30:27 - 37:21 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Elizabeth Quedina, adulta joven que busca mejorar su alimentación por motivos de salud y bienestar personal, evaluó la aplicación móvil de Foodlytics, la landing page y las funciones de monitoreo nutricional. Comentó que en los últimos meses ha intentado seguir planes alimentarios, pero le resulta difícil mantener constancia porque suele olvidar registrar sus comidas o no sabe cómo calcular porciones. Explicó que esto la frustra y hace que pierda motivación rápidamente.

Al revisar la landing page, mencionó que la información presentada le permitió entender con claridad el objetivo de Foodlytics, especialmente la idea de registrar alimentos mediante fotografía. Señaló que esta característica le resultó atractiva porque elimina el esfuerzo de tener que escribir cada comida. Sugirió que la página incluya ejemplos de usuarios reales mostrando su progreso, ya que esto podría aumentar la confianza en la herramienta.

Durante la validación de la aplicación móvil, destacó que el proceso de registro con foto es rápido y sencillo. Comentó que la detección automática del alimento le pareció útil, aunque considera importante poder corregir cantidades, ya que muchas veces sus porciones varían y no se ajustan a medidas estándar. Afirmó que la app debería permitir un registro flexible para evitar que el usuario sienta que está obligado a seguir un formato rígido.

Respecto al resumen de calorías y macronutrientes del día, mencionó que fue una de las funciones que más le llamó la atención. Explicó que nunca ha entendido del todo cómo se distribuyen sus macros, por lo que agradece que la información se muestre con gráficos claros. Dijo que ver estos datos la ayudaría a identificar si está comiendo de forma equilibrada o si está excediéndose en ciertos alimentos.

Sobre el historial de comidas, comentó que le parece una herramienta útil para evaluar su progreso. Explicó que podría revisar semanas completas para saber si está cumpliendo sus metas o si debe modificar ciertos hábitos. Además, sugirió que la app resuma los logros semanales, como días con registro completo o mejoras en la distribución de macros, para mantener al usuario motivado.

En cuanto a las notificaciones, afirmó que le servirían para recordar registrar sus comidas, ya que suele distraerse con sus actividades diarias. Le gustaría que las alertas sean personalizables en horarios y frecuencia, para que se adapten a su rutina. También mencionó que sería útil recibir mensajes breves de motivación o consejos simples sobre alimentación saludable.

Elizabeth finalizó señalando que Foodlytics le parece una solución práctica para personas que buscan mejorar su alimentación sin complicarse con registros largos. Comentó que la aplicación podría ayudarla a ser más constante y a tener una visión más clara de lo que consume. Indicó que estaría dispuesta a usarla de forma continua si mantiene una experiencia intuitiva y un registro rápido mediante fotografía.

![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS22.png)

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

Luciana Quedina, estudiante universitaria con una rutina académica y social activa, evaluó la aplicación móvil de Foodlytics, la landing page y las funciones de seguimiento nutricional. Comentó que ha intentado mejorar su alimentación en varias ocasiones, pero suele dejar de registrar sus comidas porque le resulta complicado hacerlo de forma constante. Explicó que come en distintos lugares, desde la cafetería de la universidad hasta restaurantes con amigos, lo que dificulta calcular porciones o identificar ingredientes con precisión.

Durante la revisión de la landing page, mencionó que comprendió rápidamente el propósito de la app y consideró que la explicación del reconocimiento de alimentos mediante fotografía es clara y atractiva. Dijo que le gustaría ver ejemplos visuales del proceso de registro y del análisis nutricional para entender mejor cómo funciona la inteligencia artificial. Señaló que la propuesta de valor es directa y que esto facilita que usuarios jóvenes se sientan interesados.

Al validar la aplicación móvil, destacó que el registro por foto fue la función que más la motivó a probar la herramienta. Explicó que este método es compatible con su estilo de vida, ya que no requiere tiempo adicional ni conocimientos sobre calorías o macronutrientes. Apreciaría que la app reconozca platos comunes de la universidad o comidas rápidas que consume con frecuencia, y valoró la posibilidad de corregir manualmente las porciones detectadas.

En cuanto al resumen nutricional diario, comentó que le pareció intuitivo y fácil de interpretar. Mencionó que nunca antes había usado una herramienta que le mostrara su consumo de calorías y macros con tanta claridad. Explicó que esta información le ayudaría a detectar cuando sus comidas están desbalanceadas y le permitiría tomar decisiones más conscientes durante el día.

Respecto al historial de comidas, señaló que lo usaría para revisar semanas completas y saber si está cumpliendo sus objetivos. Indicó que sería útil incluir un indicador de progreso o constancia, ya que esto la motivaría a registrar sus comidas todos los días. También mencionó que le gustaría ver pequeños resúmenes semanales, como días en los que cumplió sus metas o mejoras en ciertos nutrientes.

Sobre las notificaciones, comentó que serían útiles para recordar registrar sus comidas entre clases y actividades. Dijo que preferiría alertas simples que no interrumpan su rutina, y que le gustaría elegir los horarios en los que prefiere recibir recordatorios. Señaló que un mensaje motivador ocasional podría ayudarla a mantener la constancia.

Luciana concluyó que Foodlytics le parece una herramienta adecuada para personas con rutinas dinámicas que necesitan un sistema rápido y visual para registrar su alimentación. Comentó que la usaría si mantiene un diseño claro, un registro ágil mediante fotografía y funciones que la ayuden a ver su progreso sin complicaciones.

![Imagen extraída del video de entrevistas](src/img/cap7/EntrevistaS23.png)

\newpage

### Evaluaciones según heurísticas 

#### *Landing Page Validation*

\begin{center}
\textbf{UX Heuristics \& Principles Evaluation} \\
\textbf{Usability – Inclusive Design – Information Architecture}
\end{center}

\vspace{10pt}

\begin{tabbing}
\hspace{5cm} \= \kill
\textbf{CARRERA:} \> Ingeniería de Software \\
\textbf{CURSO:} \> Arquitectura de Software Emergentes \\
\textbf{SECCIÓN:} \> 1ASI0728 \\
\textbf{PROFESOR:} \> Ocampo Tello, Ernesto \\
\textbf{AUDITOR:} \> CodeMinds \\
\textbf{CLIENTE(S):} \> Nutricionistas y pacientes \\
\end{tabbing}
\hrule

\vspace{10pt}

**SITE o APP A EVALUAR:** *Landing Page – Foodlytics*

\vspace{10pt}

\textbf{TAREAS A EVALUAR:}  
El alcance de esta evaluación incluye las siguientes áreas de la landing page de Foodlytics, basadas en los resultados obtenidos durante las entrevistas de validación:

\begin{enumerate}
    \item \textbf{Comunicación de la propuesta de valor}: Claridad al explicar el uso de IA, registro mediante foto y sincronización con el nutricionista.
    \item \textbf{Accesibilidad y estructura de la información}: Organización de secciones, facilidad para encontrar detalles sobre funciones y privacidad.
    \item \textbf{Llamados a la acción}: Visibilidad de botones como “Empieza ahora” o “Conoce la app”.
    \item \textbf{Confianza y credibilidad}: Presencia de testimonios, respaldo profesional y percepción de seguridad.
    \item \textbf{Compatibilidad móvil}: Accesibilidad desde celulares y comportamiento del contenido en pantallas pequeñas.
\end{enumerate}

\newpage

**ESCALA DE SEVERIDAD**

Los errores fueron puntuados tomando en cuenta la siguiente escala de severidad:

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{12cm}|}
\hline
\textbf{Nivel} & \textbf{Descripción} \\ \hline
1 & Problema superficial: ocurre poco o es fácil de superar. No requiere atención inmediata. \\ \hline
2 & Problema menor: ocurre con más frecuencia o requiere algo de esfuerzo del usuario. Prioridad baja para próximas versiones. \\ \hline
3 & Problema mayor: afecta tareas principales o genera fricción frecuente. Debe corregirse con alta prioridad. \\ \hline
4 & Problema muy grave: impide continuar con el uso de la herramienta. Debe solucionarse antes del lanzamiento. \\ \hline
\end{tabular}
\end{center}
\end{table}

\vspace{10pt}

**TABLA RESUMEN**

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{5cm}|c|p{6cm}|} \hline
\textbf{\#} & \textbf{Problema} & \textbf{Severidad} & \textbf{Heurística/Principio violado} \\ \hline
1 & Falta de ejemplos visuales del uso real del sistema & 2 & Information Architecture – Content Understanding \\ \hline
2 & CTA principal con bajo contraste en secciones extensas & 2 & Usabilidad – Visibilidad del estado del sistema \\ \hline
3 & Ausencia de elementos de confianza como testimonios o respaldo clínico & 3 & Usabilidad – Confianza y seguridad \\ \hline
4 & En móvil, el CTA no es visible en el primer pantallazo & 2 & Inclusive Design – Responsive Design \\ \hline
\end{tabular}
\end{center}
\end{table}

\newpage

**DESCRIPCIÓN DE PROBLEMAS**

- **PROBLEMA \#1: Falta de ejemplos visuales del uso real del sistema**

  **Severidad:** 2  
  **Heurística violada:** Information Architecture – Content Understanding

  **Problema:** Usuarios como nutricionistas y pacientes señalaron que la landing page explica bien la propuesta de valor, pero no muestra ejemplos visuales de cómo funciona el reconocimiento por foto ni del dashboard profesional. Esto limita la comprensión inmediata del producto.

  **Recomendación:** Incluir imágenes o animaciones breves que muestren el análisis de alimentos, el registro por foto y las métricas visuales del panel profesional.

\vspace{1cm}

- **PROBLEMA \#2: Botón principal (CTA) con bajo contraste en secciones extensas**

  **Severidad:** 2  
  **Heurística violada:** Usabilidad – Visibilidad del estado del sistema

  **Problema:** El CTA “Empieza ahora” o “Conoce la app” pierde visibilidad en zonas donde el color de fondo y el tamaño del botón no destacan lo suficiente.

  **Recomendación:** Aumentar el contraste, tamaño y jerarquía visual para dirigir la atención del usuario.

\vspace{1cm}

- **PROBLEMA \#3: Ausencia de elementos de confianza como testimonios o respaldo clínico**

  **Severidad:** 3  
  **Heurística violada:** Usabilidad – Confianza y seguridad

  **Descripción:** Nutricionistas entrevistados indicaron que sería útil ver testimonios reales o respaldos institucionales. La ausencia de estos elementos disminuye la percepción de profesionalismo y precisión clínica.

  **Recomendación:** Incluir testimonios de especialistas, insignias de privacidad, certificaciones o menciones de instituciones asociadas.

\vspace{1cm}

- **PROBLEMA \#4: En versión móvil, el CTA queda oculto en el primer pantallazo**

  **Severidad:** 2  
  **Heurística violada:** Inclusive Design – Responsive Design

  **Descripción:** El botón principal no es visible cuando se carga la página en pantalla móvil, lo que reduce la probabilidad de conversión en usuarios que no hacen scroll.

  **Recomendación:** Reubicar el CTA o fijarlo en una barra superior para garantizar accesibilidad inmediata.

\newpage

#### *Dashboard Web Validation*

\begin{center}
\textbf{UX Heuristics \& Principles Evaluation} \\
\textbf{Usability – Interaction Design – Information Architecture}
\end{center}

\vspace{10pt}

\begin{tabbing}
\hspace{5cm} \= \kill
\textbf{CARRERA:} \> Ingeniería de Software \\
\textbf{CURSO:} \> Arquitectura de Software Emergentes \\
\textbf{SECCIÓN:} \> 1ASI0728 \\
\textbf{PROFESOR:} \> Ocampo Tello, Ernesto \\
\textbf{AUDITOR:} \> CodeMinds \\
\textbf{CLIENTE(S):} \> Nutricionistas y profesionales de la salud \\
\end{tabbing}
\hrule

\vspace{10pt}

\textbf{SITE o APP A EVALUAR:} \textit{Dashboard Web – Foodlytics}

\vspace{10pt}

\textbf{TAREAS A EVALUAR:}  
El alcance de esta evaluación incluye las áreas principales del dashboard de Foodlytics utilizadas por nutricionistas, basadas en los comentarios obtenidos durante las entrevistas:

\begin{enumerate}
    \item \textbf{Visualización del estado nutricional del paciente}: Claridad de métricas, tendencia semanal, calorías y distribución de macronutrientes.
    \item \textbf{Interpretación del historial de comidas}: Comprensión de registros, precisión visual y organización cronológica.
    \item \textbf{Navegación entre secciones}: Accesibilidad, jerarquía y consistencia visual.
    \item \textbf{Acceso a reportes}: Facilidad para obtener, revisar y exportar documentos.
    \item \textbf{Sincronización con la aplicación móvil}: Claridad en la actualización de datos registrados por el paciente.
\end{enumerate}

\newpage

**ESCALA DE SEVERIDAD**

Los errores fueron evaluados según la siguiente escala:

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{12cm}|}
\hline
\textbf{Nivel} & \textbf{Descripción} \\ \hline
1 & Problema superficial: ocurre rara vez o es fácil de sortear. \\ \hline
2 & Problema menor: genera fricción leve pero no bloquea tareas. \\ \hline
3 & Problema mayor: afecta tareas clave o ocurre con frecuencia. \\ \hline
4 & Problema muy grave: impide continuar el uso del dashboard. \\ \hline
\end{tabular}
\end{center}
\end{table}

\vspace{10pt}

**TABLA RESUMEN**

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{5cm}|c|p{6cm}|} \hline
\textbf{\#} & \textbf{Problema} & \textbf{Severidad} & \textbf{Heurística/Principio violado} \\ \hline
1 & Métricas nutricionales con poco contraste en visualizaciones clave & 2 & Usabilidad – Visibilidad del estado del sistema \\ \hline
2 & Historial de comidas con carga cognitiva alta por exceso de detalles simultáneos & 3 & Information Architecture – Content Organization \\ \hline
3 & Falta de indicadores temporales claros en la línea de tiempo del paciente & 2 & Usabilidad – Reconocimiento antes que recuerdo \\ \hline
4 & Reportes no presentan opciones de exportación directa & 3 & Usabilidad – Flexibilidad y eficiencia de uso \\ \hline
5 & Menú lateral con secciones similares que pueden generar confusión & 2 & Navigation – Findability \\ \hline
\end{tabular}
\end{center}
\end{table}

\newpage

**DESCRIPCIÓN DE PROBLEMAS**

- **PROBLEMA \#1: Métricas nutricionales con poco contraste en visualizaciones clave**

  **Severidad:** 2  
  **Heurística violada:** Usabilidad – Visibilidad del estado del sistema  

  **Problema:** Algunos nutricionistas mencionaron que los colores usados para los gráficos de calorías y macronutrientes no presentan suficiente contraste, dificultando la lectura rápida.

  **Recomendación:** Ajustar colores, grosor de líneas y tipografías para asegurar legibilidad inmediata en sesiones clínicas.

\vspace{1cm}

- **PROBLEMA \#2: Historial de comidas con carga cognitiva alta**

  **Severidad:** 3  
  **Heurística violada:** Information Architecture – Content Organization  

  **Descripción:** El historial muestra simultáneamente fotos, cantidades, calorías y notas del paciente. Esto genera sobrecarga visual y hace más lenta la interpretación de datos durante la consulta.

  **Recomendación:** Agrupar información por bloques, permitir colapsar elementos y añadir un modo compacto para revisión rápida.

\vspace{1cm}

- **PROBLEMA \#3: Falta de indicadores temporales claros en la línea de tiempo**

  **Severidad:** 2  
  **Heurística violada:** Usabilidad – Reconocimiento antes que recuerdo  

  **Descripción:** La línea de tiempo del paciente presenta horarios, pero no resalta diferencias entre días, horas pico de ingesta o eventos relevantes, lo cual reduce la capacidad de identificar patrones.

  **Recomendación:** Agregar etiquetas visibles por día, destacar saltos de comidas y resaltar días con registros completos.

\vspace{1cm}

- **PROBLEMA \#4: Reportes sin exportación directa**

  **Severidad:** 3  
  **Heurística violada:** Usabilidad – Flexibilidad y eficiencia de uso  

  **Descripción:** Los profesionales indicaron que necesitan exportar reportes en PDF o enviar información al paciente o a otros especialistas. La ausencia de esta función afecta la utilidad del módulo.

  **Recomendación:** Incluir exportación a PDF, descarga en Excel y botón de compartir.

\vspace{1cm}

- **PROBLEMA \#5: Menú lateral con secciones similares**

  **Severidad:** 2  
  **Heurística violada:** Navigation – Findability  

  **Descripción:** Algunas categorías, como “Historial” y “Progreso”, presentan funciones relacionadas pero sin una distinción clara. Esto puede confundir al nutricionista al navegar rápidamente.

  **Recomendación:** Reordenar el menú, agrupar secciones, renombrar opciones y aplicar iconografía consistente para diferenciar propósitos.

\newpage

#### *Mobile App Validation*

\begin{center}
\textbf{UX Heuristics \& Principles Evaluation} \\
\textbf{Usability – Cognitive Load – Interaction Design}
\end{center}

\vspace{10pt}

\begin{tabbing}
\hspace{5cm} \= \kill
\textbf{CARRERA:} \> Ingeniería de Software \\
\textbf{CURSO:} \> Arquitectura de Software Emergentes \\
\textbf{SECCIÓN:} \> 1ASI0728 \\
\textbf{PROFESOR:} \> Ocampo Tello, Ernesto \\
\textbf{AUDITOR:} \> CodeMinds \\
\textbf{CLIENTE(S):} \> Pacientes jóvenes y adultos \\
\end{tabbing}
\hrule

\vspace{10pt}

\textbf{SITE o APP A EVALUAR:} \textit{Aplicación Móvil – Foodlytics}

\vspace{10pt}

\textbf{TAREAS A EVALUAR:}  
El alcance de esta evaluación considera las áreas más utilizadas por los pacientes dentro de la app, según las entrevistas:

\begin{enumerate}
    \item \textbf{Registro de comidas mediante fotografía}: claridad del flujo, velocidad y precisión del reconocimiento.
    \item \textbf{Corrección manual de porciones}: facilidad para editar cantidades detectadas.
    \item \textbf{Visualización del resumen diario}: comprensión de calorías, macros y cumplimiento de metas.
    \item \textbf{Historial de comidas}: navegación, carga cognitiva y motivación.
    \item \textbf{Notificaciones y recordatorios}: oportunidad, personalización y claridad.
\end{enumerate}

\newpage

**ESCALA DE SEVERIDAD**

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{12cm}|}
\hline
\textbf{Nivel} & \textbf{Descripción} \\ \hline
1 & Problema superficial: mínimo impacto en la experiencia. \\ \hline
2 & Problema menor: genera fricción leve pero no afecta tareas críticas. \\ \hline
3 & Problema mayor: afecta funciones principales o comprensión del usuario. \\ \hline
4 & Problema grave: bloquea o interrumpe el uso normal de la app. \\ \hline
\end{tabular}
\end{center}
\end{table}

\vspace{10pt}

**TABLA RESUMEN**

\begin{table}[H]
\begin{center}
\begin{tabular}{|c|p{5cm}|c|p{6cm}|} \hline
\textbf{\#} & \textbf{Problema} & \textbf{Severidad} & \textbf{Heurística/Principio violado} \\ \hline
1 & Reconocimiento de alimentos carece de retroalimentación visual clara & 2 & Usabilidad – Visibilidad del estado del sistema \\ \hline
2 & Editor de porciones poco intuitivo para usuarios sin conocimientos nutricionales & 3 & Cognitive Load – Simplicidad en tareas \\ \hline
3 & Resumen diario presenta métricas sin explicar significado para el usuario & 3 & Usabilidad – Correspondencia entre sistema y mundo real \\ \hline
4 & Historial de comidas no muestra indicadores de constancia o progreso & 2 & Motivation Design – Feedback inmediato \\ \hline
5 & Notificaciones poco personalizables según horarios del usuario & 2 & Usabilidad – Control y libertad del usuario \\ \hline
\end{tabular}
\end{center}
\end{table}

\newpage

**DESCRIPCIÓN DE PROBLEMAS**

- **PROBLEMA \#1: Falta de retroalimentación visual en el reconocimiento de alimentos**

  **Severidad:** 2  
  **Heurística violada:** Usabilidad – Visibilidad del estado del sistema

  **Problema:** Usuarios comentaron que, tras tomar una foto, la app no muestra un indicador claro de que la imagen está siendo procesada, lo que genera incertidumbre.

  **Recomendación:** Añadir animaciones breves o un estado de carga que confirme el análisis en curso.

\vspace{1cm}

- **PROBLEMA \#2: Editor de porciones poco intuitivo para usuarios sin experiencia**

  **Severidad:** 3  
  **Heurística violada:** Cognitive Load – Simplicidad en tareas

  **Descripción:** Algunos pacientes no comprendieron inmediatamente cómo ajustar cantidades detectadas por la IA. Esto afecta la precisión del registro.

  **Recomendación:** Incluir controles más simples, ejemplos visuales y descripciones cortas de porciones.

\vspace{1cm}

- **PROBLEMA \#3: Métricas del resumen diario difíciles de interpretar**

  **Severidad:** 3  
  **Heurística violada:** Usabilidad – Correspondencia entre sistema y mundo real

  **Descripción:** Conceptos como distribución de macronutrientes o metas de proteínas no fueron completamente entendidos por usuarios principiantes.

  **Recomendación:** Añadir etiquetas explicativas, glosarios breves y mensajes automáticos de interpretación.

\vspace{1cm}

- **PROBLEMA \#4: Historial sin indicadores de constancia**

  **Severidad:** 2  
  **Heurística violada:** Motivation Design – Feedback inmediato

  **Descripción:** El historial muestra comidas pasadas pero no señala días completos, hábitos o logros, lo que reduce la motivación del usuario.

  **Recomendación:** Incluir indicadores como “día completado”, rachas de registro y semanas destacadas.

\vspace{1cm}

- **PROBLEMA \#5: Notificaciones limitadas en personalización**

  **Severidad:** 2  
  **Heurística violada:** Usabilidad – Control y libertad del usuario

  **Descripción:** Los usuarios expresaron que prefieren ajustar horarios y frecuencia de recordatorios según su rutina diaria.

  **Recomendación:** Incluir un panel de preferencias donde puedan elegir horarios, frecuencia y tipo de alerta.

\newpage

### About-the-Product

Se desarrolló un video que presenta de manera clara y visual las funcionalidades principales de Foodlytics, así como los beneficios y el valor diferencial que ofrece tanto a pacientes como a nutricionistas. Este material funciona como un recurso de comunicación previo al lanzamiento oficial, ya que permite explicar de forma rápida cómo la plataforma integra el registro inteligente de comidas mediante fotografía, el análisis automático de calorías y macronutrientes y la sincronización en tiempo real entre la app móvil y el dashboard profesional.

El video muestra los flujos esenciales de uso, incluye ejemplos reales de reconocimiento de alimentos y evidencia cómo los nutricionistas pueden visualizar el progreso del paciente a través de métricas claras y reportes estructurados. También destaca la experiencia del usuario en la aplicación móvil, enfocada en la simplicidad del registro diario y la comprensión visual de objetivos y tendencias nutricionales.

Este recurso sirve como apoyo para la presentación del producto ante usuarios finales, profesionales de la salud y partes interesadas. Facilita que cada grupo entienda el propósito del software y su importancia dentro del proceso de acompañamiento nutricional.

::: warn
Para acceder al video about the product, haga click a la [URL]()
:::

![Imagen extraída del video about the product](src/img/cap7/about.png)

\newpage


## Lenguaje Ubicuo ddd estratégico

The following glossary defines the core terms of the Foodlytics business domain.  
Each term is expressed in English (ubiquitous language) followed by a Spanish definition 
for clarity and alignment across all bounded contexts.

\begin{longtable}{p{4cm}p{10cm}}
\caption{Foodlytics Ubiquitous Language Glossary}\\
\toprule
\textbf{Term} & \textbf{Definition (Spanish)} \\
\midrule
\endfirsthead
\toprule
\textbf{Term} & \textbf{Definition (Spanish)} \\
\midrule
\endhead

User & Persona que utiliza la aplicación para registrar su alimentación, visualizar análisis y recibir recomendaciones de salud. \\

Nutritionist & Profesional de salud que gestiona, supervisa y personaliza los planes nutricionales de los usuarios conectados. \\

Patient Profile & Conjunto de datos personales, biométricos y nutricionales del usuario dentro de Foodlytics. \\

Meal Log & Registro diario de alimentos consumidos por el usuario, incluyendo porciones, horario y tipo de comida. \\

Food Item & Unidad alimentaria registrada dentro del sistema, utilizada para componer un Meal Log y calcular valores nutricionales. \\

Macro Intake & Cantidad de macronutrientes consumidos por el usuario (proteína, carbohidratos y grasas). \\

Nutrition Goals & Objetivos nutricionales diarios definidos para el usuario, incluyendo calorías, macros y límites personalizados. \\

Daily Summary & Vista consolidada del progreso diario del usuario respecto a sus objetivos nutricionales. \\

Image Analyzer & Módulo de IA que procesa imágenes de comida para estimar nutrientes, porciones y calidad del plato. \\

Anemia Risk Level & Clasificación generada por modelos de visión por computadora que estima riesgo de anemia infantil. \\

Hemoglobin Estimation & Predicción del nivel probable de hemoglobina usando redes neuronales convolucionales. \\

Health Indicator & Métrica derivada (IMC, calorías, anemia risk, etc.) que resume el estado nutricional del usuario. \\

Progress Report & Informe generado automáticamente que resume evolución semanal o mensual del usuario. \\

Subscription Plan & Modelo de suscripción (Free, Basic, Premium) que determina acceso a funcionalidades específicas. \\

Mobile App & Aplicación nativa utilizada por los usuarios para registrar comidas y recibir análisis. \\

Web Dashboard & Interfaz web destinada a nutricionistas para gestionar pacientes, revisar métricas y generar reportes. \\

Nutritionist–Patient Code & Código único que permite conectar un paciente con su nutricionista dentro del ecosistema Foodlytics. \\

Connection Request & Solicitud enviada por un paciente para vincularse a un nutricionista usando el código de conexión. \\

Recommendation Engine & Motor que genera sugerencias alimentarias basadas en IA y en los objetivos del usuario. \\

Meal Classification Model & Modelo de visión por computadora encargado de identificar alimentos en imágenes. \\

Authentication Token & Token generado por Auth0 para iniciar sesión de forma segura en las aplicaciones de Foodlytics. \\

Refresh Token & Token utilizado para renovar automáticamente la sesión sin requerir nuevo login del usuario. \\

User Session & Estado de autenticación activa del usuario dentro de la aplicación. \\

API Gateway & Punto de acceso unificado para las APIs del backend, responsable del ruteo y seguridad. \\

Dietary Pattern & Patrón alimentario detectado a partir del análisis de hábitos del usuario. \\

Nutritional Alert & Notificación enviada al usuario cuando supera límites o no cumple objetivos nutricionales. \\

Foodlytics Score & Métrica compuesta que resume la consistencia alimentaria del usuario a lo largo del tiempo. \\

AI Anemia Module & Subsistema dedicado al análisis temprano de anemia mediante imágenes faciales o corporales. \\

Data Labeling Task & Proceso de etiquetar imágenes para entrenar modelos de visión por computadora. \\

Health Event & Evento relevante en el seguimiento del usuario (cambios drásticos de peso, riesgo elevado, etc.). \\

Parent User (for children) & Apoderado que registra información nutricional o imágenes de un menor para el análisis de anemia. \\

Nutritional Compliance & Porcentaje de cumplimiento diario del plan nutricional establecido. \\

Foodlytics Cloud Storage & Repositorio seguro donde se almacenan imágenes, reportes y registros de usuario. \\

\bottomrule
\end{longtable}

## ¿Cómo nos ayuda la tecnología emergente al problema planteado?

Las tecnologías emergentes permiten abordar el problema central de Foodlytics —la falta de seguimiento nutricional confiable, accesible y automatizado— mediante herramientas que reducen la carga manual, mejoran la precisión del registro alimentario y ofrecen información clínicamente relevante en tiempo real. Los avances en visión por computadora, modelos de IA para reconocimiento de alimentos, arquitecturas modernas de backend y aplicaciones móviles inteligentes hacen posible transformar un proceso tradicionalmente subjetivo en un sistema estandarizado, trazable y basado en datos.

La inteligencia artificial, especialmente mediante redes convolucionales y modelos de detección, permite identificar alimentos a partir de imágenes, estimar porciones y calcular automáticamente calorías y macronutrientes. Esto reduce errores humanos y agiliza el registro diario, un punto que limita la adherencia a los planes nutricionales. A la vez, las puntuaciones de confianza, correcciones manuales y mecanismos de auditoría fortalecen la transparencia y la mejora continua del modelo.

La arquitectura moderna del backend, diseñada con enfoques como contratos OpenAPI 3.1, paginación eficiente, versionado, métricas de observabilidad y auditoría de datos, permite que el sistema sea escalable, seguro y compatible con futuras extensiones. Tecnologías emergentes asociadas a la sincronización offline, reintentos con backoff, gestión de colas locales y envío en lote aseguran que la experiencia móvil funcione incluso en condiciones de conectividad limitada.

Por otro lado, la computación móvil y el ecosistema de sensores integrados en los dispositivos actuales (cámara, acelerómetros, contadores de pasos) permiten capturar actividad física y peso de forma automática, enriqueciendo los modelos de balance energético. Esto convierte a Foodlytics en una herramienta integral que combina nutrición, actividad y progreso físico.

Finalmente, estas tecnologías emergentes habilitan una experiencia personalizada mediante dashboards dinámicos, recomendaciones basadas en datos y análisis históricos, lo que facilita la toma de decisiones tanto para pacientes como para nutricionistas. En conjunto, la IA, el procesamiento de imágenes, los servicios web modernos y la infraestructura móvil permiten resolver un problema real con un enfoque innovador, accesible y científicamente sustentado.

# Conclusiones

1. El desarrollo de Foodlytics demuestra que la combinación de inteligencia artificial,
   visión por computadora y arquitectura moderna de software puede resolver de manera
   eficiente problemas reales relacionados con el seguimiento nutricional y la monitorización
   del estado de salud de los usuarios, reduciendo la fricción en el registro alimenticio y
   mejorando la precisión del análisis diario.

2. La aplicación de modelos de reconocimiento de imágenes y estimación de macronutrientes
   evidencia que las tecnologías emergentes tienen un impacto directo en la calidad del
   tratamiento nutricional, permitiendo al paciente registrar su dieta de forma más rápida,
   intuitiva y confiable, y al nutricionista obtener datos estructurados para la toma de decisiones.

3. La arquitectura multiplataforma propuesta —compuesta por aplicación móvil, aplicación web
   para nutricionistas, backend en FastAPI y contrato OpenAPI— garantiza cohesión, 
   interoperabilidad y escalabilidad del sistema, facilitando la evolución futura del producto
   sin comprometer estabilidad ni rendimiento.

4. La implementación de principios de Domain-Driven Design y diseño táctico permitió organizar
   el dominio de manera clara y coherente, lo que redujo la complejidad del desarrollo,
   mejoró la comunicación del equipo y generó un modelo conceptual alineado con los
   procesos reales de nutrición, seguimiento clínico y registro alimentario.

5. Las prácticas de ingeniería aplicadas —como autenticación segura, manejo estandarizado de
   errores, versionamiento de API, auditoría y observabilidad— fortalecieron la calidad del
   software y establecieron una base sólida para garantizar confiabilidad, seguridad y trazabilidad
   en un contexto donde se manejan datos sensibles de salud.

6. El trabajo por Sprints permitió avanzar de manera incremental, priorizando funcionalidades
   de mayor valor para los usuarios. El Sprint 1 estableció las bases conceptuales, técnicas y
   documentales del proyecto, mientras que el Sprint 2 consolidó la implementación completa
   de los módulos principales, permitiendo demostrar el funcionamiento integral del sistema.

7. La documentación generada —incluyendo el contrato OpenAPI 3.1, la especificación de
   requisitos, el diseño táctico, las métricas, el Modelado UX y la planificación ágil— permitió
   mantener trazabilidad completa del proyecto, facilitó la colaboración entre los miembros del
   equipo y alineó todas las decisiones técnicas con los objetivos del producto.

8. El análisis del problema inicial confirmó que las herramientas actuales de registro nutricional
   siguen siendo poco precisas, manuales o incompletas. En respuesta, Foodlytics propone un
   enfoque más inteligente mediante IA que reduce el error humano, automatiza procesos y
   mejora sustancialmente la adherencia del paciente al tratamiento.

9. Los resultados obtenidos en el proyecto demuestran que la integración entre módulos —landing
   page, backend, aplicación web y aplicación móvil— logró un flujo de usuario coherente y
   funcional, lo cual refuerza el potencial del producto para ser adoptado por nutricionistas y
   pacientes en un contexto real de uso.

10. El proyecto deja una plataforma madura y preparada para escalar hacia funcionalidades más
    avanzadas, como modelos de IA más precisos para reconocimiento de alimentos, analítica
    predictiva del estado nutricional, integración con wearables, personalización basada en
    aprendizaje automático y herramientas clínicas que permitan un monitoreo más completo
    y preventivo de la salud del usuario.

# Recomendaciones

1. Se recomienda continuar ampliando el modelo de visión por computadora, 
   incorporando datasets más diversos y calibrados para mejorar la precisión en la 
   estimación de macronutrientes y porciones, especialmente en alimentos mixtos o 
   preparaciones complejas.

2. Es importante implementar un sistema de validación clínica junto a nutricionistas
   certificados, con el objetivo de comparar los resultados de la IA frente a registros
   tradicionales y ajustar parámetros antes de su despliegue en entornos reales.

3. Se sugiere integrar un módulo de analítica predictiva basado en machine learning 
   que permita anticipar hábitos de riesgo, fluctuaciones nutricionales y posibles 
   desviaciones del plan alimenticio, ofreciendo recomendaciones proactivas.

4. Se recomienda reforzar la seguridad mediante autenticación multifactor (MFA), 
   cifrado avanzado y auditoría continua, dado que el sistema maneja información 
   sensible de salud que debe cumplir estándares elevados de privacidad.

5. Sería beneficioso continuar evolucionando la arquitectura modular del backend 
   hacia un enfoque orientado a microservicios o Serverless, con el fin de mejorar la 
   escalabilidad, el aislamiento de componentes y la capacidad de despliegue continuo.

6. Se sugiere integrar la aplicación móvil con wearables (Google Fit, Apple Health, 
   smartbands) para obtener datos automáticos de actividad física, pasos y ritmo 
   cardíaco, lo cual enriquecería el análisis nutricional y el balance energético diario.

7. Para mejorar la experiencia del usuario, se recomienda realizar pruebas de 
   usabilidad con grupos de pacientes y nutricionistas, identificando puntos de fricción, 
   flujos que puedan simplificarse y mejoras en accesibilidad.

8. Es conveniente establecer un pipeline automatizado de CI/CD que incluya pruebas 
   unitarias, de integración y de performance, asegurando calidad constante del 
   producto en cada despliegue de nuevas funcionalidades.

9. Se recomienda desarrollar un módulo de educación nutricional dentro de la app, 
   incluyendo consejos, micro-lecciones, hábitos saludables y alertas personalizadas, 
   con el fin de fomentar adherencia a largo plazo, no solo el registro de comida.

10. Finalmente, se propone crear un roadmap evolutivo del producto que incluya 
    nuevas funcionalidades como: reconocimiento multimodal (foto + texto), 
    soporte multilingüe, recomendaciones automáticas de menús y dashboards 
    avanzados para profesionales de la salud, consolidando el futuro de Foodlytics 
    como una plataforma integral de nutrición inteligente.

# Video About the Team

Durante el Sprint 2, el equipo de desarrollo de Foodlytics elaboró un video en el que se presenta a cada integrante del grupo, junto con sus roles y las responsabilidades asumidas durante esta etapa del proyecto. El material muestra el trabajo colaborativo realizado y la forma en que se organizaron las tareas relacionadas con el diseño, la implementación y la validación del sistema.

El video resume las funciones principales del equipo, como el desarrollo de la aplicación móvil, el diseño del dashboard web para nutricionistas, la integración de los módulos de reconocimiento de alimentos mediante inteligencia artificial, la construcción de microservicios backend y la preparación del entorno de despliegue. También evidencia la coordinación interna realizada durante el sprint para asegurar el cumplimiento de los entregables requeridos.

Este recurso permite mostrar de manera transparente el esfuerzo del equipo, la distribución de roles y la dinámica de trabajo aplicada en Foodlytics. Además, sirve como evidencia de la organización y avance del proyecto durante el ciclo de desarrollo.

::: warn
Para visualizar el video del equipo, haga click en el siguiente enlace [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202210059_upc_edu_pe/IQCZ75QtruaFTodXA_bO1rHgAeiR6In9otu2OGe4wR56a1o?e=X9QSb4&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)
:::

![Imagen extraída del Video About the team](src/img/cap7/about-the-team.png)