# VENTA A FLOR DE SEDA EVENTOS

## PRESUPUESTO

Hice el presupuesto S00025 con mi cuenta de comercial el 12/11/2026, puse el 12/12/2026 como fecha de validez y dejé 30 días para el pago. Elegí a Flor de Seda Eventos porque quería usar el cliente de empresa que había dado de alta. La fecha de validez indica hasta cuándo puede aceptar la oferta. Los 30 días son el plazo para pagar la factura

| Producto | Unidades | Precio por unidad | Descuento | Base |
| --- | ---: | ---: | ---: | ---: |
| Vela Calma Rosa | 2 | 19,90 € | 0 % | 39,80 € |
| Aceite Pétalo Suave | 1 | 16,90 € | 10 % | 15,21 € |
| Antifaz Susurro Rosa | 1 | 14,90 € | 0 % | 14,90 € |

Al aceite le puse un 10 % de descuento en su línea para que se viera qué artículo llevaba la rebaja y cuánto se pagaba por él, el importe antes del IVA quedó en 69,91 € y el IVA del 21 % sumó 14,68 € y el total fue de 84,59 €

## CONFIRMACIÓN DEL PEDIDO

Laura abrió el presupuesto que preparé con mi cuenta de comercial y lo confirmó desde Ventas. Al pasar a pedido conservó el número S00025, así pude localizar la entrega y la factura desde la misma ficha

## ENTREGA

Desde "1 Entrega" abrí el albarán LR/OUT/00001, en "Documento de origen" figura S00025 y en "Ubicación de origen" aparece LR/Stock. Laura validó la salida y el albarán quedó en "Hecho"

Antes de dar la entrega por terminada quería comprobar que se habían sacado del almacén las mismas unidades que pidió el cliente. Miré las cantidades del albarán y salieron las dos velas, el aceite y el antifaz que se habían pedido, al entrar en LR/Stock vi que quedaban 48 velas de las 50 que había antes

| Producto | Cantidad pedida | Cantidad entregada |
| --- | ---: | ---: |
| Vela Calma Rosa | 2 | 2 |
| Aceite Pétalo Suave | 1 | 1 |
| Antifaz Susurro Rosa | 1 | 1 |

## FACTURA Y PAGO

Laura creó el borrador desde el pedido, Elena validó la factura INV/2026/00010 y registró el cobro de 84,59 € el 12/11/2026 en el diario Banco, con el método "Manual Payment" y la referencia PBNK1/2026/00001

La factura aparece como "Pagado" y el importe pendiente es 0,00 €. En el pedido, el estado de facturación aparece como "Completamente facturado"

## CÓMO COMPROBÉ QUE ERA LA MISMA VENTA

En la factura aparece S00025 como origen y en la información del pago aparece INV/2026/00010. Comparé los dos PDF y en ambos sale un total de 84,59 €. Después miré lo que quedaba por cobrar en Odoo, porque el estado "Completamente facturado" del pedido solo indica que se facturó todo lo vendido

| Documento | Referencia | Dónde lo comprobé |
| --- | --- | --- |
| Presupuesto | S00025 | venta/presupuesto.pdf |
| Pedido | S00025 | Estado de facturación en "Otra Información" |
| Entrega | LR/OUT/00001 | Albarán enlazado desde "1 Entrega" |
| Factura | INV/2026/00010 | venta/factura.pdf y estado del pago en Odoo |
| Pago | PBNK1/2026/00001 | Información del pago en la factura |

## CAPTURAS DE LA VENTA

| Qué comprobé | Archivo |
| --- | --- |
| Albarán LR/OUT/00001 en estado "Hecho" | capturas/albaran-LR-OUT-00001.jpg |
| Quedan 48 velas Calma Rosa en LR/Stock | capturas/stock-calma-rosa-48.jpg |
| S00025 aparece como "Completamente facturado" | capturas/pedido-S00025-facturado.jpg |
