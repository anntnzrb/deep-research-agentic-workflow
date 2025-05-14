# Ejemplos de Casos de Uso para Sistema de Gestión de Tienda de Ropa (Parte 1)

Este documento presenta ejemplos detallados de casos de uso para un Sistema de Gestión de Tienda de Ropa, siguiendo una estructura inspirada en el estándar IEEE 830 y las prácticas comunes de la ingeniería de requerimientos. Estos ejemplos buscan ilustrar las interacciones clave entre los actores y el sistema.

La estructura general de cada caso de uso se basa en la investigación documentada en [`01_hallazgos_primarios_parte2.md`](research/02_data_collection/01_hallazgos_primarios_parte2.md#d2-estructura-de-un-caso-de-uso-basado-en-ieee-830-y-pr%C3%A1cticas-comunes).

## Caso de Uso 1: Gestionar Devolución de Producto

**1. Identificador Único y Nombre del Caso de Uso:**
    *   **ID:** CU-001
    *   **Nombre:** Gestionar Devolución de Producto

**2. Actores:**
    *   **Primario:** Vendedor (o Cajero, Personal de Atención al Cliente)
    *   **Secundarios:** Cliente, Sistema de Inventario, Sistema de Pagos (si implica reembolso a tarjeta)

**3. Descripción Breve:**
    Este caso de uso describe el proceso mediante el cual un Vendedor gestiona la devolución de un producto previamente comprado por un Cliente. Incluye la verificación de la política de devolución, la inspección del producto, la actualización del inventario y el procesamiento del reembolso o crédito para el Cliente.

**4. Precondiciones:**
    *   El Vendedor ha iniciado sesión en el Sistema de Gestión.
    *   El Cliente está presente con el producto a devolver y, preferiblemente, el comprobante de compra (ticket/factura).
    *   El sistema tiene acceso a la información de ventas pasadas y políticas de devolución.

**5. Flujo Principal de Eventos (Curso Normal):**
    1.  El Cliente solicita al Vendedor la devolución de un producto.
    2.  El Vendedor solicita al Cliente el comprobante de compra y el producto.
    3.  El Vendedor busca la transacción de venta original en el sistema utilizando la información del comprobante (ej. número de ticket, fecha, código de producto).
        *   *Si el Cliente no tiene comprobante, el Vendedor intenta buscar la transacción por otros medios (ej. tarjeta de fidelidad, fecha aproximada y producto), si el sistema lo permite y la política lo contempla.*
    4.  El sistema muestra los detalles de la transacción original.
    5.  El Vendedor verifica que el producto y la fecha de compra cumplen con la política de devoluciones de la tienda (ej. plazo máximo para devolución, tipo de producto elegible).
    6.  El Vendedor inspecciona el estado del producto devuelto para asegurar que cumple con las condiciones de devolución (ej. sin usar, con etiquetas, en buen estado).
    7.  Si la devolución es aceptada:
        a.  El Vendedor registra la devolución en el sistema, seleccionando el/los artículo(s) a devolver de la transacción original.
        b.  El sistema pregunta el motivo de la devolución (el Vendedor selecciona de una lista o ingresa texto).
        c.  El sistema indica si el producto devuelto debe reintegrarse al stock vendible o marcarse como defectuoso/no vendible. El Vendedor confirma o ajusta según la inspección.
        d.  El Sistema de Inventario actualiza el stock del producto (aumenta el stock vendible o el stock dañado según corresponda).
        e.  El sistema calcula el monto a reembolsar o el crédito a generar, de acuerdo con la política (ej. precio original pagado, deducción de gastos si aplica).
        f.  El Vendedor pregunta al Cliente su método de reembolso preferido, según las opciones permitidas por la política (ej. mismo método de pago original, nota de crédito, efectivo).
        g.  El Vendedor procesa el reembolso:
            *   **Efectivo:** El sistema registra la salida de efectivo y el Vendedor entrega el dinero al Cliente.
            *   **Tarjeta:** El sistema se comunica con el Sistema de Pagos para procesar el reembolso a la tarjeta original.
            *   **Nota de Crédito:** El sistema genera una nota de crédito a favor del Cliente por el monto correspondiente, con un identificador único.
        h.  El sistema genera un comprobante de devolución.
        i.  El Vendedor entrega el comprobante de devolución (y el efectivo, si aplica) al Cliente.
    8.  El caso de uso finaliza.

**6. Flujos Alternativos (Cursos Alternativos):**

    *   **A1: Cliente no presenta comprobante de compra (y el sistema permite búsqueda alternativa):**
        *   En el paso 5.3, si el Cliente no tiene comprobante, el Vendedor intenta buscar la transacción por otros medios (ej. número de tarjeta de fidelidad, fecha aproximada y descripción del producto).
        *   Si la transacción se encuentra, el flujo continúa desde 5.4.
        *   Si la transacción no se encuentra, se procede al Flujo de Excepción E1.

    *   **A2: Devolución parcial de una compra múltiple:**
        *   En el paso 5.7.a, el Vendedor selecciona solo los artículos específicos que el Cliente desea devolver de la transacción original. El sistema recalcula el monto a reembolsar solo por esos artículos.

    *   **A3: Cliente solicita un cambio en lugar de un reembolso:**
        *   Si la política lo permite, después del paso 5.7.e, el Cliente puede optar por cambiar el producto devuelto por otro(s) de igual o diferente valor.
        *   El Vendedor procesa la devolución del artículo original según el flujo principal (hasta 5.7.e).
        *   Luego, el Vendedor inicia una nueva transacción de venta para el/los nuevo(s) producto(s).
        *   El monto del producto devuelto se aplica como forma de pago a la nueva transacción. Si hay diferencia a pagar por el Cliente o a devolver por la tienda, se gestiona correspondientemente.

    *   **A4: Producto devuelto está dañado pero cubierto por garantía (si aplica):**
        *   En el paso 5.6, si el producto está dañado pero la política de garantía lo cubre, el Vendedor lo registra como "devolución por garantía".
        *   En el paso 5.7.c, el producto se marca como "defectuoso para revisión" o "para enviar a proveedor".
        *   El proceso de reembolso o cambio puede tener condiciones especiales según la política de garantía.

**7. Flujos de Excepción (Manejo de Errores):**

    *   **E1: Transacción original no encontrada:**
        *   En el paso 5.3 (o A1), si el sistema no puede encontrar la transacción original, el Vendedor informa al Cliente.
        *   Según la política de la tienda, la devolución puede ser denegada o procesada bajo condiciones especiales (ej. solo cambio, crédito a precio actual más bajo). El caso de uso puede terminar o desviarse a un procedimiento manual aprobado por un supervisor.

    *   **E2: Producto no cumple con la política de devolución (plazo expirado, tipo de producto no retornable):**
        *   En el paso 5.5, si el producto no es elegible para devolución, el Vendedor informa al Cliente la razón.
        *   El caso de uso finaliza. El Vendedor puede ofrecer alternativas si la política lo contempla (ej. reparación con costo).

    *   **E3: Producto no cumple con las condiciones de estado (usado, dañado por el cliente):**
        *   En el paso 5.6, si el producto no está en condiciones aceptables para la devolución (y no es un caso de garantía), el Vendedor informa al Cliente.
        *   El caso de uso finaliza.

    *   **E4: Falla en el Sistema de Pagos al procesar reembolso a tarjeta:**
        *   En el paso 5.7.g (Tarjeta), si el Sistema de Pagos devuelve un error, el sistema informa al Vendedor.
        *   El Vendedor informa al Cliente. Se pueden intentar alternativas (ej. procesar como nota de crédito, intentar más tarde, reembolso en efectivo si la política y el monto lo permiten).

    *   **E5: No hay suficiente efectivo en caja para reembolso (si aplica):**
        *   En el paso 5.7.g (Efectivo), si el monto a reembolsar excede el efectivo disponible autorizado, el Vendedor solicita asistencia de un supervisor o propone al Cliente una alternativa (ej. nota de crédito, transferencia bancaria posterior).

**8. Postcondiciones:**
    *   **Éxito:**
        *   La devolución ha sido registrada en el sistema.
        *   El stock del producto ha sido actualizado en el Sistema de Inventario.
        *   El Cliente ha recibido su reembolso (o nota de crédito).
        *   Se ha generado y entregado un comprobante de devolución.
    *   **Fallo (Devolución no procesada):**
        *   El estado del inventario y financiero del cliente permanece sin cambios respecto a la devolución.
        *   El Cliente ha sido informado de la razón por la cual la devolución no pudo ser procesada.

**9. Requisitos Especiales (No Funcionales):**
    *   **Rendimiento:** La búsqueda de la transacción original debería completarse en menos de 5 segundos.
    *   **Seguridad:** Solo personal autorizado (Vendedor, Supervisor) puede procesar devoluciones que impliquen reembolsos en efectivo o anulación de ventas. Las devoluciones por montos elevados pueden requerir autorización de supervisor.
    *   **Usabilidad:** La interfaz para procesar devoluciones debe ser clara e intuitiva, guiando al Vendedor a través de los pasos necesarios.
    *   **Auditoría:** Todas las transacciones de devolución deben quedar registradas con detalle (fecha, hora, Vendedor, Cliente si se identifica, productos, montos, motivo) para futuras auditorías.

**10. Frecuencia de Uso:**
    *   Estimada: Media (varias veces al día, dependiendo del volumen de ventas y políticas de la tienda).

**11. Notas y Comentarios Adicionales:**
    *   Las políticas de devolución específicas de la tienda (plazos, condiciones del producto, tipos de reembolso) deben ser configurables en el sistema.
    *   El sistema debería permitir generar reportes sobre devoluciones (ej. por motivo, por producto, por cliente) para análisis de calidad y tendencias.

---
*(Continuación en 05_ejemplos_casos_uso_tienda_ropa_parte2.md si es necesario)*

## Caso de Uso 2: Aplicar Descuento Promocional

**1. Identificador Único y Nombre del Caso de Uso:**
    *   **ID:** CU-002
    *   **Nombre:** Aplicar Descuento Promocional

**2. Actores:**
    *   **Primario:** Vendedor (o Cajero)
    *   **Secundarios:** Cliente, Sistema de Promociones, Sistema de Inventario (para verificar aplicabilidad de promoción a productos específicos)

**3. Descripción Breve:**
    Este caso de uso describe el proceso mediante el cual un Vendedor aplica un descuento promocional a una transacción de venta. Esto puede incluir descuentos por cupón, promociones automáticas por volumen o tipo de producto, o descuentos manuales autorizados.

**4. Precondiciones:**
    *   El Vendedor ha iniciado sesión en el Sistema de Gestión.
    *   Se está procesando una transacción de venta (productos ya agregados al carrito o siendo agregados).
    *   El sistema tiene acceso a las reglas y condiciones de las promociones activas.

**5. Flujo Principal de Eventos (Curso Normal - Aplicación de Cupón):**
    1.  El Cliente informa al Vendedor que desea utilizar un cupón de descuento.
    2.  El Vendedor solicita el cupón al Cliente (físico o digital).
    3.  El Vendedor ingresa el código del cupón en el campo designado del sistema POS.
    4.  El Sistema de Promociones valida el código del cupón:
        a.  Verifica que el código exista y esté activo.
        b.  Verifica que no haya expirado.
        c.  Verifica que no haya sido utilizado previamente (si es de un solo uso).
        d.  Verifica que se cumplan las condiciones de la promoción asociada al cupón (ej. compra mínima, productos específicos, categoría de cliente).
    5.  Si el cupón es válido y las condiciones se cumplen:
        a.  El sistema aplica el descuento correspondiente (porcentual o fijo) al/los producto(s) elegible(s) o al total de la compra, según la configuración de la promoción.
        b.  El sistema muestra el descuento aplicado y el nuevo subtotal/total de la venta.
        c.  El Vendedor informa al Cliente que el descuento ha sido aplicado.
    6.  La transacción de venta continúa (ej. selección de método de pago).
    7.  El caso de uso finaliza (la aplicación del descuento como tal).

**6. Flujos Alternativos (Cursos Alternativos):**

    *   **A1: Promoción automática por sistema:**
        *   Durante la adición de productos al carrito (o al momento de totalizar), el Sistema de Promociones detecta automáticamente que los productos/condiciones de la venta cumplen con una promoción activa (ej. "2x1 en camisetas seleccionadas", "10% de descuento en compras superiores a X monto").
        *   El sistema aplica el descuento automáticamente.
        *   El sistema informa al Vendedor (y muestra en pantalla) el descuento aplicado.
        *   El flujo continúa desde 5.5.c.

    *   **A2: Descuento manual por Vendedor (con autorización):**
        *   El Cliente solicita un descuento especial o el Vendedor decide aplicar un descuento discrecional (ej. por un pequeño defecto en el producto, cliente VIP).
        *   El Vendedor selecciona la opción de "descuento manual" en el sistema.
        *   El sistema solicita el porcentaje o monto del descuento y el motivo.
        *   Si el descuento excede el límite autorizado para el Vendedor, el sistema solicita autorización de un Supervisor (ingreso de credenciales de supervisor).
        *   Una vez autorizado (si es necesario), el sistema aplica el descuento.
        *   El flujo continúa desde 5.5.b.

    *   **A3: Múltiples promociones aplicables (y el sistema gestiona la prioridad o combinación):**
        *   Si varios descuentos/promociones podrían aplicar a la misma venta o producto.
        *   El Sistema de Promociones determina, según reglas preconfiguradas, cuál promoción aplicar (ej. la más beneficiosa para el cliente, o si se pueden combinar).
        *   El sistema aplica la(s) promoción(es) seleccionada(s).
        *   El flujo continúa desde 5.5.b.

**7. Flujos de Excepción (Manejo de Errores):**

    *   **E1: Código de cupón inválido o expirado:**
        *   En el paso 5.4, si el Sistema de Promociones determina que el cupón no es válido (no existe, expiró, ya fue usado), el sistema informa al Vendedor.
        *   El Vendedor informa al Cliente. El descuento no se aplica. La venta continúa sin el descuento del cupón.

    *   **E2: No se cumplen las condiciones del cupón/promoción:**
        *   En el paso 5.4.d, si los productos o el monto de la venta no cumplen con las condiciones de la promoción, el sistema informa al Vendedor.
        *   El Vendedor informa al Cliente las condiciones no cumplidas. El descuento no se aplica. La venta continúa.

    *   **E3: Descuento manual no autorizado:**
        *   En el paso A2, si el Supervisor no autoriza el descuento manual, el sistema informa al Vendedor.
        *   El Vendedor informa al Cliente. El descuento no se aplica.

**8. Postcondiciones:**
    *   **Éxito:**
        *   El descuento promocional ha sido aplicado a la transacción de venta.
        *   El total de la venta ha sido recalculado.
        *   La aplicación del descuento queda registrada para la transacción.
    *   **Fallo (Descuento no aplicado):**
        *   El total de la venta permanece sin el descuento promocional intentado.
        *   El Cliente (y Vendedor) han sido informados de la razón por la cual el descuento no pudo ser aplicado.

**9. Requisitos Especiales (No Funcionales):**
    *   **Rendimiento:** La validación de cupones y la aplicación de promociones automáticas no deben demorar significativamente el proceso de cobro (idealmente &lt; 2 segundos).
    *   **Configurabilidad:** El Sistema de Promociones debe permitir definir una amplia variedad de reglas de descuento (por producto, categoría, monto, cliente, fechas, códigos de cupón, etc.) y sus prioridades.
    *   **Seguridad:** El acceso para crear/modificar promociones y aplicar descuentos manuales debe estar restringido a personal autorizado.
    *   **Auditoría:** Todas las aplicaciones de descuentos (automáticos, por cupón, manuales) deben quedar registradas con detalle (promoción, monto, Vendedor, autorización si aplica).

**10. Frecuencia de Uso:**
    *   Estimada: Alta (frecuentemente durante el día, especialmente si hay promociones activas).

**11. Notas y Comentarios Adicionales:**
    *   El sistema debería mostrar claramente al Cliente en el ticket de venta los descuentos aplicados y el ahorro obtenido.
    *   Considerar la interacción con programas de fidelización (ej. un descuento podría no ser acumulable con puntos de fidelidad o viceversa).
