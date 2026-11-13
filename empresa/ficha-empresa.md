# LOTO ROSA | FICHA DE EMPRESA

## LA TIENDA

La idea de LOTO ROSA es una tienda de bienestar y cuidado personal, para el catálogo elegí una vela, un aceite de masaje, unos dados y un antifaz, usé fondos claros y pétalos rosas para que las fotos se vieran de la misma tienda

## DATOS CONFIGURADOS EN LA COMPAÑÍA

| Campo de Odoo | Valor |
| --- | --- |
| Nombre de la empresa | LOTO ROSA |
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

Para rellenar la ficha entré en Ajustes, Usuarios y compañías, Compañías

## LOGO Y DOCUMENTOS

Archivo logo.png

Puse la flor de loto encima del nombre y usé el mismo logo en el presupuesto y la factura, elegí el formato A4, la letra Lato y dos tonos de rosa (#A75C78 y #E8C9D4), arriba puse "Bienestar y cuidado personal" y abajo indiqué que la empresa era ficticia y los documentos no tenían validez comercial

## CATÁLOGO DE PRODUCTOS



| Referencia interna | Producto | Precio de venta | Coste | IVA |
| --- | --- | ---: | ---: | --- |
| `LR-VEL-001` | Vela Aromática "Calma Rosa" | 19,90 € | 7,50 € | 21 % |
| `LR-ACE-002` | Aceite de Masaje "Pétalo Suave" | 16,90 € | 5,80 € | 21 % |
| `LR-DAD-003` | Dados para Parejas "Provócame" | 12,90 € | 3,90 € | 21 % |
| `LR-ANT-004` | Antifaz de Satén "Susurro Rosa" | 14,90 € | 4,60 € | 21 % |

### VELA AROMÁTICA "CALMA ROSA"

Archivo productos/vela-loto-rosa.png

### ACEITE DE MASAJE "PÉTALO SUAVE"

Archivo productos/aceite-masaje-petalo-suave.png

### DADOS PARA PAREJAS "PROVÓCAME"

Archivo productos/dados-romanticos.png

### ANTIFAZ DE SATÉN "SUSURRO ROSA"

Archivo productos/mascarilla-saten-rosa.png

## PRECIOS Y ALMACÉN

En Odoo utilicé Contactos para los clientes, Ventas para el presupuesto, Inventario para la entrega y Facturación para registrar la factura y el cobro

Creé la lista "LOTO ROSA - Precios en EUR" con el precio fijo de cada producto, para llevar el stock marqué el seguimiento por cantidad en la vela porque era el producto con el que quería comprobar la salida del almacén, puse 50 unidades en LR/Stock y después de la entrega quedaban 48

## CLIENTES PREPARADOS



| Referencia | Cliente | Tipo | Correo |
| --- | --- | --- | --- |
| `LR-CLI-001` | Claudia Romero Vega | Particular | `claudia.romero@example.com` |
| `LR-CLI-002` | Flor de Seda Eventos | Empresa | `administracion@flordeseda.example.com` |

Claudia está dada de alta como particular y su cuenta figura como "Portal", Flor de Seda Eventos está como empresa y es el cliente que usé para el presupuesto, en su ficha puse la lista en euros y el pago a 30 días para tener esas condiciones al preparar el presupuesto
