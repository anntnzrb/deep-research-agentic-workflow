# 3. Hallazgos Compilados de la Investigación (Parte 1)

Este capítulo consolida los principales hallazgos obtenidos durante las fases de recolección de datos de la investigación. Se estructura siguiendo los temas clave definidos en la etapa de inicialización y abordados a través de la consulta de fuentes y la generación de ejemplos específicos. Para una exploración completa y detallada de cada punto, se remite al lector a los documentos originales en los subdirectorios `research/01_initial_queries` y `research/02_data_collection`.

## 3.1. Delimitación del Alcance y Enfoque Inicial

La investigación se inició con una definición clara de su propósito: recopilar, analizar y sintetizar información para la especificación de requerimientos de un Sistema de Gestión de Tienda de Ropa (SGTR), guiada por la [`consigna.pdf`](../../consigna.pdf).

*   **Objetivo Principal:** Establecer una base de conocimiento para la especificación de requerimientos.
    *   Referencia: [`research/01_initial_queries/01_definicion_alcance.md`](../01_initial_queries/01_definicion_alcance.md)
*   **Preguntas Clave:** Se formularon preguntas iniciales para dirigir la búsqueda de información en torno a stakeholders, escenarios, directrices de requerimientos y casos de uso.
    *   Referencia: [`research/01_initial_queries/02_preguntas_clave.md`](../01_initial_queries/02_preguntas_clave.md)
*   **Fuentes de Información:** Se identificaron tipos de fuentes primarias y secundarias, con un enfoque en la búsqueda online mediante Brave Search AI.
    *   Referencia: [`research/01_initial_queries/03_fuentes_informacion.md`](../01_initial_queries/03_fuentes_informacion.md)

## 3.2. Identificación y Caracterización de Stakeholders

Un componente crucial fue la identificación de las partes interesadas (stakeholders) en un SGTR y la comprensión de sus roles y expectativas.

*   **Definición General:** Se establecieron las definiciones de stakeholder y sponsor de proyecto.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte1.md#a1-definici%C3%B3n-general-de-stakeholders-y-sponsor`](../02_data_collection/01_hallazgos_primarios_parte1.md#a1-definici%C3%B3n-general-de-stakeholders-y-sponsor)
*   **Stakeholders Específicos en Tienda de Ropa:**
    *   **Sponsor/Representante Responsable:** Se detalló que en tiendas pequeñas/medianas suele ser el Gerente General/Propietario. En grandes empresas, pueden ser Directores de Operaciones, Tecnología, Comercial o un Comité Directivo. Se listaron sus expectativas específicas (ROI, escalabilidad, omnicanalidad, etc.).
    *   **Stakeholders Internos:** Gerentes de tienda, vendedores, personal de almacén, marketing, diseñadores, personal de TI, equipo del proyecto.
    *   **Stakeholders Externos:** Clientes, proveedores, entidades reguladoras, empresas de logística, bancos/procesadores de pago.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte1.md#a2-stakeholders-espec%C3%ADficos-en-un-sistema-de-gesti%C3%B3n-de-tienda-de-ropa`](../02_data_collection/01_hallazgos_primarios_parte1.md#a2-stakeholders-espec%C3%ADficos-en-un-sistema-de-gesti%C3%B3n-de-tienda-de-ropa)
*   **Comparación con Ejemplo del Sector Salud:** Se realizó una analogía de los roles de stakeholders del sector salud (provistos en la [`consigna.pdf`](../../consigna.pdf)) con los equivalentes en una tienda de ropa.
    *   Ejemplos: Pacientes -> Clientes; Médicos -> Gerentes de Tienda/Compradores; Enfermeros -> Vendedores/Asesores.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte1.md#a3-comparaci%C3%B3n-de-stakeholders-sector-salud-vs-tienda-de-ropa-seg%C3%BAn-consignapdf`](../02_data_collection/01_hallazgos_primarios_parte1.md#a3-comparaci%C3%B3n-de-stakeholders-sector-salud-vs-tienda-de-ropa-seg%C3%BAn-consignapdf)
*   **Regulaciones y su Impacto:** Se investigaron las regulaciones clave en un contexto latinoamericano general que afectan a un SGTR:
    *   Fiscales (facturación, impuestos).
    *   Laborales (gestión de empleados, si el módulo existe).
    *   Protección de Datos Personales (consentimiento, seguridad).
    *   Etiquetado de Productos Textiles.
    *   Leyes de Protección al Consumidor.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte1.md#a4-regulaciones-espec%C3%ADficas-y-su-impacto-en-el-sistema-de-gesti%C3%B3n-contexto-latinoamericano-general`](../02_data_collection/01_hallazgos_primarios_parte1.md#a4-regulaciones-espec%C3%ADficas-y-su-impacto-en-el-sistema-de-gesti%C3%B3n-contexto-latinoamericano-general)
*   **Interacción con Proveedores:** Se exploraron los niveles y formas de interacción de los proveedores con el sistema de gestión, incluyendo portales B2B, EDI, APIs y comunicación tradicional.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte1.md#a5-nivel-de-interacci%C3%B3n-de-proveedores-con-el-sistema-de-gesti%C3%B3n`](../02_data_collection/01_hallazgos_primarios_parte1.md#a5-nivel-de-interacci%C3%B3n-de-proveedores-con-el-sistema-de-gesti%C3%B3n)

## 3.3. Especificación y Uso de Escenarios

Los escenarios fueron identificados como una técnica clave para la elicitación y validación de requerimientos.

*   **Definición y Utilidad:** Describen interacciones específicas usuario-sistema, ayudando a comprender el uso real, facilitar la comunicación y descubrir requerimientos.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#b1-definici%C3%B3n-y-utilidad-de-los-escenarios`](../02_data_collection/01_hallazgos_primarios_parte2.md#b1-definici%C3%B3n-y-utilidad-de-los-escenarios)
*   **Estructura General de un Escenario:** Se detallaron los componentes típicos de un escenario (precondiciones, flujo normal, excepciones, actividades concurrentes, postcondiciones), basados en la [`consigna.pdf`](../../consigna.pdf) y fuentes complementarias.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#b2-estructura-general-de-un-escenario`](../02_data_collection/01_hallazgos_primarios_parte2.md#b2-estructura-general-de-un-escenario)
*   **Complementos Visuales y Documentales:** Se investigaron elementos como bocetos, wireframes, mockups, prototipos y diagramas de flujo para enriquecer los escenarios.
    *   Referencia: [`research/02_data_collection/01_hallazgos_primarios_parte2.md#b3-complementos-visuales-y-documentales-para-escenarios`](../02_data_collection/01_hallazgos_primarios_parte2.md#b3-complementos-visuales-y-documentales-para-escenarios)
*   **Ejemplos Detallados de Escenarios para Tienda de Ropa:** Se desarrollaron cinco escenarios específicos para ilustrar la aplicación práctica:
    1.  Cliente realiza compra de múltiples artículos en tienda física con pago mixto.
    2.  Cliente devuelve artículo comprado online en tienda física.
    3.  Cliente gestiona y recoge pedido online en tienda física ("Click & Collect").
    4.  Recepción de nueva mercancía de un proveedor.
    5.  Gerente genera informe de ventas semanal.
    *   Referencias:
        *   [`research/02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte1.md`](../02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte1.md)
        *   [`research/02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte2.md`](../02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte2.md)

*(La compilación de hallazgos continuará en `03_hallazgos_compilados_parte2.md` si es necesario, cubriendo las directrices de requerimientos y los casos de uso.)*
