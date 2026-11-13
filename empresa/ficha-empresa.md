# LOTO ROSA | Ficha de empresa

## La idea de la marca

Para LOTO ROSA he planteado una tienda de productos de bienestar, relajación, cuidado personal y artículos para parejas. Quería que el nombre se relacionara con una imagen suave y cuidada, pero que al mismo tiempo fuera un negocio al que se le pudieran aplicar las operaciones habituales de un ERP. Por eso no preparé solamente el logo y un par de productos para enseñarlos en pantalla: configuré también los precios, los costes, los impuestos, los contactos y el inventario que necesita una venta.

La marca es ficticia. Utilicé datos de ejemplo para la dirección, el teléfono, el correo, el NIF y las personas de contacto. Así puedo mostrar la configuración comercial sin utilizar información privada de nadie. El catálogo mezcla productos pensados para una compra personal con otros que también podría adquirir una empresa para sus eventos o para preparar lotes de regalo. Esa fue la razón por la que creé un cliente particular y otro empresarial.

## Datos configurados en la compañía

| Campo de Odoo | Valor |
| --- | --- |
| Nombre de la empresa | **LOTO ROSA** |
| Identificador de compañía | `LOTO-01` |
| Sector | Bienestar y cuidado personal |
| Actividad | Venta de artículos de relajación, cuidado personal y productos para parejas |
| Dirección | Calle Azahar, 14, Local 2 |
| Código postal y ciudad | 41003 Sevilla |
| Provincia y país | Sevilla, España |
| NIF ficticio | `ESA12345674` |
| Teléfono de ejemplo | `+34 612 345 678` |
| Correo | `hola@lotorosa.es` |
| Página web indicada en Odoo | `http://www.lotorosa.es` |
| Moneda | EUR |
| Color seleccionado en la ficha | Frambuesa |

Los datos de la compañía se introdujeron en **Ajustes > Usuarios y compañías > Compañías**. La dirección pertenece a Sevilla y está pensada como la de un local comercial, no como una dirección personal. La moneda se dejó en euros porque tanto los precios del catálogo como la operación de venta y el pago están expresados en EUR.

## Identidad visual y documentos comerciales

El nombre, el logotipo y los colores siguen la misma estética. Me interesaba que al abrir un PDF se reconociera LOTO ROSA aunque la persona que lo consultase no estuviera dentro de Odoo, por eso modifiqué el diseño de los documentos en lugar de dejar todos los informes con el aspecto inicial del programa.

| Elemento | Configuración |
| --- | --- |
| Logotipo | Identidad floral de LOTO ROSA. La imagen original debe conservarse como `empresa/logo.png` |
| Color principal | Rosa frambuesa, `#A75C78` |
| Color secundario | Rosa claro, `#E8C9D4` |
| Tipografía empleada en los documentos | Lato |
| Eslogan | "Bienestar y cuidado personal" |
| Pie de página | "Loto Rosa, Empresa ficticia de práctica, Sin validez comercial" |
| Formato | A4 |

Los informes de presupuesto y factura incluyen los datos de la empresa y mantienen el mismo estilo. Me parece importante porque los documentos salen de departamentos distintos, pero de cara al cliente deben identificarse como parte del mismo negocio. En los dos se conservan los conceptos, precios e impuestos que calcula Odoo, sin sustituirlos por una imagen de una factura creada a mano.

El logo aparece en la compañía y los informes. La copia que se incorpore al repositorio tiene que ser la misma imagen que utilicé dentro de Odoo, para que no aparezcan dos versiones distintas.

## Catálogo de productos

He creado cuatro artículos relacionados con la actividad de LOTO ROSA. Cada uno tiene una imagen, un nombre comercial propio, su referencia interna, precio de venta, coste e impuesto. Separar el coste del precio es útil para representar que la tienda compra o prepara sus productos por una cantidad y después los ofrece por otra. El precio de venta es el que se utiliza al presupuestar, mientras que el coste queda como información interna.

| Referencia interna | Producto | Precio de venta | Coste | IVA |
| --- | --- | ---: | ---: | --- |
| `LR-VEL-001` | Vela Aromática "Calma Rosa" | 19,90 € | 7,50 € | 21 % |
| `LR-ACE-002` | Aceite de Masaje "Pétalo Suave" | 16,90 € | 5,80 € | 21 % |
| `LR-DAD-003` | Dados para Parejas "Provócame" | 12,90 € | 3,90 € | 21 % |
| `LR-ANT-004` | Antifaz de Satén "Susurro Rosa" | 14,90 € | 4,60 € | 21 % |

### Vela Aromática "Calma Rosa"

La vela fue el producto que utilicé para demostrar el inventario. Es un artículo físico, con una referencia propia y una cantidad de unidades que se puede consultar en el almacén. Elegí seguir sus existencias porque permite comprobar algo que no se ve solamente en el presupuesto: cuando se entrega un pedido deben salir unidades del stock. Se prepararon **50 unidades** iniciales en `LR/Stock` y en el pedido `S00025` se incluyeron dos.

Su precio de venta es de 19,90 € y el coste de 7,50 €. La foto del producto sigue los colores del catálogo. En la venta, la cantidad de dos velas supone 39,80 € antes de impuestos.

### Aceite de Masaje "Pétalo Suave"

Este producto tiene un precio de 16,90 € y un coste de 5,80 €. Lo añadí al mismo catálogo porque representa otra línea de bienestar y cuidado personal sin repetir el tipo de artículo de la vela. Además, lo elegí para aplicar un descuento en el presupuesto real. En `S00025` aparece una unidad con **10 % de descuento**, de manera que su base pasa de 16,90 € a 15,21 €. El precio habitual del producto no se modificó. El descuento afecta únicamente a esa venta.

### Dados para Parejas "Provócame"

Es un artículo de la línea de productos para parejas. Lo incorporé para que la tienda no dependiera únicamente de velas y aceites. Tiene su propia imagen, referencia `LR-DAD-003`, precio de 12,90 €, coste de 3,90 € e IVA del 21 %. Aunque forma parte del catálogo, no aparece en el pedido `S00025`, que utiliza otros tres productos.

### Antifaz de Satén "Susurro Rosa"

El antifaz completa el catálogo con un producto diferente por uso y presentación. Su precio de venta es de 14,90 €, con un coste de 4,60 €. En la operación con Flor de Seda Eventos se vendió una unidad. El producto mantiene la estética rosa de la empresa, pero tiene una referencia y un precio propios para poder identificarlo por separado en las líneas del pedido.

## Precios, impuestos e inventario

Para los importes comerciales utilizo la lista **`LOTO ROSA - Precios en EUR`**, asociada a la compañía. Preparé reglas de precio fijo para los productos, ya que quería evitar que el presupuesto cambiara a otra moneda o utilizara valores que no correspondieran con los precios que había definido para LOTO ROSA.

El IVA aplicado a los productos es del **21 %**. En el presupuesto y la factura el impuesto se calcula sobre la base de cada línea, después de aplicar el descuento cuando existe. Por eso en `S00025` el aceite no tributa sobre los 16,90 € originales sino sobre los 15,21 € de su precio descontado. La suma de las tres líneas proporciona una base de 69,91 € y un IVA redondeado de 14,68 €.

En el almacén utilicé el código corto **LR**, con la ubicación interna **`LR/Stock`**. Para la vela registré un ajuste inicial de 50 unidades. La entrega del pedido contiene dos velas, así que, si no hubo otros movimientos, el resultado esperado es que queden **48**. El pedido muestra dos velas entregadas. Para completar el dato del inventario queda comprobar la cifra de existencias que muestra la ficha del producto después de la salida.

No he tratado a los otros tres artículos como productos con seguimiento de existencias en esta configuración. Eso no impide que aparezcan en las líneas comerciales y en la operación de entrega: el objetivo del seguimiento detallado era demostrarlo con un producto concreto.

## Clientes preparados

Necesitaba un cliente particular y otro de empresa porque Odoo permite representar situaciones diferentes. En el primer caso se trata de una compra realizada por una persona. En el segundo, la empresa puede recibir un presupuesto con sus datos fiscales y condiciones comerciales. Ambos contactos son ficticios.

| Referencia | Cliente | Tipo | Correo |
| --- | --- | --- | --- |
| `LR-CLI-001` | **Claudia Romero Vega** | Particular | `claudia.romero@example.com` |
| `LR-CLI-002` | **Flor de Seda Eventos, S.L.** | Empresa | `administracion@flordeseda.example.com` |

### Claudia Romero Vega

En su ficha está marcada como **persona** y tiene una dirección de ejemplo en **Calle Pétalo Rosa, 18, 41003 Sevilla**. La creé para cubrir la venta a particulares y comprobar que un contacto individual se distingue de una empresa. También es la candidata para el acceso portal opcional: si se concede ese acceso, seguirá siendo un cliente externo y no un empleado con permisos sobre Ventas o Facturación.

### Flor de Seda Eventos, S.L.

Este cliente aparece como **compañía**. Su dirección es **Calle Jardines del Guadalquivir, 25, Local 3, 41010 Sevilla**. Tiene asociada la lista de precios de LOTO ROSA y condiciones de pago a **30 días**. Lo elegí para el presupuesto definitivo porque así podía enseñar un documento dirigido a una empresa y utilizar unas condiciones de pago que después se mantuvieran en la factura.

## Relación de la empresa con los documentos generados

La configuración de la compañía se ve aplicada en una operación concreta. El presupuesto **`S00025`** lo preparó Marta Comercial para Flor de Seda Eventos con tres productos y un total de **84,59 €**. Laura lo confirmó como pedido y la venta continuó hasta la factura **`INV/2026/00010`**. El pago registrado tiene la referencia **`PBNK1/2026/00001`**.

Estas referencias son útiles porque permiten seguir el mismo caso en Ventas, Inventario y Facturación. Los productos no son simples ejemplos aislados: los que se vendieron aparecen en el presupuesto, sus cantidades pasan al pedido y las líneas se mantienen en la factura. El detalle de cada operación se encuentra en [`../venta/proceso-venta.md`](../venta/proceso-venta.md).
