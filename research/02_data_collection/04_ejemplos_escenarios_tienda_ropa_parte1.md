# Ejemplos Detallados de Escenarios para Sistema de Gestión de Tienda de Ropa (Parte 1)

Este documento presenta ejemplos de escenarios de uso para un sistema de gestión de tienda de ropa, siguiendo la estructura detallada en la Sección B.2 de [`01_hallazgos_primarios_parte1.md`](research/02_data_collection/01_hallazgos_primarios_parte1.md) y las directrices de la [`consigna.pdf`](../../consigna.pdf). Estos ejemplos sirven para ilustrar cómo se aplicarían los conceptos en la práctica y ayudarán a suplir la falta de la "Ilustración 01" mencionada en la consigna.

## Escenario 1: Cliente realiza compra de múltiples artículos en tienda física con pago mixto

*   **Nombre del Escenario:** Cliente Compra Múltiples Artículos con Pago Mixto en Tienda Física
*   **Actor(es) Principal(es):** Cliente, Vendedor
*   **Sistema Involucrado:** Sistema de Punto de Venta (POS)
*   **Objetivo/Meta del Escenario:** El cliente completa satisfactoriamente la compra de los artículos deseados utilizando efectivo y tarjeta como métodos de pago. La tienda registra la venta, actualiza el inventario y emite el comprobante correspondiente.

*   **Precondiciones:**
    1.  El sistema POS está operativo y en línea.
    2.  El Vendedor está autenticado en el sistema POS.
    3.  El Cliente ha seleccionado los artículos que desea comprar y se acerca al punto de pago.
    4.  Los artículos tienen códigos de barras legibles y están registrados en el sistema con precio y stock.
    5.  El datáfono (terminal de pago con tarjeta) está conectado y operativo.
    6.  Hay conexión a la red para la autorización de pagos con tarjeta.

*   **Flujo Normal de Eventos (Secuencia Principal):**
    1.  Cliente presenta los artículos al Vendedor en el mostrador de caja.
    2.  Vendedor inicia una nueva transacción de venta en el sistema POS.
    3.  Para cada artículo:
        a.  Vendedor escanea el código de barras del artículo.
        b.  Sistema POS busca el artículo en la base de datos, muestra su descripción, precio unitario y lo añade al carrito de la transacción.
        c.  Sistema POS actualiza el subtotal de la venta.
    4.  Una vez escaneados todos los artículos, Vendedor confirma el listado con el Cliente.
    5.  Vendedor pregunta al Cliente si posee alguna tarjeta de fidelización o cupón de descuento.
    6.  **SI** el Cliente presenta tarjeta de fidelización/cupón:
        a.  Vendedor ingresa/escanea el código de fidelización/cupón en el sistema POS.
        b.  Sistema POS valida el código y aplica los descuentos o promociones correspondientes.
    7.  Sistema POS calcula y muestra el total final de la venta (incluyendo impuestos aplicables).
    8.  Vendedor informa el total a pagar al Cliente.
    9.  Cliente indica que desea pagar una parte en efectivo y el resto con tarjeta de crédito/débito.
    10. Cliente entrega al Vendedor el monto en efectivo.
    11. Vendedor ingresa en el sistema POS el monto recibido en efectivo.
    12. Sistema POS calcula el saldo restante a pagar.
    13. Vendedor solicita al Cliente la tarjeta para el pago del saldo.
    14. Vendedor procesa el pago con tarjeta a través del datáfono (ingresa monto, Cliente inserta/desliza tarjeta e ingresa PIN si es necesario).
    15. Datáfono se comunica con la entidad bancaria para autorizar la transacción.
    16. **SI** la transacción es aprobada:
        a.  Datáfono emite un comprobante de pago.
        b.  Sistema POS recibe la confirmación de pago del datáfono.
        c.  Sistema POS marca la transacción como completada.
        d.  Sistema POS registra la venta (detalles de artículos, montos, formas de pago, cliente si está identificado).
        e.  Sistema POS actualiza el stock de los artículos vendidos en el inventario.
        f.  Sistema POS genera e imprime el ticket/factura de venta.
        g.  Sistema POS actualiza el arqueo de caja con el efectivo recibido.
    17. Vendedor entrega al Cliente los artículos comprados, el ticket/factura y el comprobante del pago con tarjeta.
    18. Vendedor agradece al Cliente por su compra.

*   **Flujos Alternativos y de Excepción:**
    *   **Alternativo 1: Cliente decide no llevar un artículo antes de finalizar el pago.**
        1.  Cliente informa al Vendedor que ya no desea un artículo específico.
        2.  Vendedor selecciona el artículo en la transacción del POS y lo elimina.
        3.  Sistema POS recalcula el subtotal y el total final.
        4.  El escenario continúa desde el paso 8 del Flujo Normal.
    *   **Excepción 1: Código de barras de un artículo no es legible o no se encuentra.**
        1.  Vendedor intenta escanear el artículo varias veces.
        2.  **SI** no se puede escanear: Vendedor busca manualmente el artículo en el sistema POS (por nombre, categoría, código interno).
        3.  **SI** el artículo se encuentra manualmente: Vendedor lo añade a la transacción. El escenario continúa.
        4.  **SI** el artículo no se encuentra en el sistema: Vendedor informa al Cliente. Cliente decide si desea otro artículo o continuar sin él. Vendedor podría necesitar consultar con un supervisor.
    *   **Excepción 2: Artículo escaneado no tiene precio asignado en el sistema.**
        1.  Sistema POS muestra una alerta al Vendedor.
        2.  Vendedor verifica el precio (ej. etiqueta física, consulta a supervisor).
        3.  **SI** se obtiene el precio: Supervisor o Vendedor con permisos actualiza el precio en el sistema (si es posible) o lo ingresa manualmente para la transacción actual.
        4.  **SI NO** se puede determinar el precio o actualizar: Vendedor informa al Cliente. Cliente decide.
    *   **Excepción 3: Descuento/Cupón no es válido o ya expiró.**
        1.  Sistema POS muestra un mensaje de error al intentar aplicar el descuento/cupón.
        2.  Vendedor informa al Cliente.
    *   **Excepción 4: Pago con tarjeta es rechazado.**
        1.  Datáfono y/o Sistema POS indican el rechazo.
        2.  Vendedor informa al Cliente.
        3.  Cliente puede optar por:
            a.  Intentar con otra tarjeta (se repite el sub-proceso de pago con tarjeta).
            b.  Pagar el saldo restante en efectivo (si dispone).
            c.  Pagar el total en efectivo (si anula el pago parcial en efectivo previo).
            d.  Cancelar la compra de algunos artículos para reducir el total.
            e.  Cancelar toda la transacción.
    *   **Excepción 5: Falla de conexión del datáfono o sistema POS.**
        1.  Vendedor intenta reiniciar la conexión o el dispositivo según procedimientos.
        2.  **SI** se restablece: Continúa el proceso.
        3.  **SI NO** se restablece: Vendedor informa al Cliente. Podría ofrecer pago solo en efectivo (si el POS funciona offline para registro básico) o pedir al cliente que espere. Se notifica al soporte técnico.

*   **Actividades Concurrentes:**
    *   Otros Vendedores pueden estar procesando ventas en otros terminales POS.
    *   El sistema de inventario central puede estar recibiendo actualizaciones de otras fuentes (ej. recepción de mercancía, ventas online).
    *   Un Gerente podría estar consultando reportes de ventas en tiempo real.
    *   El sistema debe asegurar la integridad de los datos y la consistencia del inventario a pesar de estas actividades.

*   **Postcondiciones:**
    *   **En caso de Éxito:**
        1.  La venta está registrada en el sistema con todos sus detalles (artículos, cantidades, precios, descuentos, impuestos, formas de pago, fecha, hora, vendedor, cliente si se identificó).
        2.  El inventario de los artículos vendidos se ha decrementado correctamente.
        3.  El arqueo de caja del Vendedor se ha actualizado con el monto en efectivo recibido.
        4.  La transacción con tarjeta ha sido autorizada y registrada.
        5.  Se ha emitido un ticket/factura para el Cliente.
        6.  (Si aplica) Los puntos de fidelización del Cliente se han actualizado.
    *   **En caso de Fallo (ej. Cliente cancela la transacción antes de completarse el pago):**
        1.  La transacción de venta se anula o queda como incompleta en el sistema.
        2.  El inventario de los artículos no se modifica (o se revierte si hubo una reserva temporal).
        3.  No se afecta el arqueo de caja por esta transacción.
        4.  Cualquier autorización de pago parcial con tarjeta (si ocurrió antes de la cancelación total) debe ser anulada o gestionada según los procedimientos del banco/procesador de pagos.

*   **Frecuencia Estimada:** Muy Alta (múltiples veces por hora por cada caja activa).
*   **Notas Adicionales:**
    *   Este escenario asume una tienda física. Un escenario para compra online tendría variaciones significativas.
    *   La complejidad de los flujos de excepción puede variar según las políticas de la tienda y las capacidades del sistema POS.

*(La documentación de escenarios continúa en [`04_ejemplos_escenarios_tienda_ropa_parte2.md`](research/02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte2.md).)*

## Escenario 2: Cliente devuelve artículo comprado online en tienda física

*   **Nombre del Escenario:** Devolución en Tienda Física de Artículo Comprado Online
*   **Actor(es) Principal(es):** Cliente, Vendedor
*   **Sistema Involucrado:** Sistema de Punto de Venta (POS), Sistema de Gestión de Pedidos Online (potencialmente integrado o con interfaz al POS)
*   **Objetivo/Meta del Escenario:** El cliente devuelve satisfactoriamente un artículo comprado online en una tienda física, y el sistema procesa la devolución, actualiza el inventario y gestiona el reembolso o crédito según las políticas.

*   **Precondiciones:**
    1.  El sistema POS está operativo y en línea.
    2.  El Vendedor está autenticado en el sistema POS.
    3.  El Cliente se presenta en la tienda con el artículo a devolver y el comprobante de la compra online (ej. email de confirmación, factura online, número de pedido).
    4.  El sistema POS tiene la capacidad de buscar y acceder a los detalles de los pedidos online.
    5.  La política de la tienda permite devoluciones en tienda de compras online.

*   **Flujo Normal de Eventos (Secuencia Principal):**
    1.  Cliente informa al Vendedor que desea devolver un artículo comprado online.
    2.  Vendedor solicita al Cliente el comprobante de la compra online (ej. número de pedido) y el artículo.
    3.  Vendedor utiliza la función "Buscar Pedido Online" o similar en el sistema POS.
    4.  Vendedor ingresa el número de pedido o identificador proporcionado por el Cliente.
    5.  Sistema (POS o a través de interfaz con sistema de pedidos online) busca y muestra los detalles del pedido online, incluyendo los artículos y el estado del pedido.
    6.  Vendedor identifica el artículo a devolver en el pedido mostrado y lo selecciona en el sistema.
    7.  Vendedor verifica que el artículo y la fecha de compra cumplen con la política de devoluciones para compras online (ej. plazo, condición del artículo).
    8.  Vendedor inspecciona el estado físico del artículo devuelto.
    9.  **SI** la devolución es aceptada (cumple política y condición):
        a.  Vendedor registra la devolución del artículo online en el sistema POS.
        b.  Sistema pregunta el motivo de la devolución (Vendedor selecciona o ingresa).
        c.  Sistema indica si el producto devuelto debe reintegrarse al stock vendible de la tienda física o gestionarse de otra forma (ej. devolver a almacén central de e-commerce, marcar como defectuoso). Vendedor confirma/ajusta.
        d.  Sistema de Inventario (de la tienda física o central, según configuración) actualiza el stock del producto.
        e.  Sistema calcula el monto a reembolsar o el crédito a generar, según el precio pagado online y la política de devolución.
        f.  Vendedor informa al Cliente el monto y las opciones de reembolso (ej. reembolso a método de pago original online, nota de crédito para tienda física/online, efectivo si la política lo permite).
        g.  Cliente elige la opción de reembolso.
        h.  Vendedor procesa el reembolso:
            *   **Reembolso a método de pago original (Online):** Sistema POS (o interfaz con sistema de pedidos) inicia el proceso de reembolso a través de la pasarela de pago online original. Esto puede ser una acción diferida o requerir pasos adicionales en el sistema de e-commerce.
            *   **Nota de Crédito:** Sistema POS genera una nota de crédito válida para la tienda física y/o online.
            *   **Efectivo:** (Si permitido) Sistema POS registra la salida de efectivo y Vendedor entrega el dinero.
        i.  Sistema POS (y/o sistema de e-commerce) actualiza el estado del pedido online para reflejar la devolución.
        j.  Sistema POS genera un comprobante de la devolución en tienda.
    10. Vendedor entrega el comprobante al Cliente.
    11. El caso de uso finaliza.

*   **Flujos Alternativos y de Excepción:**
    *   **Alternativo 1: Cliente no tiene número de pedido online exacto.**
        1.  Vendedor intenta buscar el pedido por otros datos del Cliente (email, nombre, fecha de compra online), si el sistema lo permite.
        2.  Si se encuentra, continúa desde el paso 5 del Flujo Normal. Sino, Excepción 1.
    *   **Excepción 1: Pedido online no encontrado en el sistema.**
        1.  Sistema no localiza el pedido.
        2.  Vendedor informa al Cliente. Puede sugerir contactar a soporte de e-commerce o requerir intervención de supervisor para buscar por otros medios.
    *   **Excepción 2: Artículo no cumple política de devolución online (plazo, tipo).**
        1.  En el paso 7, Vendedor identifica la no conformidad.
        2.  Vendedor informa al Cliente. Devolución es denegada. El caso de uso finaliza.
    *   **Excepción 3: Artículo devuelto en mal estado (no imputable a defecto de fábrica).**
        1.  En el paso 8, Vendedor identifica el daño.
        2.  Vendedor informa al Cliente. Devolución es denegada o se aplican condiciones especiales según política.
    *   **Excepción 4: Problemas al procesar reembolso al método de pago original online.**
        1.  Sistema indica un error durante el intento de reembolso online.
        2.  Vendedor informa al Cliente. Se ofrecen alternativas (ej. nota de crédito, escalamiento a soporte de e-commerce).
    *   **Excepción 5: Sistema POS no puede comunicarse con el sistema de gestión de pedidos online.**
        1.  En el paso 5 o 9.i, hay un fallo de comunicación.
        2.  Vendedor informa al Cliente. Se puede intentar más tarde o procesar la devolución de forma condicional/manual con aprobación de supervisor, registrando para regularización posterior.

*   **Actividades Concurrentes:**
    *   Procesamiento de otras ventas y devoluciones en tienda.
    *   Gestión de pedidos y devoluciones en el sistema central de e-commerce.
    *   Actualizaciones de inventario desde múltiples canales.

*   **Postcondiciones:**
    *   **En caso de Éxito:**
        1.  La devolución del artículo comprado online está registrada en el sistema POS y/o en el sistema de e-commerce.
        2.  El inventario (físico o central) se ha actualizado.
        3.  El Cliente ha recibido la confirmación de su reembolso o la nota de crédito.
        4.  El estado del pedido online original se actualiza para reflejar la devolución.
    *   **En caso de Fallo (Devolución no procesada):**
        1.  El Cliente es informado de la razón.
        2.  El inventario y el estado del pedido online no se modifican por esta interacción.

*   **Frecuencia Estimada:** Media-Baja (dependiendo del volumen de ventas online y políticas de devolución).
*   **Notas Adicionales:**
    *   La integración entre el sistema POS de la tienda física y el sistema de gestión de pedidos/e-commerce es crucial para la fluidez de este escenario.
    *   Las políticas sobre qué artículos online se pueden devolver en tienda, y cómo se gestiona el stock devuelto (¿vuelve al stock de la tienda física o al almacén central de e-commerce?) deben ser claras y estar configuradas en el sistema.

## Escenario 3: Cliente gestiona y recoge pedido online en tienda física ("Click & Collect")

*   **Nombre del Escenario:** Gestión y Recogida en Tienda de Pedido Online (Click & Collect)
*   **Actor(es) Principal(es):** Cliente, Vendedor (o Personal de Almacén/Recogidas)
*   **Sistema Involucrado:** Sistema de Punto de Venta (POS), Sistema de Gestión de Pedidos Online, Sistema de Inventario
*   **Objetivo/Meta del Escenario:** El cliente recoge satisfactoriamente en la tienda física un pedido realizado y pagado previamente online. El sistema registra la entrega y actualiza el estado del pedido.

*   **Precondiciones:**
    1.  El Cliente ha realizado un pedido online seleccionando la opción "Recoger en Tienda" y ha recibido una notificación de que su pedido está listo para ser recogido en la tienda seleccionada.
    2.  El pedido ha sido preparado en la tienda (o recibido del almacén central) y está apartado en una zona designada para recogidas.
    3.  El sistema POS/terminal de gestión de la tienda está operativo y tiene acceso a la información de los pedidos online pendientes de recogida.
    4.  El Vendedor está autenticado en el sistema.
    5.  El Cliente se presenta en la tienda con una identificación y/o el número de pedido/confirmación de recogida.

*   **Flujo Normal de Eventos (Secuencia Principal):**
    1.  Cliente se presenta en el área de recogida de pedidos online de la tienda e informa al Vendedor que viene a recoger un pedido.
    2.  Vendedor solicita al Cliente su nombre, número de pedido o el email/SMS de confirmación de recogida.
    3.  Vendedor utiliza la función "Buscar Pedido para Recogida" en el sistema POS o terminal designado.
    4.  Vendedor ingresa la información proporcionada por el Cliente.
    5.  Sistema busca y muestra los detalles del pedido online que está listo para recogida y coincide con la información.
    6.  Vendedor verifica la identidad del Cliente (si la política lo requiere, ej. mostrando una identificación).
    7.  Vendedor localiza físicamente el paquete del pedido en la zona de almacenamiento de recogidas.
    8.  Vendedor verifica visualmente que el paquete corresponda al pedido mostrado en el sistema (ej. cotejando nombre o número de pedido en el paquete).
    9.  **SI** todo es correcto:
        a.  Vendedor entrega el paquete al Cliente.
        b.  Cliente puede inspeccionar brevemente los artículos si lo desea y la política lo permite.
        c.  Vendedor marca el pedido como "Recogido por el Cliente" en el sistema.
        d.  Sistema actualiza el estado del pedido online a "Completado" o "Entregado".
        e.  Sistema puede generar un comprobante de entrega (digital o impreso) si es requerido por la política.
        f.  (Opcional) Sistema envía una notificación automática al Cliente (email/SMS) confirmando la recogida.
    10. Vendedor agradece al Cliente.
    11. El caso de uso finaliza.

*   **Flujos Alternativos y de Excepción:**
    *   **Alternativo 1: Un tercero recoge el pedido en nombre del Cliente.**
        1.  La persona que recoge presenta la autorización del Cliente y su propia identificación, según política.
        2.  Vendedor verifica la autorización y registra los datos de la persona que recoge.
        3.  Continúa desde el paso 5 del Flujo Normal.
    *   **Excepción 1: Pedido no encontrado o no está listo para recogida.**
        1.  Sistema no encuentra el pedido o lo muestra como "En preparación" o "En tránsito".
        2.  Vendedor informa al Cliente y verifica el estado real. Puede necesitar contactar al almacén o al equipo de e-commerce. Se informa al Cliente del plazo estimado o se le pide que espere la notificación oficial.
    *   **Excepción 2: Cliente no presenta identificación válida o número de pedido.**
        1.  Vendedor no puede verificar de forma segura que es el destinatario correcto.
        2.  Vendedor explica la política y puede sugerir al Cliente que obtenga la información necesaria. La entrega se pospone.
    *   **Excepción 3: Discrepancia entre el pedido en sistema y el paquete físico encontrado.**
        1.  Vendedor nota que el paquete no coincide o faltan artículos.
        2.  Vendedor no entrega el pedido e investiga la discrepancia (consulta con personal de almacén, revisa historial del pedido). Se informa al Cliente del problema y se busca una solución (corregir el pedido, ofrecer alternativa, etc.).
    *   **Excepción 4: Cliente rechaza el pedido o algún artículo al momento de la inspección (si permitido).**
        1.  Cliente no está conforme con un artículo.
        2.  Vendedor gestiona la situación según la política:
            a.  Si es un rechazo total, el pedido vuelve a estado "Pendiente de resolución" o se inicia un proceso de devolución online.
            b.  Si es un rechazo parcial y la política lo permite, se puede gestionar una devolución inmediata de ese artículo (ver Escenario 2) y entregar el resto.
    *   **Excepción 5: Sistema no disponible para actualizar estado del pedido.**
        1.  Vendedor entrega el pedido (si se puede verificar manualmente de forma segura) y anota los detalles para actualizar el sistema posteriormente. Se informa al Cliente que la confirmación digital puede demorar.

*   **Actividades Concurrentes:**
    *   Otros clientes recogiendo pedidos.
    *   Personal de tienda preparando otros pedidos para recogida.
    *   Actualizaciones del sistema de e-commerce sobre nuevos pedidos listos.

*   **Postcondiciones:**
    *   **En caso de Éxito:**
        1.  El pedido online se marca como "Recogido" o "Completado" en todos los sistemas relevantes.
        2.  El Cliente tiene posesión de sus artículos.
        3.  (Si aplica) El inventario de "pedidos preparados para recogida" se actualiza.
    *   **En caso de Fallo (Pedido no recogido por problemas):**
        1.  El pedido permanece en estado "Listo para Recogida" o pasa a un estado de "Incidencia en Recogida".
        2.  El Cliente es informado de la situación y los pasos a seguir.

*   **Frecuencia Estimada:** Media (dependiendo del volumen de ventas online con opción "Click & Collect").
*   **Notas Adicionales:**
    *   La comunicación clara con el Cliente (notificaciones de pedido listo, recordatorios) es clave.
    *   La organización en tienda para almacenar y localizar rápidamente los pedidos preparados es importante para la eficiencia.
    *   Definir claramente el plazo máximo que un pedido permanecerá esperando recogida antes de ser cancelado o devuelto a stock.

## Escenario 4: Recepción de Nueva Mercancía de un Proveedor

*   **Nombre del Escenario:** Recepción de Mercancía de Proveedor
*   **Actor(es) Principal(es):** Personal de Almacén/Recepción, Gerente de Tienda (para validación o si hay discrepancias)
*   **Sistema Involucrado:** Sistema de Gestión de Inventario (parte del SGTR), Sistema de Gestión de Pedidos a Proveedores (si existe y está integrado)
*   **Objetivo/Meta del Escenario:** La tienda recibe correctamente la mercancía enviada por un proveedor, la verifica contra la orden de compra, y actualiza el inventario del sistema.

*   **Precondiciones:**
    1.  Se ha realizado una orden de compra (OC) al proveedor y se espera la entrega.
    2.  La OC está registrada en el sistema.
    3.  El Personal de Almacén/Recepción está autenticado en el sistema.
    4.  Hay un área designada para la recepción y verificación de mercancía.
    5.  Se dispone de la documentación de entrega del proveedor (albarán, packing list).

*   **Flujo Normal de Eventos (Secuencia Principal):**
    1.  El transportista del proveedor llega a la tienda con la mercancía y la documentación de entrega (albarán).
    2.  Personal de Almacén/Recepción recibe la documentación y localiza la OC correspondiente en el sistema (ej. buscando por número de OC, proveedor, fecha esperada).
    3.  Personal de Almacén/Recepción verifica visualmente la cantidad de bultos/cajas recibidas contra lo indicado en el albarán del proveedor.
    4.  Personal de Almacén/Recepción procede a abrir los bultos/cajas y verificar el contenido artículo por artículo contra el albarán y la OC en el sistema. Para cada tipo de artículo:
        a.  Identifica el producto (ej. por código, descripción).
        b.  Cuenta la cantidad recibida.
        c.  Inspecciona la calidad y estado de los artículos (buscando daños evidentes).
        d.  Ingresa la cantidad recibida y aceptada para ese artículo en la función de "Recepción de Mercancía" del sistema, asociada a la OC.
    5.  **SI** todas las cantidades y artículos coinciden con el albarán y la OC, y la calidad es aceptable:
        a.  Personal de Almacén/Recepción marca la OC como "Recibida Completamente" en el sistema.
        b.  Sistema actualiza el stock de cada artículo recibido en el inventario (aumenta la cantidad disponible).
        c.  Sistema puede generar una etiqueta de recepción interna o actualizar el estado de los artículos para su posterior ubicación en almacén/tienda.
        d.  Personal de Almacén/Recepción firma el albarán del proveedor como conforme y entrega una copia al transportista.
    6.  Personal de Almacén/Recepción procede a almacenar los artículos recibidos en las ubicaciones correspondientes.
    7.  El caso de uso finaliza.

*   **Flujos Alternativos y de Excepción:**
    *   **Alternativo 1: Recepción Parcial de la OC.**
        1.  Durante el paso 4, se constata que no todos los artículos o cantidades de la OC han sido entregados.
        2.  Personal de Almacén/Recepción ingresa las cantidades efectivamente recibidas para cada artículo.
        3.  En el paso 5.a, marca la OC como "Recibida Parcialmente" en el sistema.
        4.  Sistema actualiza el stock solo de los artículos y cantidades recibidas.
        5.  Personal de Almacén/Recepción anota las discrepancias en el albarán del proveedor antes de firmar y se comunica con el proveedor (o el departamento de compras) para gestionar los artículos pendientes.
    *   **Excepción 1: Discrepancia en cantidad (más o menos de lo esperado/documentado).**
        1.  En el paso 4.b, la cantidad contada no coincide con el albarán o la OC.
        2.  Personal de Almacén/Recepción registra la cantidad real recibida.
        3.  Se notifica al Gerente de Tienda o departamento de compras.
        4.  Se anota la discrepancia en el albarán del proveedor. Se contacta al proveedor para aclarar y resolver (ej. envío complementario, nota de crédito/débito).
        5.  El sistema registra la recepción con las cantidades reales y la OC queda en estado "Recibida con Discrepancias" hasta su resolución.
    *   **Excepción 2: Artículo incorrecto recibido (no estaba en la OC).**
        1.  En el paso 4.a, se identifica un artículo no solicitado.
        2.  Personal de Almacén/Recepción no ingresa este artículo como parte de la OC.
        3.  Se notifica al Gerente y se contacta al proveedor para gestionar la devolución del artículo incorrecto.
    *   **Excepción 3: Artículos dañados o de calidad inaceptable.**
        1.  En el paso 4.c, se detectan artículos dañados.
        2.  Personal de Almacén/Recepción separa los artículos dañados y registra la cantidad aceptada (no dañada) y la cantidad rechazada/dañada en el sistema.
        3.  Se notifica al Gerente y se contacta al proveedor para gestionar el reemplazo, crédito o devolución de los artículos dañados. Se documenta con fotografías si es posible.
    *   **Excepción 4: OC no encontrada en el sistema.**
        1.  En el paso 2, el sistema no encuentra la OC referenciada en el albarán.
        2.  Personal de Almacén/Recepción verifica los datos con el transportista. Si persiste, contacta al departamento de compras para validar la entrega antes de aceptarla formalmente. La mercancía puede quedar en una zona de "recepción pendiente de validación".

*   **Actividades Concurrentes:**
    *   Procesamiento de ventas en tienda.
    *   Movimientos de inventario internos (ej. reposición de estanterías).
    *   Consultas de stock por parte de vendedores o el sistema de e-commerce.

*   **Postcondiciones:**
    *   **En caso de Éxito (Recepción Completa y Conforme):**
        1.  La OC se marca como "Recibida Completamente" en el sistema.
        2.  El inventario de los artículos recibidos se ha incrementado correctamente.
        3.  La documentación de entrega del proveedor ha sido firmada y procesada.
        4.  Los artículos están listos para ser almacenados o puestos a la venta.
    *   **En caso de Recepción Parcial o con Discrepancias:**
        1.  La OC se marca como "Recibida Parcialmente" o "Recibida con Discrepancias".
        2.  El inventario se actualiza solo con las cantidades y artículos aceptados.
        3.  Se han iniciado los procesos para resolver las discrepancias con el proveedor.
    *   **En caso de Rechazo de Entrega (si aplica por problemas mayores):**
        1.  La mercancía no se acepta formalmente.
        2.  El inventario no se modifica.
        3.  Se documentan las razones del rechazo y se comunica al proveedor.

*   **Frecuencia Estimada:** Variable (desde diaria hasta semanal, dependiendo del tipo de tienda y la frecuencia de pedidos a proveedores).
*   **Notas Adicionales:**
    *   El uso de lectores de códigos de barras puede agilizar significativamente el proceso de verificación de artículos.
    *   El sistema podría permitir adjuntar copias digitales del albarán firmado a la recepción en el sistema.
    *   Es importante tener un proceso claro para la gestión de discrepancias con los proveedores.
