<!-- Carátula UPC -->

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/UPC_logo_transparente.png" alt="Logo UPC" width="200">
</p>

<h2 align="center">UNIVERSIDAD PERUANA DE CIENCIAS APLICADAS</h2>

<h3 align="center">
INGENIERÍA DE SOFTWARE
</h3>

<p align="center"><strong>PERIODO:</strong> 202610 </p>

<p align="center">
  1ACC0238 - Aplicaciones para Dispositivos Móviles<br>
  <strong>NRC:</strong> 12612<br>
  <strong>Docente:</strong> David Gerardo Quevedo Velazco
</p>

<hr style="width:60%; border:1px solid #ccc;">

<h1 align="center">Informe de Trabajo Final</h1>

<p align="center">
  <strong>Startup:</strong> Movi<br>
  <strong>Producto:</strong> Courtly
</p>

<h3 align="center">Integrantes</h3>

<div align="center" style="line-height: 1.8; text-align: center;">
  <p>U202317692 — Angulo Abud, Juan Carlos</p>

</div>

<br>

<p align="center" style="font-weight: bold;">Abril 2026</p>


<div style="page-break-after: always;"></div>


<!--Registro de versiones-->
<h1 align="left">Registro de versiones del Informe</h1>
</br>
<table border="1" cellpadding="10" cellspacing="0" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;">Versión</td>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;">Fecha</td>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;">Autores</td>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;">Descripción</td>
  </tr>
  <tr>
    <td style="border: 1px solid #ddd; padding: 8px;">AV1</td>
    <td style="border: 1px solid #ddd; padding: 8px;">21/04/2026</td>
    <td style="border: 1px solid #ddd; padding: 8px;">
      <ul>
        <li>Juan Carlos Angulo</li>
      </ul>
    </td>
    <td style="border: 1px solid #ddd; padding: 8px;">            
      <ul>
        <li>Capítulo II: Punto 2.5.1 (EventStorming)</li>
        <li>Capítulo II: Punto 2.5.1.1 (Candidate Context Discovery)</li>
        <li>Capítulo II: Punto 2.5.1.2 (Domain Message Flows Modeling)</li>
        <li>Capítulo II: Punto 2.6.5 (Court &amp; Venue Management)</li>
        <li>Capítulo II: Punto 2.6.5.1 al 2.6.5.6.2</li>
        <li>Capítulo II: Punto 2.6.6 (Availabilities)</li>
        <li>Capítulo II: Punto 2.6.6.1 al 2.6.6.6.2</li>
        </ul>
    </td>
  </tr>
</table><br>




<h1>AV1</h1>

<p>Para el desarrollo del informe perteneciente a la entrega AV1, se dividió la implementación de secciones de la siguiente forma para cada integrante del equipo:</p>

<table align="center" border="1" cellpadding="10" cellspacing="0" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;"><strong>Integrante</strong></td>
    <td align="center" style="border: 1px solid #ddd; padding: 8px;"><strong>Tareas Asignadas</strong></td>
  </tr>
  <tr>
    <td style="border: 1px solid #ddd; padding: 8px;">Juan Carlos Angulo</td>
    <td style="border: 1px solid #ddd; padding: 8px;">
      <ul>
        <li><strong>2.5.1 EventStorming</strong></li>
        <li>2.5.1.1 Candidate Context Discovery</li>
        <li>2.5.1.2 Domain Message Flows Modeling</li>
        <li><strong>2.6 Tactical-Level DDD</strong> para bounded contexts <em>Courts</em> y <em>Availabilities</em>:</li>
        <li>Domain Layer, Interface Layer, Application Layer e Infrastructure Layer</li>
        <li>Bounded Context Software Architecture Component Level Diagrams</li>
        <li>Bounded Context Software Architecture Code Level Diagrams</li>
        <li>Bounded Context Domain Layer Class Diagrams y Bounded Context Database Design Diagram</li>
      </ul>
    </td>
  </tr>
</table>



<!--ÍNDICE-->
# Contenido
[Student Outcome](#student-outcome)

[Capítulo I: Introducción](#capítulo-i-introducción)
- [1.1. Startup Profile](#11-startup-profile)
  - [1.1.1. Descripción de la Startup](#111-descripción-de-la-startup)
  - [1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)
- [1.2. Solution Profile](#12-solution-profile)
- [1.2.1 Antecedentes y problemática](#121-antecedentes-y-problemática)
  - [1.2.2 Lean UX Process](#122-lean-ux-process)
  -  [1.2.2.1. Lean UX Problem Statements](#1221-lean-ux-problem-statements)
    - [1.2.2.2. Lean UX Assumptions](#1222-lean-ux-assumptions)
    - [1.2.2.3. Lean UX Hypothesis Statements](#1223-lean-ux-hypothesis-statements)
    - [1.2.2.4. Lean UX Canvas](#1224-lean-ux-canvas)
- [1.3. Segmentos objetivo](#13-segmentos-objetivo)
  
  [Capítulo II: Requirements Elicitation \& Analysis](#capítulo-ii-Requirements-Development-and-Software-Solution-Design)
  - [2.1. Competidores](#21-competidores)
    - [2.1.1. Análisis competitivo](#211-análisis-competitivo)
    - [2.1.2. Estrategias y tácticas frente a competidores](#212-estrategias-y-tácticas-frente-a-competidores)
  - [2.2. Entrevistas](#22-entrevistas)
    - [2.2.1. Diseño de entrevistas](#221-diseño-de-entrevistas)
    - [2.2.2. Registro de entrevistas](#222-registro-de-entrevistas)
    - [2.2.3. Análisis de entrevistas](#223-análisis-de-entrevistas)
  - [2.3. Needfinding](#23-needfinding)
    - [2.3.1. User Personas](#231-user-personas)
    - [2.3.2. User Task Matrix](#232-user-task-matrix)
    - [2.3.3. User Journey Mapping](#233-user-journey-mapping)
    - [2.3.4. Empathy Mapping](#234-empathy-mapping)
    - [2.3.5. Ubiquitous Language](#235-UbiquitousLanguage)
  - [2.4 Requirements specification](#236-Requirements-specification)
- [2.4.1. User Stories](#241-user-stories)  
- [2.4.2. Impact Mapping](#242-impact-mapping)  
- [2.4.3. Product Backlog](#243-product-backlog)  
- [2.5. Strategic-Level Domain-Driven Design](#25-strategic-level-domain-driven-design)  
  - [2.5.1. EventStorming](#251-eventstorming)  
    - [2.5.1.1. Candidate Context Discovery](#2511-candidate-context-discovery)  
    - [2.5.1.2. Domain Message Flows Modeling](#2512-domain-message-flows-modeling)  
    - [2.5.1.3. Bounded Context Canvases](#2513-bounded-context-canvases)  
  - [2.5.2. Context Mapping](#252-context-mapping)  
- [2.5.3. Software Architecture](#253-software-architecture)  
  - [2.5.3.1. Software Architecture Context Level Diagrams](#2531-software-architecture-context-level-diagrams)  
  - [2.5.3.2. Software Architecture Container Level Diagrams](#2532-software-architecture-container-level-diagrams)  
  - [2.5.3.3. Software Architecture Deployment Diagrams](#2533-software-architecture-deployment-diagrams)  
 - [2.6.1. Bounded Context: Bookings](#261-bounded-context-bookings)
    - [2.6.1.1. Domain Layer](#2611-domain-layer)
    - [2.6.1.2. Interface Layer](#2612-interface-layer)
    - [2.6.1.3. Application Layer](#2613-application-layer)
    - [2.6.1.4. Infrastructure Layer](#2614-infrastructure-layer)
    - [2.6.1.5. Bounded Context Software Architecture Component Level Diagrams](#2615-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.1.6. Bounded Context Software Architecture Code Level Diagrams](#2616-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.1.6.1. Bounded Context Domain Layer Class Diagrams](#26161-bounded-context-domain-layer-class-diagrams)
    - [2.6.1.6.2. Bounded Context Database Design Diagram](#26162-bounded-context-database-design-diagram)
  - [2.6.2. Bounded Context: Payments (Pagos)](#262-bounded-context-payments-pagos)
    - [2.6.2.1. Domain Layer](#2621-domain-layer)
    - [2.6.2.2. Interface Layer](#2622-interface-layer)
    - [2.6.2.3. Application Layer](#2623-application-layer)
    - [2.6.2.4. Infrastructure Layer](#2624-infrastructure-layer)
    - [2.6.2.5. Bounded Context Software Architecture Component Level Diagrams](#2625-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.2.6. Bounded Context Software Architecture Code Level Diagrams](#2626-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.2.6.1. Bounded Context Domain Layer Class Diagrams](#26261-bounded-context-domain-layer-class-diagrams)
    - [2.6.2.6.2. Bounded Context Database Design Diagram](#26262-bounded-context-database-design-diagram)
  - [2.6.3. Bounded Context: Users](#263-bounded-context-users)
    - [2.6.3.1. Domain Layer](#2631-domain-layer)
    - [2.6.3.2. Interface Layer](#2632-interface-layer)
    - [2.6.3.3. Application Layer](#2633-application-layer)
    - [2.6.3.4. Infrastructure Layer](#2634-infrastructure-layer)
    - [2.6.3.5. Bounded Context Software Architecture Component Level Diagrams](#2635-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.3.6. Bounded Context Software Architecture Code Level Diagrams](#2636-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.3.6.1. Bounded Context Domain Layer Class Diagrams](#26361-bounded-context-domain-layer-class-diagrams)
    - [2.6.3.6.2. Bounded Context Database Design Diagram](#26362-bounded-context-database-design-diagram)
  - [2.6.4. Bounded Context: Coaches](#264-bounded-context-coaches)
    - [2.6.4.1. Domain Layer](#2641-domain-layer)
    - [2.6.4.2. Interface Layer](#2642-interface-layer)
    - [2.6.4.3. Application Layer](#2643-application-layer)
    - [2.6.4.4. Infrastructure Layer](#2644-infrastructure-layer)
    - [2.6.4.5. Bounded Context Software Architecture Component Level Diagrams](#2645-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.4.6. Bounded Context Software Architecture Code Level Diagrams](#2646-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.4.6.1. Bounded Context Domain Layer Class Diagrams](#26461-bounded-context-domain-layer-class-diagrams)
    - [2.6.4.6.2. Bounded Context Database Design Diagram](#26462-bounded-context-database-design-diagram)
  - [2.6.5. Bounded Context: Court & Venue Management (Gestión de Canchas)](#265-bounded-context-court--venue-management-gestión-de-canchas)
    - [2.6.5.1. Domain Layer](#2651-domain-layer)
    - [2.6.5.2. Interface Layer](#2652-interface-layer)
    - [2.6.5.3. Application Layer](#2653-application-layer)
    - [2.6.5.4. Infrastructure Layer](#2654-infrastructure-layer)
    - [2.6.5.5. Bounded Context Software Architecture Component Level Diagrams](#2655-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.5.6. Bounded Context Software Architecture Code Level Diagrams](#2656-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.5.6.1. Bounded Context Domain Layer Class Diagrams](#26561-bounded-context-domain-layer-class-diagrams)
    - [2.6.5.6.2. Bounded Context Database Design Diagram](#26562-bounded-context-database-design-diagram)
  - [2.6.6. Bounded Context: Availabilities (Disponibilidad de Coaches)](#266-bounded-context-availabilities-disponibilidad-de-coaches)
    - [2.6.6.1. Domain Layer](#2661-domain-layer)
    - [2.6.6.2. Interface Layer](#2662-interface-layer)
    - [2.6.6.3. Application Layer](#2663-application-layer)
    - [2.6.6.4. Infrastructure Layer](#2664-infrastructure-layer)
    - [2.6.6.5. Bounded Context Software Architecture Component Level Diagrams](#2665-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.6.6. Bounded Context Software Architecture Code Level Diagrams](#2666-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.6.6.1. Bounded Context Domain Layer Class Diagrams](#26661-bounded-context-domain-layer-class-diagrams)
    - [2.6.6.6.2. Bounded Context Database Design Diagram](#26662-bounded-context-database-design-diagram)
  - [2.6.7. Bounded Context: Reviews](#267-bounded-context-reviews)
    - [2.6.7.1. Domain Layer](#2671-domain-layer)
    - [2.6.7.2. Interface Layer](#2672-interface-layer)
    - [2.6.7.3. Application Layer](#2673-application-layer)
    - [2.6.7.4. Infrastructure Layer](#2674-infrastructure-layer)
    - [2.6.7.5. Bounded Context Software Architecture Component Level Diagrams](#2675-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.7.6. Bounded Context Software Architecture Code Level Diagrams](#2676-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.7.6.1. Bounded Context Domain Layer Class Diagrams](#26761-bounded-context-domain-layer-class-diagrams)
    - [2.6.7.6.2. Bounded Context Database Design Diagram](#26762-bounded-context-database-design-diagram)
  - [2.6.8. Bounded Context: Analytics](#268-bounded-context-analytics)
    - [2.6.8.1. Domain Layer](#2681-domain-layer)
    - [2.6.8.2. Interface Layer](#2682-interface-layer)
    - [2.6.8.3. Application Layer](#2683-application-layer)
    - [2.6.8.4. Infrastructure Layer](#2684-infrastructure-layer)
    - [2.6.8.5. Bounded Context Software Architecture Component Level Diagrams](#2685-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.8.6. Bounded Context Software Architecture Code Level Diagrams](#2686-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.8.6.1. Bounded Context Domain Layer Class Diagrams](#26861-bounded-context-domain-layer-class-diagrams)
    - [2.6.8.6.2. Bounded Context Database Design Diagram](#26862-bounded-context-database-design-diagram)
  - [2.6.9. Bounded Context: Matches (Partidos)](#269-bounded-context-matches-partidos)
    - [2.6.9.1. Domain Layer](#2691-domain-layer)
    - [2.6.9.2. Interface Layer](#2692-interface-layer)
    - [2.6.9.3. Application Layer](#2693-application-layer)
    - [2.6.9.4. Infrastructure Layer](#2694-infrastructure-layer)
    - [2.6.9.5. Bounded Context Software Architecture Component Level Diagrams](#2695-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.9.6. Bounded Context Software Architecture Code Level Diagrams](#2696-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.9.6.1. Bounded Context Domain Layer Class Diagrams](#26961-bounded-context-domain-layer-class-diagrams)
    - [2.6.9.6.2. Bounded Context Database Design Diagram](#26962-bounded-context-database-design-diagram)
  - [2.6.10. Bounded Context: Notifications](#2610-bounded-context-notifications)
    - [2.6.10.1. Domain Layer](#26101-domain-layer)
    - [2.6.10.2. Interface Layer](#26102-interface-layer)
    - [2.6.10.3. Application Layer](#26103-application-layer)
    - [2.6.10.4. Infrastructure Layer](#26104-infrastructure-layer)
    - [2.6.10.5. Bounded Context Software Architecture Component Level Diagrams](#26105-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.10.6. Bounded Context Software Architecture Code Level Diagrams](#26106-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.10.6.1. Bounded Context Domain Layer Class Diagrams](#261061-bounded-context-domain-layer-class-diagrams)
    - [2.6.10.6.2. Bounded Context Database Design Diagram](#261062-bounded-context-database-design-diagram)
  - [2.6.11. Bounded Context: IAM](#2611-bounded-context-iam)
    - [2.6.11.1. Domain Layer](#26111-domain-layer)
    - [2.6.11.2. Interface Layer](#26112-interface-layer)
    - [2.6.11.3. Application Layer](#26113-application-layer)
    - [2.6.11.4. Infrastructure Layer](#26114-infrastructure-layer)
    - [2.6.11.5. Bounded Context Software Architecture Component Level Diagrams](#26115-bounded-context-software-architecture-component-level-diagrams)
    - [2.6.11.6. Bounded Context Software Architecture Code Level Diagrams](#26116-bounded-context-software-architecture-code-level-diagrams)
    - [2.6.11.6.1. Bounded Context Domain Layer Class Diagrams](#261161-bounded-context-domain-layer-class-diagrams)
    - [2.6.11.6.2. Bounded Context Database Design Diagram](#261162-bounded-context-database-design-diagram)
[Capítulo III: Solution UI/UX Design](#capítulo-iii-solution-uiux-design)
- [3.1. Product design](#31-product-design)
  - [3.1.1. Style Guidelines](#311-style-guidelines)
    - [3.1.1.1. General Style Guidelines](#3111-general-style-guidelines)
  - [3.1.2. Information Architecture](#312-information-architecture)
    - [3.1.2.1. Organization Systems](#3121-organization-systems)
    - [3.1.2.2. Labelling Systems](#3122-labelling-systems)
    - [3.1.2.3. SEO Tags and Meta Tags](#3123-seo-tags-and-meta-tags)
    - [3.1.2.4. Searching Systems](#3124-searching-systems)
    - [3.1.2.5. Navigation Systems](#3125-navigation-systems)
  - [3.1.3. Landing Page UI Design](#313-landing-page-ui-design)
    - [3.1.3.1. Landing Page Wireframe](#3131-landing-page-wireframe)
    - [3.1.3.2. Landing Page Mock-up](#3132-landing-page-mock-up)
  - [3.1.4. Mobile Applications UX/UI Design](#314-mobile-applications-uxui-design)
    - [3.1.4.1. Mobile Applications Wireframes](#3141-mobile-applications-wireframes)
    - [3.1.4.2. Mobile Applications Wireflow Diagrams](#3142-mobile-applications-wireflow-diagrams)
    - [3.1.4.3. Mobile Applications Mock-ups](#3143-mobile-applications-mock-ups)
    - [3.1.4.4. Mobile Applications User Flow Diagrams](#3144-mobile-applications-user-flow-diagrams)
    - [3.1.4.5. Mobile Applications Prototyping](#3145-mobile-applications-prototyping)

[Capítulo IV: Product Implementation & Validation](#capítulo-iv-product-implementation--validation)
- [4.1. Software Configuration Management](#41-software-configuration-management)
  - [4.1.1. Software Development Environment Configuration](#411-software-development-environment-configuration)
  - [4.1.2. Source Code Management](#412-source-code-management)
  - [4.1.3. Source Code Style Guide & Conventions](#413-source-code-style-guide--conventions)
  - [4.1.4. Software Deployment Configuration](#414-software-deployment-configuration)
- [4.2. Landing Page & Mobile Application Implementation](#42-landing-page--mobile-application-implementation)
  - [4.2.1. Sprint n](#421-sprint-n)
    - [4.2.1.1. Sprint Planning n](#4211-sprint-planning-n)
    - [4.2.1.2. Sprint Backlog n](#4212-sprint-backlog-n)
    - [4.2.1.3. Development Evidence for Sprint Review](#4213-development-evidence-for-sprint-review)
    - [4.2.1.4. Testing Suite Evidence for Sprint Review](#4214-testing-suite-evidence-for-sprint-review)
    - [4.2.1.5. Execution Evidence for Sprint Review](#4215-execution-evidence-for-sprint-review)
    - [4.2.1.6. Services Documentation Evidence for Sprint Review](#4216-services-documentation-evidence-for-sprint-review)
    - [4.2.1.7. Software Deployment Evidence for Sprint Review](#4217-software-deployment-evidence-for-sprint-review)
    - [4.2.1.8. Team Collaboration Insights during Sprint](#4218-team-collaboration-insights-during-sprint)
- [4.3. Validation Interviews](#43-validation-interviews)
  - [4.3.1. Diseño de Entrevistas](#431-diseño-de-entrevistas)
  - [4.3.2. Registro de Entrevistas](#432-registro-de-entrevistas)
  - [4.3.3. Evaluaciones según heurísticas](#433-evaluaciones-según-heurísticas)


<!--STUDENT OUTCOME-->
# Student Outcome
<div style="text-align:center;">
    <table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%;">
        <tr>
            <th style="text-align:center; border: 1px solid #ddd;">Student Outcomes</th>
            <th style="text-align:center; border: 1px solid #ddd;">Acciones realizadas</th>
            <th style="text-align:center; border: 1px solid #ddd;">Conclusiones</th>
        </tr>
        <tr>
            <td style="border: 1px solid #ddd; vertical-align: top;">
            Actualiza conceptos y conocimientos necesarios para su desarrollo profesional y en especial para su proyecto en soluciones de software.
            </td>
            <td style="border: 1px solid #ddd; vertical-align: top;">
                <strong>Juan Carlos Angulo</strong><br>
            AV1:<br>Durante el desarrollo del AV1, actualicé y apliqué conocimientos en Domain-Driven Design y arquitectura de software mediante la elaboración de EventStorming (2.5.1.1 Candidate Context Discovery y 2.5.1.2 Domain Message Flows Modeling). Además, desarrollé los bounded contexts de Courts y Availabilities, incluyendo sus capas Domain, Interface, Application e Infrastructure, junto con diagramas de arquitectura y de código.<br><br>
                <strong>Integrante 2</strong><br>
                AV1:<br>Durante el desarrollo del AV1<br>
                TP: Durante el desarrollo<br>
                <strong>TB2:</strong><br>Desarrollé las APIs<br><br>
                <strong>Integrante 3</strong><br>
                AV1:<br>Durante el desarrollo<br>
                TP1:<br>Durante esta entrega,<br>
                <strong>TB2:</strong><br>Lideré el<br><br>
                <strong>Integrante 4</strong><br>
                AV1:<br>Durante el AV1<br>
                TP1:<br>En esta fase<br>
                <strong>TB2:</strong><br>Me encargué de<br><br>
                <strong>Integrante 5</strong><br>
                AV1:<br>Durante el AV1,<br>
                <strong>TB2:</strong><br>Me enfoqué
            </td>
            <td style="border: 1px solid #ddd; vertical-align: top;">
                La actualización y aplicación continua de conceptos de DDD y arquitectura permitieron consolidar una base técnica sólida para el proyecto. Esta contribución fortaleció la calidad del análisis de dominio y la coherencia de los artefactos técnicos desarrollados en AV1.
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid #ddd; vertical-align: top;">
                Reconoce la necesidad del aprendizaje permanente para el desempeño profesional y el desarrollo de proyectos en soluciones de software.
            </td>
            <td style="border: 1px solid #ddd; vertical-align: top;">
                <strong>Juan Carlos Angulo</strong><br>
                AV1:<br>Durante el AV1, reforcé el aprendizaje continuo investigando y aplicando buenas prácticas de modelado de dominio, separación de responsabilidades y documentación arquitectónica. Esto se evidenció en la definición de flujos de mensajes de negocio y en el desarrollo integral de los bounded contexts Courts y Availabilities con sus respectivos diagramas técnicos.<br><br>
                <strong>Integrante 2</strong><br>
                AV1:<br>Durante el AV1,<br>
                <strong>TB2:</strong><br>En el TB2,<br><br>
                <strong>Integrante 3</strong><br>
                AV1:<br>En el transcurso del proyecto,<br>
                TP1:<br>En este proceso,<br>
                <strong>TB2:</strong><br>Durante el TB2,<br><br>
                <strong>Integrante 4</strong><br>
                AV1:<br>En el AV1 contribuí<br>
                TP1:<br>A lo largo de esta etapa,<br>
                <strong>TB2:</strong><br>En el TB2,<br><br>
                <strong>Integrante 5</strong><br>
                AV1:<br>Contribuí a crear un entorno<br><br>
                <strong>TP1:</strong><br>En esta entrega, diseñé y<br><br>
                <strong>TB2:</strong><br>Durante el TB2,
            </td>
            <td style="border: 1px solid #ddd; vertical-align: top;">
                El desarrollo del AV1 evidenció que el aprendizaje permanente es clave para mejorar el desempeño profesional. La incorporación de nuevas prácticas y herramientas permitió elevar la calidad de la documentación técnica y fortalecer la capacidad de diseño de soluciones de software.
            </td>
        </tr>
    </table>
</div>

<!--TODAS LAS SECCIONES A COMPLETAR-->

##  Objetivos SMART

En esta sección, cada miembro del equipo de trabajo formulará al menos dos objetivos SMART que se centren en el desarrollo profesional una vez finalizada su carrera. Estos objetivos deben ser claros, medibles y alcanzables, reflejando cómo cada integrante planea continuar con su crecimiento profesional después de la graduación.

### Miembro 1: Juan Carlos Angulo

### Objetivo 1
**Específico:** Consolidar competencias en Domain-Driven Design mediante el desarrollo de EventStorming y modelado de bounded contexts en COURTLY.

**Medible:**
- Documentar 1 EventStorming completo de negocio.
- Completar y sustentar 2.5.1.1 Candidate Context Discovery y 2.5.1.2 Domain Message Flows Modeling.
- Entregar artefactos validados por el equipo en el repositorio del proyecto.

**Alcanzable:** Aplicación directa de lo aprendido en el curso y de la experiencia obtenida durante AV1.

**Relevante:** Fortalece habilidades clave para roles de Software Engineer con enfoque en análisis de dominio y arquitectura.

**Tiempo:** 8 semanas.

### Objetivo 2
**Específico:** Fortalecer el diseño táctico de arquitectura backend desarrollando integralmente bounded contexts en COURTLY.

**Medible:**
- Desarrollar 2 bounded contexts completos (Courts y Availabilities).
- Documentar en cada contexto las capas Domain, Interface, Application e Infrastructure.
- Elaborar diagramas de componentes, diagramas de código, diagramas de clases de dominio y diagramas de base de datos.

**Alcanzable:** Uso de herramientas de diagramación y documentación técnica aplicadas en el proyecto.

**Relevante:** Mejora la capacidad para estructurar soluciones mantenibles, escalables y alineadas al negocio.

**Tiempo:** 10 semanas.

### Objetivo 3
**Específico:** Mejorar la trazabilidad entre análisis de dominio y documentación técnica para facilitar la colaboración del equipo.

**Medible:**
- Relacionar explícitamente eventos de negocio con decisiones arquitectónicas en al menos 2 entregables.
- Mantener documentación actualizada y estructurada en README y anexos técnicos.
- Realizar revisiones quincenales de consistencia de artefactos con el equipo.

**Alcanzable:** Trabajo colaborativo continuo y seguimiento por entregables durante AV1.

**Relevante:** Eleva la calidad del proyecto y la comunicación técnica entre integrantes.

**Tiempo:** 8 semanas, en paralelo al desarrollo del proyecto.

---
## Miembro 2: []

### Objetivo 1
**Específico:** Entregar el **MVP funcional de COURTLY** (app móvil + backend básico) con registro/login, búsqueda de canchas, búsqueda de entrenadores, sistema de reservas y notificaciones.

**Medible:**  
- Completar **al menos 18 user stories** del backlog priorizado para el MVP.  
- Publicar **beta interna** (TestFlight/Play Console) con **≥ 95% crash-free** y **≤ 1s** de tiempo de respuesta promedio en las APIs principales.  
- Conseguir **mín. 20 feedbacks** de usuarios de prueba (deportistas y entrenadores) y cerrar **≥ 80%** de los hallazgos críticos.

**Alcanzable:** Dedicación de **8–10 h/semana**; uso de stack ya definido (React Native + módulos Kotlin, Node.js, SQLite) y plantillas/DSL de arquitectura ya preparadas.

**Relevante:** Alineado al objetivo del curso y a la visión de **COURTLY**; permite validar el problema y preparar el piloto con entrenadores y propietarios de canchas.

**Tiempo:** **12 semanas** para MVP (3 sprints de 4 semanas):  
- Sprint 1: Auth + Búsqueda de Canchas y Entrenadores.  
- Sprint 2: Sistema de Reservas + Pagos + Notificaciones.  
- Sprint 3: Sistema de Valoraciones, Endurecimiento, métricas, beta y cierre de hallazgos.

---

### Objetivo 2
**Específico:** **Fortalecer competencias profesionales** para liderar el proyecto: arquitectura (C4/DDD), mobile con **Kotlin/React Native**, y prácticas de entrega continua.

**Medible:**  
- Completar **3 cursos** (1 de React Native avanzado, 1 de Kotlin nativo, 1 de DDD/C4 o arquitectura).  
- Elaborar y subir a repo **la documentación técnica**: 3 diagramas C4 (Context, Containers, Deployment) + sección **DDD táctico** por contextos.  
- Configurar **pipeline CI** (lint, tests, build, distribución interna) con **≥ 70%** de pruebas unitarias en módulos críticos.

**Alcanzable:** Plan de estudio de **6 h/semana** con recursos online y aplicación directa en COURTLY.

**Relevante:** Mejora mi capacidad para liderar técnicamente el proyecto y asegurar calidad y mantenibilidad.

**Tiempo:** **16 semanas** totales:  
- Semanas 1–6: cursos y prácticas guiadas.  
- Semanas 7–12: documentación C4/DDD integrada al repo.  
- Semanas 13–16: CI/CD y aumento de cobertura de tests.


---

### Miembro 3: []

**Objetivo 1:**  
<br>**Específico:** Mejorar mis habilidades en programación, especialmente en lenguajes y herramientas utilizados en inteligencia artificial y desarrollo de videojuegos.</br>
<br>**Medible:** Completar al menos 3 cursos especializados en **Python** para IA y **C#** o **Unity** para videojuegos, aplicando estos conocimientos en al menos un proyecto personal.</br>
<br>**Alcanzable:** Dedicar 4 horas a la semana para aprender de forma autodidacta y participar en proyectos colaborativos donde pueda practicar y mejorar estas habilidades.</br>
<br>**Relevante:** Las habilidades de programación en IA y videojuegos son cruciales para mi desarrollo profesional y me permitirán contribuir en proyectos innovadores que tengan un impacto positivo.</br>
<br>**Tiempo:** Finalizar estos cursos y aplicar lo aprendido en proyectos personales en los próximos 9 meses.</br>
<br></br>
**Objetivo 2:**  
<br>**Específico:** Desarrollar un proyecto de **videojuego accesible** con elementos de inteligencia artificial que pueda ayudar a personas con dificultades cognitivas o de aprendizaje.</br>
<br>**Medible:** Diseñar y lanzar un prototipo de videojuego en el que implemente IA para mejorar la experiencia del usuario, buscando que sea evaluado por al menos 5 personas con experiencias en el área de accesibilidad.</br>
<br>**Alcanzable:** Aprovechar recursos como plataformas de código abierto, herramientas de desarrollo de videojuegos (como Unity) y tutoriales especializados en IA para crear el prototipo.</br>
<br>**Relevante:** Crear videojuegos que ayuden a personas a través de la IA es una manera en la que puedo aportar positivamente a la sociedad, combinando mis intereses con mi deseo de hacer un impacto.</br>
<br>**Tiempo:** Desarrollar el prototipo en los próximos 12 meses, con una versión funcional disponible para evaluación en 15 meses.</br>

---

### Miembro 4: []

**Objetivo 1:**  
<br>**Específico:** Desarrollar experiencia profesional como desarrollador de software en una empresa tecnológica reconocida, participando en proyectos reales de frontend y backend.  
<br>**Medible:** Conseguir un puesto de practicante preprofesional antes de finalizar la carrera y completar al menos 6 meses de experiencia comprobable.  
<br>**Alcanzable:** Cuento con bases sólidas en programación, frameworks modernos (Angular, Vue) y buenas prácticas, lo que me permite aplicar a convocatorias de empresas en el sector.  
<br>**Relevante:** Ganar experiencia laboral me permitirá consolidar mi perfil profesional y aumentar mis oportunidades de empleabilidad al terminar la universidad.  
<br>**Tiempo:** Lograr este objetivo dentro de los próximos 12 meses.  

**Objetivo 2:**  
<br>**Específico:** Obtener una certificación internacional en desarrollo web (por ejemplo, AWS Cloud Practitioner o una certificación en Angular).  
<br>**Medible:** Aprobar al menos un examen de certificación reconocido y obtener el diploma correspondiente.  
<br>**Alcanzable:** Dedicaré entre 6 a 8 horas semanales al estudio, combinando recursos online, cursos especializados y práctica en proyectos personales.  
<br>**Relevante:** La certificación fortalecerá mi CV y me diferenciará frente a otros candidatos al momento de postular a empleos.  
<br>**Tiempo:** Completar la certificación en un plazo de 18 meses tras mi graduación.  

---


### Miembro 5: []


**Objetivo 1:**  
<br>**Específico:** Elaborar los diagramas de arquitectura de software a nivel de **componentes** y **código** para los Bounded Contexts del proyecto, asegurando que reflejen fielmente la estructura del sistema.</br>
<br>**Medible:** Completar al menos 2 diagramas (component level y code level) validados por el equipo y listos para integrarse a la documentación oficial del proyecto.</br>
<br>**Alcanzable:** Utilizar mis conocimientos en UML y C4-Model, junto con herramientas de diagramación disponibles, dedicando tiempo específico cada semana hasta completar los diagramas.</br>
<br>**Relevante:** Estos diagramas son esenciales para que el equipo comprenda la arquitectura del sistema, favoreciendo la correcta implementación y comunicación entre módulos.</br>
<br>**Tiempo:** Finalizar y entregar los diagramas dentro de la fase 2.6.x del proyecto, cumpliendo los plazos establecidos en el cronograma.</br>

<br></br>

**Objetivo 2:**  
<br>**Específico:** Diseñar los diagramas de la **capa de dominio** (clases) y de **base de datos** para los Bounded Contexts, mostrando relaciones, dependencias y estructuras de almacenamiento.</br>
<br>**Medible:** Elaborar al menos 2 diagramas (Domain Layer Class y Database Design) que sean revisados y aprobados por el equipo para su uso en la implementación del sistema.</br>
<br>**Alcanzable:** Basarme en los requerimientos y modelos previos, usando herramientas UML y ERD disponibles, aplicando buenas prácticas de diseño de software.</br>
<br>**Relevante:** Documentar y visualizar la estructura interna del sistema es clave para asegurar la mantenibilidad, escalabilidad y correcta implementación del software.</br>
<br>**Tiempo:** Completar los diagramas durante la fase 2.6.x.6 del proyecto, respetando los tiempos del cronograma general.</br>


---

# Capítulo I: Presentación

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

### 1.1.2. Perfiles de integrantes del equipo

---

## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

### 1.2.2. Lean UX Process

#### 1.2.2.1. Lean UX Problem Statements

#### 1.2.2.2. Lean UX Assumptions

#### 1.2.2.3. Lean UX Hypothesis Statements

#### 1.2.2.4. Lean UX Canvas

---

## 1.3. Segmentos objetivo

---

# Capítulo II: Requirements Development and Software Solution Design

## 2.1. Competidores

### 2.1.1. Análisis competitivo

### 2.1.2. Estrategias y tácticas frente a competidores

---

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

### 2.2.2. Registro de entrevistas

### 2.2.3. Análisis de entrevistas

---

## 2.3. Needfinding

### 2.3.1. User Personas

### 2.3.2. User Task Matrix

### 2.3.3. User Journey Mapping

### 2.3.4. Empathy Mapping

### 2.3.5. Big Picture EventStorming

### 2.3.6. Ubiquitous Language

---

## 2.4. Requirements specification

### 2.4.1. User Stories

### 2.4.2. Impact Mapping

### 2.4.3. Product Backlog

---

## 2.5. Strategic-Level Domain-Driven Design

### 2.5.1. EventStorming

#### Introducción

EventStorming es una técnica colaborativa de modelado del dominio que permite al equipo visualizar y comprender los procesos de negocio a través de eventos que ocurren en el sistema. Para el proyecto Courtly, se realizó una sesión de EventStorming con el objetivo de identificar los eventos clave, los actores principales y los bounded contexts del dominio de reserva de canchas deportivas y conexión con entrenadores. Esta sesión facilitó la comunicación entre los miembros del equipo, permitiendo alinear una visión común del sistema y establecer una base sólida para el diseño de la arquitectura.

La sesión de EventStorming se llevó a cabo considerando los principales flujos de negocio: búsqueda y reserva de canchas, registro de entrenadores, gestión de pagos y sistema de valoraciones. El resultado fue un modelo visual que refleja las interacciones entre los actores principales (Deportistas, Entrenadores, Propietarios de Canchas) en el contexto del ecosistema deportivo amateur.

---

#### 2.5.1.1. Candidate Context Discovery

**Objetivo:**
Identificar y delimitar los contextos acotados (bounded contexts) que estructurarán el sistema Courtly, asegurando que cada contexto posea un propósito claro, un vocabulario ubicuo específico y reglas de negocio bien delimitadas.

**Proceso Realizado:**

La sesión de Candidate Context Discovery se llevó a cabo aplicando las técnicas recomendadas en Domain-Driven Design (DDD), que permitieron descomponer el dominio deportivo amateur en áreas funcionales coherentes y manejables.

1. **Start-with-Value (Comenzar por el Valor):**
   - Se identificaron las áreas de mayor valor de negocio en Courtly:
     - Búsqueda y reserva de canchas disponibles para deportistas
     - Registro y visibilidad de entrenadores independientes
     - Gestión de pagos y transacciones
     - Sistema de valoraciones y confianza entre usuarios

2. **Start-with-Simple (Comenzar con lo Simple):**
   - Se organizó el timeline del proceso en pasos secuenciales y lógicos:
     - **Registro:** Usuario (deportista/entrenador) se registra en la plataforma
     - **Búsqueda:** Usuario busca canchas o entrenadores según sus criterios
     - **Reserva:** Usuario realiza la reserva y pago
     - **Operación:** Realización de la actividad deportiva
     - **Evaluación:** Usuario deja valoración y comentarios
   - Este enfoque permitió agrupar eventos en bloques naturales de negocio.

3. **Look-for-Pivotal-Events (Buscar Eventos Clave):**
   - Se detectaron eventos pivotales que marcan cambios de estado críticos:
     - "Usuario Registrado" → inicio de participación en plataforma
     - "Reserva Confirmada" → cambio en disponibilidad de cancha/entrenador
     - "Pago Procesado" → activación de servicios
     - "Actividad Completada" → habilitación para valoración
     - "Reseña Publicada" → impacto en reputación
   - Estos eventos sirvieron como puntos de corte naturales para separar contextos.

**Bounded Contexts Identificados:**

1. **User Account & Authentication Context (Autenticación e Identidad)**
   - **Propósito:** Gestionar la seguridad, autenticación y perfiles de usuarios
   - **Responsabilidades:** Registro de usuarios, inicio de sesión, gestión de roles (Deportista, Entrenador, Administrador)
   - **Vocabulario:** Usuario, Credencial, Rol, Perfil, Token, Sesión
   - **Justificación:** Base fundamental del sistema que valida y controla el acceso de todos los actores

2. **Court & Venue Management Context (Gestión de Canchas)**
   - **Propósito:** Permitir que propietarios publiquen canchas y gestionen disponibilidad
   - **Responsabilidades:** Registro de canchas, gestión de horarios disponibles, información de servicios e instalaciones
   - **Vocabulario:** Cancha, Deporte, Horario, Disponibilidad, Ubicación, Tarifa
   - **Justificación:** Proporciona la oferta central de servicios deportivos en la plataforma

3. **Booking & Reservation Context (Gestión de Reservas)**
   - **Propósito:** Facilitar el proceso de búsqueda y reserva de canchas y entrenadores
   - **Responsabilidades:** Búsqueda con filtros, creación de reservas, confirmación y cancelación
   - **Vocabulario:** Reserva, Búsqueda, Filtro, Confirmación, Cancelación, Slot de Tiempo
   - **Justificación:** Core del negocio que conecta demanda y oferta de servicios deportivos

4. **Coach & Trainer Context (Gestión de Entrenadores)**
   - **Propósito:** Habilitar que entrenadores independientes ofrezcan sus servicios
   - **Responsabilidades:** Perfil de entrenador, especialidades, horarios disponibles, tarifas
   - **Vocabulario:** Entrenador, Especialidad, Experiencia, Disponibilidad, Tarifa, Certificación
   - **Justificación:** Soporta un segmento clave de usuarios que desean monetizar sus conocimientos

5. **Payment & Billing Context (Gestión de Pagos)**
   - **Propósito:** Procesar pagos y gestionar transacciones de manera segura
   - **Responsabilidades:** Procesamiento de pagos, generación de facturas, conciliación de transacciones
   - **Vocabulario:** Pago, Transacción, Factura, Método de Pago, Monto, Comisión
   - **Justificación:** Crítico para monetizar la plataforma y generar confianza en transacciones

6. **Review & Rating Context (Sistema de Valoraciones)**
   - **Propósito:** Construir confianza mediante valoraciones y reseñas de usuarios
   - **Responsabilidades:** Publicación de reseñas, cálculo de ratings, visualización de historial
   - **Vocabulario:** Reseña, Rating, Calificación, Comentario, Confianza, Historial
   - **Justificación:** Fundamental para establecer confianza entre usuarios en un marketplace

7. **Search & Discovery Context (Búsqueda y Descubrimiento)**
   - **Propósito:** Facilitar el descubrimiento de canchas y entrenadores mediante búsqueda inteligente
   - **Responsabilidades:** Indexación de contenido, búsqueda con filtros, recomendaciones
   - **Vocabulario:** Búsqueda, Filtro, Índice, Resultado, Recomendación, Ubicación
   - **Justificación:** Mejora significativamente la experiencia de usuario al encontrar servicios relevantes

8. **Notification & Communication Context (Notificaciones y Comunicación)**
   - **Propósito:** Facilitar la comunicación entre usuarios y con el sistema
   - **Responsabilidades:** Notificaciones de reservas, recordatorios, comunicación entre usuarios
   - **Vocabulario:** Notificación, Mensaje, Recordatorio, Canal, Preferencia
   - **Justificación:** Asegura que los usuarios se mantengan informados sobre sus reservas y oportunidades

---

#### 2.5.1.2. Domain Message Flows Modeling

**Objetivo:**
Visualizar cómo colaboran los bounded contexts para resolver los casos de negocio de Courtly, asegurando trazabilidad en el flujo de información y claridad en las responsabilidades.

**Técnica Aplicada:**
Se utilizó Domain Storytelling para modelar las interacciones entre actores, contextos y eventos principales. Esta técnica permite describir narrativamente cómo fluye la información entre contextos y qué eventos desencadenan acciones en otros dominios.

**Flujos de Mensajes Modelados:**

**1. Flujo: Deportista Busca y Reserva una Cancha**

```
Deportista (Actor)
     ↓
[Search & Discovery Context] - Recibe comando "BuscarCanchas"
     ├─ Aplica filtros (ubicación, deporte, horario, tarifa)
     ├─ Retorna resultados ordenados por relevancia
     └─ Genera evento "BúsquedaRealizada"
          ↓
[Booking & Reservation Context]
     ├─ Recibe comando "ConfirmarReserva"
     ├─ Valida disponibilidad de slot horario
     ├─ Genera evento "ReservaCreada"
     └─ Notifica a otros contextos
          ├─ Payment & Billing Context
          │   ├─ Procesa pago
          │   └─ Genera evento "PagoProcesado"
          │
          └─ Notification & Communication Context
              ├─ Envía confirmación al deportista
              └─ Notifica al propietario de la cancha
```

**Responsabilidades:**
- **Search & Discovery Context:** Búsqueda y filtrado eficiente
- **Booking & Reservation Context:** Validación y creación de reserva
- **Payment & Billing Context:** Procesamiento seguro de pago
- **Notification & Communication Context:** Confirmaciones a ambas partes

---

**2. Flujo: Entrenador se Registra y Ofrece Servicios**

```
Entrenador Independiente (Actor)
     ↓
[User Account & Authentication Context]
     ├─ Registra credenciales como Entrenador
     └─ Genera evento "UsuarioRegistrado"
          ↓
[Coach & Trainer Context]
     ├─ Crea perfil de entrenador
     ├─ Define especialidades y tarifas
     ├─ Establece horarios disponibles
     ├─ Genera evento "EntrenadorRegistrado"
     └─ Notifica a Search & Discovery Context
          ↓
[Search & Discovery Context]
     ├─ Indexa perfil de entrenador
     ├─ Hace disponible para búsqueda
     └─ Genera evento "EntrenadorIndizado"
```

**Responsabilidades:**
- **User Account & Authentication Context:** Validación de identidad
- **Coach & Trainer Context:** Gestión del perfil y disponibilidad
- **Search & Discovery Context:** Indexación para búsqueda

---

**3. Flujo: Deportista Reserva Sesión con Entrenador**

```
Deportista (Actor)
     ↓
[Search & Discovery Context]
     ├─ Busca por especialidad del entrenador
     └─ Retorna resultados con ratings
          ↓
[Booking & Reservation Context]
     ├─ Recibe comando "ReservarSesion"
     ├─ Valida disponibilidad del entrenador
     ├─ Genera evento "ReservaConEntrenador"
     └─ Coordina con
          ├─ Coach & Trainer Context
          │   ├─ Actualiza disponibilidad
          │   └─ Genera evento "DisponibilidadActualizada"
          │
          ├─ Payment & Billing Context
          │   ├─ Procesa pago a entrenador
          │   └─ Calcula comisión de plataforma
          │
          └─ Notification & Communication Context
              ├─ Notifica al entrenador
              └─ Confirma con deportista
```

**Responsabilidades:**
- **Booking & Reservation Context:** Coordinación de la reserva
- **Coach & Trainer Context:** Actualización de disponibilidad
- **Payment & Billing Context:** Distribución de pagos
- **Notification & Communication Context:** Notificaciones a ambas partes

---

**4. Flujo: Completar Actividad y Publicar Reseña**

```
Deportista y/o Entrenador (Actores)
     ↓
[Booking & Reservation Context]
     ├─ Marca actividad como completada
     └─ Genera evento "ActividadCompletada"
          ↓
[Review & Rating Context]
     ├─ Habilita creación de reseña
     ├─ Recibe comando "PublicarReseña"
     ├─ Valida que la actividad fue completada
     ├─ Genera evento "ReseñaPublicada"
     └─ Notifica a
          ├─ User Account & Authentication Context
          │   └─ Actualiza historial del usuario evaluado
          │
          └─ Notification & Communication Context
              ├─ Notifica al usuario evaluado
              └─ Genera notificación pública de reseña
```

**Responsabilidades:**
- **Booking & Reservation Context:** Marca actividad como completada
- **Review & Rating Context:** Gestión de reseñas y ratings
- **User Account & Authentication Context:** Actualiza reputación
- **Notification & Communication Context:** Notificaciones

---

#### 2.5.1.3. Bounded Context Canvases

**Objetivo:**
Documentar de forma detallada cada bounded context mediante el Bounded Context Canvas, especificando el propósito, las capacidades, las reglas de negocio y las dependencias de cada dominio.

**Proceso de Diseño:**
Se siguió un proceso iterativo para cada canvas que incluyó:
1. **Context Overview Definition:** Definición clara del nombre, propósito y alcance
2. **Business Rules Distillation & Ubiquitous Language Capture:** Extracción de reglas y vocabulario del dominio
3. **Capability Analysis:** Identificación de capacidades técnicas y de negocio
4. **Capability Layering:** Organización jerárquica de capacidades
5. **Dependencies Capture:** Mapeo de dependencias internas y externas
6. **Design Critique:** Validación con stakeholders

---

**Canvas 1: User Account & Authentication Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | User Account & Authentication Context |
| **Propósito** | Proveer autenticación, autorización y gestión de perfiles de usuario para toda la plataforma Courtly |
| **Descripción** | Contexto encargado de validar credenciales, gestionar sesiones seguras y mantener perfiles de usuario con roles diferenciados (Deportista, Entrenador, Administrador) |
| **Actores Principales** | Deportista, Entrenador, Administrador del Sistema |
| **Eventos Principales** | UsuarioRegistrado, SesionIniciada, SesionCerrada, PerfilActualizado, RolAsignado |
| **Comandos** | RegistrarUsuario, IniciarSesion, CerrarSesion, ActualizarPerfil, AsignarRol |
| **Reglas de Negocio** | • Las contraseñas deben cumplir estándares de seguridad (mínimo 8 caracteres)<br>• Las sesiones expiran después de 2 horas de inactividad<br>• Un usuario puede tener un único rol primario<br>• El email debe ser único en el sistema<br>• La validación de email es obligatoria antes de usar la cuenta |
| **Capacidades** | • Registro de usuarios con validación de datos<br>• Autenticación con email/contraseña<br>• Gestión de sesiones y tokens JWT<br>• Control de acceso basado en roles (RBAC)<br>• Recuperación de contraseña<br>• Actualización de perfil |
| **Dependencias** | → Notification & Communication Context (para enviar emails de verificación)<br>→ Review & Rating Context (para gestionar reputación de usuarios) |
| **Vocabulario Ubicuo** | Usuario, Credencial, Rol, Perfil, Token, Sesión, Autenticación, Autorización, Email |

---

**Canvas 2: Court & Venue Management Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Court & Venue Management Context |
| **Propósito** | Habilitar que propietarios de canchas publiquen, gestionen y actualicen su oferta de servicios |
| **Descripción** | Contexto que permite a propietarios crear perfiles de canchas, gestionar horarios disponibles, precios y características de instalaciones |
| **Actores Principales** | Propietario de Cancha, Administrador de Sede |
| **Eventos Principales** | CanchaPublicada, HorarioActualizado, TarifaModificada, DisponibilidadCambiada, CanchaDesactivada |
| **Comandos** | PublicarCancha, ActualizarHorarios, ModificarTarifa, CambiarDisponibilidad, DesactivarCancha |
| **Reglas de Negocio** | • Una cancha debe tener al menos un deporte asociado<br>• Los horarios disponibles deben estar entre 06:00 y 23:00<br>• La tarifa debe ser mayor a cero<br>• Las modificaciones de disponibilidad se aplican de inmediato<br>• No puede reservarse un horario ya ocupado |
| **Capacidades** | • Registro de canchas con información completa<br>• Gestión de horarios y disponibilidad<br>• Gestión de tarifas y promociones<br>• Visualización de reservas próximas<br>• Estadísticas de ocupación<br>• Gestión de instalaciones y servicios adicionales |
| **Dependencias** | ← User Account & Authentication Context (para autenticación de propietarios)<br>↔ Booking & Reservation Context (para gestionar reservas)<br>→ Search & Discovery Context (para indexación)<br>→ Notification & Communication Context (para cambios de disponibilidad) |
| **Vocabulario Ubicuo** | Cancha, Deporte, Horario, Disponibilidad, Tarifa, Ubicación, Instalación, Reserva |

---

**Canvas 3: Booking & Reservation Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Booking & Reservation Context |
| **Propósito** | Gestionar el ciclo completo de reservas desde búsqueda hasta confirmación y cancelación |
| **Descripción** | Contexto central que orquesta la creación, validación y gestión de reservas de canchas y entrenadores |
| **Actores Principales** | Deportista, Propietario de Cancha, Entrenador, Sistema de Pagos |
| **Eventos Principales** | ReservaCreada, ReservaConfirmada, PagoAutorizado, ReservaCancelada, ActividadCompletada |
| **Comandos** | CrearReserva, ConfirmarReserva, CancelarReserva, CompletarActividad, ModificarFecha |
| **Reglas de Negocio** | • No pueden crearse reservas retroactivas<br>• Una cancha no puede tener reservas solapadas<br>• El deportista debe estar autenticado para reservar<br>• La cancelación dentro de 24 horas antes de la actividad tiene penalidad<br>• Las reservas se confirman después del pago exitoso<br>• Máximo 5 reservas activas simultáneas por usuario |
| **Capacidades** | • Creación y validación de reservas<br>• Confirmación de disponibilidad en tiempo real<br>• Gestión del ciclo de vida de reservas<br>• Cancelación con políticas de reembolso<br>• Historial de reservas<br>• Notificaciones de cambios |
| **Dependencias** | ← User Account & Authentication Context (para validar usuarios)<br>← Court & Venue Management Context (para validar disponibilidad)<br>← Coach & Trainer Context (para validar disponibilidad de entrenadores)<br>↔ Payment & Billing Context (para procesar pagos)<br>→ Notification & Communication Context (para confirmar)<br>↔ Review & Rating Context (para permitir reseñas) |
| **Vocabulario Ubicuo** | Reserva, Slot Horario, Confirmación, Cancelación, Pago, Depósito, Penalidad, Reembolso |

---

**Canvas 4: Coach & Trainer Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Coach & Trainer Context |
| **Propósito** | Habilitar que entrenadores independientes ofrezcan y gestionen sus servicios |
| **Descripción** | Contexto que permite a entrenadores crear perfiles profesionales, definir especialidades, horarios y tarifas |
| **Actores Principales** | Entrenador Independiente, Deportista Interesado |
| **Eventos Principales** | EntrenadorRegistrado, EspecialidadDefinida, HorarioPublicado, TarifaEstablecida, EntrenadorDesactivado |
| **Comandos** | CrearPerfilEntrenador, DefinirEspecialidades, PublicarHorarios, EstablecerTarifa, ActualizarExperiencia |
| **Reglas de Negocio** | • Un entrenador debe tener al menos una especialidad<br>• La experiencia debe ser un número positivo (años)<br>• Los horarios deben estar disponibles al menos 7 días a la semana<br>• La tarifa debe ser competitiva (rango: $5-$200 USD por sesión)<br>• Las certificaciones pueden ser opcionales pero aumentan confianza |
| **Capacidades** | • Creación de perfil profesional<br>• Gestión de especialidades y experiencia<br>• Publicación de horarios disponibles<br>• Gestión de tarifas por especialidad<br>• Visualización de sesiones próximas<br>• Estadísticas de ganancias<br>• Gestión de certificaciones |
| **Dependencias** | ← User Account & Authentication Context (para crear cuenta como entrenador)<br>↔ Booking & Reservation Context (para gestionar sesiones)<br>→ Search & Discovery Context (para ser descubible)<br>↔ Payment & Billing Context (para recibir pagos)<br>↔ Review & Rating Context (para construir reputación)<br>→ Notification & Communication Context (para confirmar sesiones) |
| **Vocabulario Ubicuo** | Entrenador, Especialidad, Experiencia, Certificación, Tarifa, Sesión, Horario, Disponibilidad |

---

**Canvas 5: Payment & Billing Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Payment & Billing Context |
| **Propósito** | Procesar pagos de manera segura y gestionar la distribución de ingresos |
| **Descripción** | Contexto responsable de procesamiento de transacciones, generación de facturas y conciliación de pagos |
| **Actores Principales** | Deportista (pagador), Propietario/Entrenador (receptor), Gateway de Pagos |
| **Eventos Principales** | PagoProcesado, PagoAutorizado, PagoRechazado, FacturaGenerada, ReembolsoProcessado, ComisionCalculada |
| **Comandos** | ProcesarPago, AutorizarTransaccion, GenerarFactura, ProcessarReembolso, CalcularComision |
| **Reglas de Negocio** | • Todas las transacciones deben ser encriptadas con estándar PCI-DSS<br>• La comisión de plataforma es 15% por defecto<br>• Los reembolsos se procesan dentro de 5-7 días hábiles<br>• Los montos mínimos de transacción son $2 USD<br>• Se mantiene historial de transacciones por 7 años<br>• Las facturas son generadas automáticamente para cada pago |
| **Capacidades** | • Procesamiento seguro de pagos<br>• Soporte para múltiples métodos de pago (tarjeta, wallet, transferencia)<br>• Generación automática de facturas<br>• Gestión de reembolsos y devoluciones<br>• Cálculo de comisiones<br>• Conciliación bancaria<br>• Reportes de ingresos<br>• Detección de fraude |
| **Dependencias** | ← Booking & Reservation Context (para obtener monto a cobrar)<br>← User Account & Authentication Context (para validar beneficiarios)<br>→ Notification & Communication Context (para confirmar pagos)<br>→ Servicios Externos: Stripe, PayPal, transferencias bancarias |
| **Vocabulario Ubicuo** | Pago, Transacción, Factura, Comisión, Reembolso, Método de Pago, Gateway, PCI-DSS |

---

**Canvas 6: Review & Rating Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Review & Rating Context |
| **Propósito** | Construir confianza mediante un sistema de valoraciones y reseñas verificadas |
| **Descripción** | Contexto que gestiona reseñas, ratings y reputación de usuarios basado en actividades completadas |
| **Actores Principales** | Deportista que Revisa, Entrenador Evaluado, Propietario Evaluado |
| **Eventos Principales** | ReseñaPublicada, RatingCalculado, RatingMaliciosoDetectado, ReputacionActualizada, ReseñaEliminada |
| **Comandos** | PublicarReseña, QuitarReseña, ReportarReseñaMaliciosa, CalcularRatingPromedio |
| **Reglas de Negocio** | • Solo pueden reseñar usuarios que completaron la actividad<br>• Las reseñas deben ser publicadas dentro de 30 días de completada la actividad<br>• El rating es un valor 1-5 (no decimales)<br>• Una reseña debe tener mínimo 10 caracteres y máximo 500<br>• Un usuario solo puede reseñar una vez por transacción<br>• Las reseñas no pueden modificarse, solo eliminarse |
| **Capacidades** | • Publicación de reseñas y ratings<br>• Cálculo de rating promedio ponderado<br>• Detección de reseñas anómalas o maliciosas<br>• Visualización de historial de reseñas<br>• Gestión de reportes de contenido inapropiado<br>• Cálculo de confianza de usuario<br>• Filtrado por calidad de reseña |
| **Dependencias** | ← User Account & Authentication Context (para validar usuarios)<br>← Booking & Reservation Context (para verificar actividades completadas)<br>→ Notification & Communication Context (para notificar sobre nuevas reseñas)<br>→ User Account & Authentication Context (para actualizar reputación) |
| **Vocabulario Ubicuo** | Reseña, Rating, Calificación, Comentario, Confianza, Reputación, Historial, Anomalía |

---

**Canvas 7: Search & Discovery Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Search & Discovery Context |
| **Propósito** | Facilitar el descubrimiento rápido y relevante de canchas y entrenadores |
| **Descripción** | Contexto que mantiene índices optimizados de canchas y entrenadores, permitiendo búsquedas eficientes con múltiples criterios |
| **Actores Principales** | Deportista Buscador, Sistema de Indexación |
| **Eventos Principales** | BúsquedaRealizada, CanchaIndexada, EntrenadorIndexado, ResultadosRetornados, ÍndiceActualizado |
| **Comandos** | BuscarCanchas, BuscarEntrenadores, AplicarFiltros, Recomendar, IndexarContenido |
| **Reglas de Negocio** | • Los resultados se ordenan por relevancia (ubicación, rating, disponibilidad)<br>• Máximo 5km de distancia por defecto sin filtro de ubicación<br>• Solo se muestran canchas y entrenadores con rating >= 3.0<br>• Los índices se actualizan en tiempo real<br>• Se cachean búsquedas frecuentes por 1 hora<br>• Máximo 100 resultados por búsqueda |
| **Capacidades** | • Búsqueda de texto completo<br>• Filtrado por múltiples criterios (ubicación, deporte, precio, horario)<br>• Búsqueda geoespacial<br>• Ordenamiento por relevancia<br>• Recomendaciones personalizadas<br>• Autocomplete de búsquedas<br>• Análisis de tendencias de búsqueda |
| **Dependencias** | ← Court & Venue Management Context (para indexar canchas)<br>← Coach & Trainer Context (para indexar entrenadores)<br>← Review & Rating Context (para incluir ratings)<br>→ Notification & Communication Context (para tracking de búsquedas) |
| **Vocabulario Ubicuo** | Búsqueda, Índice, Filtro, Resultado, Relevancia, Ubicación, Deporte, Recomendación |

---

**Canvas 8: Notification & Communication Context**

| Elemento | Descripción |
|----------|-------------|
| **Nombre** | Notification & Communication Context |
| **Propósito** | Facilitar la comunicación efectiva entre usuarios y del sistema hacia usuarios |
| **Descripción** | Contexto transversal responsable de orquestar notificaciones multi-canal, recordatorios y mensajería entre usuarios |
| **Actores Principales** | Deportista, Entrenador, Sistema de Eventos, Servicios de Email |
| **Eventos Principales** | NotificacionEnviada, ReminderCreado, MensajeEnviado, NotificacionEntregada, NotificacionLeida |
| **Comandos** | EnviarNotificacion, CrearReminder, EnviarMensaje, ActualizarPreferencias, ConfirmarEntrega |
| **Reglas de Negocio** | • Las notificaciones respetan preferencias de usuario (push, email o SMS)<br>• No se envían notificaciones después de las 22:00 ni antes de las 08:00<br>• Los recordatorios de actividades se envían 1 hora antes<br>• El historial de notificaciones se mantiene por 90 días<br>• El usuario puede silenciar notificaciones por contexto<br>• Máximo 3 notificaciones por hora por usuario |
| **Capacidades** | • Sistema de notificaciones multi-canal (push, email, SMS)<br>• Recordatorios automáticos de actividades<br>• Mensajería directa entre usuarios<br>• Preferencias de notificación personalizables<br>• Historial de notificaciones<br>• Análisis de entrega<br>• Integración con Firebase Cloud Messaging |
| **Dependencias** | ↔ Todos los contextos (escucha y envía eventos)<br>→ Servicios Externos: Firebase FCM, SendGrid, Twilio |
| **Vocabulario Ubicuo** | Notificación, Mensaje, Reminder, Canal, Preferencia, Entrega, Leitura |

---

**Notas Sobre los Canvases:**

- Cada canvas ha sido diseñado iterativamente considerando la experiencia del usuario deportista y las necesidades operacionales de entrenadores.
- Las dependencias muestran explícitamente cómo los contextos colaboran para completar flujos de negocio complejos.
- El vocabulario ubicuo de cada contexto ha sido validado con stakeholders (deportistas, entrenadores, propietarios de canchas).
- Los canvases servirán de base para el diseño táctico de la arquitectura en las secciones posteriores (2.6.x).

### 2.5.2. Context Mapping

### 2.5.3. Software Architecture

#### 2.5.3.1. Software Architecture Context Level Diagrams

#### 2.5.3.2. Software Architecture Container Level Diagrams

#### 2.5.3.3. Software Architecture Deployment Diagrams

---

## 2.6. Tactical-Level Domain-Driven Design

### 2.6.5. Bounded Context: Court & Venue Management (Gestión de Canchas)

#### 2.6.5.1. Domain Layer

**Entities / Aggregates**

```
Court (Cancha - Aggregate Root)
├── courtId: int → Identificador único de la cancha
├── ownerId: int → Propietario de la cancha
├── name: String → Nombre de la cancha
├── description: String → Descripción de la cancha
├── location: Location (Value Object)
├── sportType: SportType (Enum) → Tipo de deporte (Fútbol, Tenis, Básquet, etc.)
├── surface: String → Tipo de superficie (Sintética, Grass, Cemento)
├── pricePerHour: double → Precio por hora de uso
├── capacity: int → Capacidad máxima de usuarios
├── amenities: List<Amenity> → Servicios adicionales (estacionamiento, vestuarios, etc.)
├── rating: double → Calificación promedio
├── availability: AvailabilitySchedule (Value Object)
├── images: List<ImageUrl> → Fotos de la cancha
├── state: CourtState (Enum) → Estado (Activa, Inactiva, Bloqueada)
├── createdAt: DateTime → Fecha de creación
├── updatedAt: DateTime → Fecha de última actualización

Métodos:
├── createAvailability(horario) → Crea disponibilidad para horarios específicos
├── updatePricing(newPrice) → Actualiza el precio por hora
├── updateAvailability(slot, available) → Marca un slot como disponible o no
├── blockTime(startTime, endTime, reason) → Bloquea tiempo por mantenimiento
├── publishCourt() → Publica la cancha en la plataforma
├── deactivateCourt() → Desactiva la cancha
└── calculateOccupancy(period) → Calcula porcentaje de ocupación
```

**Value Objects**

```
Location
├── address: String → Dirección completa
├── city: String → Ciudad
├── latitude: double → Latitud
├── longitude: double → Longitud
└── districtCode: String → Código del distrito

AvailabilitySchedule
├── slots: List<TimeSlot>
├── workingHours: WorkingHours (lunes-domingo, hora inicio-fin)
└── exceptions: List<BlockedPeriod> (fechas cerradas, mantenimiento)

TimeSlot
├── date: Date → Fecha específica
├── startTime: Time → Hora de inicio
├── endTime: Time → Hora de finalización
└── isAvailable: boolean → Disponibilidad actual

Amenity
├── amenityId: int
├── name: String (Estacionamiento, Vestuarios, Ducha, Cafetería, etc.)
└── included: boolean
```

**Domain Services**

```
CourtAvailabilityService
├── checkAvailability(courtId, dateTime, duration) → boolean
└── suggestAlternativeSlots(courtId, preferences) → List<TimeSlot>

PricingService
├── calculatePrice(courtId, duration, dayOfWeek) → double
├── applyDiscount(courtId, reservationCount) → double
└── validatePriceRange(price) → boolean

CourtScheduleService
├── generateAvailabilityCalendar(courtId, month) → Calendar
├── publishSchedule(courtId, schedule) → void
└── syncWithReservationSystem(courtId) → void
```

**Domain Events**

```
CourtPublished(courtId, ownerId, timestamp)
CourtDeactivated(courtId, reason, timestamp)
PricingUpdated(courtId, oldPrice, newPrice, timestamp)
AvailabilityUpdated(courtId, slot, isAvailable, timestamp)
TimeBlocked(courtId, startTime, endTime, reason, timestamp)
CourtReviewed(courtId, rating, timestamp)
```

**Enums**

```
SportType: FUTBOL, TENIS, BASQUET, VOLEIBOL, PADEL, BADMINTON, OTRO
CourtState: ACTIVA, INACTIVA, BLOQUEADA, EN_MANTENIMIENTO
```

---

#### 2.6.5.2. Interface Layer

**REST Controllers**

```
CourtController
├── POST /courts → Crear nueva cancha
│   Request: CreateCourtDTO
│   Response: CourtResponseDTO
│
├── GET /courts/{courtId} → Obtener detalles de cancha
│   Response: CourtDetailDTO
│
├── PUT /courts/{courtId} → Actualizar información de cancha
│   Request: UpdateCourtDTO
│   Response: CourtResponseDTO
│
├── GET /courts → Listar canchas (con filtros)
│   Query: ?sport=FUTBOL&city=Lima&page=1
│   Response: PagedCourtDTO
│
├── PATCH /courts/{courtId}/pricing → Actualizar precio
│   Request: UpdatePricingDTO
│   Response: PricingResponseDTO
│
├── PATCH /courts/{courtId}/availability → Actualizar disponibilidad
│   Request: UpdateAvailabilityDTO
│   Response: AvailabilityResponseDTO
│
├── POST /courts/{courtId}/block-time → Bloquear tiempo
│   Request: BlockTimeDTO
│   Response: BlockResponseDTO
│
├── DELETE /courts/{courtId} → Desactivar cancha
│   Response: 204 No Content
│
├── GET /courts/{courtId}/calendar → Obtener calendario
│   Query: ?month=2024-04
│   Response: CalendarDTO
│
└── GET /courts/{courtId}/occupancy → Estadísticas de ocupación
    Query: ?period=MONTH
    Response: OccupancyStatisticsDTO
```

**DTOs (Data Transfer Objects)**

```
CreateCourtDTO
├── name: String
├── description: String
├── location: LocationDTO
├── sportType: String
├── surface: String
├── pricePerHour: double
├── capacity: int
├── amenities: List<String>
└── images: List<MultipartFile>

UpdateCourtDTO
├── name: String
├── description: String
├── amenities: List<String>
└── images: List<MultipartFile>

UpdatePricingDTO
├── pricePerHour: double
└── effectiveDate: Date

UpdateAvailabilityDTO
├── workingHours: WorkingHoursDTO
└── exceptions: List<BlockedPeriodDTO>

BlockTimeDTO
├── startTime: DateTime
├── endTime: DateTime
└── reason: String

CourtResponseDTO
├── courtId: int
├── name: String
├── location: LocationDTO
├── sportType: String
├── pricePerHour: double
├── rating: double
├── availability: AvailabilityDTO
└── state: String

CourtDetailDTO
├── (todos los campos de CourtResponseDTO)
├── description: String
├── surface: String
├── capacity: int
├── amenities: List<AmenityDTO>
├── images: List<ImageDTO>
├── owner: CourtOwnerDTO
└── reviews: List<ReviewDTO>

CalendarDTO
├── courtId: int
├── month: String
└── slots: List<SlotDTO>

OccupancyStatisticsDTO
├── courtId: int
├── period: String
├── totalSlots: int
├── bookedSlots: int
├── occupancyPercentage: double
└── revenueEstimate: double
```

---

#### 2.6.5.3. Application Layer

**Command Handlers**

```
CreateCourtCommandHandler
├── Input: CreateCourtCommand (name, location, sportType, pricePerHour, etc.)
├── Validaciones:
│   ├── Verificar que el propietario existe y está activo
│   ├── Validar que la ubicación es válida
│   ├── Validar que el precio está en rango permitido
│   └── Verificar que el usuario no tiene más de N canchas activas
└── Output: CourtCreatedEvent

UpdateCourtCommandHandler
├── Input: UpdateCourtCommand (courtId, updates)
├── Validaciones:
│   ├── Verificar que la cancha existe
│   ├── Verificar que el usuario es propietario
│   └── Validar datos actualizados
└── Output: CourtUpdatedEvent

UpdatePricingCommandHandler
├── Input: UpdatePricingCommand (courtId, newPrice)
├── Validaciones:
│   ├── Precio debe ser > 0
│   ├── No puede cambiar si hay reservas próximas (< 24 horas)
│   └── Verificar permisos del propietario
└── Output: PricingUpdatedEvent

UpdateAvailabilityCommandHandler
├── Input: UpdateAvailabilityCommand (courtId, schedule)
├── Validaciones:
│   ├── Horarios deben ser realistas (06:00 - 23:00)
│   ├── No puede cerrar con reservas activas
│   └── Validar formato de horarios
└── Output: AvailabilityUpdatedEvent

BlockTimeCommandHandler
├── Input: BlockTimeCommand (courtId, startTime, endTime, reason)
├── Validaciones:
│   ├── Verificar que no hay reservas en ese período
│   ├── Bloque no puede ser > 30 días
│   └── Verificar permisos del propietario
└── Output: TimeBlockedEvent

DeactivateCourtCommandHandler
├── Input: DeactivateCourtCommand (courtId, reason)
├── Validaciones:
│   ├── Verificar que no hay reservas activas
│   ├── Cancelar todas las reservas futuras
│   └── Verificar permisos del propietario
└── Output: CourtDeactivatedEvent
```

**Event Handlers**

```
OnCourtPublishedHandler
├── Escucha: CourtPublishedEvent
├── Acciones:
│   ├── Indexar cancha en Search & Discovery Context
│   ├── Enviar confirmación por email al propietario
│   └── Inicializar estadísticas
└── Publica: CourtIndexedEvent

OnPricingUpdatedHandler
├── Escucha: PricingUpdatedEvent
├── Acciones:
│   ├── Notificar a propietario sobre cambio
│   ├── Enviar notificación a deportistas que la siguen
│   └── Actualizar índices de búsqueda
└── Publica: SearchIndexUpdatedEvent

OnAvailabilityUpdatedHandler
├── Escucha: AvailabilityUpdatedEvent
├── Acciones:
│   ├── Sincronizar con Booking & Reservation Context
│   ├── Actualizar calendario de reservas disponibles
│   └── Notificar cambios a usuarios interesados
└── Publica: ReservationAvailabilityChangedEvent

OnTimeBlockedHandler
├── Escucha: TimeBlockedEvent
├── Acciones:
│   ├── Marcar slots como no disponibles
│   ├── Notificar sobre cierre temporal
│   └── Generar recordatorio de reapertura
└── Publica: TimeSlotBlockedEvent
```

---

#### 2.6.5.4. Infrastructure Layer

**Repositories**

```
CourtRepository
├── save(court: Court) → void
├── findById(courtId: int) → Court
├── findByOwnerId(ownerId: int) → List<Court>
├── findBySportType(sportType: SportType) → List<Court>
├── findByLocation(latitude, longitude, radiusKm) → List<Court>
├── update(court: Court) → void
├── delete(courtId: int) → void
└── findAvailableCourts(sportType, date, time, duration) → List<Court>

AvailabilityRepository
├── save(availability: AvailabilitySchedule) → void
├── findByCourtId(courtId: int) → AvailabilitySchedule
├── updateSlot(courtId, slot, available) → void
├── blockTime(courtId, startTime, endTime) → void
└── getCalendar(courtId, month) → Calendar

CourtRatingRepository
├── save(rating: Rating) → void
├── findByCourtId(courtId: int) → List<Rating>
├── calculateAverageRating(courtId: int) → double
└── updateCourtRating(courtId, newAverage) → void
```

**Adapters**

```
ImageStorageAdapter (Cloud Storage: AWS S3 / Google Cloud Storage)
├── uploadImage(file: MultipartFile, courtId: int) → String (URL)
├── deleteImage(imageUrl: String) → void
└── generateThumbnail(imageUrl: String) → String

LocationGeocoder (Google Maps API)
├── geocode(address: String) → Location (lat, lng)
├── reverseGeocode(lat, lng) → Address
└── calculateDistance(lat1, lng1, lat2, lng2) → double

CourtNotificationAdapter
├── sendCourtPublishedEmail(owner, court) → void
├── sendPricingChangeNotification(followers, court, oldPrice, newPrice) → void
└── sendAvailabilityAlert(users, court, newSchedule) → void

SearchIndexAdapter (Elasticsearch / Algolia)
├── indexCourt(court: Court) → void
├── updateIndex(courtId, updates) → void
├── removeCourt(courtId: int) → void
└── searchCourts(filters) → List<CourtSearchResult>
```

**Persistencia**

```
Tabla: courts
├── court_id (PK, INT, AUTO_INCREMENT)
├── owner_id (FK → users.user_id)
├── name (VARCHAR(255), NOT NULL)
├── description (TEXT)
├── address (VARCHAR(500), NOT NULL)
├── city (VARCHAR(100), NOT NULL)
├── latitude (DECIMAL(10,8), NOT NULL)
├── longitude (DECIMAL(11,8), NOT NULL)
├── sport_type (ENUM, NOT NULL)
├── surface (VARCHAR(50))
├── price_per_hour (DECIMAL(10,2), NOT NULL)
├── capacity (INT, NOT NULL)
├── rating (DECIMAL(3,2), DEFAULT 0)
├── state (ENUM, DEFAULT 'ACTIVA')
├── created_at (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)
├── updated_at (TIMESTAMP, ON UPDATE CURRENT_TIMESTAMP)
└── INDEX (owner_id, state), INDEX (sport_type, city), SPATIAL INDEX (latitude, longitude)

Tabla: court_amenities
├── amenity_id (PK, INT, AUTO_INCREMENT)
├── court_id (FK → courts.court_id)
├── amenity_name (VARCHAR(100))
├── included (BOOLEAN)
└── INDEX (court_id)

Tabla: court_availability
├── availability_id (PK, INT, AUTO_INCREMENT)
├── court_id (FK → courts.court_id, UNIQUE)
├── monday_start (TIME)
├── monday_end (TIME)
├── tuesday_start (TIME)
├── ... (miércoles a domingo)
└── updated_at (TIMESTAMP)

Tabla: court_blocked_periods
├── block_id (PK, INT, AUTO_INCREMENT)
├── court_id (FK → courts.court_id)
├── start_time (DATETIME)
├── end_time (DATETIME)
├── reason (VARCHAR(255))
├── created_at (TIMESTAMP)
└── INDEX (court_id, start_time)

Tabla: court_images
├── image_id (PK, INT, AUTO_INCREMENT)
├── court_id (FK → courts.court_id)
├── image_url (VARCHAR(500))
├── is_primary (BOOLEAN)
└── created_at (TIMESTAMP)

Tabla: court_ratings
├── rating_id (PK, INT, AUTO_INCREMENT)
├── court_id (FK → courts.court_id)
├── user_id (FK → users.user_id)
├── score (INT, CONSTRAINT CHECK (score >= 1 AND score <= 5))
├── comment (TEXT)
├── created_at (TIMESTAMP)
└── INDEX (court_id, created_at)
```

---

#### 2.6.5.5. Bounded Context Software Architecture Component Level Diagrams

**Descripción:**

El diagrama de componentes para el Court & Venue Management Context presenta la descomposición del contenedor en componentes funcionales cohesivos que manejan aspectos específicos del negocio de gestión de canchas:

**Componentes Principales:**

```
┌─────────────────────────────────────────────────────────────┐
│         Court & Venue Management Container                  │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Court Management Component                          │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Crear/Actualizar canchas                           │   │
│  │ • Gestionar información de canchas                   │   │
│  │ • Validar datos de entrada                           │   │
│  │ • Publicar/Desactivar canchas                        │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Availability & Scheduling Component                │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Gestionar disponibilidad por horarios              │   │
│  │ • Bloquear tiempo para mantenimiento                 │   │
│  │ • Generar calendario de disponibilidad               │   │
│  │ • Sincronizar con sistema de reservas                │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Pricing & Commerce Component                        │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Gestionar precios por hora                         │   │
│  │ • Aplicar descuentos dinámicos                       │   │
│  │ • Calcular ingresos y estadísticas                   │   │
│  │ • Validar rangos de precios                          │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Search & Discovery Component                        │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Indexar canchas en motor de búsqueda               │   │
│  │ • Mantener metadatos para búsqueda                   │   │
│  │ • Optimizar para consultas geoespaciales             │   │
│  │ • Actualizar índices en tiempo real                  │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Notification Component                              │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Enviar notificaciones a propietarios                │   │
│  │ • Alertas de cambios de disponibilidad                │   │
│  │ • Recordatorios de eventos importantes                │   │
│  │ • Coordinar con Notification & Communication Context  │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Repository & Data Access Component                  │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • CourtRepository                                     │   │
│  │ • AvailabilityRepository                              │   │
│  │ • CourtRatingRepository                               │   │
│  │ • Implementación de patrones de persistencia          │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
└─────────────────────────────────────────────────────────────┘
         ↓                           ↓                   ↓
    ┌────────────┐      ┌────────────────┐      ┌──────────────┐
    │   SQLite   │      │  AWS S3 / GCS  │      │   Elasticsearch│
    │  (Courts)  │      │  (Images)      │      │  (Índices)     │
    └────────────┘      └────────────────┘      └──────────────┘
```

**Relaciones entre Componentes:**

- **Court Management ↔ Availability & Scheduling:** Court Management actualiza Availability cuando se publica una cancha
- **Pricing & Commerce → Repository:** Persiste cambios de precios en la base de datos
- **Availability & Scheduling → Search & Discovery:** Notifica cambios de disponibilidad para actualizar índices
- **Notification ← Todos:** Se suscribe a eventos de todos los componentes para enviar notificaciones
- **Repository → Data Store:** Accede y persiste toda la información en SQLite
- **Search & Discovery ↔ Elasticsearch:** Mantiene sincronizado el índice de búsqueda

---

#### 2.6.5.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.5.6.1. Bounded Context Domain Layer Class Diagrams

**Diagrama UML de Clases - Court & Venue Management Domain Layer**

```
┌─────────────────────────────┐
│      <<Aggregate>>          │
│         Court               │
├─────────────────────────────┤
│ - courtId: int              │
│ - ownerId: int              │
│ - name: String              │
│ - description: String       │
│ - location: Location        │
│ - sportType: SportType      │
│ - surface: String           │
│ - pricePerHour: double      │
│ - capacity: int             │
│ - amenities: List<Amenity>  │
│ - rating: double            │
│ - availability: AvailSched  │
│ - images: List<ImageUrl>    │
│ - state: CourtState         │
│ - createdAt: DateTime       │
│ - updatedAt: DateTime       │
├─────────────────────────────┤
│ + publishCourt(): void      │
│ + updatePricing(p): void    │
│ + updateAvailability(): void│
│ + blockTime(s,e,r): void    │
│ + deactivateCourt(): void   │
│ + calculateOccupancy(): dbl │
│ + addAmenity(a): void       │
│ + removeAmenity(a): void    │
└────────────────┬────────────┘
                 │
     ┌───────────┴────────────┐
     │                        │
┌────▼──────────────────┐ ┌──▼──────────────────────────┐
│   <<ValueObject>>     │ │  <<ValueObject>>            │
│     Location          │ │  AvailabilitySchedule       │
├───────────────────────┤ ├─────────────────────────────┤
│ - address: String     │ │ - slots: List<TimeSlot>     │
│ - city: String        │ │ - workingHours: WorkHours   │
│ - latitude: double    │ │ - exceptions: List<Block>   │
│ - longitude: double   │ ├─────────────────────────────┤
│ - districtCode: String│ │ + isAvailable(slot): bool   │
├───────────────────────┤ │ + getAvailableSlots(): List │
│ + distance(loc): dbl  │ │ + blockPeriod(s,e): void    │
│ + isValid(): boolean  │ │ + unblockPeriod(s,e): void  │
└───────────────────────┘ └─────────────────────────────┘
          ▲                          ▲
          │                          │
          │ uses                     │ contains
          │                          │
     ┌────┴───────────────┐    ┌────┴─────────────────────┐
     │                    │    │                          │
┌────▼─────────────────┐  │ ┌──▼────────────────────────┐│
│  <<ValueObject>>     │  │ │  <<ValueObject>>          ││
│   TimeSlot           │  │ │   Amenity                 ││
├──────────────────────┤  │ ├──────────────────────────┤│
│ - date: Date         │  │ │ - amenityId: int         ││
│ - startTime: Time    │  │ │ - name: String           ││
│ - endTime: Time      │  │ │ - included: boolean      ││
│ - isAvailable: bool  │  │ ├──────────────────────────┤│
├──────────────────────┤  │ │ + getName(): String      ││
│ + duration(): int    │  │ │ + isIncluded(): bool     ││
│ + overlaps(ts): bool │  │ └──────────────────────────┘│
└──────────────────────┘  └───────────────────────────┘

┌─────────────────────────────┐      ┌────────────────────┐
│   <<Interface>>             │      │   <<Enum>>         │
│   CourtRepository           │      │   SportType        │
├─────────────────────────────┤      ├────────────────────┤
│ + save(c: Court): void      │      │ FUTBOL             │
│ + findById(id): Court       │      │ TENIS              │
│ + findByOwnerId(id): List   │      │ BASQUET            │
│ + update(c: Court): void    │      │ VOLEIBOL           │
│ + delete(id): void          │      │ PADEL              │
│ + findAvailable(): List     │      │ BADMINTON          │
└─────────────────────────────┘      │ OTRO               │
           △                         └────────────────────┘
           │ implements
           │                        ┌────────────────────┐
    ┌──────┴───────┐                │   <<Enum>>         │
    │              │                │   CourtState       │
┌───▼──────────────────────────┐    ├────────────────────┤
│ CourtRepositoryImpl           │    │ ACTIVA             │
├──────────────────────────────┤    │ INACTIVA           │
│ - db: Database               │    │ BLOQUEADA          │
├──────────────────────────────┤    │ EN_MANTENIMIENTO   │
│ + save(c): void              │    └────────────────────┘
│ + findById(id): Court        │
│ + update(c): void            │
│ + delete(id): void           │
└──────────────────────────────┘

┌────────────────────────────────────┐
│   <<Service>>                      │
│   CourtAvailabilityService         │
├────────────────────────────────────┤
│ - courtRepository: CourtRepository │
├────────────────────────────────────┤
│ + checkAvailability(): boolean     │
│ + suggestAlternativeSlots(): List  │
│ + reserveSlot(slot): void          │
│ + releaseSlot(slot): void          │
└────────────────────────────────────┘

Relaciones:
- Court *──────── 1 Location (contains)
- Court *──────── 1 AvailabilitySchedule (contains)
- Court *──────── * Amenity (contains)
- AvailabilitySchedule *──────── * TimeSlot (contains)
- CourtRepository ◄────────────── Court (manages)
- CourtAvailabilityService ───────► CourtRepository (uses)
```

---

##### 2.6.5.6.2. Bounded Context Database Design Diagram

**Entity Relationship Diagram (ERD) - Court & Venue Management**

```
┌──────────────────────────────┐
│         users                │
├──────────────────────────────┤
│ PK user_id (INT)             │
│ name (VARCHAR)               │
│ email (VARCHAR, UNIQUE)      │
│ role (ENUM)                  │
└──────────────────────────────┘
         ▲
         │ FK (owner_id)
         │
┌─────────┴──────────────────────────────┐
│          courts                        │
├────────────────────────────────────────┤
│ PK court_id (INT, AUTO_INCREMENT)      │
│ FK owner_id (INT)                      │
│ name (VARCHAR(255), NOT NULL)          │
│ description (TEXT)                     │
│ address (VARCHAR(500), NOT NULL)       │
│ city (VARCHAR(100), NOT NULL)          │
│ district_code (VARCHAR(20))            │
│ latitude (DECIMAL(10,8), NOT NULL)     │
│ longitude (DECIMAL(11,8), NOT NULL)    │
│ sport_type (ENUM, NOT NULL)            │
│ surface (VARCHAR(50))                  │
│ price_per_hour (DECIMAL(10,2))         │
│ capacity (INT)                         │
│ rating (DECIMAL(3,2), DEFAULT 0)       │
│ state (ENUM, DEFAULT 'ACTIVA')         │
│ created_at (TIMESTAMP)                 │
│ updated_at (TIMESTAMP)                 │
│ UNIQUE KEY (owner_id, name)            │
│ INDEX idx_sport_city (sport_type, city)│
│ SPATIAL INDEX idx_location (lat, lng)  │
└─────────────────────┬────────────────────┘
     ┌────────────────┼────────────────┐
     │                │                │
     │                │                │
┌────▼──────────┐ ┌──▼────────────┐ ┌▼─────────────────┐
│court_amenities│ │court_images    │ │court_availability│
├───────────────┤ ├────────────────┤ ├──────────────────┤
│PK amenity_id  │ │PK image_id     │ │PK availability_id│
│FK court_id    │ │FK court_id     │ │FK court_id (UNIQ)│
│amenity_name   │ │image_url       │ │monday_start (TIM)│
│included (BOOL)│ │is_primary (BOO)│ │monday_end (TIME) │
│               │ │created_at      │ │tuesday_start     │
│               │ │                │ │tuesday_end       │
│               │ │                │ │...wednesday-sun..│
│               │ │                │ │updated_at        │
└───────────────┘ └────────────────┘ └──────────────────┘
     │                │
     │                │
     └────────┬───────┘
              │ FK (court_id)
              │
┌─────────────▼──────────────────┐
│ court_blocked_periods          │
├────────────────────────────────┤
│ PK block_id (INT)              │
│ FK court_id (INT)              │
│ start_time (DATETIME)          │
│ end_time (DATETIME)            │
│ reason (VARCHAR(255))          │
│ created_at (TIMESTAMP)         │
│ CONSTRAINT no_overlapping_blocks│
│ INDEX idx_court_dates          │
└────────────────────────────────┘

┌────────────────────────────────┐
│ court_ratings                  │
├────────────────────────────────┤
│ PK rating_id (INT)             │
│ FK court_id (INT)              │
│ FK user_id (INT)               │
│ score (INT, CHECK 1-5)         │
│ comment (TEXT)                 │
│ created_at (TIMESTAMP)         │
│ UNIQUE (court_id, user_id)     │
│ INDEX idx_court_score          │
└────────────────────────────────┘

Relaciones:
- users (1) ──── (*) courts
- courts (1) ──── (*) court_amenities
- courts (1) ──── (*) court_images
- courts (1) ──── (1) court_availability
- courts (1) ──── (*) court_blocked_periods
- courts (1) ──── (*) court_ratings
- users (1) ──── (*) court_ratings
```

---

### 2.6.6. Bounded Context: Availabilities (Disponibilidad de Coaches)

#### 2.6.6.1. Domain Layer

**Entities / Aggregates**

```
Availability (Aggregate Root)
├── id: int → Identificador único de la disponibilidad
├── date: Date → Fecha del bloque horario
├── startTime: Time → Hora de inicio del bloque
├── endTime: Time → Hora de finalización del bloque
├── status: AvailabilityStatus (Enum) → Estado actual
├── coach: Coach (Reference) → Entrenador propietario
├── createdAt: DateTime → Fecha de creación
└── updatedAt: DateTime → Fecha de última actualización

Métodos:
├── isConflictWith(otherAvailability) → boolean
├── getSlotDuration() → int (en minutos)
├── markAsReserved() → void
├── markAsAvailable() → void
├── markAsUnavailable() → void
├── isValidTimeRange() → boolean
├── canBeModified() → boolean
└── overlapsWithDate(date) → boolean
```

**Value Objects**

```
AvailabilityStatus
├── AVAILABLE → Slot disponible para reserva
├── RESERVED → Slot ya reservado por un cliente
└── UNAVAILABLE → Slot bloqueado por el entrenador
```

**Domain Services**

```
AvailabilityScheduleService
├── generateWeeklySchedule(coachId, schedule) → void
├── checkConflicts(coachId, date, startTime, endTime) → List<Availability>
├── suggestAlternativeSlots(coachId, date, duration) → List<Availability>
└── validateAvailabilityRange(startTime, endTime) → boolean

AvailabilityStatusService
├── updateStatusFromBooking(availability, booking) → void
├── releaseSlot(availability) → void
├── markPermanentlyUnavailable(availability, reason) → void
└── syncStatusWithBookings(coachId) → void
```

**Domain Events**

```
AvailabilityCreated(availabilityId, coachId, date, startTime, endTime)
AvailabilityReserved(availabilityId, coachId, bookingId, timestamp)
AvailabilityReleased(availabilityId, coachId, timestamp)
AvailabilityMarkedUnavailable(availabilityId, coachId, reason, timestamp)
SlotDurationCalculated(availabilityId, durationMinutes, timestamp)
ConflictDetected(availabilityId, conflictingSlots[], timestamp)
```

**Enums**

```
AvailabilityStatus: AVAILABLE, RESERVED, UNAVAILABLE
TimeRange: [06:00 - 23:00] (válido solo dentro de este rango)
```

---

#### 2.6.6.2. Interface Layer

**REST Controllers**

```
AvailabilityController
├── POST /api/v1/availabilities → Crear nueva disponibilidad
│   Request: CreateAvailabilityDTO
│   Response: AvailabilityResponseDTO
│
├── GET /api/v1/availabilities → Listar disponibilidades (con filtros)
│   Query: ?coachId=1&date=2024-04-25&status=AVAILABLE
│   Response: PagedAvailabilityDTO
│
├── GET /api/v1/availabilities/{id} → Obtener disponibilidad específica
│   Response: AvailabilityDetailDTO
│
├── PUT /api/v1/availabilities/{id} → Actualizar disponibilidad
│   Request: UpdateAvailabilityDTO
│   Response: AvailabilityResponseDTO
│
├── DELETE /api/v1/availabilities/{id} → Eliminar disponibilidad
│   Response: 204 No Content
│
├── GET /api/v1/availabilities/coach/{coachId} → Listar por entrenador
│   Query: ?startDate=2024-04-25&endDate=2024-05-25
│   Response: List<AvailabilityDTO>
│
├── GET /api/v1/availabilities/coach/{coachId}/weekly → Agenda semanal
│   Query: ?week=2024-W17
│   Response: WeeklyScheduleDTO
│
├── PATCH /api/v1/availabilities/{id}/mark-reserved → Marcar como reservado
│   Request: MarkReservedDTO { bookingId }
│   Response: AvailabilityResponseDTO
│
├── PATCH /api/v1/availabilities/{id}/mark-available → Marcar como disponible
│   Request: EmptyRequest
│   Response: AvailabilityResponseDTO
│
└── GET /api/v1/availabilities/coach/{coachId}/conflicts → Detectar conflictos
    Query: ?startDate=2024-04-25
    Response: List<ConflictDTO>
```

**DTOs (Data Transfer Objects)**

```
CreateAvailabilityDTO
├── coachId: int (obligatorio)
├── date: Date (obligatorio)
├── startTime: Time (obligatorio, formato HH:mm)
├── endTime: Time (obligatorio, formato HH:mm)
└── status: String (opcional, default: AVAILABLE)

UpdateAvailabilityDTO
├── date: Date
├── startTime: Time
├── endTime: Time
└── status: String

AvailabilityResponseDTO
├── id: int
├── date: Date
├── startTime: Time
├── endTime: Time
├── status: String
├── durationMinutes: int
├── coach: CoachSummaryDTO { id, name }
└── createdAt: DateTime

AvailabilityDetailDTO
├── (todos los campos de AvailabilityResponseDTO)
├── updatedAt: DateTime
├── canBeModified: boolean
└── relatedBooking: BookingSummaryDTO (si status=RESERVED)

WeeklyScheduleDTO
├── coachId: int
├── weekStart: Date
├── weekEnd: Date
└── slots: List<DayScheduleDTO>

DayScheduleDTO
├── date: Date
├── dayName: String
├── availabilities: List<SlotDTO>

SlotDTO
├── id: int
├── startTime: Time
├── endTime: Time
├── status: String
└── isConflicted: boolean

CoachSummaryDTO
├── id: int
└── name: String

ConflictDTO
├── slot1Id: int
├── slot2Id: int
├── startTime: Time
├── endTime: Time
└── reason: String

MarkReservedDTO
├── bookingId: int → ID de la reserva asociada
└── reservedAt: DateTime

PagedAvailabilityDTO
├── content: List<AvailabilityDTO>
├── totalElements: long
├── totalPages: int
├── currentPage: int
└── pageSize: int
```

---

#### 2.6.6.3. Application Layer

**Command Handlers**

```
CreateAvailabilityCommandHandler
├── Input: CreateAvailabilityCommand (coachId, date, startTime, endTime, status)
├── Validaciones:
│   ├── Coach debe existir y estar activo
│   ├── startTime debe ser >= 06:00
│   ├── endTime debe ser <= 23:00
│   ├── startTime < endTime (validación débil, no implementada)
│   └── No validar solapes con otros slots (limitación actual)
├── Acciones:
│   ├── Crear entidad Availability
│   ├── Persistir en repositorio
│   └── Emitir evento AvailabilityCreated
└── Output: AvailabilityCreatedEvent

UpdateAvailabilityCommandHandler
├── Input: UpdateAvailabilityCommand (availabilityId, updates)
├── Validaciones:
│   ├── Availability debe existir
│   ├── Status actual != RESERVED (si está reservado no se puede cambiar)
│   ├── Validar rango horario si se envía
│   └── Verificar que el coach propietario autoriza el cambio
├── Acciones:
│   ├── Actualizar campos (date, startTime, endTime)
│   ├── Mantener integridad de reservas
│   └── Emitir evento AvailabilityUpdated
└── Output: AvailabilityUpdatedEvent

MarkAsReservedCommandHandler
├── Input: MarkAsReservedCommand (availabilityId, bookingId)
├── Validaciones:
│   ├── Availability debe estar en estado AVAILABLE
│   ├── Booking debe existir
│   └── Fechas deben coincidir
├── Acciones:
│   ├── Cambiar status a RESERVED
│   ├── Guardar referencia a booking
│   └── Emitir evento AvailabilityReserved
└── Output: AvailabilityReservedEvent

MarkAsAvailableCommandHandler
├── Input: MarkAsAvailableCommand (availabilityId)
├── Validaciones:
│   ├── Availability debe existir
│   └── Puede ser RESERVED o UNAVAILABLE
├── Acciones:
│   ├── Cambiar status a AVAILABLE
│   ├── Limpiar referencia a booking si existe
│   └── Emitir evento AvailabilityReleased
└── Output: AvailabilityReleasedEvent

MarkAsUnavailableCommandHandler
├── Input: MarkAsUnavailableCommand (availabilityId, reason)
├── Validaciones:
│   ├── Availability debe existir
│   └── No puede estar RESERVED
├── Acciones:
│   ├── Cambiar status a UNAVAILABLE
│   ├── Guardar reason/motivo
│   └── Emitir evento AvailabilityMarkedUnavailable
└── Output: AvailabilityMarkedUnavailableEvent

DeleteAvailabilityCommandHandler
├── Input: DeleteAvailabilityCommand (availabilityId)
├── Validaciones:
│   ├── Availability debe existir
│   └── No puede estar RESERVED
├── Acciones:
│   ├── Eliminar registro
│   └── Emitir evento AvailabilityDeleted
└── Output: AvailabilityDeletedEvent
```

**Event Handlers**

```
OnAvailabilityCreatedHandler
├── Escucha: AvailabilityCreatedEvent
├── Acciones:
│   ├── Notificar al coach que su disponibilidad fue creada
│   ├── Indexar en Search & Discovery para búsquedas futuras
│   └── Actualizar calendario visible en frontend
└── Publica: AvailabilityIndexedEvent

OnAvailabilityReservedHandler
├── Escucha: AvailabilityReservedEvent
├── Acciones:
│   ├── Notificar al coach que su slot fue reservado
│   ├── Actualizar estado en índices de búsqueda
│   ├── Enviar confirmación al usuario que hizo la reserva
│   └── Iniciar proceso de facturación si aplica
└── Publica: SlotReservedConfirmedEvent

OnAvailabilityReleasedHandler
├── Escucha: AvailabilityReleasedEvent
├── Acciones:
│   ├── Revertir a AVAILABLE si fue RESERVED
│   ├── Notificar cambio de estado
│   ├── Actualizar índices de búsqueda
│   └── Generar notificación a usuarios interesados
└── Publica: SlotBecameAvailableEvent

OnBookingCancelledHandler (desde Booking Context)
├── Escucha: BookingCancelledEvent
├── Acciones:
│   ├── Encontrar Availability asociada
│   ├── Cambiar status de RESERVED a AVAILABLE
│   └── Notificar al coach que el slot quedó libre
└── Publica: AvailabilityReleasedEvent
```

---

#### 2.6.6.4. Infrastructure Layer

**Repositories**

```
AvailabilityRepository
├── save(availability: Availability) → void
├── findById(availabilityId: int) → Availability
├── findByCoachId(coachId: int) → List<Availability>
├── findByCoachAndDate(coachId, date) → List<Availability>
├── findByCoachAndDateRange(coachId, startDate, endDate) → List<Availability>
├── findByStatus(status: AvailabilityStatus) → List<Availability>
├── findConflicts(coachId, date, startTime, endTime) → List<Availability>
├── findAvailableSlots(coachId, date) → List<Availability>
├── update(availability: Availability) → void
├── delete(availabilityId: int) → void
└── findByCoachIdAndWeek(coachId, weekNumber) → List<Availability>
```

**Adapters**

```
AvailabilityNotificationAdapter
├── notifyCoachSlotCreated(coach, availability) → void
├── notifyCoachSlotReserved(coach, availability, booking) → void
├── notifyCoachSlotReleased(coach, availability) → void
├── notifyUserSlotAvailable(user, availability, coach) → void
└── sendWeeklyScheduleReminder(coach) → void

AvailabilitySearchIndexAdapter (Elasticsearch)
├── indexAvailability(availability) → void
├── updateIndex(availabilityId, updates) → void
├── removeFromIndex(availabilityId) → void
├── searchAvailableSlots(coachId, date, duration) → List<SearchResult>
└── bulkIndexCoachSchedule(coachId) → void

AvailabilityCalendarAdapter (Google Calendar Integration)
├── syncToCalendar(coach, availability) → void
├── removeFromCalendar(availability) → void
├── getCoachCalendarEvents(coachId, dateRange) → List<CalendarEvent>
└── markBlockedTime(coach, startDate, endDate, reason) → void

ConflictDetectionAdapter
├── detectTimeConflicts(coachId, startTime, endTime, date) → List<Conflict>
├── validateTimeRange(startTime, endTime) → boolean
└── calculateSlotsOverlap(slot1, slot2) → int (duración en minutos)
```

**Persistencia**

```
Tabla: availabilities
├── availability_id (PK, INT, AUTO_INCREMENT)
├── coach_id (FK → coaches.coach_id, NOT NULL)
├── date (DATE, NOT NULL)
├── start_time (TIME, NOT NULL)
├── end_time (TIME, NOT NULL)
├── status (ENUM, DEFAULT 'AVAILABLE')
├── booking_id (FK → bookings.booking_id, NULLABLE)
├── created_at (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)
├── updated_at (TIMESTAMP, ON UPDATE CURRENT_TIMESTAMP)
├── UNIQUE KEY (coach_id, date, start_time, end_time)
├── INDEX idx_coach_date (coach_id, date)
├── INDEX idx_coach_status (coach_id, status)
├── INDEX idx_date_status (date, status)
└── CONSTRAINT check_time_range (start_time < end_time AND HOUR(start_time) >= 6 AND HOUR(end_time) <= 23)

Tabla: availability_conflicts_log (para auditoría)
├── conflict_id (PK, INT, AUTO_INCREMENT)
├── availability_id1 (FK → availabilities.availability_id)
├── availability_id2 (FK → availabilities.availability_id)
├── conflict_type (VARCHAR, e.g., 'TIME_OVERLAP')
├── detected_at (TIMESTAMP)
└── resolved (BOOLEAN, DEFAULT FALSE)
```

---

#### 2.6.6.5. Bounded Context Software Architecture Component Level Diagrams

**Descripción:**

El diagrama de componentes para el Availabilities Context muestra cómo se organiza la gestión de disponibilidad de coaches:

```
┌─────────────────────────────────────────────────────────────┐
│      Availabilities Container                               │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Availability Management Component                   │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Crear/Actualizar disponibilidades                  │   │
│  │ • Gestionar duración de slots                        │   │
│  │ • Cambiar estados (AVAILABLE/RESERVED/UNAVAILABLE)   │   │
│  │ • Validar rangos horarios                            │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Conflict Detection Component                        │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Detectar solapes de horarios                       │   │
│  │ • Validar integridad de slots                        │   │
│  │ • Sugerir slots alternativos                         │   │
│  │ • Generar reportes de conflictos                     │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Schedule Generation Component                       │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Generar agenda semanal/mensual                     │   │
│  │ • Crear bloques horarios recurrentes                 │   │
│  │ • Gestionar excepciones y bloques                    │   │
│  │ • Sincronizar con calendario externo                 │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Status Management Component                         │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Actualizar estado de slots                         │   │
│  │ • Sincronizar con reservas (Booking Context)         │   │
│  │ • Liberar slots cuando se cancela reserva            │   │
│  │ • Bloquear slots permanentemente                     │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Notification Component                              │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • Notificar al coach sobre cambios                   │   │
│  │ • Alertar a usuarios de nuevos slots                 │   │
│  │ • Enviar recordatorios de sesiones próximas          │   │
│  │ • Coordinar con Notification & Communication Context │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Repository & Data Access Component                  │   │
│  ├──────────────────────────────────────────────────────┤   │
│  │ • AvailabilityRepository                             │   │
│  │ • Persistencia en base de datos                      │   │
│  │ • Caché de disponibilidades frecuentes               │   │
│  │ • Optimización de queries                            │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
└─────────────────────────────────────────────────────────────┘
         ↓                           ↓                   ↓
    ┌────────────┐      ┌────────────────┐      ┌──────────────┐
    │   SQLite   │      │  Elasticsearch  │      │Google Calendar│
    │(Availabil) │      │  (Índices)      │      │  (Sync)      │
    └────────────┘      └────────────────┘      └──────────────┘
         ↑                                              
         │ Interacción con Booking Context
    ┌────────────┐
    │  Bookings  │
    └────────────┘
```

**Relaciones entre Componentes:**

- **Availability Management ↔ Conflict Detection:** Valida y detecta conflictos antes de persistir
- **Schedule Generation → Availability Management:** Genera slots que luego Availability Management persiste
- **Status Management ← Booking Context:** Escucha cambios en reservas para actualizar estados
- **Notification ← Todos:** Se suscribe a eventos de todos los componentes
- **Repository ← Todos:** Accede a los datos persistidos en SQLite
- **Elasticsearch:** Mantiene índices para búsquedas rápidas de slots disponibles
- **Google Calendar:** Sincroniza la agenda del coach para coordinación externa

---

#### 2.6.6.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.6.6.1. Bounded Context Domain Layer Class Diagrams

**Diagrama UML de Clases - Availabilities Domain Layer**

```
┌─────────────────────────────────────┐
│      <<Aggregate>>                  │
│      Availability                   │
├─────────────────────────────────────┤
│ - id: int                           │
│ - date: Date                        │
│ - startTime: Time                   │
│ - endTime: Time                     │
│ - status: AvailabilityStatus        │
│ - coach: Coach (Reference)          │
│ - bookingId: int (nullable)         │
│ - createdAt: DateTime               │
│ - updatedAt: DateTime               │
├─────────────────────────────────────┤
│ + isConflictWith(other): boolean    │
│ + getSlotDuration(): int            │
│ + markAsReserved(): void            │
│ + markAsAvailable(): void           │
│ + markAsUnavailable(): void         │
│ + isValidTimeRange(): boolean       │
│ + canBeModified(): boolean          │
│ + overlapsWithDate(date): boolean   │
└────────────────┬────────────────────┘
                 │
     ┌───────────┴────────────┐
     │                        │
┌────▼──────────────────┐ ┌──▼────────────────────────┐
│   <<ValueObject>>     │ │  <<ValueObject>>          │
│  AvailabilityStatus   │ │  TimeRange                │
├───────────────────────┤ ├───────────────────────────┤
│ - name: String        │ │ - startTime: Time         │
│ - value: String       │ │ - endTime: Time           │
├───────────────────────┤ ├───────────────────────────┤
│ + isAvailable(): bool │ │ + isValid(): boolean      │
│ + isReserved(): bool  │ │ + duration(): int         │
│ + isUnavailable(): bo │ │ + overlaps(range): bool   │
└───────────────────────┘ │ + contains(time): bool    │
          ▲                └───────────────────────────┘
          │                         ▲
          │                         │
          │                    uses │
          │                         │
          ├─────────────────────────┤

┌─────────────────────────────────────┐
│   <<Reference>>                     │
│   Coach                             │
├─────────────────────────────────────┤
│ - id: int                           │
│ - name: String                      │
│ - expertise: String                 │
│ - phone: String                     │
└─────────────────────────────────────┘
          ▲
          │ references
          │
    ┌─────┴──────────┐

┌──────────────────────────────────────┐
│   <<Interface>>                      │
│   AvailabilityRepository             │
├──────────────────────────────────────┤
│ + save(a: Availability): void        │
│ + findById(id: int): Availability    │
│ + findByCoachId(coachId): List       │
│ + findByCoachAndDate(c, d): List     │
│ + findByStatus(status): List         │
│ + findConflicts(c, d, s, e): List    │
│ + update(a: Availability): void      │
│ + delete(id: int): void              │
└──────────────────────────────────────┘
           △
           │ implements
           │
    ┌──────┴───────┐
    │              │
┌───▼───────────────────────────────┐
│ AvailabilityRepositoryImpl         │
├───────────────────────────────────┤
│ - db: Database                    │
├───────────────────────────────────┤
│ + save(a): void                   │
│ + findById(id): Availability      │
│ + findByCoachId(cId): List        │
│ + findByCoachAndDate(c,d): List   │
│ + update(a): void                 │
│ + delete(id): void                │
└───────────────────────────────────┘

┌────────────────────────────────────────┐
│   <<Service>>                          │
│   AvailabilityScheduleService          │
├────────────────────────────────────────┤
│ - availabilityRepository               │
├────────────────────────────────────────┤
│ + generateWeeklySchedule(): void       │
│ + checkConflicts(): List               │
│ + suggestAlternativeSlots(): List      │
│ + validateAvailabilityRange(): boolean │
└────────────────────────────────────────┘

┌─────────────────────────────────────┐
│   <<Service>>                       │
│   AvailabilityStatusService         │
├─────────────────────────────────────┤
│ - availabilityRepository            │
├─────────────────────────────────────┤
│ + updateStatusFromBooking(): void   │
│ + releaseSlot(): void               │
│ + markPermanentlyUnavailable(): v   │
│ + syncStatusWithBookings(): void    │
└─────────────────────────────────────┘

┌────────────────────────────────────────┐
│   <<Enum>>                             │
│   AvailabilityStatus                   │
├────────────────────────────────────────┤
│ AVAILABLE                              │
│ RESERVED                               │
│ UNAVAILABLE                            │
└────────────────────────────────────────┘

Relaciones:
- Availability *───────── 1 Coach (references)
- Availability 1───────── * AvailabilityRepository (persisted by)
- AvailabilityScheduleService ──────► AvailabilityRepository
- AvailabilityStatusService ──────► AvailabilityRepository
- Availability ───────► AvailabilityStatus (has-a)
- Availability ───────► TimeRange (contains)
```

---

##### 2.6.6.6.2. Bounded Context Database Design Diagram

**Entity Relationship Diagram (ERD) - Availabilities**

```
┌──────────────────────────────────┐
│        coaches                    │
├──────────────────────────────────┤
│ PK coach_id (INT)                │
│ name (VARCHAR)                   │
│ expertise (VARCHAR)              │
│ phone (VARCHAR)                  │
└──────────────────────────────────┘
         ▲
         │ FK (coach_id)
         │
┌────────┴───────────────────────────────────────┐
│       availabilities                           │
├────────────────────────────────────────────────┤
│ PK availability_id (INT, AUTO_INCREMENT)       │
│ FK coach_id (INT, NOT NULL)                    │
│ date (DATE, NOT NULL)                          │
│ start_time (TIME, NOT NULL)                    │
│ end_time (TIME, NOT NULL)                      │
│ status (ENUM: AVAILABLE/RESERVED/UNAVAILABLE)  │
│ FK booking_id (INT, NULLABLE)                  │
│ created_at (TIMESTAMP)                         │
│ updated_at (TIMESTAMP)                         │
│ UNIQUE (coach_id, date, start_time, end_time)  │
│ INDEX idx_coach_date (coach_id, date)          │
│ INDEX idx_coach_status (coach_id, status)      │
│ INDEX idx_date_status (date, status)           │
│ CONSTRAINT check_time (start_time < end_time)  │
│ CONSTRAINT check_hours (HOUR >= 6 AND <= 23)   │
└───────────┬────────────────────────────────────┘
            │
            │ FK (booking_id)
            │
┌───────────▼────────────────────────┐
│        bookings                    │
├────────────────────────────────────┤
│ PK booking_id (INT)                │
│ FK user_id (INT)                   │
│ FK court_id (INT)                  │
│ start_time (DATETIME)              │
│ end_time (DATETIME)                │
│ created_at (TIMESTAMP)             │
└────────────────────────────────────┘

┌────────────────────────────────────────┐
│ availability_conflicts_log (auditoría) │
├────────────────────────────────────────┤
│ PK conflict_id (INT)                   │
│ FK availability_id1 (INT)              │
│ FK availability_id2 (INT)              │
│ conflict_type (VARCHAR)                │
│ detected_at (TIMESTAMP)                │
│ resolved (BOOLEAN)                     │
│ FOREIGN KEY (availability_id1) refs    │
│   availabilities.availability_id       │
│ FOREIGN KEY (availability_id2) refs    │
│   availabilities.availability_id       │
└────────────────────────────────────────┘

Relaciones:
- coaches (1) ──── (*) availabilities
- availabilities (*) ──── (1) bookings (reference cuando está RESERVED)
- availabilities (1) ──── (*) availability_conflicts_log
```

