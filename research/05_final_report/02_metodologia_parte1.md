# 2. Metodología de Investigación (Parte 1)

Este documento describe la metodología empleada en la fase inicial de investigación para la especificación de requerimientos de un Sistema de Gestión de Tienda de Ropa (SGTR). El proceso se diseñó para ser estructurado, recursivo y enfocado en la construcción de una base de conocimiento sólida, tal como se refleja en el estado actual del proyecto descrito en el [`01_resumen_ejecutivo_parte1.md`](./01_resumen_ejecutivo_parte1.md).

**2.1. Enfoque General**

Se adoptó un enfoque de investigación cualitativa, centrado en la recopilación y análisis de información documental y conceptual. El proceso se guio por las directrices de la [`consigna.pdf`](../../consigna.pdf) y se apoyó en el uso de herramientas de inteligencia artificial para la búsqueda de información (Brave Search AI).

**2.2. Fases de la Investigación Realizadas (Primer Ciclo)**

El primer ciclo de investigación completado comprendió las siguientes fases:

1.  **Fase 1: Inicialización y Delimitación del Alcance**
    *   **Objetivo:** Comprender los requerimientos generales del proyecto de investigación y establecer un marco inicial.
    *   **Actividades:**
        *   Revisión exhaustiva de la [`consigna.pdf`](../../consigna.pdf) para extraer los objetivos principales, temas de investigación (stakeholders, escenarios, directrices de requerimientos, casos de uso) y restricciones (estructura de directorios, formato de salida).
        *   Creación del documento [`01_definicion_alcance.md`](../01_initial_queries/01_definicion_alcance.md) para formalizar la comprensión del objetivo y los entregables esperados.
        *   Formulación de un conjunto inicial de preguntas clave en [`02_preguntas_clave.md`](../01_initial_queries/02_preguntas_clave.md) para guiar la búsqueda de información.
        *   Identificación preliminar de tipos de fuentes de información en [`03_fuentes_informacion.md`](../01_initial_queries/03_fuentes_informacion.md).

2.  **Fase 2: Recolección Inicial de Datos y Documentación de Hallazgos Primarios**
    *   **Objetivo:** Recopilar información general y fundamental sobre cada uno de los temas de investigación definidos.
    *   **Actividades:**
        *   Ejecución de consultas de búsqueda amplias utilizando Brave Search AI, basadas en las preguntas clave.
        *   Análisis de los resultados de búsqueda para identificar fuentes relevantes (artículos, blogs, documentación técnica, ejemplos).
        *   Documentación sistemática de los hallazgos directos en los archivos de "Hallazgos Primarios":
            *   [`01_hallazgos_primarios_parte1.md`](../02_data_collection/01_hallazgos_primarios_parte1.md) (enfocado en stakeholders, regulaciones, interacción con proveedores).
            *   [`01_hallazgos_primarios_parte2.md`](../02_data_collection/01_hallazgos_primarios_parte2.md) (enfocado en escenarios, directrices de requerimientos, casos de uso y estándar IEEE 830).
        *   Citación de fuentes para asegurar la trazabilidad de la información.

3.  **Fase 3: Primer Análisis e Identificación de Brechas de Conocimiento**
    *   **Objetivo:** Evaluar la información recopilada, identificar patrones iniciales y, crucialmente, determinar las áreas donde se requería información más específica o detallada.
    *   **Actividades:**
        *   Revisión crítica de los hallazgos primarios.
        *   Creación y mantenimiento del documento [`03_brechas_conocimiento_criticas_parte1.md`](../03_analysis/03_brechas_conocimiento_criticas_parte1.md), listando preguntas específicas sin respuesta o áreas que necesitaban mayor profundización (ej. ejemplos concretos de escenarios y casos de uso para tienda de ropa, detalles sobre ilustraciones faltantes).

4.  **Fase 4: Ciclos de Investigación Específica (Abordaje de Brechas)**
    *   **Objetivo:** Abordar sistemáticamente las brechas de conocimiento identificadas mediante búsquedas más enfocadas y la generación de contenido específico.
    *   **Actividades:**
        *   Para cada brecha prioritaria:
            *   Formulación de nuevas consultas de búsqueda específicas para Brave Search AI.
            *   Análisis de los resultados y síntesis de la información relevante.
            *   Generación de contenido nuevo o ampliación del existente en los documentos de hallazgos o creación de nuevos documentos de ejemplos, tales como:
                *   Ampliación de secciones en [`01_hallazgos_primarios_parte1.md`](../02_data_collection/01_hallazgos_primarios_parte1.md) y [`01_hallazgos_primarios_parte2.md`](../02_data_collection/01_hallazgos_primarios_parte2.md).
                *   Creación de [`04_ejemplos_escenarios_tienda_ropa_parte1.md`](../02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte1.md) y [`04_ejemplos_escenarios_tienda_ropa_parte2.md`](../02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte2.md).
                *   Creación de [`05_ejemplos_casos_uso_tienda_ropa_parte1.md`](../02_data_collection/05_ejemplos_casos_uso_tienda_ropa_parte1.md).
                *   Creación de [`06_diagrama_casos_uso_borrador_parte1.md`](../02_data_collection/06_diagrama_casos_uso_borrador_parte1.md).
            *   Actualización del estado de la brecha en [`03_brechas_conocimiento_criticas_parte1.md`](../03_analysis/03_brechas_conocimiento_criticas_parte1.md).
        *   Este proceso se repitió hasta que todas las brechas identificadas inicialmente fueron abordadas satisfactoriamente.

5.  **Fase 5: Síntesis (Actual)**
    *   **Objetivo:** Consolidar y estructurar el conocimiento adquirido en un modelo cohesivo y extraer las ideas principales.
    *   **Actividades:**
        *   Creación del [`01_modelo_integrado_parte1.md`](../04_synthesis/01_modelo_integrado_parte1.md) del SGTR.
        *   Destilación de [`02_ideas_clave_parte1.md`](../04_synthesis/02_ideas_clave_parte1.md).
        *   Identificación de [`03_aplicaciones_practicas_parte1.md`](../04_synthesis/03_aplicaciones_practicas_parte1.md).

**2.3. Herramientas y Técnicas**

*   **Búsqueda de Información:** Brave Search AI (a través de MCP Tool).
*   **Organización Documental:** Estructura de directorios y archivos Markdown según lo especificado.
*   **Gestión de Brechas:** Documento dedicado ([`03_brechas_conocimiento_criticas_parte1.md`](../03_analysis/03_brechas_conocimiento_criticas_parte1.md)) para un seguimiento recursivo.
*   **Control de Tamaño de Archivos:** Adhesión a la restricción de aproximadamente 500 líneas por archivo físico, dividiendo el contenido conceptualmente extenso en partes secuenciales.

**2.4. Limitaciones de la Fase Actual**

*   La investigación se ha basado principalmente en fuentes secundarias accesibles en línea. No se realizaron entrevistas directas con stakeholders de tiendas de ropa.
*   Las "ilustraciones" mencionadas en la [`consigna.pdf`](../../consigna.pdf) no estaban disponibles, por lo que se buscaron o crearon interpretaciones basadas en ejemplos y mejores prácticas.
*   El enfoque ha sido genérico para un "Sistema de Gestión de Tienda de Ropa", sin adaptarse a un contexto de negocio ultra-específico.

Esta metodología ha permitido construir una base de conocimiento inicial robusta y bien estructurada, sentando las bases para la elaboración de un informe final detallado y, potencialmente, para ciclos de investigación futuros más profundos si fueran necesarios.
