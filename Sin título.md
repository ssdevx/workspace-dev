Actualmente utilizo una aplicación llamada **Money Flow** dentro del ecosistema de Apple para registrar mis gastos y tener visibilidad sobre el uso de mi dinero.

La aplicación cumple bien su función, pero el principal problema es que el registro de gastos no está automatizado.

En el caso del efectivo, que uso con menor frecuencia, realizo el registro manual de forma diaria. Sin embargo, con las tarjetas de crédito el comportamiento es distinto: no siempre registro los gastos en el momento y, además, no todos los movimientos deben considerarse como gastos reales. Por ejemplo, ya tengo definido un presupuesto personal semanal (1000 pesos), y algunos pagos con tarjeta se liquidan con ese monto, o algunas compras que se hacen para otras personas, por lo que no todos deben duplicarse como gasto en la aplicación.

Para compensar esto, cuando se genera el corte de mis tarjetas, realizo un proceso manual que consiste en:

- Exportar los estados de cuenta en PDF desde las aplicaciones bancarias (cada banco con formato distinto).
- Registrar los movimientos en un archivo de Excel para:
    - Validar que no existan cargos no reconocidos.
    - Cuadrar los montos.
    - Determinar qué movimientos deben registrarse en la aplicación y cuáles no.
- Registrar manualmente cada gasto en la aplicación, respetando fecha, categoría y demás atributos para mantener consistencia en los reportes.

Este proceso lo repito para 4 tarjetas, lo que lo convierte en una tarea que puede tomar varias horas.

### **Objetivo**

Automatizar la extracción de información desde los estados de cuenta en PDF para generar un archivo de Excel estructurado, que posteriormente pueda utilizarse como base para cargar la información en la aplicación.

### **Requerimientos del archivo de salida**

El archivo de Excel debe contener, como mínimo, las siguientes columnas:

- Fecha
- Cuenta
- Suma
- Moneda (siempre MXN)
- Categoría
- Nota

Adicionalmente, manejo una estructura complementaria para control interno con los siguientes campos:

| **Tarjeta** | **Fecha Operación** | **Cashback** | **Total** | **Pagado** | **Pendiente** | **Categoría** | **Estatus** | **Origen Pago** | **Observaciones** |
| ----------- | ------------------- | ------------ | --------- | ---------- | ------------- | ------------- | ----------- | --------------- | ----------------- |

Donde:

- **Tarjeta**: Banco o medio de pago.
- **Cashback**: Porcentaje de reembolso aplicado (cuando corresponda).
- **Total**: Importe total de la transacción.
- **Pagado**: Monto ya cubierto dentro del presupuesto.
- **Pendiente**: Diferencia entre Total y Pagado.
- **Estatus**: Puede ser _Pago Completo_, _Pago Parcial_ o _Sin Pago_.
La idea es hacer un solo archivo excel. me puedes ayudar primero a generar las mejores ideas para automatizar este flujo, considerar conocimientos de programación por si se requiere implementarlas.
