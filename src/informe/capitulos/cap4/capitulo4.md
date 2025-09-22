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
  \usepackage{tabularx}
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

La sesión de Event Storming permitió mapear de manera colaborativa el flujo completo de la aplicación de seguimiento nutricional, identificando los eventos clave, los actores involucrados y las interacciones entre ellos. Se definieron los procesos principales: Onboarding del Paciente, Análisis de Datos Nutricionales mediante IA, Seguimiento y Registro de Comidas, Notificaciones y Feedback al Paciente, y el Dashboard para Paciente. 

En cada proceso se visualizaron los eventos disparadores, los comandos, los servicios implicados y las métricas que alimentan el análisis nutricional, facilitando la detección de dependencias, la definición de bounded contexts y la comprensión integral del dominio para guiar el diseño de la solución. 


![Recurso realizado en Miro - EventStorming](src/img/cap4/EventStorming.png)

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

1. **Contexto de Onboarding del Paciente**

  - **Límite:** Abarca desde el registro inicial hasta la asignación de un nutricionista.

  - **Eventos clave:** Creación de cuenta, validación de datos, asignación de nutricionista.

  - **Justificación:** Este bounded context se centra en la identidad y perfil del paciente. Su independencia asegura integridad en la gestión de usuarios y facilita la interoperabilidad con los demás módulos.

![EventStorming - Bounded Context Onboarding del Paciente ](src/img/cap4/EventStorming1.png)

\newpage


2. **Contexto de Análisis Nutricional (IA)**

  - **Límite:** Procesamiento de datos nutricionales, cálculos de calorías/nutrientes y generación de alertas.

  - **Eventos clave:** Solicitar registro de comidas, análisis automático de fotos, emisión de alertas de hábitos críticos.

  - **Justificación:** Representa el corazón de la propuesta de valor de Foodlytics. Mantenerlo aislado permite escalar los algoritmos de IA sin afectar otros procesos.

![EventStorming - Bounded Context Análisis Nutricional (IA)](src/img/cap4/EventStorming2.png)

\newpage

3. **Contexto de Seguimiento y Registro de Comidas**

  - **Límite:** Captura y almacenamiento del historial alimenticio de cada paciente.

  - **Eventos clave:** Registro de comida por foto o texto, validación de la entrada, consolidación de histórico.

  - **Justificación:** Actúa como repositorio de datos de consumo, asegurando consistencia y sirviendo de insumo directo para el análisis nutricional.

![EventStorming - Bounded Context Seguimiento y Registro de Comidas](src/img/cap4/EventStorming3.png)

\newpage

4. **Contexto de Notificaciones y Feedback**

  - **Límite:** Comunicación personalizada con el paciente en base a resultados y hábitos detectados.

  - **Eventos clave:** Envío de recordatorios, alertas de progreso, mensajes motivacionales.

  - **Justificación:** Se mantiene independiente para poder adaptar canales de comunicación (app, email, SMS) sin modificar la lógica de negocio central.

![EventStorming - Bounded Context Notificaciones y Feedback](src/img/cap4/EventStorming4.png)

\newpage

5. **Contexto de Dashboard para Paciente**

  - **Límite:** Visualización de métricas, reportes de progreso y estado nutricional.

  - **Eventos clave:** Generación de reportes, consulta de métricas de consumo, feedback visual.

  - **Justificación:** Constituye la capa de presentación del sistema hacia el paciente, desacoplada de la lógica de análisis para asegurar flexibilidad en la interfaz.

![EventStorming - Bounded Context Dashboard para Paciente](src/img/cap4/EventStorming5.png)

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

![1: Food Tracking (Registro de Comidas)](src/img/cap4/Bounded_Context_Canvases_1.png)

**Canvas 2 — Nutrition Analysis (Motor IA/ML)**

![2: Nutrition Analysis (Motor IA/ML)](src/img/cap4/Bounded_Context_Canvases_2.png)

**Canvas 3 — Clinician Dashboard**

![3: Clinician Dashboard](src/img/cap4/Bounded_Context_Canvases_3.png)

**Canvas 4 — User & Access (Autenticación y Consentimiento)**

![4: User & Access (Autenticación y Consentimiento)](src/img/cap4/Bounded_Context_Canvases_4.png)

**Canvas 5 — Notifications & Reminders**

![5: Notifications & Reminders](src/img/cap4/Bounded_Context_Canvases_5.png)

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

![Context Mapping](src/img/cap4/ContextMapping.png)

El context map resultante proporciona un marco claro para comprender las dependencias y flujos de datos entre módulos, facilita la identificación de puntos críticos de acoplamiento y sirve como guía práctica para la posterior implementación técnica de integraciones entre microservicios.

\newpage

## Software Architecture 

### Software Architecture System Landscape Diagram

En este caso, se optó por un monolito modular con arquitectura en capas y principios de DDD para mantener cohesión interna, claridad en los dominios de negocio y simplicidad operativa en las primeras fases del proyecto. Al mismo tiempo, se decidió integrar servicios externos desplegados en la nube, como Culqi para el procesamiento seguro de pagos, Auth0 para la autenticación y gestión de identidades, y un servicio de detección de imágenes para enriquecer las funcionalidades. 

![System Landscape Diagram ](src/img/cap4/Emergentes-Landscape.png)

\newpage

### Software Architecture Context Level Diagrams  

La primera imagen muestra cómo los pacientes y nutricionistas interactúan con Foodlytics. El paciente registra su consumo y recibe un cálculo aproximado de calorías, mientras que el nutricionista accede a la misma plataforma para hacer seguimiento. Foodlytics se integra con un servicio externo de autenticación (Auth0) que gestiona accesos y con un servicio de IA (GPT4) que procesa imágenes de alimentos. Las fotos enviadas no se almacenan, solo se procesan para devolver información nutricional. El sistema actúa como punto central de interacción entre usuarios y servicios externos. 

![C4 - System context diagram ](src/img/cap4/Emergentes-Contexto.png)

\newpage

### Software Architecture Container Level Diagrams  

La segunda imagen describe la arquitectura por contenedores de Foodlytics. Los usuarios acceden a través de una aplicación móvil y una aplicación web, que se conectan con una landing page que redirige según el perfil. La API en Flask recibe datos, envía imágenes al servicio de IA y maneja autenticación con Auth0. La base de datos en Postgres guarda perfiles e históricos pero no imágenes. El servicio externo de IA procesa las fotos y devuelve calorías y macros. Cada contenedor cumple un rol definido y se conecta con los demás para mantener el flujo de información. 

![C4 - Container diagram ](src/img/cap4/Emergentes-Contenedores.png)

Al tener una arquitectura monolítica, las instrucciones del docente fue incluir los datos adicionales de los bounded contexts a modo de componentes 

![C4 - Component diagram ](src/img/cap4/Emergentes-Componentes.png)

El diagrama muestra la arquitectura de Foodlytics dividida en bounded contexts y componentes conectados. Los actores son paciente y nutricionista, quienes acceden por aplicación web y móvil. El sistema usa un servicio externo de autenticación (Auth0) y un servicio externo de IA para procesar imágenes de comida. 

En la API se agrupan los módulos: autenticación, perfil, actividad física, dashboard, notificaciones, seguimiento de pacientes y procesamiento de imágenes. Cada módulo gestiona funciones específicas y se comunica con los bounded contexts que necesita. Los anti corruption layers permiten el intercambio de datos entre bounded contexts, por ejemplo, entre gestión de pacientes y dashboard o entre gestión de dieta y reconocimiento de alimentos. 

El almacenamiento está en Foodlytics DB con soporte de un ORM, que guarda información de pacientes, perfiles, notificaciones e históricos de actividad, sin almacenar imágenes. El flujo principal es que el paciente registra comidas o actividad, la información se procesa con IA o se guarda en la base, y el nutricionista accede al dashboard para seguimiento. 

\newpage

### Software Architecture Deployment Diagrams

![Software Architecture Deployment Diagrams](src/img/cap4/SoftwareArchitectureDeploymentDiagrams.png)

El diagrama muestra la arquitectura de despliegue de la solución, donde la aplicación móvil desarrollada en React Native y publicada en App Store y Play Store se conecta mediante una API al servidor de Hostinger, que aloja un backend monolítico en Python Flask encargado de procesar las solicitudes, ejecutar comandos SQL y comunicarse con la base de datos PostgreSQL desplegada en Railway. En el mismo servidor se encuentra el frontend web en Angular, que interactúa con la API a través de HTTPS/JSON, mientras que la Landing Page informativa se aloja de forma independiente en GitHub Pages usando React, permitiendo así que las aplicaciones móviles y web compartan los mismos servicios centralizados y se garantice consistencia de datos y escalabilidad. 

\newpage