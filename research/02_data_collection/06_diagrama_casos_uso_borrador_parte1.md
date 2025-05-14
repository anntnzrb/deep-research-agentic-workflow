# Borrador de Diagrama de Casos de Uso: Sistema de Gestión de Tienda de Ropa (Parte 1)

Este documento proporciona una descripción textual para un borrador de diagrama de casos de uso para un Sistema de Gestión de Tienda de Ropa. Está destinado a ser una guía para la creación de un diagrama visual, en ausencia de la "Ilustración 5" mencionada en la [`consigna.pdf`](../../consigna.pdf).

## 1. Actores Principales

Se identifican los siguientes actores principales:

*   **Cliente:**
    *   Descripción: Persona que interactúa con la tienda para buscar información, comprar productos o solicitar servicios postventa (como devoluciones). Puede interactuar en tienda física o a través de un canal online (si existe).
*   **Vendedor/Cajero (Empleado de Tienda):**
    *   Descripción: Empleado de la tienda que opera el Punto de Venta (POS), asiste a los clientes, procesa ventas, devoluciones y gestiona la caja.
*   **Gerente/Administrador del Sistema:**
    *   Descripción: Empleado con responsabilidades de supervisión y gestión, encargado de la configuración del sistema, gestión de inventario, productos, promociones, usuarios, y generación de reportes.
*   **Sistema de Inventario:**
    *   Descripción: Puede ser un módulo interno del sistema de gestión o un sistema externo. Responsable de mantener el registro y control de las existencias de productos. (Considerado actor si es un sistema separado con el que el sistema principal interactúa).
*   **Pasarela de Pago Externa:**
    *   Descripción: Sistema externo responsable de procesar transacciones de pago electrónico (ej. tarjetas de crédito/débito).
*   **Sistema de Proveedores:**
    *   Descripción: Sistema externo (o portal) utilizado para la comunicación y gestión de pedidos con los proveedores de mercancía. (Considerado actor si hay interacción directa del sistema).

## 2. Casos de Uso Principales y Relaciones

A continuación, se listan los casos de uso principales agrupados por el actor que típicamente los inicia o es el principal beneficiario, junto con sus relaciones más relevantes (`<<include>>`, `<<extend>>`).

---

### Actor: Cliente

*   **CU-CLI-001: Buscar Información de Producto**
    *   Descripción: El cliente busca detalles sobre productos (precio, disponibilidad, características).
    *   *Relaciones:* Puede ser realizado en tienda (asistido por Vendedor) o en línea.
*   **CU-CLI-002: Realizar Compra en Tienda**
    *   Descripción: El cliente selecciona productos y procede al pago en la tienda física.
    *   *Relaciones:*
        *   Interactúa con: Vendedor/Cajero (quien ejecuta "CU-VEN-001: Procesar Venta en POS").
*   **CU-CLI-003: Solicitar Devolución/Cambio de Producto**
    *   Descripción: El cliente inicia el proceso para devolver o cambiar un producto comprado.
    *   *Relaciones:*
        *   Interactúa con: Vendedor/Cajero (quien ejecuta "CU-VEN-002: Gestionar Devolución de Producto").
*   **(Opcional, si hay e-commerce) CU-CLI-004: Realizar Compra Online**
    *   *Incluye:* CU-CLI-001: Buscar Información de Producto
    *   *Incluye:* CU-SYS-001: Procesar Pago Online (que interactúa con Pasarela de Pago Externa)
    *   *Incluye:* CU-SYS-002: Verificar Stock Online
*   **(Opcional, si hay e-commerce) CU-CLI-005: Gestionar Cuenta de Cliente Online**

---

### Actor: Vendedor/Cajero (Empleado de Tienda)

*   **CU-VEN-001: Procesar Venta en POS**
    *   Descripción: El vendedor registra los productos, calcula el total, aplica descuentos y procesa el pago.
    *   *Relaciones:*
        *   `<<include>>`: CU-VEN-003: Consultar Precio de Producto
        *   `<<include>>`: CU-VEN-004: Calcular Total Venta
        *   `<<extend>>`: CU-VEN-005: Aplicar Descuento Promocional (Detallado en [`05_ejemplos_casos_uso_tienda_ropa_parte1.md`](research/02_data_collection/05_ejemplos_casos_uso_tienda_ropa_parte1.md))
        *   `<<include>>`: CU-VEN-006: Procesar Pago
        *   `<<include>>`: CU-SYS-003: Actualizar Stock por Venta (Interactúa con Sistema de Inventario)
        *   `<<include>>`: CU-VEN-007: Emitir Comprobante de Venta
*   **CU-VEN-002: Gestionar Devolución de Producto** (Detallado en [`05_ejemplos_casos_uso_tienda_ropa_parte1.md`](research/02_data_collection/05_ejemplos_casos_uso_tienda_ropa_parte1.md))
    *   Descripción: El vendedor gestiona la devolución de un producto según las políticas.
    *   *Relaciones:*
        *   `<<include>>`: CU-VEN-008: Verificar Política de Devolución
        *   `<<include>>`: CU-VEN-009: Inspeccionar Producto Devuelto
        *   `<<include>>`: CU-SYS-004: Actualizar Stock por Devolución (Interactúa con Sistema de Inventario)
        *   `<<extend>>`: CU-VEN-010: Procesar Reembolso (puede interactuar con Pasarela de Pago Externa o ser efectivo)
        *   `<<extend>>`: CU-VEN-011: Emitir Nota de Crédito
*   **CU-VEN-003: Consultar Precio de Producto**
*   **CU-VEN-004: Calcular Total Venta**
*   **CU-VEN-005: Aplicar Descuento Promocional** (Referencia al CU-002 detallado previamente)
*   **CU-VEN-006: Procesar Pago**
    *   *Extendido por:* CU-VEN-006a: Procesar Pago en Efectivo
    *   *Extendido por:* CU-VEN-006b: Procesar Pago con Tarjeta (Interactúa con Pasarela de Pago Externa)
    *   *Extendido por:* CU-VEN-006c: Procesar Pago con Nota de Crédito
*   **CU-VEN-007: Emitir Comprobante de Venta**
*   **CU-VEN-008: Verificar Política de Devolución**
*   **CU-VEN-009: Inspeccionar Producto Devuelto**
*   **CU-VEN-010: Procesar Reembolso**
*   **CU-VEN-011: Emitir Nota de Crédito**
*   **CU-VEN-012: Consultar Stock de Producto**
    *   *Relaciones:* Interactúa con Sistema de Inventario.
*   **CU-VEN-013: Realizar Arqueo de Caja (Abrir/Cerrar Turno)**

---

### Actor: Gerente/Administrador del Sistema

*   **CU-GER-001: Gestionar Productos**
    *   Descripción: Crear, modificar, eliminar productos y sus atributos (descripción, precio, tallas, colores, categorías, SKU).
    *   *Relaciones:* Interactúa con Sistema de Inventario.
*   **CU-GER-002: Gestionar Inventario**
    *   Descripción: Registrar entradas (compras a proveedor), salidas (mermas), realizar ajustes de stock, conteos físicos.
    *   *Relaciones:*
        *   `<<include>>`: CU-VEN-012: Consultar Stock de Producto
        *   Interactúa con Sistema de Inventario.
*   **CU-GER-003: Gestionar Pedidos a Proveedores**
    *   Descripción: Crear y enviar órdenes de compra a proveedores.
    *   *Relaciones:* Puede interactuar con Sistema de Proveedores.
*   **CU-GER-004: Gestionar Promociones y Descuentos**
    *   Descripción: Definir reglas para promociones, cupones, descuentos por volumen, etc.
*   **CU-GER-005: Gestionar Clientes**
    *   Descripción: Consultar, agregar o modificar información de clientes, gestionar programas de fidelización.
*   **CU-GER-006: Gestionar Usuarios del Sistema**
    *   Descripción: Crear, modificar roles y permisos para los empleados que usan el sistema.
*   **CU-GER-007: Generar Reportes**
    *   Descripción: Visualizar y exportar reportes de ventas, inventario, clientes, rendimiento, etc.
*   **CU-GER-008: Configurar Parámetros del Sistema**
    *   Descripción: Definir políticas de la tienda (devoluciones, formas de pago), impuestos, información de la tienda, etc.

---

### Casos de Uso del Sistema (Internos o interactuando con otros sistemas)

*   **CU-SYS-001: Procesar Pago Online** (Parte de CU-CLI-004)
    *   *Relaciones:* Interactúa con Pasarela de Pago Externa.
*   **CU-SYS-002: Verificar Stock Online** (Parte de CU-CLI-004)
    *   *Relaciones:* Interactúa con Sistema de Inventario.
*   **CU-SYS-003: Actualizar Stock por Venta** (Parte de CU-VEN-001)
    *   *Relaciones:* Interactúa con Sistema de Inventario.
*   **CU-SYS-004: Actualizar Stock por Devolución** (Parte de CU-VEN-002)
    *   *Relaciones:* Interactúa con Sistema de Inventario.

## 3. Consideraciones para el Diagrama Visual

*   **Límite del Sistema:** Un rectángulo deberá englobar todos los Casos de Uso que son responsabilidad del "Sistema de Gestión de Tienda de Ropa".
*   **Actores Externos:** Pasarela de Pago Externa, Sistema de Inventario (si es conceptualmente separado), y Sistema de Proveedores se dibujarían fuera del límite del sistema principal, interactuando mediante asociaciones a los casos de uso relevantes.
*   **Claridad:** Dado el número de casos de uso, se podría considerar crear diagramas separados para módulos principales (Ventas, Inventario, Gestión) o niveles de detalle, si un solo diagrama resulta muy congestionado. La [`consigna.pdf`](../../consigna.pdf) (Paso 3d) sugiere agrupar por subsistemas.

Este borrador textual sirve como punto de partida. Un diagrama visual permitiría una mejor comprensión de las interacciones.
