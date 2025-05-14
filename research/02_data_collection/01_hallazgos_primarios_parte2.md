# Hallazgos Primarios (Parte 2)

Este documento es la continuación de [`01_hallazgos_primarios_parte1.md`](research/02_data_collection/01_hallazgos_primarios_parte1.md) y contiene los hallazgos directos obtenidos de las búsquedas de información, enfocándose en responder las [`02_preguntas_clave.md`](../01_initial_queries/02_preguntas_clave.md). Se citarán las fuentes siempre que sea posible.

## Sección B: Especificación de Escenarios (Contexto: Paso 2 de [`consigna.pdf`](../../consigna.pdf))

### B.1. Definición y Utilidad de los Escenarios

Los escenarios son una técnica utilizada en la ingeniería de requerimientos para describir la interacción entre los usuarios (o otros sistemas) y el sistema que se está desarrollando. Son particularmente útiles para detallar un bosquejo de descripción de requerimientos, transformando ideas informales y vagas en una especificación más comprensible y acordada por todos los involucrados. (Fuente: SEDICI UNLP, "Escenarios en la ingenieria de requerimientos", [[http://sedici.unlp.edu.ar/handle/10915/2155](http://sedici.unlp.edu.ar/handle/10915/2155)]; SEDICI UNLP, "2. INGENIERÍA DE REQUERIMIENTOS.", [[http://sedici.unlp.edu.ar/bitstream/handle/10915/4057/2_-_Ingenier%C3%ADa_de_requerimientos.pdf?sequence=4](http://sedici.unlp.edu.ar/bitstream/handle/10915/4057/2_-_Ingenier%C3%ADa_de_requerimientos.pdf?sequence=4)])

Un escenario describe una secuencia particular de uso del sistema, representando un ejemplo de una sesión de interacción. Comienza con un bosquejo de la interacción y, durante el proceso de adquisición de requerimientos, se le suman detalles para crear una representación completa. (Fuente: [`consigna.pdf`](../../consigna.pdf), Paso 2b; UNICEN, "Escenarios", [[https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf](https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf)])

**Utilidad de los escenarios:**
*   Ayudan a comprender cómo los usuarios interactuarán con el sistema en situaciones concretas.
*   Facilitan la comunicación entre los stakeholders (desarrolladores, clientes, usuarios).
*   Permiten identificar requerimientos funcionales y no funcionales.
*   Sirven como base para el diseño de casos de prueba.
*   Ayudan a validar que el sistema cumplirá con las expectativas de los usuarios.
(Derivado de las fuentes anteriores y principios generales de ingeniería de requerimientos).

### B.2. Estructura General de un Escenario

Según la [`consigna.pdf`](../../consigna.pdf) (Paso 2b) y complementado por las fuentes, un escenario generalmente incluye:

1.  **Una descripción de qué esperan el sistema y los usuarios cuando inicia el escenario (Precondiciones):** Estado inicial del sistema y del entorno, y qué conocimientos o herramientas tiene el usuario. (Fuente: UNICEN, "Escenarios", [[https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf](https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf)])
2.  **Una descripción en el escenario del flujo normal de los eventos (Secuencia Principal):** La secuencia paso a paso de las interacciones entre el usuario y el sistema para lograr el objetivo del escenario.
3.  **Una descripción de qué puede salir mal y cómo se manejaría (Excepciones / Flujos Alternativos):** Posibles errores, problemas o desviaciones del flujo normal y cómo el sistema o el usuario los gestionan. (Fuente: UNICEN, "Escenarios", [[https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf](https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf)])
4.  **Información de otras actividades que estén en marcha al mismo tiempo (Actividades Concurrentes):** Aunque no siempre se detalla explícitamente en todos los formatos de escenario, es una consideración importante para sistemas multiusuario o con procesos en segundo plano.
5.  **Una descripción del estado del sistema cuando termina el escenario (Postcondiciones):** El resultado final de la interacción y el estado del sistema después de que el escenario se completa exitosamente (o falla). (Fuente: UNICEN, "Escenarios", [[https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf](https://users.exa.unicen.edu.ar/catedras/ingrequi/index_archivos/Notas-Escenarios.pdf)])

Un documento de la Universidad Nacional de La Plata (SEDICI UNLP, "4_-_Escenarios.pdf", [[http://sedici.unlp.edu.ar/bitstream/handle/10915/4057/4_-_Escenarios.pdf?sequence=5](http://sedici.unlp.edu.ar/bitstream/handle/10915/4057/4_-_Escenarios.pdf?sequence=5)]) también profundiza en la estructura y uso de escenarios, mencionando elementos como:
*   **Título:** Un nombre descriptivo.
*   **Objetivo/Meta:** Qué se espera lograr con el escenario.
*   **Contexto:** Situación inicial.
*   **Recursos:** Elementos necesarios.
*   **Actores:** Quiénes participan.
*   **Episodios:** Secuencia de acciones.

Los escenarios pueden escribirse como texto y complementarse con especificaciones, tomas de pantalla, etc. (Fuente: [`consigna.pdf`](../../consigna.pdf), Paso 2b).

Para ejemplos detallados de escenarios aplicados al contexto de una tienda de ropa, ver el documento [`04_ejemplos_escenarios_tienda_ropa_parte1.md`](research/02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte1.md).

*(Esta sección se continuará desarrollando con más detalles sobre la elaboración de escenarios y referencias a ejemplos adicionales si se crean más partes del archivo de ejemplos.)*

### B.3. Complementos Visuales y Documentales para Escenarios

Además de la descripción textual, los escenarios pueden enriquecerse con diversos elementos para mejorar su comprensión y utilidad, especialmente en el contexto de un sistema de gestión de tienda de ropa que tendrá interfaces de usuario (UI) y procesos específicos:

1.  **Bocetos (Sketches):**
    *   Dibujos rápidos de baja fidelidad (a mano o digital) de pantallas clave o flujos de interacción. Útiles para exploración temprana.
    *   *Ej. Tienda de Ropa:* Un boceto rápido de la pantalla del POS durante el escaneo de artículos.
    *   (Fuente: Mosaic UOC [[https://mosaic.uoc.edu/2015/09/15/proceso-de-desarrollo-de-un-proyecto-digital/](https://mosaic.uoc.edu/2015/09/15/proceso-de-desarrollo-de-un-proyecto-digital/)]).

2.  **Wireframes:**
    *   Representaciones esquemáticas de la estructura y disposición de elementos en una UI, enfocadas en funcionalidad y jerarquía de información. Pueden ser de baja o alta fidelidad (clicables).
    *   *Ej. Tienda de Ropa:* Wireframes de las pantallas del sistema POS para el escenario de venta, o de las páginas de catálogo y detalle de producto para un escenario de compra online.
    *   (Fuentes: Adictos al Trabajo [[https://adictosaltrabajo.com/2019/10/01/diferencias-entre-wireframes-y-mockups/](https://adictosaltrabajo.com/2019/10/01/diferencias-entre-wireframes-y-mockups/)]; Miro [[https://miro.com/es/wireframe/que-es-wireframe/](https://miro.com/es/wireframe/que-es-wireframe/)]).
    *   Herramientas como Moqups [[https://moqups.com/](https://moqups.com/)] o Lucidchart [[https://www.lucidchart.com/pages/es/ejemplos/herramienta-de-prototipos-de-sitios-web](https://www.lucidchart.com/pages/es/ejemplos/herramienta-de-prototipos-de-sitios-web)] pueden ser útiles.

3.  **Mockups (Maquetas Visuales):**
    *   Diseños de alta fidelidad que muestran la apariencia visual final (colores, tipografía, imágenes). Generalmente estáticos.
    *   *Ej. Tienda de Ropa:* Mockup de la pantalla de inicio de la app móvil de la tienda, o de la ficha de producto en el e-commerce.
    *   (Fuentes: Adictos al Trabajo [[https://adictosaltrabajo.com/2019/10/01/diferencias-entre-wireframes-y-mockups/](https://adictosaltrabajo.com/2019/10/01/diferencias-entre-wireframes-y-mockups/)]; Medium - Rocket Studio UX [[https://medium.com/rocket-studio-ux/wireframe-mockup-y-prototipos-en-busca-de-sus-diferencias-23a03bcbdb69](https://medium.com/rocket-studio-ux/wireframe-mockup-y-prototipos-en-busca-de-sus-diferencias-23a03bcbdb69)]).

4.  **Prototipos:**
    *   Representaciones interactivas (clicables) de la interfaz, simulando la navegación. Pueden ser de baja o alta fidelidad.
    *   *Ej. Tienda de Ropa:* Un prototipo clicable del proceso de checkout en la tienda online, o de la navegación por los reportes de ventas para un gerente.
    *   (Fuente: Medium - Rocket Studio UX [[https://medium.com/rocket-studio-ux/wireframe-mockup-y-prototipos-en-busca-de-sus-diferencias-23a03bcbdb69](https://medium.com/rocket-studio-ux/wireframe-mockup-y-prototipos-en-busca-de-sus-diferencias-23a03bcbdb69)]).

5.  **Diagramas de Flujo o Actividad (UML):**
    *   Representaciones gráficas formales de los pasos, decisiones y flujos de un proceso.
    *   *Ej. Tienda de Ropa:* Un diagrama de actividad para el proceso de devolución de mercancía, mostrando las diferentes validaciones y caminos posibles.

6.  **Especificaciones Adicionales / Reglas de Negocio:**
    *   Documentos o secciones que detallan reglas de negocio específicas, algoritmos, validaciones, etc.
    *   *Ej. Tienda de Ropa:* Una especificación detallada de cómo se calculan los puntos de fidelidad o las condiciones para aplicar un descuento por volumen.

La elección del complemento dependerá de la complejidad del escenario, la audiencia y el objetivo. Los wireframes son a menudo los más efectivos para clarificar funcionalidad en etapas tempranas.

## Sección C: Directrices para la Especificación de Requerimientos (en [`consigna.pdf`](../../consigna.pdf))

### C.1. Uso de Lenguaje Claro y Distinción entre Requerimientos Obligatorios y Deseables

La [`consigna.pdf`](../../consigna.pdf) (punto 6) enfatiza el uso de lenguaje claro para distinguir entre requerimientos obligatorios y deseables.
*   **Requerimientos Obligatorios:** Son aquellos que el sistema **debe** soportar. Se redactan comúnmente usando el futuro "debe ser" o imperativos como "El sistema permitirá...".
    *   Ejemplo (Tienda de Ropa - General): "El sistema **debe permitir** registrar nuevos productos con su descripción, talla, color y precio."
*   **Requerimientos Deseables:** No son estrictamente necesarios para la funcionalidad básica, pero añaden valor. Se redactan usando el condicional "debería ser" o "podría ser".
    *   Ejemplo (Tienda de Ropa - General): "El sistema **debería ofrecer** recomendaciones de productos personalizadas basadas en el historial de compras del cliente."

La norma UNE-ISO 24495-1 establece principios rectores y directrices para elaborar documentos en lenguaje claro, lo cual es aplicable a la redacción de requerimientos para asegurar su comprensión por todos los stakeholders. (Fuente: Revista UNE, "Lenguaje claro. Parte 1: Principios rectores y directrices | Nº 67", [[https://revista.une.org/67/lenguaje-claro.-parte-1-principios-rectores-y-directrices.html](https://revista.une.org/67/lenguaje-claro.-parte-1-principios-rectores-y-directrices.html)]; Revista UNE, "Lenguaje claro. Parte 1: Principios rectores y directrices | Nº 61", [[https://revista.une.org/61/lenguaje-claro.-parte-1-principios-rectores-y-directrices.html](https://revista.une.org/61/lenguaje-claro.-parte-1-principios-rectores-y-directrices.html)])

Un documento de requisitos de software (DRS) bien redactado transforma objetivos comerciales de alto nivel en tareas viables para el desarrollo. El uso de un lenguaje claro y preciso es fundamental para evitar ambigüedades. (Fuente: Asana, "Cómo redactar un documento de requisitos de software", [[https://asana.com/es/resources/software-requirement-document-template](https://asana.com/es/resources/software-requirement-document-template)])

**Ejemplos Adicionales de Requerimientos para Sistema de Gestión de Tienda de Ropa:**

**Módulo: Gestión de Inventario / Productos**

*   **Requerimientos Obligatorios:**
    *   "El sistema **debe permitir** el registro de nuevos productos especificando: código único (SKU), nombre, descripción, marca, categoría, subcategoría, proveedor, costo y precio de venta." (Adaptado de PMOInformatica [[https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html](https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html)])
        *   **Razón:** Fundamental para la gestión y venta de productos.
    *   "El sistema **debe permitir** la gestión de variantes de productos (ej. talla, color, estampado) asociadas a un producto base, cada una con su propio SKU y control de stock."
        *   **Razón:** Esencial para tiendas de ropa donde los productos tienen múltiples variaciones.
    *   "El sistema **debe permitir** registrar la entrada de mercancía al inventario (compras a proveedores, devoluciones de clientes en buen estado), actualizando el stock disponible por SKU."
        *   **Razón:** Necesario para mantener la precisión del inventario.
    *   "El sistema **debe permitir** registrar las salidas de mercancía del inventario (ventas, mermas, devoluciones a proveedor), actualizando el stock disponible por SKU."
        *   **Razón:** Necesario para mantener la precisión del inventario.
    *   "El sistema **debe proveer** una función para realizar conteos de inventario físico y generar reportes de discrepancias contra el stock teórico del sistema."
        *   **Razón:** Para control de inventario y detección de pérdidas.
    *   "El sistema **debe permitir** la consulta de stock actual de un producto/variante en tiempo real."
        *   **Razón:** Crítico para ventas en tienda y online, y para la toma de decisiones de reposición.
    *   "El sistema **debe permitir** definir niveles de stock mínimo y máximo por producto/variante para alertar sobre necesidad de reposición o exceso de inventario."
        *   **Razón:** Ayuda a evitar quiebres de stock y optimizar el capital invertido en inventario.

*   **Requerimientos Deseables:**
    *   "El sistema **debería permitir** la gestión de múltiples almacenes o ubicaciones de stock (ej. tienda principal, bodega, tienda online)."
        *   **Razón:** Útil para negocios con más de un punto de stock.
    *   "El sistema **debería permitir** el manejo de productos compuestos o "packs" (ej. un conjunto de camisa y corbata vendido como un solo producto con precio especial)."
        *   **Razón:** Facilita estrategias promocionales y de venta.
    *   "El sistema **debería generar** sugerencias de pedidos a proveedores basadas en niveles de stock, historial de ventas y plazos de entrega."
        *   **Razón:** Optimiza el proceso de compra y reduce el riesgo de error humano.
    *   "El sistema **debería soportar** el uso de lectores de códigos de barras para agilizar la entrada/salida de mercancía y los conteos de inventario."
        *   **Razón:** Mejora la eficiencia y reduce errores de digitación.
    *   "El sistema **debería permitir** adjuntar múltiples imágenes y videos a cada producto/variante."
        *   **Razón:** Mejora la presentación del producto, especialmente para ventas online.
    *   "El sistema **debería permitir** la gestión de transferencias de stock entre diferentes tiendas o almacenes de la empresa."
        *   **Razón:** Optimiza la disponibilidad de inventario en la red de tiendas.

**Módulo: Gestión de Clientes**

*   **Requerimientos Obligatorios:**
    *   "El sistema **debe permitir** el registro de información básica de clientes (nombre, contacto) de forma opcional durante la venta." (Adaptado de PMOInformatica [[https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html](https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html)])
        *   **Razón:** Para asociar ventas a clientes y futuras acciones de marketing o servicio.
    *   "El sistema **debe permitir** la búsqueda de clientes existentes por diversos criterios (nombre, número de identificación, teléfono, email)."
        *   **Razón:** Para agilizar la atención y consulta de historial.

*   **Requerimientos Deseables:**
    *   "El sistema **debería permitir** registrar un historial de compras detallado por cada cliente."
        *   **Razón:** Fundamental para análisis de comportamiento, personalización y servicio postventa.
    *   "El sistema **debería permitir** la segmentación de clientes basada criterioss (ej. frecuencia de compra, monto gastado, preferencias)."
        *   **Razón:** Facilita campañas de marketing dirigidas.
    *   "El sistema **debería integrarse** con un programa de fidelización, permitiendo acumular y redimir puntos o beneficios."
        *   **Razón:** Fomenta la lealtad del cliente.
    *   "El sistema **debería permitir** registrar preferencias de comunicación del cliente (ej. si acepta recibir emails promocionales)."
        *   **Razón:** Cumplimiento de normativas de privacidad y mejora de la relación con el cliente.

**Módulo: Ventas y Facturación (Punto de Venta - POS)**

*   **Requerimientos Obligatorios:**
    *   "El sistema **debe permitir** procesar ventas, añadiendo productos al carrito mediante escaneo de código de barras o búsqueda manual." (Adaptado de PMOInformatica [[https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html](https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html)])
        *   **Razón:** Funcionalidad central del POS.
    *   "El sistema **debe calcular** automáticamente los subtotales, impuestos aplicables (según configuración local) y el total de la venta."
        *   **Razón:** Precisión en el cobro y cumplimiento fiscal.
    *   "El sistema **debe soportar** múltiples formas de pago (efectivo, tarjeta de crédito/débito, transferencias, vales)."
        *   **Razón:** Flexibilidad para el cliente.
    *   "El sistema **debe permitir** la aplicación de descuentos (porcentuales o fijos) a productos individuales o al total de la venta, con los permisos adecuados."
        *   **Razón:** Para gestionar promociones y ofertas.
    *   "El sistema **debe generar** e imprimir un ticket o factura de venta con la información legal requerida." (Adaptado de PMOInformatica [[https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html](https://www.pmoinformatica.com/2018/04/requerimientos-funcionales-de-un-sistema-de-ventas.html)])
        *   **Razón:** Cumplimiento legal y comprobante para el cliente.
    *   "El sistema **debe permitir** la gestión de devoluciones y cambios, actualizando el inventario y generando notas de crédito si aplica."
        *   **Razón:** Servicio al cliente y control de inventario.
    *   "El sistema **debe permitir** realizar arqueos de caja (cierre de caja) por vendedor/terminal, comparando el efectivo registrado con el físico."
        *   **Razón:** Control financiero y detección de descuadres.

*   **Requerimientos Deseables:**
    *   "El sistema **debería funcionar** en modo offline básico (registrar ventas) en caso de pérdida de conexión a internet, sincronizando los datos una vez restablecida."
        *   **Razón:** Continuidad del negocio ante fallos de red.
    *   "El sistema **debería permitir** la suspensión y recuperación de ventas (ej. cliente olvida un artículo y va a buscarlo)."
        *   **Razón:** Mejora la experiencia del cliente y agiliza la operación.
    *   "El sistema **debería integrarse** con terminales de pago (datáfonos) para agilizar el cobro con tarjeta."
        *   **Razón:** Eficiencia y reducción de errores en el cobro.
    *   "El sistema **debería permitir** la emisión de tarjetas de regalo (gift cards) y su redención como forma de pago."
        *   **Razón:** Estrategia de ventas y captación de nuevos clientes.

**Módulo: Reportes y Análisis**

*   **Requerimientos Obligatorios:**
    *   "El sistema **debe generar** reportes de ventas detallados por período, producto, vendedor, forma de pago, etc."
        *   **Razón:** Fundamental para el análisis del negocio.
    *   "El sistema **debe generar** reportes de inventario (stock actual, movimientos, valorización)."
        *   **Razón:** Control y gestión de inventario.

*   **Requerimientos Deseables:**
    *   "El sistema **debería ofrecer** un dashboard configurable con los principales KPIs (Indicadores Clave de Rendimiento) del negocio."
        *   **Razón:** Visualización rápida del estado del negocio para la toma de decisiones.
    *   "El sistema **debería permitir** la exportación de reportes a formatos comunes (Excel, PDF, CSV)."
        *   **Razón:** Facilita el análisis externo y la compartición de información.
    *   "El sistema **debería generar** reportes de análisis de rentabilidad por producto o categoría."
        *   **Razón:** Ayuda a identificar los productos más y menos rentables.

### C.2. Uso de Texto Resaltado

La [`consigna.pdf`](../../consigna.pdf) (punto 7) recomienda "Use texto resaltado (negrita, cursiva o color) para seleccionar partes clave del requerimiento". El objetivo es mejorar la legibilidad y destacar información crucial sin generar "ruido visual".

**Mejores Prácticas Generales:**
*   **Consistencia:** Definir y aplicar uniformemente cuándo y cómo se usa cada tipo de resaltado.
*   **Moderación:** El exceso de resaltado diluye su efecto. Si todo está resaltado, nada lo está realmente.
*   **Propósito:** Usar el resaltado para guiar al lector y mejorar la comprensión, no para decorar.
*   **Claridad:** El resaltado debe contribuir a la claridad general del documento de requisitos. (Fuente: Asana [[https://asana.com/es/resources/software-requirement-document-template](https://asana.com/es/resources/software-requirement-document-template)]).
*   **Accesibilidad:** Si se usa color, asegurar que la información también sea accesible por otros medios (texto, símbolos) debido a posibles problemas de percepción del color (daltonismo) o impresión en blanco y negro.

**Uso Específico:**
*   **Negrita (Bold):**
    *   Para **palabras clave o frases muy importantes** que definen la capacidad principal o un componente crítico.
    *   Para resaltar los verbos modales de obligatoriedad/deseabilidad (**debe**, **debería**).
    *   *Ejemplo:* "El sistema **debe permitir** al usuario **buscar productos** por nombre."
    *   (Fuente General: ADR Formación [[https://www.adrformacion.com/knowledge/administracion-publica/negrita__subrayado_y_cursiva__recomendaciones_de_uso.html](https://www.adrformacion.com/knowledge/administracion-publica/negrita__subrayado_y_cursiva__recomendaciones_de_uso.html)]).
*   **Cursiva (Italics):**
    *   Para el **primer uso de términos o frases clave** que se definen en otro lugar (ej. glosario). (Fuente: Normas APA [[https://normas-apa.org/estilo/cursiva/](https://normas-apa.org/estilo/cursiva/)]).
    *   Para **énfasis ligero** o para referenciar títulos de otros documentos/secciones.
    *   *Ejemplo:* "El *stock de seguridad* no debe ser inferior a 5 unidades (ver *Apéndice A: Glosario*)."
*   **Color:**
    *   Usar con extrema precaución. Si se usa, debe ser parte de una leyenda clara y no ser el único medio para transmitir información importante. Generalmente, es más seguro evitarlo en el texto principal de los requerimientos y optar por negrita/cursiva.

### C.3. Evitar Jerga Técnica Innecesaria y Uso de Glosario

La [`consigna.pdf`](../../consigna.pdf) (punto 8) advierte sobre asumir que los lectores entienden el lenguaje técnico de ingeniería de software. Palabras como "arquitectura", "módulo", "API", etc., pueden ser malinterpretadas. Se debe preferir un lenguaje sencillo y, si un término técnico es indispensable, debe explicarse.

*   **No recomendado:** "El módulo de inventario debe exponer una API RESTful para la integración con el ERP."
*   **Recomendado:** "El sistema de gestión de inventario **debe permitir** que otros sistemas de la empresa (como el sistema de planificación de recursos empresariales o ERP) accedan y actualicen la información de las existencias de productos de forma segura y estándar."

El objetivo es producir un sistema de alta calidad, y esto se logra aplicando métodos efectivos, lo que incluye una comunicación clara de los requerimientos. (Fuente: Oocities - Temainves, [[https://www.oocities.org/infinitobo/temainves/temainves.html](https://www.oocities.org/infinitobo/temainves/temainves.html)])

Para facilitar la comprensión por parte de stakeholders no técnicos, es altamente recomendable **crear y mantener un glosario de términos técnicos** que sean necesarios en el documento de requerimientos. Cada término en el glosario debe tener una explicación en lenguaje sencillo y adaptado al contexto del negocio de la tienda de ropa. (Inspirado por Redwerk [[https://redwerk.es/blog/vocabulario-de-terminos-de-desarrollo-de-software-para-no-tecnicos-los-60-mas-importantes/](https://redwerk.es/blog/vocabulario-de-terminos-de-desarrollo-de-software-para-no-tecnicos-los-60-mas-importantes/)] y Asana - Project Management Terms [[https://asana.com/es/resources/project-management-terms](https://asana.com/es/resources/project-management-terms)]).

**Posibles Términos para un Glosario (Explicados en Lenguaje Sencillo):**

1.  **Software/Aplicación/Sistema:** Programa de computadora para manejar operaciones de la tienda.
2.  **Interfaz de Usuario (UI):** Pantallas y botones con los que las personas interactúan.
3.  **Base de Datos:** Archivo digital central donde se guarda toda la información organizada.
4.  **Módulo:** Parte del software encargada de una función específica (ej. módulo de inventario).
5.  **Requerimiento (Funcional / No Funcional):**
    *   **Funcional:** Algo que el software *hace* (ej. "calcular el total").
    *   **No Funcional:** Cómo el software *es* (ej. "rápido", "fácil de usar").
6.  **API (Interfaz de Programación de Aplicaciones):** Forma estándar para que diferentes programas "hablen" entre sí.
7.  **Backup (Copia de Seguridad):** Copia de la información guardada para recuperación en caso de problemas.
8.  **POS (Punto de Venta):** Sistema de "caja" moderna para registrar ventas y pagos.
9.  **SKU (Unidad de Mantenimiento de Stock):** Código único para identificar cada producto/variante.
10. **E-commerce (Comercio Electrónico):** Tienda online para comprar por internet.
11. **CRM (Gestión de Relaciones con Clientes):** Herramientas para gestionar información e interacciones con clientes.
12. **KPI (Indicador Clave de Rendimiento):** Métricas para medir el rendimiento del negocio (ej. ventas diarias).
13. **Omnicanalidad:** Experiencia de compra integrada entre todos los canales (tienda física, web, app).
14. **Wireframe/Mockup/Prototipo:** Dibujos o maquetas del software: Wireframe (plano básico), Mockup (diseño visual), Prototipo (versión interactiva).

### C.4. Asociar una Razón con Cada Requerimiento

La [`consigna.pdf`](../../consigna.pdf) (punto 9) sugiere asociar una razón con cada requerimiento de usuario para explicar por qué se incluyó. Esto es útil durante el desarrollo y, especialmente, cuando los requerimientos cambian, ya que ayuda a tomar decisiones informadas sobre la deseabilidad de los cambios.

*   Ejemplo:
    *   **Requerimiento:** "El sistema **debe permitir** a los clientes registrarse y crear una cuenta personal."
    *   **Razón:** "Para facilitar compras futuras, permitir el seguimiento de pedidos y posibilitar campañas de marketing personalizadas."

Un documento de Studocu sobre especificación de requerimientos, aunque es un ejemplo de un estudiante, reitera la importancia de que los requerimientos sean claros y detallados para facilitar el entendimiento entre las partes. (Fuente: Studocu, "Especificación de requerimientos. GA1-220501092-AA4-EV02", [[https://www.studocu.com/co/document/servicio-nacional-de-aprendizaje/analisis-y-desarrollo-de-software/especificacion-de-requerimientos-ga1-220501092-aa4-ev02/50794128](https://www.studocu.com/co/document/servicio-nacional-de-aprendizaje/analisis-y-desarrollo-de-software/especificacion-de-requerimientos-ga1-220501092-aa4-ev02/50794128)])

##### C.4.1. Impacto Práctico de la Razón del Requerimiento: Estudios y Ejemplos

Si bien los estudios de caso que aíslan de forma exclusiva el "impacto de la razón del requerimiento" son específicos, la literatura sobre evolución de requerimientos y gestión de cambios subraya consistentemente la importancia de comprender el "por qué" detrás de un requerimiento. Este entendimiento es crucial para la toma de decisiones informadas a lo largo del ciclo de vida del software.

*   **Mejor Comprensión de la Evolución:** Investigaciones sobre la evolución de procesos de software sugieren que capturar la información sobre la razón fundamental de los cambios en los procesos (análogo a la razón de los requerimientos) permite una mejor comprensión de dicha evolución. Esto implica que conocer la razón de un requerimiento es vital cuando este necesita cambiar, ayudando a decidir si el cambio se alinea con la intención original o si la propia razón ha perdido validez. (Adaptado de: "Rationale modeling for software process evolution", [[https://www.researchgate.net/publication/220542201_Rationale_modeling_for_software_process_evolution](https://www.researchgate.net/publication/220542201_Rationale_modeling_for_software_process_evolution)])

*   **Gestión de Cambios y Contexto:** Estudios sobre las causas y efectos de los cambios en los requerimientos de software indican que una mayor comprensión de estos factores apoya la gestión de requerimientos. La "razón" de un requerimiento es una parte intrínseca de sus "causas" y del "contexto" en el que surgió. Por ejemplo, si un requerimiento se basa en un contexto operativo específico (la razón), y ese contexto cambia, el requerimiento debe evolucionar. Un estudio de caso sobre la evolución de requerimientos en software empresarial destacó el papel del contexto y las experiencias; el "contexto" a menudo encapsula la razón fundamental del requerimiento. Un requerimiento para una funcionalidad de reporte específica podría tener su razón en un contexto regulatorio; si la regulación cambia, el requerimiento y su razón necesitan ser reevaluados. (Adaptado de: "Towards an understanding of the causes and effects of software requirements change: two case studies", [[https://link.springer.com/article/10.1007/s00766-012-0149-0](https://link.springer.com/article/10.1007/s00766-012-0149-0)]; "How do requirements evolve over time? A case study investigating the role of context and experiences...", [[https://link.springer.com/article/10.1057/s41265-016-0001-y](https://link.springer.com/article/10.1057/s41265-016-0001-y)])

*   **Impacto en el Desarrollo Posterior:** Un estudio de caso industrial sobre el impacto de la Ingeniería de Requerimientos (IR) en las fases posteriores del desarrollo, aunque más amplio, implícitamente soporta la importancia de la razón. Una buena práctica de IR incluye la captura de la razón de los requerimientos. Es probable que los proyectos con mejores prácticas de IR (incluyendo la captura de la razón) experimenten un desarrollo posterior más fluido. Por ejemplo, si un desarrollador entiende *por qué* existe un requerimiento de rendimiento particular (ej., "Razón: el sistema debe procesar 1000 transacciones por segundo durante las ventas pico del Black Friday para evitar pérdidas de ingresos"), puede tomar decisiones de diseño e implementación más informadas y alineadas con los objetivos críticos del negocio. Sin esta razón, un requerimiento podría parecer arbitrario y llevar a decisiones subóptimas. (Adaptado de: "An Industrial Case Study of the Impact of Requirements Engineering on Downstream Development", [[https://www.researchgate.net/publication/221440380_An_Industrial_Case_Study_of_the_Impact_of_Requirements_Engineering_on_Downstream_Development](https://www.researchgate.net/publication/221440380_An_Industrial_Case_Study_of_the_Impact_of_Requirements_Engineering_on_Downstream_Development)])

En resumen, la razón de un requerimiento:
1.  Permite **evaluar el impacto de los cambios propuestos** de manera efectiva.
2.  Facilita la **toma de decisiones de diseño y desarrollo informadas**.
3.  Ayuda a **prevenir la "corrupción del alcance" (scope creep)** al cuestionar características que no se alinean con las razones fundamentales.
4.  Mejora la **comunicación y reduce la ambigüedad** entre los stakeholders.

La documentación explícita de la razón de cada requerimiento es, por lo tanto, una práctica valiosa que contribuye a la adaptabilidad y al éxito general del proyecto de software.
*(Esta sección se ampliará con más ejemplos y refinamientos conforme avance la investigación.)*

## Sección D: Análisis y Descripción de Casos de Uso (Contexto: Paso 3))

### D.1. Casos de Uso y el Estándar IEEE 830

La Especificación de Requisitos de Software (ERS), según el estándar IEEE 830, es una descripción completa del comportamiento del sistema a desarrollar. Una parte fundamental de esta especificación es el conjunto de **casos de uso**, que describen todas las interacciones que tendrán los usuarios (actores) con el software. (Fuente: Prezi - Andres Tascon, "Norma IEEE 830", [[https://prezi.com/x4cdwhai-zvm/norma-ieee-830/](https://prezi.com/x4cdwhai-zvm/norma-ieee-830/)]; FDI UCM, "Especificación de Requisitos según el estándar de IEEE 830", [[https://www.fdi.ucm.es/profesor/gmendez/docs/is0809/ieee830.pdf](https://www.fdi.ucm.es/profesor/gmendez/docs/is0809/ieee830.pdf)])

El estándar IEEE 830 proporciona una guía para la creación de un Documento de Especificación de Requisitos de Software (ERS o SRS en inglés). Aunque el estándar en sí mismo puede tener ventajas y desventajas en su aplicación práctica (Fuente: LinkedIn, "What are the benefits and drawbacks of using IEEE 830...", [[https://www.linkedin.com/advice/3/what-benefits-drawbacks-using-ieee-830-requirements](https://www.linkedin.com/advice/3/what-benefits-drawbacks-using-ieee-830-requirements)]), la [`consigna.pdf`](../../consigna.pdf) lo establece como referencia.

Un caso de uso define una secuencia de acciones que el sistema realiza y que producen un resultado observable de valor para un actor particular. Los casos de uso capturan los requerimientos funcionales del sistema desde la perspectiva del usuario.

### D.2. Estructura de un Caso de Uso (Basado en IEEE 830 y Prácticas Comunes)

Si bien el IEEE 830 describe el contenido general de un ERS, la estructura detallada de un caso de uso individual puede variar. Comúnmente, una descripción de caso de uso incluye:

1.  **Identificador Único y Nombre del Caso de Uso:** Un código y un nombre descriptivo y conciso (ej. CU-001: Procesar Venta en Tienda).
2.  **Actores:** Personas o sistemas externos que interactúan con el sistema en este caso de uso (ej. Vendedor, Cliente, Sistema de Inventario).
3.  **Descripción Breve:** Un resumen del propósito del caso de uso.
4.  **Precondiciones:** Condiciones que deben ser verdaderas antes de que el caso de uso pueda iniciarse.
5.  **Flujo Principal de Eventos (Curso Normal):** La secuencia de pasos numerados que describen la interacción típica y exitosa entre el actor y el sistema.
6.  **Flujos Alternativos (Cursos Alternativos):** Otras secuencias de pasos que pueden ocurrir, incluyendo variaciones del flujo normal o manejo de situaciones menos comunes pero válidas.
7.  **Flujos de Excepción (Manejo de Errores):** Secuencias que describen cómo se manejan los errores o situaciones excepcionales que impiden completar el flujo principal.
8.  **Postcondiciones:** Condiciones que deben ser verdaderas después de que el caso de uso ha finalizado (tanto para éxito como para fracaso).
9.  **Requisitos Especiales (No Funcionales):** Cualquier restricción o requisito no funcional relevante para este caso de uso (ej. rendimiento, seguridad).
10. **Frecuencia de Uso:** Estimación de cuán a menudo se ejecutará el caso de uso.
11. **Notas y Comentarios Adicionales.**

(Fuentes combinadas: Ejemplo formato IEEE 830 - Studocu, [[https://www.studocu.com/co/document/universidad-catolica-de-colombia/ingenieria-de-software/ejemplo-formato-ieee-830/5670142](https://www.studocu.com/co/document/universidad-catolica-de-colombia/ingenieria-de-software/ejemplo-formato-ieee-830/5670142)]; Slideshare, "Formato ieee830", [[https://www.slideshare.net/slideshow/formato-ieee830/112643782](https://www.slideshare.net/slideshow/formato-ieee830/112643782)] y conocimientos generales de ingeniería de software). Las ilustraciones 3 y 4 de la [`consigna.pdf`](../../consigna.pdf) servirán como guía específica para el formato esperado.

### D.3. Diagramas de Casos de Uso

Un diagrama de casos de uso es una representación gráfica de las interacciones entre los actores y los casos de uso del sistema. Muestra:
*   **Actores:** Representados usualmente como figuras de palo ("stick figures").
*   **Casos de Uso:** Representados como óvalos.
*   **Relaciones:**
    *   **Asociación:** Líneas que conectan actores con casos de uso, indicando participación.
    *   **Inclusión (`<<include>>`):** Un caso de uso base incorpora explícitamente el comportamiento de otro caso de uso.
    *   **Extensión (`<<extend>>`):** Un caso de uso base puede ser extendido por el comportamiento de otro caso de uso bajo ciertas condiciones.
    *   **Generalización:** Relaciones de herencia entre actores o entre casos de uso.
*   **Límite del Sistema:** Un rectángulo que delimita los casos de uso pertenecientes al sistema.

La Ilustración 5 de la [`consigna.pdf`](../../consigna.pdf) deberá ser consultada para el estilo específico del diagrama esperado.

*(Esta sección se poblará con ejemplos concretos de casos de uso y fragmentos de diagramas para un sistema de gestión de tienda de ropa, una vez que se avance en el análisis.)*
### D.4. Contenido de un ERS (IEEE 830) para un Sistema de Gestión de Tienda de Ropa

Adaptar el estándar IEEE 830 para un Sistema de Gestión de Tienda de Ropa implicaría detallar cada sección con información específica del dominio y del proyecto. A continuación, se describe cómo se podrían contextualizar las secciones principales:

**1. Introducción**

*   **1.1. Propósito:**
    *   Declarar que el documento especifica los requisitos para un Sistema de Gestión de Tienda de Ropa (SGTR).
    *   Identificar a la audiencia prevista (ej. desarrolladores, testers, gerentes de proyecto, stakeholders de la tienda).
*   **1.2. Alcance del Producto:**
    *   Nombrar el software: "Sistema de Gestión de Tienda de Ropa [Nombre del Proyecto/Producto]".
    *   Describir brevemente lo que el SGTR hará (y no hará). Ej: "El sistema gestionará el inventario, ventas (POS), clientes, y generará reportes para la tienda de ropa XYZ. No incluirá la gestión de nómina de empleados ni contabilidad avanzada, ya que se integrará con sistemas existentes para ello."
    *   Mencionar los beneficios clave, objetivos y metas para la tienda (ej. mejorar eficiencia operativa, optimizar inventario, mejorar experiencia del cliente).
*   **1.3. Definiciones, Acrónimos y Abreviaturas:**
    *   Listar términos específicos del dominio de retail de moda (ej. SKU, Talla, Color, Temporada, Colección, POS, Merma, Arqueo de Caja) y términos técnicos del software, con sus definiciones claras. Ver también la propuesta de glosario en la sección C.3.
*   **1.4. Referencias:**
    *   Listar todos los documentos referenciados (ej. [`consigna.pdf`](../../consigna.pdf), plan de proyecto, guías de estilo de la marca, manuales de sistemas existentes con los que se integrará, normativas fiscales relevantes).
*   **1.5. Resumen del Resto del Documento:**
    *   Describir brevemente qué contiene cada una de las siguientes secciones del ERS.

**2. Descripción General**

*   **2.1. Perspectiva del Producto:**
    *   ¿Es un producto nuevo e independiente, o reemplaza/complementa un sistema existente?
    *   Contextualizarlo dentro del entorno operativo de la tienda. Ej: "El SGTR reemplazará el sistema de caja manual y las hojas de cálculo de inventario actuales."
    *   Describir cómo se integra con otros sistemas (ej. sistema de contabilidad, pasarela de pagos, plataforma de e-commerce si existe).
    *   Incluir un diagrama de contexto del sistema de alto nivel mostrando sus interfaces principales con usuarios y otros sistemas.
*   **2.2. Funciones Principales del Producto:**
    *   Resumir las principales funcionalidades que ofrecerá el SGTR. Esto se derivaría de los casos de uso principales.
    *   Ejemplos: Gestión de Inventario y Productos, Procesamiento de Ventas (POS), Gestión de Clientes (CRM básico), Gestión de Devoluciones y Cambios, Gestión de Promociones, Generación de Reportes, Gestión de Usuarios y Seguridad.
*   **2.3. Características de los Usuarios:**
    *   Describir los diferentes tipos de usuarios (actores) y sus características relevantes.
    *   Ej:
        *   **Vendedor/Cajero:** Experiencia básica con computadoras, requiere interfaz intuitiva y rápida para el POS.
        *   **Gerente de Tienda:** Necesita acceso a reportes, configuración de promociones, gestión de inventario. Puede tener más experiencia con software de gestión.
        *   **Administrador del Sistema (TI):** Conocimientos técnicos para mantenimiento, backups, gestión de usuarios avanzados.
*   **2.4. Restricciones Generales:**
    *   Cualquier factor que limite las opciones del desarrollador.
    *   Ej: Políticas de la empresa, limitaciones de hardware (ej. debe funcionar en tablets específicas para el POS), interfaces con otros sistemas ya definidos, tecnologías obligatorias (ej. base de datos específica si la empresa lo requiere), restricciones de presupuesto o tiempo, cumplimiento de normativas (fiscales, protección de datos).
*   **2.5. Suposiciones y Dependencias:**
    *   Factores que se asumen verdaderos y que, si cambian, podrían afectar los requisitos.
    *   Ej: Se asume disponibilidad de conexión a internet estable para sincronización (si es un sistema distribuido o con componentes en la nube). Dependencia de que la pasarela de pagos externa provea una API funcional. Se asume que los empleados recibirán capacitación adecuada.

**3. Requisitos Específicos**

Esta es la sección más detallada y extensa. Se organizarían los requisitos por funcionalidad, por caso de uso, por modo de operación, o una combinación. Para un SGTR, podría ser útil agruparlos por módulos funcionales.

*   **3.1. Requisitos de Interfaz Externa:**
    *   **Interfaces de Usuario (UI):** Describir las características lógicas de cada interfaz. No el diseño detallado, sino qué información se muestra, qué interacciones son posibles. Se pueden referenciar wireframes o prototipos.
        *   Ej: "La pantalla del POS debe mostrar claramente los artículos escaneados, subtotal, impuestos, total. Debe permitir ingresar códigos de cupón y seleccionar múltiples formas de pago."
    *   **Interfaces de Hardware:** Interacción con lectores de códigos de barras, impresoras de tickets, cajones de dinero, datáfonos.
    *   **Interfaces de Software:** Conexión con la pasarela de pagos, sistema de contabilidad, sistema de e-commerce, APIs de proveedores si aplica. Detallar el propósito, formato de datos, protocolos.
    *   **Interfaces de Comunicación:** Protocolos de red, seguridad de la comunicación.
*   **3.2. Requisitos Funcionales:**
    *   Detallar todas las acciones que el sistema debe ser capaz de realizar. Estos se derivan directamente de los casos de uso y escenarios. Se pueden organizar por módulo:
        *   **Módulo de Gestión de Productos e Inventario:**
            *   RF-INV-001: El sistema **debe permitir** registrar nuevos productos con atributos (SKU, nombre, descripción, categoría, marca, proveedor, costo, precio de venta, tallas, colores, imágenes). (Razón: Esencial para catalogar y vender).
            *   RF-INV-002: El sistema **debe permitir** actualizar el stock al recibir mercancía.
            *   ... (todos los "debe" y "debería" detallados previamente en C.1 y los casos de uso).
        *   **Módulo de Punto de Venta (POS):**
            *   RF-POS-001: El sistema **debe permitir** escanear códigos de barras para agregar productos a la venta.
            *   ...
        *   **Módulo de Gestión de Clientes:**
            *   ...
        *   **Módulo de Devoluciones y Cambios:**
            *   ...
        *   **Módulo de Reportes y Análisis:**
            *   ...
        *   **Módulo de Seguridad y Usuarios:**
            *   ...
    *   Para cada requisito funcional, se especificaría su identificador, descripción, razón, fuente, prioridad (obligatorio/deseable), criterios de aceptación.
*   **3.3. Requisitos de Rendimiento:**
    *   Requisitos cuantitativos sobre la velocidad, capacidad, tiempos de respuesta.
    *   Ej: "El sistema debe procesar una transacción de venta promedio (5 artículos) en menos de 30 segundos desde el primer escaneo hasta la impresión del ticket." "El sistema debe soportar hasta 10 usuarios concurrentes en el POS sin degradación notable del rendimiento." "La consulta de stock de un producto debe mostrar resultados en menos de 2 segundos."
*   **3.4. Restricciones de Diseño (Impuestas):**
    *   Si hay estándares de codificación, lenguajes de programación específicos, o herramientas de desarrollo obligatorias.
    *   Ej: "El sistema debe desarrollarse utilizando Python y PostgreSQL." "La interfaz de usuario debe seguir las guías de estilo de la marca X."
*   **3.5. Atributos de Calidad del Software:**
    *   **Disponibilidad:** Ej: "El sistema POS debe tener una disponibilidad del 99.9% durante el horario comercial." "Capacidad de operar en modo offline básico para ventas si se pierde la conexión a la base de datos central."
    *   **Seguridad:** Protección contra acceso no autorizado, cifrado de datos sensibles (datos de clientes, pagos), roles y permisos.
    *   **Mantenibilidad:** Facilidad para corregir errores, adaptar a nuevos requisitos, claridad del código.
    *   **Usabilidad:** Facilidad de aprendizaje y uso para los diferentes roles de usuario. Intuitividad de la interfaz.
    *   **Portabilidad (si aplica):** Ej: "El módulo de administración debe ser accesible desde un navegador web estándar."
*   **3.6. Otros Requisitos:**
    *   Cualquier requisito no cubierto anteriormente. Ej: Requisitos de datos (formatos, retención), requisitos legales y regulatorios específicos (ej. generación de reportes fiscales en formato X exigido por la autoridad local), requisitos de internacionalización/localización si la tienda opera en múltiples regiones o idiomas.

**Apéndices (Opcional)**
*   Glosario (si no está en la sección 1.3).
*   Modelos de análisis (diagramas de flujo, diagramas de actividad, si complementan los casos de uso).
*   Descripción detallada de escenarios complejos.

**Índice**
*   Para facilitar la navegación del documento.

Esta estructura, poblada con los detalles específicos investigados para una tienda de ropa (stakeholders, regulaciones, procesos de venta, inventario, etc.), conformaría un ERS robusto según el estándar IEEE 830.
