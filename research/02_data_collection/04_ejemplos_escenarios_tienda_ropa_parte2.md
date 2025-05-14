# Ejemplos Detallados de Escenarios para Sistema de Gestión de Tienda de Ropa (Parte 2)

Este documento es la continuación de [`04_ejemplos_escenarios_tienda_ropa_parte1.md`](research/02_data_collection/04_ejemplos_escenarios_tienda_ropa_parte1.md) y presenta más ejemplos de escenarios de uso para un sistema de gestión de tienda de ropa.

## Escenario 5: Gerente genera informe de ventas semanal

*   **Nombre del Escenario:** Generación de Informe de Ventas Semanal por Gerente
*   **Actor(es) Principal(es):** Gerente de Tienda
*   **Sistema Involucrado:** Sistema de Gestión de Tienda de Ropa (Módulo de Reportes)
*   **Objetivo/Meta del Escenario:** El Gerente de Tienda obtiene un informe detallado de las ventas de la semana anterior para analizar el rendimiento y tomar decisiones.

*   **Precondiciones:**
    1.  El Gerente de Tienda está autenticado en el Sistema de Gestión con los permisos adecuados para acceder a los reportes.
    2.  El sistema ha estado registrando transacciones de venta durante la semana anterior.
    3.  El sistema está operativo.

*   **Flujo Normal de Eventos (Secuencia Principal):**
    1.  El Gerente de Tienda accede al módulo de "Reportes" o "Análisis de Ventas" del sistema.
    2.  El Gerente selecciona la opción para generar un "Informe de Ventas".
    3.  El sistema presenta filtros para el informe. El Gerente selecciona/ingresa:
        a.  Rango de Fechas: Desde el primer día de la semana anterior hasta el último día de la semana anterior.
        b.  (Opcional) Nivel de Detalle: Resumido por día, detallado por transacción, agrupado por categoría de producto, etc. (Gerente selecciona "Detallado por día y categoría").
        c.  (Opcional) Tienda/Sucursal: Si el gerente gestiona múltiples tiendas, selecciona la tienda específica o "Todas". (Gerente selecciona "Tienda Principal").
    4.  El Gerente hace clic en "Generar Informe".
    5.  El sistema procesa los datos de ventas del período y filtros seleccionados.
    6.  El sistema muestra el informe de ventas semanal en pantalla, incluyendo:
        a.  Ventas totales del período.
        b.  Ventas por día.
        c.  Ventas por categoría de producto.
        d.  Número de transacciones.
        e.  Valor promedio de transacción.
        f.  Productos más vendidos.
        g.  (Otros KPIs relevantes configurados).
    7.  El Gerente revisa el informe en pantalla.
    8.  (Opcional) El Gerente selecciona la opción de "Exportar" o "Imprimir" el informe.
        a.  Si exporta: Selecciona el formato (ej. PDF, Excel/CSV). El sistema genera el archivo y lo descarga o permite guardarlo.
        b.  Si imprime: El sistema envía el informe a la impresora configurada.
    9.  El caso de uso finaliza.

*   **Flujos Alternativos y de Excepción:**
    *   **Alternativo 1: Gerente selecciona diferentes filtros o agrupación.**
        1.  En el paso 3, el Gerente elige agrupar por vendedor, o ver solo ventas de una promoción específica, o un rango de fechas diferente.
        2.  El sistema genera el informe según los nuevos criterios.
    *   **Alternativo 2: Gerente guarda la configuración del informe como favorito.**
        1.  Después de generar un informe con filtros específicos (paso 6), el Gerente usa una opción "Guardar como plantilla" o "Informe Favorito".
        2.  En futuras ocasiones, puede seleccionar este informe favorito para generarlo rápidamente con los mismos filtros (solo ajustando el rango de fechas dinámicamente si es una plantilla semanal).
    *   **Excepción 1: No hay datos de ventas para el período seleccionado.**
        1.  En el paso 6, el sistema informa que no se encontraron transacciones para el rango de fechas.
        2.  Gerente verifica los filtros (especialmente el rango de fechas).
    *   **Excepción 2: El sistema tarda demasiado en generar un informe muy complejo.**
        1.  En el paso 5, si el volumen de datos y la complejidad de los cálculos son muy altos, el sistema podría mostrar un indicador de progreso.
        2.  Si excede un tiempo límite razonable, el Gerente podría optar por simplificar los filtros (ej. rango de fechas más corto, menos detalle) o el sistema podría ofrecer generar el informe en segundo plano y notificar cuando esté listo.
    *   **Excepción 3: Error al exportar o imprimir el informe.**
        1.  En el paso 8, el sistema muestra un error (ej. problema con la impresora, formato de exportación no disponible).
        2.  Gerente intenta con otro formato o verifica la configuración de la impresora.

*   **Actividades Concurrentes:**
    *   El sistema sigue registrando ventas en tiempo real.
    *   Otros usuarios pueden estar utilizando el sistema.
    *   El sistema debe asegurar que la generación de reportes no degrade significativamente el rendimiento de las operaciones transaccionales (ej. ventas en POS).

*   **Postcondiciones:**
    *   **En caso de Éxito:**
        1.  El Gerente ha visualizado y/o obtenido (exportado/impreso) el informe de ventas semanal según los criterios especificados.
        2.  El sistema no ha modificado ningún dato de ventas, solo los ha consultado y procesado para el reporte.
    *   **En caso de Fallo (Informe no generado o incompleto):**
        1.  El Gerente es informado de la razón del fallo.

*   **Frecuencia Estimada:** Semanal (o según necesidad del Gerente, podría ser diario o mensual también).
*   **Notas Adicionales:**
    *   La capacidad de personalización de los informes (selección de campos, filtros, agrupaciones, gráficos) es un atributo de calidad importante para el módulo de reportes.
    *   El sistema debería permitir programar la generación automática de ciertos informes y su envío por email a destinatarios predefinidos.
