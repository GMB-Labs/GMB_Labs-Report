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
\textbf{RF-01} & El paciente debe poder registrarse proporcionando nombres, apellidos, correo electrónico válido y contraseña, para crear su cuenta en la aplicación. \\
\hline
\textbf{RF-02} & El usuario (paciente o nutricionista) debe poder iniciar y cerrar sesión de forma segura mediante autenticación con credenciales, para proteger su información personal. \\
\hline
\textbf{RF-03} & El paciente debe poder editar su perfil con edad, peso, talla y objetivos de salud, para mantener sus datos actualizados. \\
\hline
\textbf{RF-04} & El paciente debe poder registrar comidas mediante fotografía con reconocimiento automático por IA, para acelerar el ingreso de alimentos. \\
\hline
\textbf{RF-05} & El paciente debe poder corregir manualmente alimentos o porciones detectadas por la IA, para asegurar precisión en el registro. \\
\hline
\textbf{RF-06} & El paciente debe poder visualizar un resumen diario de calorías y macronutrientes consumidos, para monitorear su ingesta. \\
\hline
\textbf{RF-07} & El paciente debe poder consultar un historial semanal de comidas y balance calórico, para identificar tendencias de consumo. \\
\hline
\textbf{RF-08} & El paciente debe poder registrar actividad física manual con tipo, duración e intensidad, para completar el cálculo de su gasto energético. \\
\hline
\textbf{RF-09} & El paciente debe poder registrar periódicamente su peso corporal, para hacer seguimiento de su progreso. \\
\hline
\textbf{RF-10} & El paciente debe poder visualizar el cálculo automático del IMC en base a su peso y talla, para conocer su clasificación nutricional. \\
\hline
\textbf{RF-11} & El nutricionista debe poder crear planes de dieta personalizados asignados a cada paciente, para guiar su progreso nutricional. \\
\hline
\textbf{RF-12} & El nutricionista debe poder visualizar un dashboard con métricas semanales de cada paciente (calorías, macros, peso, actividad), para evaluar su evolución. \\
\hline
\textbf{RF-13} & El nutricionista debe poder generar reportes históricos descargables en PDF o CSV, para compartirlos o archivarlos como evidencia de progreso. \\
\hline
\textbf{RF-14} & El paciente debe poder recibir notificaciones automáticas para registrar comidas y hábitos, para mantener constancia diaria en el uso de la aplicación. \\
\hline
\textbf{RF-15} & El paciente debe poder sincronizar en un único envío diario sus datos locales al backend, para actualizar su historial sin generar duplicados. \\
\hline
\textbf{RF-16} & El nutricionista debe poder suscribirse a planes de pago según la cantidad de pacientes gestionados (por ejemplo: básico, intermedio, avanzado), para ajustar la plataforma a sus necesidades. \\
\hline
\textbf{RF-17} & El nutricionista debe poder cancelar su suscripción en cualquier momento desde la plataforma web, para evitar cobros adicionales. \\
\hline
\textbf{RF-18} & El sistema debe permitir pagos en línea a través de pasarelas seguras (tarjeta de crédito/débito, billeteras digitales, transferencias), para facilitar el acceso a los planes de nutricionista. \\
\hline
\end{longtable}

\newpage

### Requisitos No Funcionales

\begin{longtable}{|p{1.5cm}|p{9cm}|p{4.5cm}|}
\hline
\textbf{ID} & \textbf{Requisito no funcional} & \textbf{Atributo de calidad} \\
\hline
\textbf{RNF-01} & El sistema debe detectar hasta 10,000 usuarios concurrentes activos y mantener una latencia menor a 300 ms en operaciones críticas (login, registro de comidas, sincronización). & Rendimiento \\
\hline
\textbf{RNF-02} & Toda comunicación de datos entre cliente, servidor y dispositivos debe realizarse mediante HTTPS con TLS 1.3. & Seguridad \\
\hline
\textbf{RNF-03} & El sistema debe estar disponible al menos el 99.9\% del tiempo durante el horario laboral definido de 6:00 a 23:00 (hora Perú). & Disponibilidad \\
\hline
\textbf{RNF-04} & La interfaz móvil y web debe cargar en menos de 2 segundos únicamente en conexiones de red 4G o superiores (LTE, 5G o WiFi equivalente). En conexiones menores (3G o inferiores) no se garantiza este tiempo de respuesta. & Rendimiento \\
\hline
\textbf{RNF-05} & El sistema debe registrar métricas de eventos críticos (errores 4xx/5xx, fallos de autenticación, tiempo de respuesta promedio, tasa de sincronización fallida) en logs estructurados, accesibles y auditables. & Observabilidad \\
\hline
\textbf{RNF-06} & El backend debe ser escalable horizontalmente y soportar un incremento del 100\% de usuarios en picos de demanda, manteniendo latencia < 500 ms en operaciones críticas. & Escalabilidad \\
\hline
\textbf{RNF-07} & Los datos sensibles de pacientes y nutricionistas deben almacenarse cifrados en reposo con AES-256. El acceso debe estar limitado al 0\% para personal no autorizado. & Seguridad \\
\hline
\textbf{RNF-08} & La infraestructura debe contar con redundancia al fallo (failover automático con RPO $\leq$ 15 min y RTO $\leq$ 1 hora). & Confiabilidad/Disponibilidad \\
\hline
\textbf{RNF-09} & La interfaz debe ser intuitiva y accesible, cumpliendo con las pautas WCAG 2.1 AA (contraste mínimo, navegación por teclado, texto alternativo en imágenes). & Usabilidad/Accesibilidad \\
\hline
\textbf{RNF-10} & El sistema debe ser compatible con navegadores modernos (Chrome, Firefox, Edge, Safari en sus dos últimas versiones) y dispositivos iOS/Android con versiones no mayores a 3 años. & Compatibilidad \\
\hline
\textbf{RNF-11} & El código del backend debe estar modularizado en microservicios documentados, con métricas de cobertura de pruebas unitarias $\geq$ 80\%. & Mantenibilidad \\
\hline
\textbf{RNF-12} & Se deben realizar copias de seguridad automáticas de la base de datos al menos una vez al día, garantizando una tasa de éxito del 100\%. & Confiabilidad \\
\hline
\textbf{RNF-13} & El sistema debe implementar control de acceso basado en roles (RBAC) garantizando que ningún usuario sin permisos pueda acceder a recursos restringidos. & Seguridad \\
\hline
\textbf{RNF-14} & El sistema debe garantizar integridad de datos asegurando 0\% de duplicados en procesos de sincronización diaria. & Confiabilidad \\
\hline
\textbf{RNF-15} & El sistema debe cumplir con la Ley de Protección de Datos Personales (Perú) y GDPR, garantizando que el 100\% de los datos personales se procesen bajo consentimiento informado. & Regulatorio/Seguridad \\
\hline
\textbf{RNF-16} & La aplicación debe ofrecer modo oscuro y claro, garantizando que todos los elementos mantengan un contraste mínimo de 4.5:1 en ambos modos. & Usabilidad \\
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
