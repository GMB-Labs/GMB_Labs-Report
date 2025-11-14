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

\newpage

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


## teus te mete el chop
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
