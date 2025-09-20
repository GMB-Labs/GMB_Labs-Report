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

Para construir una solución digital que responda de manera efectiva al dominio de la nutrición y el cuidado de la salud, es necesario comprender en profundidad a los usuarios, sus necesidades y el contexto en el que interactuarán con la aplicación. Este capítulo aborda el proceso de Requirements Elicitation & Analysis, etapa fundamental para garantizar que Foodlytics se desarrolle como una herramienta alineada a las expectativas del mercado y con un impacto positivo en la vida de pacientes y profesionales de la salud.

En esta fase se identifican y analizan los requerimientos del público objetivo, se estudia la oferta existente en el mercado y se emplean técnicas como entrevistas, análisis competitivo, mapeo de tareas y escenarios de uso. Todo ello permite definir de manera clara los requisitos funcionales y no funcionales del sistema. La información obtenida en este capítulo constituye la base sólida para el diseño y la implementación de una solución tecnológica innovadora, con capacidad de mejorar la adherencia a los planes nutricionales y optimizar el trabajo de los especialistas.

\newpage

## Competidores

![Recurso extraído de Canva](src/img/cap2/competidores-introduccion.png)

Después de realizar un análisis del mercado, se identificaron diversas plataformas y aplicaciones que ofrecen servicios vinculados a la nutrición digital, el seguimiento alimenticio y la salud preventiva. Estas soluciones constituyen referencias relevantes, ya que presentan características orientadas a resolver problemas similares a los abordados por Foodlytics, tales como el registro de la dieta diaria, la adherencia a planes nutricionales y la interacción entre pacientes y profesionales de la salud.

El estudio de estos competidores permite reconocer fortalezas y limitaciones en sus propuestas, lo cual representa un insumo fundamental para identificar oportunidades de mejora y diseñar una propuesta de valor diferencial. De esta manera, Foodlytics podrá posicionarse como una alternativa innovadora y adaptada al contexto local, aportando beneficios concretos tanto a pacientes como a especialistas en nutrición y medicina deportiva.

\newpage


**Competidores:**

- ***MyFitnessPal:*** Es una de las aplicaciones de nutrición más utilizadas a nivel mundial. Permite registrar alimentos, contar calorías y realizar un seguimiento de macronutrientes. Su ventaja radica en la base de datos global de alimentos y su integración con dispositivos de salud (relojes inteligentes, apps de ejercicio). Sin embargo, no está diseñada específicamente para el contexto peruano y carece de un componente directo de interacción entre nutricionista y paciente.

![Imagen extraída de MyFitnessPal [(URL)](https://www.myfitnesspal.com/es)](src/img/cap2/MyFitnessPal-landing.png)

\vspace{1em}

- ***Nutrify:*** Es una aplicación presente en varios países de Latinoamérica que se centra en la gestión de pacientes para nutricionistas. Ofrece herramientas para planificar dietas, enviar recordatorios y dar seguimiento al progreso de los pacientes. Su fortaleza está en que está adaptada a la realidad latinoamericana, pero se enfoca más en generar planes y menús que en la recolección de datos del paciente en tiempo real mediante fotos o retroalimentación interactiva.

![Imagen extraída de Nutrify [(URL)](https://nutrify.io/)](src/img/cap2/Nutrify-landing.png)

\newpage

- ***Google Fit*** Es una aplicación de salud y bienestar desarrollada por Google. Está disponible de forma gratuita en Android y también se puede sincronizar con dispositivos iOS mediante Google Health Connect. Su objetivo principal es el monitoreo integral de la actividad física y la salud.

![Imagen extraída de Google Fit [(URL)](https://www.google.com/fit/)](src/img/cap2/GoogleFit-landing.png)

\vspace{1em}

- ***Nutrium:*** Es un software para nutricionistas que combina gestión de pacientes, planificación de dietas y seguimiento del progreso. Su fortaleza es ofrecer un ecosistema integral para profesionales, con recordatorios y comunicación directa con los pacientes. Sin embargo, no cuenta con reconocimiento automático de alimentos por imágenes y su base de datos no está adaptada al contexto peruano.

![Imagen extraída de Nutrium [(URL)](https://nutrium.com/es/professionals?gad_source=1&gad_campaignid=22771486204&gbraid=0AAAAADfQ3ofimzajEaWw5uP39K7JmbCxW&gclid=Cj0KCQjw267GBhCSARIsAOjVJ4EVhNU-t-XwvyVAUj2iCTc8oVZQtl1vYb_d7P96jMWgLa0kUh2v5QsaAg2xEALw_wcB)](src/img/cap2/Nutrium-landing.png)

\newpage



### Análisis competitivo  

Tras haber identificado a los principales actores en el ámbito de la nutrición digital y la salud preventiva, se presenta a continuación un análisis comparativo que permite evaluar sus propuestas de valor. Este análisis se centra en aspectos clave como el enfoque de mercado, las funcionalidades principales, el nivel de especialización y los elementos diferenciadores. La finalidad es reconocer patrones, ventajas competitivas y áreas de oportunidad que orienten el posicionamiento estratégico de Foodlytics, asegurando que su propuesta responda de manera efectiva a las necesidades de pacientes y profesionales de la salud en el contexto peruano.

![](src/img/cap2/analisisCompetitivo_1.png)

![](src/img/cap2/analisisCompetitivo_2.png)

![](src/img/cap2/analisisCompetitivo_3.png)

\newpage

### Estrategias y tácticas frente a competidores  

En el cambiante entorno de la salud digital y la nutrición personalizada, desarrollar estrategias competitivas efectivas implica no solo conocer las capacidades internas de la organización, sino también adaptarse de forma proactiva a las tendencias tecnológicas y las expectativas del mercado.

\begin{quote}
Una estrategia digital bien diseñada es clave para el éxito competitivo en el sector salud, ya que permite atraer pacientes, fortalecer la marca y adaptarse a las tendencias tecnológicas emergentes (Cutipa-Coro, 2024)
\end{quote}

\vspace{1em}

Este enfoque resulta clave para identificar oportunidades de diferenciación, incorporar herramientas tecnológicas innovadoras y anticipar los cambios en las dinámicas de consumo de salud y bienestar.

En este contexto, Foodlytics —una solución basada en inteligencia artificial orientada a mejorar la alimentación y la gestión nutricional— ha llevado a cabo un análisis competitivo que le ha permitido mapear a los principales actores del mercado, detectar tendencias emergentes y encontrar espacios estratégicos aún poco aprovechados.

A partir de este diagnóstico, se presentan a continuación las estrategias y tácticas que permitirán a Foodlytics fortalecer su ventaja competitiva, adaptarse a las nuevas exigencias del sector y consolidar su liderazgo en el ámbito de la salud digital personalizada.

\vspace{1em}

**Estrategias competitivas para Foodlytics**

\vspace{1em}

::: box
**Diferenciación cultural con base en alimentos locales**
:::

**Estrategia:** Foodlytics debe posicionarse como la primera plataforma de nutrición digital que reconoce y analiza platos típicos peruanos y latinoamericanos, resolviendo la brecha cultural de las apps globales.

**Tácticas propuestas:**

  - Entrenar la IA con un banco de imágenes de platos peruanos (ej. lomo saltado, ají de gallina) y de la región.

  - Generar reportes comparativos de consumo local vs. recomendaciones nutricionales internacionales.

  - Establecer un ciclo de actualizaciones periódicas basado en retroalimentación de pacientes y especialistas.

\vspace{2em}

::: box
**Inteligencia Artificial como ventaja competitiva central**
:::

**Estrategia:** A diferencia de Nutrify o Nutrium, Foodlytics debe basar su propuesta en la captura de datos en tiempo real a través de IA, reduciendo la carga manual de pacientes y aumentando la adherencia.

**Tácticas propuestas:**

  - Optimizar la velocidad y precisión del reconocimiento de alimentos.

  - Permitir correcciones manuales rápidas que alimenten el modelo.

  - Convertir cada interacción en un dataset que fortalezca la IA (aprendizaje continuo).

\vspace{2em}

::: box
**Segmentación según perfil de usuario**
:::

**Estrategia:** La propuesta de Foodlytics debe adaptarse a las necesidades de pacientes jóvenes/adultos en control de peso o rendimiento deportivo, y a nutricionistas que gestionan múltiples pacientes.

**Tácticas propuestas:**

  - Diseñar planes escalables para pacientes (gratuito/premium) y profesionales (suscripción mensual o institucional).

  - Personalizar dashboards clínicos según tipo de especialista (nutricionista clínico, deportivo o de consulta privada).

  - Implementar campañas educativas en redes sociales y webinars según el perfil del usuario objetivo.

\vspace{2em}

::: box
**Integración con la práctica clínica**
:::

**Estrategia:** Foodlytics debe ser más que una app de registro, convirtiéndose en un aliado de los nutricionistas en la consulta, con reportes automáticos y paneles que ahorren tiempo de análisis.

**Tácticas propuestas:**

  - Incluir gráficos comparativos de evolución (peso, IMC, calorías).

  - Generar reportes exportables para historia clínica digital.

  - Ofrecer módulos adicionales para nutrición deportiva y control preventivo de enfermedades crónicas.

\vspace{2em}

::: box
**Construcción de redes y alianzas estratégicas**
:::

**Estrategia:** Foodlytics debe fortalecer su posicionamiento a través de alianzas con clínicas, universidades y asociaciones de nutricionistas que validen la confiabilidad del sistema y faciliten su adopción en la práctica profesional.

**Tácticas propuestas:**

  - Establecer convenios con clínicas privadas y consultorios nutricionales para validar la herramienta en entornos reales.

  - Vincularse con asociaciones profesionales de nutricionistas para generar credibilidad.

  - Integrarse con dispositivos de salud (básculas inteligentes, relojes deportivos) para ampliar el ecosistema de valor.

\vspace{3em} 

**Tácticas Específicas para para el Fortalecimiento de *Foodlytics***

\vspace{1em}

::: box
**Posicionamiento como la app de nutrición “localizada” para Perú y Latinoamerica**
:::

**Táctica:**  
Construir una identidad de marca confiable que comunique el valor de Foodlytics como solución accesible, científica y culturalmente adaptada, destacando su capacidad para mejorar la adherencia a planes nutricionales y la práctica profesional de los especialistas.

**Acciones:**

  - Crear campañas gráficas y audiovisuales que muestren casos reales de pacientes que mejoraron su alimentación usando la app.

  - Participar en congresos de nutrición, ferias de salud y espacios universitarios para aumentar la visibilidad académica y profesional.

  - Adaptar los mensajes de comunicación según el público: pacientes (simplicidad y motivación) y nutricionistas (precisión y ahorro de tiempo).

\vspace{2em}

::: box
**Mejora continua del reconocimiento automático de alimentos**
:::

**Táctica:**  
Mantener la IA como el núcleo diferenciador del producto, asegurando precisión y confianza clínica.

**Acciones:**

  - Implementar entrenamientos periódicos con datasets de imágenes de platos peruanos y latinos.

  - Permitir que los usuarios corrijan manualmente errores y usar esa data como retroalimentación para entrenar al modelo.
  
  - Integrar validaciones con nutricionistas: panel de revisión donde especialistas confirmen datos de porciones y nutrientes.

\vspace{2em}

::: box
**Optimización continua de la experiencia de usuario (UX)**
:::

**Táctica:** Garantizar que tanto la app de pacientes como el panel web para nutricionistas sean intuitivos, rápidos y funcionales, priorizando la simplicidad de registro y la claridad en los reportes clínicos.

**Acciones:**

   - Implementar un sistema de feedback en la app para recibir sugerencias de pacientes y profesionales.

   - Realizar pruebas de usabilidad con grupos de nutricionistas y jóvenes pacientes para detectar fricciones en la interfaz.

   - Ajustar la app para minimizar el tiempo de registro de comidas y ofrecer reportes automáticos en formatos fáciles de interpretar.

\vspace{2em}

::: box
**Adherencia y motivación de pacientes**
:::

**Táctica:** Evitar el abandono de la app creando mecanismos de motivación continua y personalización.

**Acciones:**

   - Diseñar notificaciones inteligentes: felicitaciones al registrar comidas, recordatorios cuando omiten registros o metas alcanzadas.

   - Crear retos cortos (“Registra tus comidas 7 días seguidos”) con recompensas digitales.

   - Generar dashboards simples donde el paciente pueda ver visualmente su progreso (peso, calorías, macros).

\vspace{2em}

::: box
**Fidelización de profesionales y pacientes:**
:::

**Táctica:** Fortalecer las relaciones de largo plazo con nutricionistas y pacientes, creando un ecosistema de soporte y motivación que incremente la adherencia y reduzca el abandono de la app.

**Acciones:**

   - Crear un programa de referidos que ofrezca beneficios (descuentos o funciones premium) a quienes inviten a colegas o pacientes.

   - Brindar capacitaciones virtuales y guías prácticas a los nutricionistas para optimizar el uso del panel clínico.

   - Generar notificaciones personalizadas y reportes periódicos que motiven a los pacientes y refuercen el vínculo con su especialista.

\newpage

## Entrevistas  

Las entrevistas fueron diseñadas como técnica principal de recolección cualitativa para comprender tanto aspectos objetivos (edad, ocupación, nivel educativo, acceso a tecnología) como subjetivos (hábitos alimenticios, motivaciones para mejorar su nutrición, frustraciones con el uso de aplicaciones actuales y expectativas respecto a herramientas digitales). Esta información resulta esencial para la construcción de arquetipos de usuarios (User Personas), así como para la elaboración de Empathy Maps y Journey Maps que orienten el diseño centrado en el usuario de Foodlytics.

![Recurso extraído de Canva](src/img/cap2/entrevistas-introduccion.png)

::: note
Para acceder al video de las entrevistas, haga click en la [URL](enlace entrevistas)
:::

\newpage

### Diseño de entrevistas  

Para el diseño de entrevistas se definieron dos segmentos objetivo con perfiles claramente diferenciados: **Médicos Nutricionistas o del deporte** y **Pacientes**. 

::: box
**Segmento Objetivo 1:** Médicos Nutricionistas o del deporte
:::

**Objetivo:**

Explorar cómo los nutricionistas gestionan actualmente a sus pacientes, qué herramientas usan, cuáles son sus principales dificultades en el control de dietas y rutinas, y conocer su interés en usar soluciones tecnológicas de apoyo.

**Perfil general**

1) ¿Podría indicarnos su nombre, edad y especialidad? 

2) ¿Hace cuánto tiempo ejerce como nutricionista o médico especialista? 

3) ¿Atiende principalmente en consultorio privado, clínica u hospital? 

**Gestión actual de pacientes**

4) ¿Cómo lleva actualmente el registro de dietas y rutinas de sus pacientes? (Ejemplo: cuadernos, Excel, apps)

5) ¿Con qué frecuencia actualiza los planes de alimentación de sus pacientes?

6) ¿Qué tan confiables considera los reportes que le dan sus pacientes sobre su consumo de alimentos?

**Uso de herramientas y tecnología**

7) ¿Ha probado antes alguna herramienta digital o app para seguimiento nutricional? ¿Cuál fue su experiencia?

8) ¿Qué limitaciones encuentra en los métodos actuales de seguimiento (ejemplo: falta de datos reales, poca adherencia del paciente)?

9) ¿Qué tan dispuesto estaría a usar un sistema con IA que reconozca alimentos y calcule macros automáticamente?

**Interés y expectativas sobre soluciones digitale**

10) ¿Qué funcionalidades considera más útiles en una plataforma de este tipo?
   - Seguimiento de la dieta en tiempo real
   - Reportes automáticos de calorías y macros 
   - Registro de peso y evolución 
   - Panel de control con reportes por paciente 

11) ¿Qué beneficios cree que traería para su práctica profesional contar con una app así? 

12) ¿Qué obstáculos ve para implementar una herramienta digital en su consulta? (ejemplo: tiempo de uso, costos, confianza en IA, resistencia de pacientes) 

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación 
:::

**Objetivo:**  
Entender cómo los pacientes perciben el control de su dieta, sus frustraciones con los métodos actuales, su interés en usar tecnología para registrar lo que comen y su disposición a pagar por un servicio que mejore su salud y seguimiento.

**Perfil general** 

1) ¿Cuál es su nombre, edad y ocupación? 

2) ¿Actualmente sigue un plan nutricional? ¿Con qué frecuencia visita a un nutricionista? 

3) ¿Ha usado alguna aplicación o método para controlar su dieta y peso? 

**Experiencia y percepción actual**  

4) ¿Cómo suele registrar o recordar lo que come en el día?

5) ¿Qué tan difícil le resulta seguir las recomendaciones de su nutricionista?

6) ¿Cuál ha sido su mayor frustración al intentar mejorar su alimentación o controlar su peso?

**Uso y apertura a tecnología** 

7) ¿Qué tipo de celular usa actualmente (Android o iPhone)?

8) ¿Usa apps relacionadas con salud o nutrición? ¿Cuáles y para qué?

9) ¿Le gustaría que una aplicación móvil le calcule automáticamente calorías y macros a partir de fotos de sus comidas? ¿Por qué?

10) ¿Le sería útil recibir notificaciones automáticas (ejemplo: recordatorios de comida, control de peso, alertas de metas)?


**Confianza y motivación** 

11) ¿Qué es lo que más le generaría confianza en una aplicación móvil de nutrición? (ejemplo: respaldo del nutricionista, precisión de datos, facilidad de uso)

12) ¿Qué tendría que pasar para que dejara de usar la app?

13) ¿Confía más en su propio registro manual, en lo que le indica el nutricionista, o en una app con IA que lo acompañe diariamente?

**Valor percibido y disposición de pago** 

14) Si una aplicación le ayudara a mejorar su salud y mantener sus metas, ¿estaría dispuesto/a a pagar por ella?

15) ¿Qué características debería tener para sentir que vale la pena el costo?

16) Imagine su sistema de nutrición ideal:
  - ¿Cómo le informaría sobre sus progresos? 
  - ¿Qué vería en su celular? 
  - ¿Qué control tendría usted mismo?

\newpage

### Registro de entrevistas 

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

Luisa Fernanda Gutiérrez Herrera es licenciada en nutrición desde 2009, con especialidad en nutrición clínica y oncología. Se desempeña en un hospital de alta complejidad en Trujillo y también en consulta privada. En su práctica, utiliza un sistema manual basado en *cardex* para registrar dietas y evolución de pacientes; sin embargo, menciona que actualmente cuenta con una aplicación institucional en fase de implementación, aunque esta no está completamente desarrollada y aún presenta limitaciones que la hacen poco práctica para su día a día.

Sobre los reportes de pacientes, considera que no siempre son confiables, ya que algunos omiten información o cambian de opinión constantemente respecto a su dieta. Aunque ha probado sistemas digitales básicos para notas de ingreso y evaluaciones nutricionales, destaca que la mayoría de ellos son costosos y poco adaptados a la práctica clínica cotidiana.

Frente a la posibilidad de usar una aplicación con inteligencia artificial que reconozca alimentos y calcule automáticamente calorías y macronutrientes, afirma que sería de gran utilidad, pues reduciría el tiempo de cálculo y permitiría un seguimiento más preciso en casos complejos, como niños y pacientes hospitalizados con desnutrición. Además, considera fundamental que la aplicación se base en una tabla nutricional confiable y adaptada a alimentos peruanos, lo que garantizaría la veracidad de la información.

Resalta que la falta de herramientas digitales efectivas dificulta el seguimiento detallado de pacientes, sobre todo en contextos complejos como la oncología o la desnutrición infantil. En Trujillo, la alta prevalencia de desnutrición hace indispensable contar con registros confiables y mediciones frecuentes de peso, talla y consumo real de alimentos. La ausencia de este control riguroso retrasa intervenciones oportunas y compromete la recuperación de pacientes vulnerables.

Finalmente, advierte que el éxito de la solución dependerá de que sea ágil, intuitiva y fácil de integrar en la rutina clínica. Un sistema engorroso podría ser descartado rápidamente, mientras que una herramienta confiable y sencilla podría mejorar la eficiencia del profesional, la adherencia de los pacientes y la calidad del servicio de nutrición en el país.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS11.png)

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
Gainella Rodríguez, licenciada en nutrición clínica con 29 años de edad, cuenta con alrededor de 10 años de experiencia profesional y actualmente se desempeña en un hospital nacional del sector público. Su práctica combina registros en historias clínicas físicas con el Sistema de Gestión de Servicios de Salud  ***SGSS*** ( herramienta informática desarrollada en entorno web, que permite el registro e integración de las actividades asistenciales y administrativas), donde documenta evolución nutricional y diagnósticos de pacientes. Además, ha utilizado herramientas digitales básicas como Google Drive para registrar y dar seguimiento a la información, aunque reconoce que estos métodos siguen siendo limitados en precisión y agilidad.

Explica que en pacientes hospitalizados las actualizaciones nutricionales son diarias, mientras que en consulta externa se realizan mensualmente. Reconoce, sin embargo, que los reportes entregados por pacientes, en especial adultos mayores, suelen ser poco confiables debido a olvidos o dificultad para estimar cantidades. Para superar esta brecha, emplea imágenes o medidas caseras que facilitan el recuerdo de los alimentos consumidos.

Valora positivamente la propuesta de una aplicación como Foodlytics, ya que considera que el registro fotográfico con análisis automático de calorías y macronutrientes permitiría un seguimiento más preciso, reduciendo tiempos de consulta y mejorando la educación alimentaria del paciente. Además, resalta que el sistema podría integrar información relevante como antecedentes patológicos, consumo de medicamentos y evaluaciones antropométricas (peso, pliegues cutáneos, análisis bioquímicos), lo que lo convertiría en una herramienta más completa y clínica.

Entre los beneficios más importantes identifica el ahorro de tiempo en la atención, la posibilidad de personalizar planes nutricionales y la educación directa del paciente mediante visualizaciones claras de su consumo. Sin embargo, advierte sobre riesgos como la confidencialidad de datos sensibles, la resistencia tecnológica de adultos mayores y la limitada disponibilidad de dispositivos móviles en ciertos sectores. Finalmente, recalca la importancia de que la plataforma se respalde en guías de la OMS y referencias científicas, para generar confianza en los profesionales de salud y garantizar la validez de los cálculos.


![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS12.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Graciela del Rocío Alza \\ \hline
\textbf{Edad}                 & 50 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Nutricionista especializada en nutrición deportiva \\ \hline
\textbf{Tiempo de entrevista} & 20:41 - 30:34 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Graciela del Rocío Alza es nutricionista con más de 25 años de experiencia en el ámbito clínico y deportivo. Actualmente trabaja en una clínica privada en Lima y ofrece consultas particulares a pacientes que buscan mejorar su rendimiento físico y su estado de salud general. Su práctica combina el uso de hojas de cálculo y aplicaciones básicas como Excel y WhatsApp, donde los pacientes suelen enviar fotos de sus comidas. No obstante, reconoce que estos métodos son poco sistemáticos, lo que dificulta llevar un control confiable de la adherencia a los planes nutricionales.

Explica que uno de los mayores retos en su trabajo es el seguimiento detallado de la ingesta calórica y proteica, especialmente en deportistas y pacientes con requerimientos específicos. Señala que los pacientes jóvenes tienden a registrar sus consumos de forma más activa, mientras que los adultos muestran menor constancia, lo que genera vacíos en la información.

Respecto a la propuesta de Foodlytics, considera que la app sería altamente beneficiosa al permitir el reconocimiento automático de alimentos mediante fotos, con cálculos inmediatos de calorías y macronutrientes. Para los nutricionistas, el panel web clínico representaría una ventaja significativa, ya que facilitaría la comparación de progresos y el ajuste de planes sin depender de registros manuales.

Graciela subraya que, además de la precisión en los cálculos, la aplicación debería incluir un módulo de recordatorios y alertas motivacionales que ayude a los pacientes a mantener la adherencia. También recomienda que se incorporen opciones para registrar suplementos nutricionales y horarios de ingesta, aspectos especialmente relevantes en la nutrición deportiva.

Finalmente, advierte que el éxito de Foodlytics dependerá de su facilidad de uso y de que esté adaptada a la realidad peruana, con bases de datos de alimentos locales. Concluye que, si cumple con estas condiciones, se convertiría en una herramienta clave no solo para pacientes jóvenes, sino también para profesionales con amplia trayectoria que buscan digitalizar su práctica.


![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS13.png)

\newpage

::: box
**Segmento Objetivo 2:** Pacientes con interés en mejorar su alimentación
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Elizabeth Quedina \\ \hline
\textbf{Edad}                 & 59 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Contadora \\ \hline
\textbf{Tiempo de entrevista} & 30:34 - 35:14 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Elizabeth Quedina, de 59 años, trabaja como contadora y muestra un interés creciente en mejorar su alimentación. Actualmente, sus visitas al nutricionista son esporádicas —aproximadamente una vez al año— y se basa principalmente en un recetario inicial para organizar sus comidas, reduciendo el consumo de arroz y priorizando verduras según las indicaciones médicas. Reconoce que no utiliza aplicaciones móviles para el control de la dieta ni herramientas de seguimiento, lo que limita la precisión de sus registros.

Al describir sus hábitos, menciona que suele recordar mentalmente qué alimentos puede consumir y organiza sus comidas de forma intuitiva, sin un control sistemático. Considera que una aplicación con inteligencia artificial que calcule automáticamente calorías y macronutrientes a partir de fotos sería muy útil, ya que le permitiría llevar un control más práctico y constante. Además, valora positivamente la posibilidad de recibir notificaciones automáticas como recordatorios de comidas o alertas sobre metas nutricionales, pues admite que con frecuencia se olvida de comer de manera ordenada debido a su carga laboral.

Destaca que la facilidad de uso y la precisión de los datos son los factores que más le generarían confianza en una app de este tipo. Está dispuesta a pagar por el servicio siempre que la aplicación le proporcione horarios claros, alarmas para recordarle qué alimentos consumir y reportes sobre sus progresos semanales. Señala que dejaría de usarla únicamente si logra cumplir sus metas nutricionales, aunque reconoce que el control alimenticio debería ser un proceso continuo.

Finalmente, Elizabeth enfatiza que una aplicación como Foodlytics no solo simplificaría su rutina, sino que también se convertiría en un apoyo motivacional para mantener hábitos saludables en el tiempo.


![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS21.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Carlos Sánchez \\ \hline
\textbf{Edad}                 & 22 años \\ \hline
\textbf{Ubicación geográfica} & Lima, Perú \\ \hline
\textbf{Cargo}                & Estudiante de Ingeniería en la UPC \\ \hline
\textbf{Tiempo de entrevista} & 00:00 - 10:34 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**
Carlos Sánchez, estudiante de 22 años en la Universidad Peruana de Ciencias Aplicadas (UPC), visita al nutricionista una o dos veces cada seis meses. Actualmente utiliza aplicaciones digitales como MyFitnessPal para registrar su alimentación diaria y la app vinculada a su balanza digital para monitorear su peso. Además, emplea una pulsera inteligente para medir calorías quemadas y calidad de sueño.

Reconoce que seguir los planes nutricionales le resulta difícil por falta de tiempo y por el esfuerzo que requiere cocinar y medir calorías. Estas limitaciones lo llevan con frecuencia a recurrir a comida rápida o snacks poco saludables. Identifica el tiempo y la organización como sus principales frustraciones al intentar mejorar su alimentación.

Valora positivamente la idea de una aplicación que, mediante fotos, calcule automáticamente calorías y macronutrientes, ya que le ahorraría el proceso de pesar y medir alimentos. Considera fundamental la precisión de los datos, pues desconfía cuando las apps presentan valores diferentes a los empaques de los productos. También vería útil recibir notificaciones automáticas de recordatorios de comidas y metas nutricionales, dado que suele olvidar mantener su dieta.

Está dispuesto a pagar por la aplicación siempre que garantice precisión y facilidad de uso. Además, sugiere que se incorporen funcionalidades adicionales, como recomendaciones personalizadas ajustadas al presupuesto, lo cual sería de gran ayuda para estudiantes. Sobre los reportes de progreso, prefiere un esquema combinado: reportes semanales para seguimiento inmediato y uno mensual más completo para evaluar resultados generales.

Concluye que su permanencia en el uso de la aplicación dependería de que los cálculos sean confiables y la experiencia de usuario sencilla. De ser así, afirma que la adoptaría de manera continua.


![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS22.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & n \\ \hline
\textbf{Edad}                 & n \\ \hline
\textbf{Ubicación geográfica} & n \\ \hline
\textbf{Cargo}                & n \\ \hline
\textbf{Tiempo de entrevista} & 00:00 - 10:34 \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**



![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaS23.png)

\newpage


### Análisis de entrevistas

:::
**Segmento Objetivo 1:** Médicos nutricionistas o del deporte
:::

**Perfil Demográfico**

- **Edades:** Entre 29 y 50 años, con un promedio aproximado de 36 años.

- **Ubicación geográfica:** Principalmente en ciudades urbanas como Trujillo y Lima.

**Cargos ocupados:**

- Nutricionista clínica con especialización en oncología.

- Nutricionista en hospital público.

- Nutricionista deportiva en clínica privada.

Este segmento está compuesto por profesionales con formación especializada y más de 10 años de experiencia promedio. Desempeñan labores en hospitales, clínicas y consultas privadas, atendiendo tanto a pacientes con enfermedades crónicas como a deportistas y población general.

**Experiencia y Conocimientos sobre Nutrición Digital**

Los nutricionistas entrevistados muestran un panorama mixto respecto al uso de tecnología. Aunque en algunos contextos ya emplean aplicaciones institucionales o el *SGSS* (Sistema de Gestión de Servicios de Salud), estas plataformas aún presentan limitaciones de usabilidad y adaptación a la práctica clínica cotidiana. La mayoría depende de herramientas básicas como hojas de cálculo, notas manuales o incluso *WhatsApp* para el envío de fotos de comidas por parte de los pacientes.

Los principales problemas identificados fueron:

- Información incompleta o poco confiable entregada por los pacientes (olvidos, estimaciones imprecisas).

- Falta de adaptación cultural de las apps globales, que no incluyen alimentos locales peruanos.

- Alto costo y poca accesibilidad de sistemas digitales especializados.

- Escasa automatización en el cálculo de calorías, macronutrientes y reportes clínicos.

**Herramientas y Tecnología Actual**

- **Herramientas usadas:**

  - SGSS en hospitales públicos (registro administrativo y clínico).

  - Aplicaciones institucionales en fase inicial de implementación.

  - Google Drive y hojas de Excel como registros complementarios.

  - Comunicación por WhatsApp para recibir evidencia de consumo alimenticio.

- **Brechas tecnológicas:**

  - Ausencia de un sistema integral que combine IA, registro fotográfico y panel clínico.

  - Dificultad para obtener datos antropométricos y bioquímicos integrados en un mismo espacio.

  - Falta de trazabilidad en el seguimiento entre consulta presencial y rutina diaria del paciente.


**Intereses y Necesidades Tecnológicas**

Los nutricionistas entrevistados destacan el interés por una solución como Foodlytics, siempre que responda a sus necesidades reales:

- **Necesidades principales:**

  - Registro fotográfico con análisis automático de calorías y macronutrientes.

  - Base de datos confiable con alimentos peruanos y locales.

  - Panel clínico web que permita ver evolución de peso, talla y reportes de adherencia.

  - Módulos complementarios para antecedentes médicos, medicamentos y suplementos.

  - Recordatorios y alertas motivacionales para mejorar la adherencia del paciente.

- **Valor percibido:**

  - Ahorro de tiempo en la consulta.

  - Reportes clínicos más completos y confiables.

  - Mejora de la adherencia y motivación de los pacientes.

  - Reputación profesional al integrar tecnología moderna en la práctica clínica.

- **Viabilidad económica:**

  Aunque los costos son un factor crítico, se percibe que clínicas privadas y pacientes con interés en nutrición deportiva estarían dispuestos a invertir, siempre que la herramienta ofrezca beneficios claros y medibles.

**Preferencias y Comportamientos**

- **Comportamientos actuales:**

  - Uso combinado de registros manuales y herramientas digitales básicas.

  - Comunicación directa con pacientes vía WhatsApp.

  - Control antropométrico periódico con reportes físicos.

- **Cambios que buscan:**

  - Un sistema automatizado que reduzca la dependencia de reportes manuales.

  - Integración de todos los datos del paciente en una sola plataforma.

  - Soporte a la toma de decisiones con reportes visuales y objetivos.

En síntesis, los nutricionistas constituyen un segmento dispuesto a adoptar soluciones tecnológicas siempre que sean prácticas, confiables y culturalmente adaptadas. Una aplicación como Foodlytics tiene el potencial de convertirse en un aliado clave en la modernización de la nutrición clínica y deportiva en el Perú.

**Estadísticas y Porcentajes**

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico1.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico2.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico3.png)

![Creado en base a los datos recolectados en las entrevistas](src/img/cap2/grafico4.png)

\newpage

**Análisis de datos**

Las entrevistas realizadas permitieron identificar coincidencias importantes en el perfil y necesidades de los nutricionistas. Un hallazgo clave es que todos utilizan herramientas digitales básicas (Excel, WhatsApp, SGSS) pero reconocen que estas son insuficientes para garantizar precisión, trazabilidad y adherencia del paciente.

En cuanto al acceso tecnológico, se observa un uso diversificado de dispositivos: dos de las entrevistadas utilizan iOS y una Android en móviles, mientras que en laptops predominan los entornos de Windows (66.7%) frente a MacOS (33.3%). Esto sugiere que la plataforma debe ser multiplataforma y priorizar la accesibilidad en entornos comunes.

Respecto a las funcionalidades más mencionadas, destacan:

Registro fotográfico con IA y análisis automático de nutrientes, visto como la solución al principal dolor de los nutricionistas: la falta de precisión en reportes de pacientes.

Paneles clínicos con reportes automáticos y datos antropométricos, mencionados como clave para ahorrar tiempo y personalizar tratamientos.

Alertas y recordatorios motivacionales, percibidos como esenciales para combatir la falta de constancia de los pacientes.

::: note
En síntesis, los datos muestran que existe una brecha clara entre el nivel de digitalización actual y las necesidades clínicas de los nutricionistas. Aunque cuentan con herramientas básicas, la falta de precisión y personalización limita su efectividad. Una solución como Foodlytics, que combine IA para reconocimiento de alimentos, paneles clínicos adaptados al contexto peruano y mecanismos de motivación para pacientes, podría cerrar esta brecha y posicionarse como una herramienta estratégica para el sector.
:::



## Needfinding

Para diseñar soluciones que realmente respondan a los desafíos del transporte escolar, fue crucial comprender profundamente a los usuarios, sus contextos y sus experiencias. En un entorno donde aumentan las exigencias de seguridad, puntualidad y confianza, adoptar un enfoque centrado en el usuario permitió identificar no solo problemas evidentes, sino también necesidades latentes y oportunidades de innovación reales. 

\begin{quote}
Según Brown (2009), el diseño centrado en las personas comienza con una inmersión empática en la vida de los usuarios, observando lo que hacen, cómo piensan y qué sienten para revelar soluciones que de otro modo pasarían desapercibidas.
\end{quote}

\vspace{1em}

Durante esta etapa de needfinding, se aplicaron métodos como observación directa, entrevistas semiestructuradas y herramientas de empatía. Esto permitió descubrir tareas críticas, frustraciones y aspiraciones de padres, estudiantes, colegios y operadores. Además, se elaboraron perfiles de usuario, mapas de empatía y customer journeys que ayudaron a visualizar la experiencia completa, identificando puntos de fricción y momentos clave donde intervenir con soluciones más efectivas.

![Imagen extraída de Canva](src/img/cap2/intro_needfinding.png)

\newpage

### User Personas

Presentamos perfiles representativos de nuestros usuarios objetivos. Estos arquetipos nos ayudan a diseñar centrados en sus motivaciones, frustraciones y objetivos.

**Segmento  1: Médicos Nutricionistas / Nutricionistas Deportivos**

Frank Zane representa a profesionales con formación clínica o deportiva que atienden a pacientes con sobrepeso o que desean mejorar su rendimiento físico. Este perfil busca herramientas digitales que les permitan ofrecer un servicio más eficiente, moderno y con respaldo en datos objetivos.

- **Objetivos clave:** optimizar el tiempo de consulta, automatizar reportes y mejorar la adherencia de los pacientes.

- **Motivaciones:** diferenciarse como profesionales innovadores y mostrar evidencia clara de los progresos de sus pacientes.

- **Frustraciones:** pérdida de tiempo por información desordenada, falta de trazabilidad y métodos manuales poco ágiles (uso de cardex, hojas sueltas o mensajes por WhatsApp).

- **Necesidades implícitas:** una plataforma que integre funciones clínicas con una interfaz intuitiva, capaz de adaptarse al ritmo de la consulta sin requerir tiempo extra.

Este arquetipo inspira el diseño del dashboard web clínico, la automatización de reportes, y las funciones que convierten el registro de pacientes en una herramienta confiable de monitoreo.

![User Persona 1 - Recurso de UXPRESSIA](src/img/cap2/userperson1.png)


**Segmento 2:Pacientes con interés en mejorar su alimentación**

Mike Mentzer representa a adolescentes y jóvenes adultos con acceso a internet, motivados por metas físicas visibles, pero sin conocimientos técnicos sobre nutrición. Este perfil busca resultados rápidos, claridad en sus acciones y herramientas que lo guíen paso a paso.

- **Objetivos clave:** ganar masa muscular, controlar su dieta, mejorar su imagen y rendimiento.

- **Motivaciones:** alcanzar metas visibles que refuercen su disciplina, inspirarse en referentes fitness y destacar entre sus pares.

- **Frustraciones:** dificultad para calcular calorías, contradicciones en internet, y desmotivación por falta de seguimiento profesional.

- **Conductas comunes:** toma fotos de sus comidas, usa apps o redes sociales para buscar información, pero con baja constancia.

Este arquetipo orienta el diseño de la app móvil del paciente, especialmente en funcionalidades como el registro fotográfico automático, alertas personalizadas, visualización de progreso, y herramientas educativas fáciles de entender.

![User Persona 2 - Recurso de UXPRESSIA](src/img/cap2/userperson2.png)

\newpage

### User Task Matrix

Se ha mapeado la relación entre los distintos perfiles de usuarios y las tareas clave que realizan dentro del ecosistema de la solución. Esta matriz permite visualizar qué actividades son más relevantes para cada segmento, y con ello, priorizar las funcionalidades más críticas del sistema. De esta forma, se alinean las decisiones de diseño con las verdaderas necesidades y expectativas de los usuarios.

\begin{longtable}{|m{6cm}|m{4.5cm}|m{4.5cm}|}
\hline
\textbf{Tarea} & \textbf{Médico Nutricionista} & \textbf{Paciente joven-adulto} \\ \hline
Registrar historial de alimentación & Media & Baja \\ \hline
Revisar dieta diaria & Alta & Media \\ \hline
Asignar planes nutricionales & Alta  & – \\ \hline
Controlar peso y progreso & Media & Alta \\ \hline
Diseñar rutinas de ejercicio personalizadas & Media & – \\ \hline
Revisar cumplimiento de la rutina & Media  & Alta  \\ \hline
Buscar información confiable sobre nutrición & Media  & Alta \\ \hline
Tomar fotos de las comidas & – & Alta  \\ \hline
Ajustar cantidades de comida registradas & – & Media \\ \hline
Consultar calorías y macros ingeridos & Media  & Alta  \\ \hline
Coordinar próxima cita / contacto & Media  & Baja  \\ \hline
Compartir resultados con el médico & – & Media  \\ \hline
Usar apps o herramientas digitales & Media  & Alta \\ \hline
Buscar motivación en redes sociales o influencers & Baja & Alta \\ \hline
\end{longtable}


\newpage

### Empathy Mapping  

Permite profundizar en la perspectiva emocional y racional de los usuarios: lo que piensan, sienten, ven, escuchan, dicen y hacen. Esta herramienta ayuda a identificar barreras cognitivas, motivaciones profundas y oportunidades de diseño centradas en la experiencia real.

**Empathy Map – Frank Zane (Nutricionista Deportivo)**

![Empathy Mapping 1 – Frank Zane](src/img/cap2/empathy1.png){ width=75% }

La figura, nos permite comprender las necesidades y tensiones de Frank como profesional de la salud que busca optimizar su tiempo de consulta, diferenciarse digitalmente y mejorar el seguimiento nutricional de sus pacientes mediante herramientas confiables.

\newpage

**Empathy Map – Mike Mentzer (Paciente joven con interés en mejorar su alimentación)**

![Empathy Mapping 2 – Mike Mentzer](src/img/cap2/empathy2.png){ width=75% }

La figura, expone los hábitos, frustraciones y aspiraciones de Mike, un usuario motivado por mejorar su físico y salud, que necesita guía clara, acompañamiento profesional y tecnología accesible para avanzar con seguridad en sus objetivos nutricionales.

\newpage

### As-is Scenario Mapping

Describe cómo es actualmente la experiencia de los usuarios sin una solución tecnológica centralizada. A través de sus rutinas diarias, se evidencian fricciones, ineficiencias y puntos críticos que limitan tanto el progreso del paciente como la calidad de atención del profesional. Estas limitaciones representan oportunidades clave para la intervención digital.

**As-Is Scenario – Frank Zane (Nutricionista clínico-deportivo)**

Frank gestiona sus consultas con herramientas básicas como Excel y WhatsApp, lo que le obliga a invertir tiempo valioso recolectando información dispersa. Al depender de datos incompletos de sus pacientes, no puede personalizar de forma efectiva los planes de alimentación ni medir el progreso con objetividad. Esta falta de trazabilidad diaria y seguimiento confiable afecta la adherencia del paciente y complica la evaluación de resultados. Además, le impide posicionarse como un profesional moderno e innovador en su campo.

![As-is Scenario Mapping – Frank Zane](src/img/cap2/asis1.jpg)

\newpage

**As-Is Scenario – Mike Mentzer (Paciente joven-adulto)**

Mike enfrenta una experiencia fragmentada y poco eficiente en su camino hacia una mejor alimentación y rendimiento físico. Registra sus comidas con fotos desordenadas, sigue rutinas de influencers sin supervisión profesional y recopila información de forma manual o incompleta. Al momento de asistir a una consulta, no cuenta con datos precisos ni organizados para evaluar su progreso. Esto le genera frustración, dudas sobre su avance real y desmotivación por no ver resultados claros.

![As-is Scenario Mapping – Mike Mentzer](src/img/cap2/asis2.jpg)

\newpage

### Ubiquitous Language

* **Paciente**: Persona que busca mejorar su alimentación o rendimiento físico. Puede estar en consulta ambulatoria, deportiva o en hospitalización. (Sinónimos: Usuario, Cliente)

* **Nutricionista**: Profesional de la salud que diseña, ajusta y monitorea planes alimentarios, con base en datos clínicos, antropométricos y de consumo. (Sinónimos: Profesional de nutrición, Especialista)

* **Consulta Nutricional**: Interacción entre Nutricionista y Paciente en la cual se evalúa el estado actual, se registran datos y se definen estrategias dietéticas.

* **Cardex Nutricional**: Formato clínico manual utilizado tradicionalmente para registrar la evolución diaria del paciente, sus comidas y anotaciones sobre tolerancia o consumo. (Usado en hospitales)

* **SGSS** (*Sistema de Gestión de Servicios de Salud*): Plataforma institucional usada para documentar diagnósticos, evolución y acciones nutricionales en hospitales del sector público. Puede tener limitaciones en velocidad o usabilidad.

* **Evaluación Antropométrica**: Conjunto de mediciones como peso, talla, pliegues cutáneos y perímetros corporales. Se utilizan para evaluar el estado nutricional.

* **Análisis Bioquímico**: Pruebas de laboratorio utilizadas como soporte diagnóstico (glucosa, colesterol, hemoglobina, etc.)

* **Registro Fotográfico**: Funcionalidad que permite al paciente subir imágenes de sus comidas. Puede ser procesado automáticamente por IA para estimar calorías y macros.

* **Macronutrientes (Macros)**: Nutrientes energéticos fundamentales: carbohidratos, proteínas y grasas. Se calculan en gramos y kilocalorías por día. (Sinónimos: Macros)

* **Tabla Nutricional Peruana**: Base de datos de referencia local con valores nutricionales de alimentos comunes en Perú. Fundamental para cálculos contextualizados.

* **Plan Nutricional**: Estrategia alimentaria personalizada que incluye porciones, horarios, alimentos sugeridos y objetivos metabólicos.

* **Adherencia Nutricional**: Grado en que el paciente sigue el plan alimentario propuesto. Puede medirse por registros, fotos, peso y otros indicadores.

* **Dashboard Clínico**: Panel web para Nutricionistas que permite visualizar progresos, comparar datos, generar reportes y ajustar planes. (Sinónimos: Plataforma del profesional)

* **App Foodlytics (Paciente)**: Aplicación móvil donde el usuario registra comidas, consulta metas, visualiza avances y recibe recordatorios.

* **Recordatorio Nutricional**: Alerta o mensaje enviado por la app para fomentar la constancia (por ejemplo: registrar almuerzo, pesar alimentos, hidratarse).

* **Registro de Suplementos**: Módulo opcional donde el paciente puede anotar proteínas, creatina, multivitamínicos u otros productos consumidos.

* **Reporte de Consumo**: Documento visual generado automáticamente por el sistema, que resume el consumo calórico, proteico, cumplimiento y frecuencia.

* **Medidas Caseras**: Unidades no estandarizadas como “una taza”, “una cucharada” o “medio plato”, usadas por pacientes para estimar cantidades.

* **Reconocimiento de Alimentos**: Funcionalidad basada en IA que analiza fotos para identificar ingredientes, porciones y estimar calorías/macros automáticamente.

* **Seguimiento Nutricional**: Monitoreo continuo del progreso del paciente en función de metas, registros, cambios físicos y adherencia al plan.

* **Consulta Externa**: Modalidad ambulatoria donde los pacientes asisten regularmente al nutricionista para controles.

* **Paciente Hospitalizado**: Usuario en estado clínico más complejo que requiere registro diario y constante revisión por parte del equipo nutricional.

* **Perfil del Paciente**: Ficha digital que contiene información como antecedentes médicos, alergias, diagnósticos, objetivos y evolución.

* **Educación Alimentaria**: Funcionalidad o módulo que entrega al paciente explicaciones visuales, gráficas o interactivas sobre su dieta, metas o errores comunes.

* **Sistema Interoperable**: Capacidad de la plataforma para integrarse con otras bases clínicas o aplicativos existentes (SGSS, historiales electrónicos, etc.)

* **Privacidad de Datos**: Consideración ética y legal para proteger la información clínica y personal del paciente. Incluye consentimiento informado y cifrado de datos.