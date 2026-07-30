1. ¿Por qué LEFT JOIN y no INNER JOIN en la Consulta 1?
¿Por qué LEFT JOIN?: Porque garantiza mostrar todos los productos del catálogo, tengan ventas o no.

¿Qué se perdería con INNER JOIN?: Se descartarían los productos 108 (Hub USB-C 7p) y 109 (Parlante Bluetooth) por no tener ventas, impidiendo responder la pregunta de negocio.

2. ¿Por qué RIGHT JOIN en la Consulta 2 y qué tabla está a cada lado?
¿Por qué RIGHT JOIN?: Para priorizar la tabla ventas y detectar transacciones con productos inexistentes en el catálogo.

Ubicación: Tabla a la izquierda = productos | Tabla a la derecha = ventas.

3. ¿Qué representan los valores NULL en cada consulta?
venta_id es NULL (Consulta 1): Significa que el producto existe en el catálogo pero nunca se vendió (ej. producto 108).

producto_id de productos es NULL (Consulta 2): Significa que se registró una venta de un producto que no existe en el catálogo (ej. venta 10 con producto 999), evidenciando un error de datos.

4. ¿Cuándo usarías FULL OUTER JOIN en un caso real?
Se usa para auditorías y conciliaciones de 2 vías, como comparar los cobros de una pasarela de pagos (Stripe/Mercado Pago) contra las ventas del sistema interno para detectar cobros sin pedido registrado y pedidos sin cobro real en una sola vista.
