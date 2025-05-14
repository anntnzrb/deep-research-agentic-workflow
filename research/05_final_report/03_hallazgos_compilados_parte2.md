# 3. Hallazgos Compilados de la Investigación (Parte 2)

Este documento es la continuación de [`03_hallazgos_compilados_parte1.md`](./03_hallazgos_compilados_parte1.md) y sigue consolidando los principales hallazgos de la investigación, enfocándose en las directrices para la especificación de requerimientos y el análisis de casos de uso.

## 3.4. Directrices para la Especificación de Requerimientos

Se investigaron y documentaron varias directrices cruciales para la correcta especificación de requerimientos, basadas en la [`consigna.pdf`](../../consigna.pdf) y fuentes complementarias.

*   **Uso de Lenguaje Claro y Distinción Obligatorio/Deseable:**
    *   Se enfatizó la necesidad de un lenguaje preciso y la clara diferenciación entre requerimientos que el sistema "debe" cumplir (obligatorios) y aquellos que "debería" o "podría" cumplir (deseables).
    *   Se proporcionaron múltiples ejemplos de requerimientos obligatorios y deseables para diversos módulos de un SGTR (Gestión de Inventario/Productos, Gestión de Clientes, Ventas y Facturación POS, Reportes y Análisis).
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#c1-uso-de-lenguaje-claro-y-distinci%C3%B3n-entre-requerimientos-obligatorios-y-deseables`](../02_data_collection/01_hallazgos_primarios_parte2.md#c1-uso-de-lenguaje-claro-y-distinci%C3%B3n-entre-requerimientos-obligatorios-y-deseables)
*   **Uso de Texto Resaltado:**
    *   Se exploraron mejores prácticas para el uso de negrita, cursiva y color, con el fin de mejorar la legibilidad y destacar información clave sin generar ruido visual. Se recomendó moderación, consistencia y un propósito claro para el resaltado.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#c2-uso-de-texto-resaltado`](../02_data_collection/01_hallazgos_primarios_parte2.md#c2-uso-de-texto-resaltado)
*   **Evitar Jerga Técnica Innecesaria y Uso de Glosario:**
    *   Se destacó la importancia de preferir un lenguaje sencillo y, cuando los términos técnicos son indispensables, explicarlos adecuadamente.
    *   Se propuso la creación de un glosario de términos técnicos comunes (ej. API, SKU, CRM, KPI) explicados en lenguaje sencillo para los stakeholders.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#c3-evitar-jerga-t%C3%A9cnica-innecesaria-y-uso-de-glosario`](../02_data_collection/01_hallazgos_primarios_parte2.md#c3-evitar-jerga-t%C3%A9cnica-innecesaria-y-uso-de-glosario)
*   **Asociar una Razón con Cada Requerimiento:**
    *   Se subrayó la utilidad de explicar el "por qué" de cada requerimiento para facilitar la toma de decisiones durante el desarrollo y, especialmente, durante la gestión de cambios.
    *   Se investigó el impacto práctico de esta directriz, concluyendo que, aunque no abundan estudios de caso específicos bajo ese título exacto, el principio está implícito en la gestión exitosa de la evolución de requerimientos. Conocer la razón ayuda a evaluar cambios, tomar decisiones de diseño informadas y prevenir "scope creep".
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#c4-asociar-una-raz%C3%B3n-con-cada-requerimiento`](../02_data_collection/01_hallazgos_primarios_parte2.md#c4-asociar-una-raz%C3%B3n-con-cada-requerimiento) y [`research/02_data_collection/01_hallazgos_primarios_parte2.md#c41-impacto-pr%C3%A1ctico-de-la-raz%C3%B3n-del-requerimiento-estudios-y-ejemplos`](../02_data_collection/01_hallazgos_primarios_parte2.md#c41-impacto-pr%C3%A1ctico-de-la-raz%C3%B3n-del-requerimiento-estudios-y-ejemplos)

## 3.5. Análisis y Descripción de Casos de Uso (Estándar IEEE 830)

Se investigó la aplicación de casos de uso, con referencia al estándar IEEE 830, para la especificación de requerimientos funcionales del SGTR.

*   **Casos de Uso y el Estándar IEEE 830:**
    *   Se definió la Especificación de Requisitos de Software (ERS) según IEEE 830 y el papel central de los casos de uso para describir las interacciones usuario-sistema.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#d1-casos-de-uso-y-el-est%C3%A1ndar-ieee-830`](../02_data_collection/01_hallazgos_primarios_parte2.md#d1-casos-de-uso-y-el-est%C3%A1ndar-ieee-830)
*   **Estructura de un Caso de Uso:**
    *   Se detalló una estructura común para la descripción de casos de uso, incluyendo identificador, actores, descripción, precondiciones, flujo principal, flujos alternativos y de excepción, postcondiciones y requisitos especiales.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#d2-estructura-de-un-caso-de-uso-basado-en-ieee-830-y-pr%C3%A1cticas-comunes`](../02_data_collection/01_hallazgos_primarios_parte2.md#d2-estructura-de-un-caso-de-uso-basado-en-ieee-830-y-pr%C3%A1cticas-comunes)
*   **Ejemplos Detallados de Casos de Uso para Tienda de Ropa:**
    *   Se desarrollaron dos ejemplos completos de casos de uso:
        1.  CU-001: Gestionar Devolución de Producto.
        2.  CU-002: Aplicar Descuento Promocional.
    *   Referencia: [`research/02_data_collection/05_ejemplos_casos_uso_tienda_ropa_parte1.md`](../02_data_collection/05_ejemplos_casos_uso_tienda_ropa_parte1.md)
*   **Diagramas de Casos de Uso:**
    *   Se describieron los elementos de un diagrama de casos de uso (actores, casos de uso, relaciones, límite del sistema).
    *   Se creó un borrador textual para un diagrama de casos de uso específico para un SGTR, identificando actores principales, casos de uso clave y sus interrelaciones.
    *   Referencias:
        *   [`research/02_data_collection/01_hallazgos_primarios_parte2.md#d3-diagramas-de-casos-de-uso`](../02_data_collection/01_hallazgos_primarios_parte2.md#d3-diagramas-de-casos-de-uso)
        *   [`research/02_data_collection/06_diagrama_casos_uso_borrador_parte1.md`](../02_data_collection/06_diagrama_casos_uso_borrador_parte1.md)
*   **Contenido de un ERS (IEEE 830) para SGTR:**
    *   Se detalló cómo se contextualizarían las secciones principales de un ERS (Introducción, Descripción General, Requisitos Específicos) para un Sistema de Gestión de Tienda de Ropa.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#d4-contenido-de-un-ers-ieee-830-para-un-sistema-de-gesti%C3%B3n-de-tienda-de-ropa`](../02_data_collection/01_hallazgos_primarios_parte2.md#d4-contenido-de-un-ers-ieee-830-para-un-sistema-de-gesti%C3%B3n-de-tienda-de-ropa)

Esta compilación resume los datos y ejemplos generados. El análisis y la síntesis de esta información se presentan en los capítulos subsiguientes de este informe.
