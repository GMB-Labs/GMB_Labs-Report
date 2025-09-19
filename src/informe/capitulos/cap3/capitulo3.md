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

## To-Be Scenario Mapping  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

## User Stories 

**Requisitos Funcionales**

\begin{longtable}{|m{5cm}|m{10cm}|}
\hline
\textbf{RF-01} & Autenticación de usuario (registro, inicio/cierre de sesión) \\ \hline
\textbf{RF-02} & Gestión del perfil del nutricionista y paciente \\ \hline
\textbf{RF-03} & Registro de comidas con foto y reconocimiento mediante IA \\ \hline
\textbf{RF-04} & Modificación manual de comidas detectadas incorrectamente \\ \hline
\textbf{RF-05} & Visualización diaria de calorías y macros consumidos \\ \hline
\textbf{RF-06} & Registro de peso y cálculo automático del IMC \\ \hline
\textbf{RF-07} & Generación de reportes históricos (peso, consumo vs gasto calórico) \\ \hline
\textbf{RF-08} & Notificaciones para registrar comidas y alertas de déficit/exceso calórico \\ \hline
\textbf{RF-09} & Sincronización diaria en lote de datos locales al backend con manejo de duplicados \\ \hline
\textbf{RF-10} & Integración de conteo de pasos físicos (hardware / librería) \\ \hline
\textbf{RF-11} & Dashboard web para nutricionista con filtros y métricas semanales \\ \hline
\end{longtable}

**Requisitos No Funcionales**

\begin{longtable}{|m{5cm}|m{10cm}|}
\hline
\textbf{RNF-01} & Tiempo de respuesta operacionales comunes < 2 segundos en web y móvil \\ \hline
\textbf{RNF-02} & Seguridad: cifrado de datos en tránsito, autenticación segura, permisos según rol \\ \hline
\textbf{RNF-03} & Disponibilidad: sistema accesible al menos 99.5% del tiempo \\ \hline
\textbf{RNF-04} & Privacidad: cumplimiento de normativas locales de protección de datos \\ \hline
\textbf{RNF-05} & Usabilidad: interfaz intuitiva, navegación clara, adecuada para jóvenes y profesionales \\ \hline
\textbf{RNF-06} & Accesibilidad: soporte para discapacidades visuales, tamaño de texto ajustable \\ \hline
\textbf{RNF-07} & Multiplataforma: soporte iOS y Android para la app móvil; navegadores modernos para web \\ \hline
\textbf{RNF-08} & Escalabilidad: backend debe soportar crecimiento de usuarios sin degradar desempeño \\ \hline
\textbf{RNF-09} & Mantenibilidad: código modular, logs, observabilidad, facilidad para implementar mejoras \\ \hline
\textbf{RNF-10} & Localización adicional de múltiples idiomas \\ \hline
\textbf{RNF-11} & Personalización visual como modo oscuro y temas configurables \\ \hline
\end{longtable}

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
\end{longtable}

## Impact Mapping  

Lorem ipsum dolor sit amet consectetur adipiscing elit consequat, nullam felis erat urna at fringilla aptent interdum, pharetra sagittis aliquam inceptos venenatis cum vivamus. Curae maecenas aliquam venenatis urna ligula integer mollis ullamcorper et dis vehicula, purus eu ridiculus blandit cubilia cursus imperdiet convallis eget feugiat. Ornare montes sem potenti risus a cum felis nec, proin phasellus est lacinia primis nisl iaculis posuere, torquent curabitur egestas aptent imperdiet integer vestibulum.

## Product Backlog

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