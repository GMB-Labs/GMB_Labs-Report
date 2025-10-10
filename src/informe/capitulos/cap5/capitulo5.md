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

# Capítulo V: Tactical-Level Software Design  

## Bounded Context: Image Recognition

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto AI Recognition}\label{tab:ai-recognition-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{DailyIntake} & Representa el conjunto de comidas registradas por el usuario en un día. Contiene los datos nutricionales totales y la lista de ítems reconocidos por IA.\\
Entity & \code{MealItem} & Representa una comida individual detectada en una imagen. Incluye nombre del alimento, calorías, proteínas, carbohidratos y grasas.\\
Entity & \code{RecognitionRequest} & Modela una solicitud de análisis enviada al servicio de IA. Guarda metadatos como fecha, usuario, estado y referencia al archivo procesado.\\
Value Object & \code{NutritionFacts} & Agrupa los valores nutricionales (calorías, proteínas, carbohidratos, grasas) estimados por IA.\\
Value Object & \code{ImageMetadata} & Contiene información técnica de la imagen, resolución, formato, tamaño y hash de archivo.\\
Enum & \code{RecognitionStatus} & \code{\{PENDING, PROCESSING, COMPLETED, FAILED\}}.\\
Domain Event & \code{RecognitionCompletedEvent} & Se emite cuando una imagen ha sido procesada exitosamente por el servicio de IA.\\
Domain Event & \code{RecognitionFailedEvent} & Se emite cuando la solicitud de reconocimiento falla por error de red o servicio.\\
\bottomrule
\end{tabularx}

### Interface Layer 

\begin{tabularx}{\textwidth}{L{0.22\textwidth}L{0.28\textwidth}Y}
\caption{Elementos de la capa Interface del contexto AI Recognition}\label{tab:ai-recognition-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Controller & \code{RecognitionController} & Expone endpoints REST para subir imágenes y obtener resultados de reconocimiento.\\
Resource & \code{RecognitionRequestResource} & Representa la solicitud de análisis enviada por el usuario.\\
Resource & \code{MealItemResource} & Representa los alimentos detectados y sus datos nutricionales.\\
Resource & \code{DailyIntakeResource} & Representa el resumen diario de ingesta alimenticia, listo para exposición vía API.\\
Transform & \code{RecognitionTransform} & Convierte entidades del dominio a recursos API.\\
Adapter (ACL) & \code{StorageClientAdapter} & Cliente para subir y recuperar imágenes desde el servicio de almacenamiento en la nube.\\
Adapter (ACL) & \code{AIModelClientAdapter} & Cliente para comunicarse con el motor de reconocimiento basado en IA.\\
\bottomrule
\end{tabularx}

### Application Layer  

\begin{tabularx}{\textwidth}{L{0.23\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Application del contexto AI Recognition}\label{tab:ai-recognition-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Command & \code{CreateRecognitionRequestCommand} & Solicitud para registrar una nueva imagen a analizar.\\
Command & \code{ProcessRecognitionResultCommand} & Instrucción para actualizar los resultados del análisis de IA.\\
Service & \code{RecognitionCommandService} & Gestiona el flujo de creación y actualización de solicitudes de reconocimiento.\\
Service & \code{RecognitionQueryService} & Permite consultar resultados de reconocimiento por usuario o fecha.\\
Event Handler & \code{RecognitionCompletedEventHandler} & Escucha \code{RecognitionCompletedEvent} para actualizar agregados y notificar a otros contextos.\\
Repository Interface & \code{RecognitionRepository} & Define las operaciones para persistir solicitudes e ítems de comida.\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Infrastructure del contexto AI Recognition}\label{tab:ai-recognition-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Repository Implementation & \code{SQLAlchemyRecognitionRepository} & Implementa \code{RecognitionRepository} usando SQLAlchemy.\\
ORM Model & \code{RecognitionRequestModel} & Mapea la entidad \code{RecognitionRequest} a la base de datos PostgreSQL.\\
ORM Model & \code{MealItemModel} & Mapea la entidad \code{MealItem} y sus atributos nutricionales.\\
ORM Model & \code{DailyIntakeModel} & Entidad ORM para el agregado \code{DailyIntake}.\\
External Client & \code{AIModelClient} & Cliente HTTP/gRPC para comunicarse con el servicio de reconocimiento IA.\\
External Client & \code{StorageClient} & Cliente para manejo de imágenes en la nube.\\
Unit of Work & \code{SQLAlchemyUnitOfWork} & Coordina transacciones en operaciones de reconocimiento.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Image Recognition (Component Level Diagram)](src/img/cap5/Recognition/Componente.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Image Recognition (Layer Class Diagram)](src/img/cap5/Recognition/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Image Recognition (Database Design Diagram)](src\img\cap5\Recognition\ERD _ recognition.png)

## Bounded Context: Diet Tracking 

### Domain Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Aggregate Root & \code{DietTrackingRecord} & Representa el seguimiento diario de la dieta y progreso físico de un usuario. Contiene los resultados de comparación entre el \code{DailyIntake} actual y el del día anterior. \\
\addlinespace
Aggregate (externo) & \code{DailyIntake} & Agregado raíz del contexto \code{AI Recognition}. Contiene los datos nutricionales del día (calorías, macros, etc.). \\
\addlinespace
Value Object & \code{NutrientComparison} & Diferencia entre nutrientes (calorías, proteínas, carbohidratos y grasas) de dos \code{DailyIntake} consecutivos. \\
\addlinespace
Value Object & \code{WeightComparison} & Diferencia entre el peso actual y el del día anterior. \\
\addlinespace
Value Object & \code{ProgressTrend} & Resultado del análisis conjunto de nutrientes y peso. \\
\addlinespace
Enum & \code{ProgressStatus} & \code{\{IMPROVED, DECLINED, STABLE\}}. \\
\bottomrule
\end{tabularx}
\end{table}

### Interface Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Aggregate Root & \code{DietTrackingRecord} & Representa el seguimiento diario de la dieta y progreso físico de un usuario. Contiene los resultados de comparación entre el \code{DailyIntake} actual y el del día anterior. \\
\addlinespace
Aggregate (externo) & \code{DailyIntake} & Agregado raíz del contexto \code{AI Recognition}. Contiene los datos nutricionales del día (calorías, macros, etc.). \\
\addlinespace
Value Object & \code{NutrientComparison} & Diferencia entre nutrientes (calorías, proteínas, carbohidratos y grasas) de dos \code{DailyIntake} consecutivos. \\
\addlinespace
Value Object & \code{WeightComparison} & Diferencia entre el peso actual y el del día anterior. \\
\addlinespace
Value Object & \code{ProgressTrend} & Resultado del análisis conjunto de nutrientes y peso. \\
\addlinespace
Enum & \code{ProgressStatus} & \code{\{IMPROVED, DECLINED, STABLE\}}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.22\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Command & \code{GenerateDietTrackingRecordCommand} & Instrucción para crear un nuevo registro diario y comparar con el anterior. \\
\addlinespace
Command & \code{EvaluateProgressCommand} & Evalúa el progreso del día y genera un evento si hubo mejora. \\
\addlinespace
Service & \code{GenerateDietTrackingRecordService} & Caso de uso principal. Obtiene datos desde \code{Recognition} y \code{Profile}, crea el \code{DietTrackingRecord}, evalúa progreso y publica eventos. \\
\addlinespace
Service & \code{GetProgressService} & Consulta el historial de progreso del usuario. \\
\addlinespace
Event & \code{ProgressImprovedEvent} & Evento de dominio emitido cuando el progreso del usuario mejora. \\
\addlinespace
Event Handler & \code{ProgressImprovedEventHandler} & Escucha \code{ProgressImprovedEvent} y genera una notificación en el contexto \code{Notifications}. \\
\addlinespace
Repository Interface & \code{DietTrackingRepository} & Abstracción de acceso a registros \code{DietTrackingRecord}. \\
\addlinespace
ACL Adapter & \code{NotificationClientAdapter} & Cliente para enviar notificaciones al contexto \code{Notifications}. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Diet Tracking}
\begin{tabularx}{\textwidth}{L{0.28\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Repository Implementation & \code{SQLDietTrackingRepository} & Implementación concreta de \code{DietTrackingRepository} usando SQLAlchemy (o equivalente ORM). \\
\addlinespace
Repository Interface (del dominio) & \code{DietTrackingRepository} & Define operaciones como \code{save}, \code{find\_by\_user\_and\_date}, \code{find\_latest\_by\_user}. \\
\addlinespace
Event Publisher & \code{DomainEventPublisher} & Publica eventos de dominio dentro del sistema. \\
\addlinespace
Event Subscriber & \code{EventBusSubscriber} & Escucha eventos desde otros contextos si fuera necesario (no principal aquí). \\
\addlinespace
Mapper / ORM Model & \code{DietTrackingModel} & Entidad ORM equivalente a \code{DietTrackingRecord}. \\
\addlinespace
Unit of Work & \code{SQLAlchemyUnitOfWork} & Coordina transacciones de repositorios durante operaciones complejas. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Diet Tracking (Component Level Diagram)](src/img/cap5/Diet Tracking/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Diet Tracking (Layer Class Diagram)](src/img/cap5/Diet Tracking/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Diet Tracking (Database Design Diagram)](src/img/cap5/Diet Tracking/ERD.png)

## Bounded Context: Notification

### Domain Layer  

\begin{table}[H]
\centering
\caption{Elementos del dominio del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.25\textwidth} Y}
\toprule
\textbf{Nombre} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{Notification} & Entity (Aggregate Root) & Representa una notificación interna dirigida a un usuario (paciente o nutricionista). Contiene el estado y métodos de dominio como \code{mark\_as\_read()}. \\
\addlinespace
\code{NotificationStatus} & Enum & Define los estados posibles de una notificación: \code{UNREAD}, \code{READ}. \\
\addlinespace
\code{NotificationRepository} & Interface (ABC) & Define las operaciones del repositorio: \code{save()}, \code{find\_by\_recipient()}, \code{find\_unread()}. No conoce la implementación. \\
\bottomrule
\end{tabularx}
\end{table}

### Interface Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Interface del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{NotificationController} & Flask Controller / Blueprint & Expone los endpoints REST del bounded context (\code{/notifications}, \code{/notifications/read}). Interactúa con los \code{CommandHandlers} y \code{QueryHandlers}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer 

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.33\textwidth} L{0.27\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{CreateNotificationCommand} & Command (Value Object) & Encapsula los datos necesarios para crear una notificación (\code{recipient\_id}, \code{title}, \code{message}). \\
\addlinespace
\code{MarkNotificationAsReadCommand} & Command (Value Object) & Contiene el identificador de la notificación a marcar como leída. \\
\addlinespace
\code{NotificationCommandHandler} & Application Service & Orquesta la ejecución de los comandos: crea notificaciones o actualiza su estado. Se comunica con \code{NotificationRepository}. \\
\addlinespace
\code{GetNotificationsQuery (opcional)} & Query & Permite solicitar las notificaciones de un usuario. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Notifications}
\begin{tabularx}{\textwidth}{L{0.33\textwidth} L{0.27\textwidth} Y}
\toprule
\textbf{Clase} & \textbf{Tipo} & \textbf{Descripción} \\
\midrule
\code{SqlAlchemyNotificationRepository} & Repository Implementation & Implementa \code{NotificationRepository} usando SQLAlchemy. Ejecuta persistencia y consultas en PostgreSQL. \\
\addlinespace
\code{NotificationModel (opcional)} & ORM Entity & Mapeo de la tabla \code{notifications} en la base de datos. \\
\addlinespace
\code{Unit of Work} & \code{SQLAlchemyUnitOfWork} & Coordina transacciones de repositorios durante operaciones complejas. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Notifications (Component Level Diagram)](src/img/cap5/Notifications/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Notifications (Layer Class Diagram)](src/img/cap5/Notifications/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Notifications (Database Design Diagram )](src/img/cap5/Notifications/ERD.png)

## Bounded Context: Payments

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.30\textwidth} Y}
\caption{Elementos del dominio del contexto Payments}\label{tab:payments-domain} \\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
\endfirsthead

\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
\endhead

\midrule
\multicolumn{3}{r}{\small Continúa en la siguiente página} \\
\endfoot

\bottomrule
\endlastfoot

Aggregate Root & \code{Payment} & Representa un cobro único realizado por un paciente. Atributos: \code{paymentId}, \code{amount} (\code{Money}), \code{status} \code{\{INITIATED, AUTHORIZED, CAPTURED, FAILED, REFUNDED\}}, \code{methodToken}, \code{customerId}, \code{externalTxnId}, \code{failureReason}, \code{occurredAt}. \\
Aggregate Root & \code{Subscription} & Representa una suscripción de un nutricionista. Atributos: \code{subscriptionId}, \code{planId}, \code{customerId}, \code{status} \code{\{ACTIVE, PAST\_DUE, CANCELED\}}, \code{currentPeriodStart}, \code{currentPeriodEnd}, \code{externalSubId}. \\
Value Object & \code{Money} & \code{currency}, \code{value}. Monto monetario con su moneda. \\
Value Object & \code{IdempotencyKey} & Identificador único para evitar cobros duplicados. \\
Value Object & \code{ExternalTxnId} & ID de transacción en \code{Culqi}. \\
Enum & \code{PaymentStatus} & \code{\{INITIATED, AUTHORIZED, CAPTURED, FAILED, REFUNDED\}}. \\
Enum & \code{SubscriptionStatus} & \code{\{ACTIVE, PAST\_DUE, CANCELED\}}. \\
Domain Event & \code{PaymentCaptured} & Emite un evento cuando un pago se confirma. \\
Domain Event & \code{SubscriptionRenewed} & Emite un evento cuando una suscripción se renueva automáticamente. \\
\end{tabularx}

### Interface Layer 

\begin{table}[H]
\centering
\caption{Elementos de la capa Interface del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.23\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Controller & \code{PaymentsController} & Endpoints: \code{/api/payments/charge}, \code{/api/payments/refund}, \code{/api/payments/\{paymentId\}}. \\
\addlinespace
Controller & \code{SubscriptionsController} & Endpoints: \code{/api/payments/subscriptions}, \code{/api/payments/subscriptions/\{id\}}. \\
\addlinespace
Controller & \code{CulqiWebhookController} & Endpoint \code{/api/payments/webhooks/culqi}. Verifica firma HMAC y traduce eventos \code{charge.*} y \code{subscription.*}. \\
\addlinespace
Resource & \code{CreateChargeResource} & Estructura para crear un cobro. \\
\addlinespace
Resource & \code{CreateSubscriptionResource} & Estructura para iniciar una suscripción. \\
\addlinespace
Resource & \code{RefundResource} & Datos para procesar un reembolso. \\
\addlinespace
Resource & \code{PaymentResource} & Representación API del agregado \code{Payment}. \\
\addlinespace
Resource & \code{SubscriptionResource} & Representación API del agregado \code{Subscription}. \\
\bottomrule
\end{tabularx}
\end{table}

### Application Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Application del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.25\textwidth} L{0.32\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Command Service & \code{PaymentCommandService} & Métodos: \code{initiateCharge(cmd)}, \code{refund(cmd)}. Gestiona el flujo completo del pago y publica eventos. \\
\addlinespace
Command Service & \code{SubscriptionCommandService} & Métodos: \code{start(cmd)}, \code{cancel(cmd)}. Gestiona creación y cancelación de suscripciones. \\
\addlinespace
Query Service & \code{PaymentQueryService} & Consulta pagos por ID o cliente. \\
\addlinespace
Query Service & \code{SubscriptionQueryService} & Consulta suscripciones activas o por plan. \\
\addlinespace
Event Handler & \code{CulqiWebhookHandler} & Procesa eventos asíncronos desde \code{Culqi} y actualiza los agregados. \\
\bottomrule
\end{tabularx}
\end{table}

### Infrastructure Layer  

\begin{table}[H]
\centering
\caption{Elementos de la capa Infrastructure del contexto Payments}
\begin{tabularx}{\textwidth}{L{0.30\textwidth} L{0.30\textwidth} Y}
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
Repository Implementation & \code{SQLPaymentRepository} & Implementa \code{PaymentRepositoryPort} con SQLAlchemy. \\
\addlinespace
Repository Implementation & \code{SQLSubscriptionRepository} & Implementa \code{SubscriptionRepositoryPort} con SQLAlchemy. \\
\addlinespace
External Client & \code{CulqiClient} & Gestiona cobros, reembolsos y suscripciones vía API \code{Culqi}. \\
\addlinespace
Utility & \code{CulqiWebhookSignatureVerifier} & Verifica la firma HMAC del webhook de \code{Culqi}. \\
\addlinespace
ORM Model & \code{PaymentModel} & Entidad ORM para \code{Payment}. \\
\addlinespace
ORM Model & \code{SubscriptionModel} & Entidad ORM para \code{Subscription}. \\
\addlinespace
Unit of Work & \code{SQLAlchemyUnitOfWork} & Maneja transacciones y persistencia atómica. \\
\bottomrule
\end{tabularx}
\end{table}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Payments (Component Level Diagram)](src\img\cap5\Payments\Foodlytics - Payment Module C4.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Payments (Layer Class Diagram)](src\img\cap5\Payments\Foodlytics - Payment Module Domain Class Diagram.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Payments (Database Design Diagram )](src\img\cap5\Payments\Foodlytics - Payment Module Database.png)

## Bounded Context: Identity and Access Management 

### Domain Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto IAM}\label{tab:iam-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{User} & Entidad principal que representa a cualquier persona que interactúa con el sistema. Gestiona la identidad y la autenticación.\\
Aggregate Root & \code{Patient} & Representa a un cliente que recibe asesoramiento nutricional. Es la raíz que agrupa sus métricas, dieta, comidas y objetivos.\\
Aggregate Root & \code{Nutritionist} & Representa al profesional que provee el servicio. Es la raíz que agrupa a sus pacientes asignados y las dietas que crea.\\
Entity & \code{Profile} & Contiene la información personal y de contacto común tanto para pacientes como para nutricionistas.\\
Entity & \code{Diet} & Representa un plan nutricional específico creado por un nutricionista para un paciente.\\
Entity & \code{Meal} & Representa una comida específica registrada por un paciente, con su desglose de macronutrientes.\\
Entity & \code{PatientMetrics} & Almacena un resumen del progreso del paciente en un período determinado, como peso, calorías y adherencia.\\
Entity & \code{Schedule} & Define el calendario de seguimiento del paciente, incluyendo las fechas de inicio y fin del plan.\\
Entity & \code{Goal} & Define los objetivos diarios y finales del paciente dentro de un \code{Schedule}, como las calorías o el peso objetivo.\\
Value Object & \code{Notification} & Representa un mensaje o alerta enviado a un usuario dentro del sistema.\\
\bottomrule
\end{tabularx}

### Interface Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Interface del contexto IAM}\label{tab:iam-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} \\
\midrule
API Controller & \code{AuthController} & Gestiona las solicitudes de registro e inicio de sesión, interactuando con el proveedor de identidad externo Google. \\
API Controller & \code{PatientController} & Expone endpoints para que la aplicación móvil gestione los datos del paciente, registre comidas, consulte su dieta y vea su progreso. \\
API Controller & \code{NutritionistController} & Expone endpoints para que la aplicación web gestione el dashboard, la lista de pacientes, cree dietas y vea las métricas de sus clientes. \\
API Controller & \code{MealTrackingController} & Procesa las solicitudes de registro de comidas, incluyendo la recepción de imágenes para el análisis de IA. \\
User Interface & Aplicación móvil (cliente) & Interfaz para el paciente, desarrollada en Flutter o React Native. Permite la interacción con la API. \\
User Interface & Aplicación web (nutricionista) & Interfaz para el nutricionista, desarrollada en React o Angular. Permite la interacción con la API. \\
\bottomrule
\end{tabularx}

### Application Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Application del contexto IAM}\label{tab:iam-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Application Service & \code{PatientManagementService} & Orquesta los casos de uso relacionados con la gestión de pacientes, como la asignación de un nutricionista y la actualización de datos personales.\\
Application Service & \code{DietService} & Maneja la lógica de creación, asignación y actualización de dietas por parte de los nutricionistas.\\
Application Service & \code{MealTrackingService} & Coordina el proceso de registro de una comida, desde la recepción de datos hasta la comunicación con el servicio de IA y el cálculo de macronutrientes.\\
Application Service & \code{DashboardService} & Procesa y agrega los datos necesarios para construir los dashboards tanto del paciente como del nutricionista.\\
Application Service & \code{NotificationService} & Gestiona la creación y el envío de notificaciones a los usuarios según las acciones que ocurren en el sistema (por ejemplo, nueva dieta asignada).\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos de la capa Infrastructure del contexto IAM}\label{tab:iam-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Database & \code{FoodlyticsDB (PostgreSQL)} & Sistema de base de datos relacional que proporciona persistencia a todas las entidades del dominio.\\
ORM Framework & \code{SQLAlchemy} & Abstrae la comunicación con la base de datos \code{PostgreSQL}, mapeando las entidades del dominio a tablas.\\
External Service & \code{Google Identity Service} & Proveedor de identidad externo utilizado para la autenticación y autorización de usuarios (\code{OAuth 2.0}).\\
External Service & \code{AI Food Recognition API} & Servicio externo de IA que recibe imágenes de comidas y devuelve información sobre alimentos y macronutrientes.\\
File Storage & \code{Cloud Storage (e.g., S3/GCS)} & Servicio para almacenar archivos subidos por los usuarios, como imágenes de perfil o fotos de comidas.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Identity and Access Management (Component Level Diagram)](src/img/cap5/Iam/Componentes.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Identity and Access Management (Layer Class Diagram)](src/img/cap5/Iam/Clases.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Identity and Access Management (Database Design Diagram )](src/img/cap5/Iam/BD.png)

## Bounded Context: Profile

### Domain Layer 

\begin{tabularx}{\textwidth}{L{0.25\textwidth}L{0.30\textwidth}Y}
\caption{Elementos del dominio del contexto Profile}\label{tab:profile-domain}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción}\\
\midrule
Aggregate Root & \code{Profile} & Representa la información personal de un usuario dentro del sistema. Es el punto central de este contexto. Contiene datos como nombre, género, contacto y fechas de registro.\\
Entity (referencia externa) & \code{User} & Entidad referenciada desde el contexto \code{IAM (Identity Access Management)}. Relación lógica mediante \code{user\_id}. No se persiste aquí.\\
\bottomrule
\end{tabularx}

### Interface Layer  

\begin{tabularx}{\textwidth}{L{0.18\textwidth}L{0.27\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Interface del contexto Profile}\label{tab:profile-interface}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Controller & \code{ProfileController} & Expone endpoints REST para crear, obtener y actualizar perfiles de usuario. & Se comunica con los servicios de la capa de aplicación.\\
Resource & \code{ProfileResource} & Representa los datos de un perfil en las respuestas HTTP. & Generado desde la entidad \code{Profile}.\\
Transform & \code{ProfileTransform} & Convierte entre la entidad \code{Profile} y su \code{ProfileResource}. & Evita exponer directamente la capa de dominio.\\
\bottomrule
\end{tabularx}

### Application Layer 

\begin{tabularx}{\textwidth}{L{0.18\textwidth}L{0.25\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Application del contexto Profile}\label{tab:profile-application}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Command & \code{CreateProfileCommand} & Solicitud para registrar un nuevo perfil asociado a un usuario. & Contiene \code{user\_id}, \code{first\_name}, \code{last\_name}, \code{gender}, \code{contact\_phone}.\\
Command & \code{UpdateProfileCommand} & Solicitud para modificar los datos personales de un perfil existente. & Contiene campos opcionales de actualización.\\
Query & \code{GetProfileByUserIdQuery} & Permite recuperar el perfil asociado a un usuario. & Devuelve un objeto \code{Profile}.\\
Service & \code{ProfileCommandService} & Gestiona operaciones de creación y actualización de perfiles. & Aplica reglas de negocio básicas antes de persistir.\\
Service & \code{ProfileQueryService} & Gestiona la lectura de perfiles desde el repositorio. & Se usa en consultas \code{GET}.\\
Repository Interface & \code{ProfileRepository} & Abstracción para la persistencia de entidades \code{Profile}. & Implementado en la capa de infraestructura.\\
\bottomrule
\end{tabularx}

### Infrastructure Layer  

\begin{tabularx}{\textwidth}{L{0.20\textwidth}L{0.28\textwidth}Y L{0.25\textwidth}}
\caption{Elementos de la capa Infrastructure del contexto Profile}\label{tab:profile-infrastructure}\\
\toprule
\textbf{Tipo} & \textbf{Nombre} & \textbf{Descripción} & \textbf{Relación / Comentario}\\
\midrule
Repository Implementation & \code{SQLAlchemyProfileRepository} & Implementación concreta del repositorio de perfiles con SQLAlchemy. & Gestiona operaciones CRUD sobre la tabla \code{profile}.\\
ORM Model & \code{ProfileModel} & Mapea la entidad de dominio \code{Profile} a la base de datos \code{PostgreSQL}. & Define columnas y restricciones (\code{id}, \code{user\_id}, \code{first\_name}, etc.).\\
Database Table & \code{profile} & Tabla persistente que almacena los datos de perfil. & Campos: \code{id}, \code{user\_id}, \code{first\_name}, \code{last\_name}, \code{gender}, \code{contact\_phone}, \code{updated\_at}, \code{created\_at}.\\
ACL Adapter & \code{UserClientAdapter} & Conector hacia el contexto \code{IAM} para validar existencia del usuario (\code{user\_id}). & Se invoca antes de crear un perfil.\\
\bottomrule
\end{tabularx}

### Bounded Context Software Architecture Component Level Diagrams 

Debido a que se está planteando una arquitectura monolitica, se están repartiendo los componentes mediante los *Bounded Context*. 

![Profile (Component Level Diagram)](src\img\cap5\Profile\Emergentes-Profile.drawio.png)

### Bounded Context Software Architecture Code Level Diagrams  

#### Bounded Context Domain Layer Class Diagrams  

**Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.**

*En este diagrama se crearon las clases necesarias para el desarrollo de un bounded context*

![Profile (Layer Class Diagram)](src/img/cap5/Profile/CLASES.png)

#### Bounded Context Database Design Diagram  

*Python no cuenta con interfaces ni records, por lo que se opta por usar Abstract Classes y Dataclasses.*

![Profile (Database Design Diagram )](src/img/cap5/Profile/ERD.png)
