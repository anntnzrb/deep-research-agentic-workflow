# Preguntas Clave de la Investigación

Este documento lista las preguntas fundamentales que guiarán el proceso de investigación para la elaboración de la especificación de requerimientos del "Sistema de Gestión de Tienda de Ropa". Estas preguntas se derivan del documento [`consigna.pdf`](../../consigna.pdf) y del archivo [`01_definicion_alcance.md`](research/01_initial_queries/01_definicion_alcance.md).

## 1. Sobre la Identificación de Stakeholders (Contexto: Paso 1)

*   ¿Quiénes son los *sponsors* o representantes responsables típicos en un modelo de negocio de "Gestión de Tienda de Ropa"? ¿Cuáles son sus principales responsabilidades e intereses en un nuevo sistema de gestión?
*   ¿Cuáles son los diferentes grupos de *stakeholders* (internos y externos) involucrados en una tienda de ropa?
    *   ¿Qué roles administrativos (gerentes de tienda, encargados de inventario, personal de marketing, etc.) interactuarían con el sistema y cuáles serían sus necesidades?
    *   ¿Qué roles de usuarios finales (cajeros, vendedores, clientes web/móvil) utilizarían el sistema y qué funcionalidades esperarían?
    *   ¿Existen participantes externos relevantes (proveedores, empresas de logística, reguladores fiscales, certificadores de calidad, etc.) y cómo podrían interactuar o ser afectados por el sistema?
*   ¿Cómo se puede aplicar el ejemplo de stakeholders del sistema de salud (pacientes, médicos, enfermeros, etc.) al contexto de una tienda de ropa para identificar roles análogos?

## 2. Sobre la Especificación de Escenarios

*   ¿Qué es un escenario en el contexto de la adquisición de requerimientos y cuál es su utilidad para un sistema de gestión de tienda de ropa?
*   ¿Cómo se estructura un escenario típico?
    *   ¿Cómo describir "qué esperan el sistema y los usuarios cuando inicia el escenario" para una tienda de ropa (ej. inicio de sesión, búsqueda de producto)?
    *   ¿Cómo detallar "el flujo normal de los eventos" en escenarios comunes (ej. proceso de venta, devolución de un artículo, gestión de inventario, registro de nuevo cliente)?
    *   ¿Cómo identificar y describir "qué puede salir mal y cómo se manejaría" (ej. producto sin stock, fallo en el sistema de pago, datos de cliente incorrectos)?
    *   ¿Qué tipo de "información de otras actividades que estén en marcha al mismo tiempo" es relevante considerar (ej. múltiples ventas simultáneas, actualización de inventario mientras se consulta)?
    *   ¿Cómo definir "el estado del sistema cuando termina el escenario" (ej. venta completada y registrada, inventario actualizado)?
*   ¿Qué ejemplos concretos de escenarios se pueden desarrollar para un sistema de gestión de tienda de ropa (ej. "Cliente realiza compra online", "Vendedor procesa devolución en tienda", "Administrador genera reporte de ventas")?
*   ¿Qué elementos adicionales (especificaciones, tomas de pantalla, etc.) pueden complementar la descripción textual de un escenario?

## 3. Sobre las Directrices para la Especificación de Requerimientos

*   ¿Cómo se distingue lingüísticamente entre requerimientos obligatorios ("el sistema debe ser capaz de...") y deseables ("el sistema debería permitir...") en la especificación para una tienda de ropa? Proporcionar ejemplos.
*   ¿Cuál es la mejor manera de utilizar el texto resaltado (negrita, cursiva) para enfatizar partes clave de un requerimiento sin sobrecargar el documento?
*   ¿Qué términos técnicos comunes en ingeniería de software (ej. "arquitectura", "módulo", "API", "base de datos") podrían ser malinterpretados por stakeholders no técnicos de una tienda de ropa y cómo se pueden evitar o aclarar?
*   ¿Por qué es importante asociar una "razón" o justificación a cada requerimiento de usuario? ¿Cómo ayuda esto en el ciclo de vida del software, especialmente ante cambios?
*   ¿Cómo se pueden aplicar estas directrices para mejorar la claridad y precisión de los requerimientos de un sistema de gestión de tienda de ropa?

## 4. Sobre el Análisis y Descripción de Casos de Uso (Contexto: Paso 3)

*   ¿Qué es un caso de uso y cuál es su rol en la especificación de requerimientos según el estándar IEEE 830?
*   ¿Cómo se identifican los actores y los casos de uso principales para un sistema de gestión de tienda de ropa?
*   ¿Cuál es la estructura típica de una descripción de caso de uso (ej. nombre, actores, precondiciones, flujo principal, flujos alternativos, postcondiciones)?
*   ¿Cómo se elabora un diagrama de casos de uso para representar las interacciones en un sistema de gestión de tienda de ropa? (Referenciar Ilustración 5 de [`consigna.pdf`](../../consigna.pdf) como guía para el tipo de diagrama esperado).
*   ¿Qué ejemplos de casos de uso detallados (siguiendo la estructura de IEEE 830, como se sugiere en Ilustraciones 3 y 4 de [`consigna.pdf`](../../consigna.pdf)) se pueden desarrollar para el sistema (ej. "Gestionar inventario de productos", "Procesar venta en punto físico", "Registrar cliente", "Consultar historial de compras")?

## 5. Generales sobre el Proceso de Investigación

*   ¿Cuáles son las fuentes de información más fiables (artículos académicos, estudios de la industria, documentación de software similar, foros de expertos) para cada una de las áreas anteriores?
*   ¿Cómo se puede asegurar que la información recopilada sea relevante, actual y aplicable al contexto específico de un sistema de gestión de tienda de ropa en un entorno web/móvil?
