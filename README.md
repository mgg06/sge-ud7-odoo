# LOTO ROSA | Gestión de una empresa en Odoo 19 Community

**Marta González González, 2.º DAM, Sistemas de Gestión Empresarial**  
**Repositorio:** [mgg06/sge-ud7-odoo](https://github.com/mgg06/sge-ud7-odoo)  
**Empresa:** LOTO ROSA, bienestar, cuidado personal y productos para parejas  
**ERP:** Odoo 19 Community, Docker Desktop y PostgreSQL

LOTO ROSA es la empresa que he creado para organizar una venta completa en Odoo. La idea era que tuviera una personalidad reconocible, desde los productos hasta el aspecto de sus documentos, pero también que funcionara como un negocio en el que no todo lo hace la misma persona. He separado el trabajo del comercial, la responsable de Ventas y la persona encargada de Facturación, porque así se ve para qué sirven los usuarios y los permisos cuando se trabaja con un ERP.

La empresa y sus clientes son ficticios. Los productos, los precios y las condiciones están preparados para poder seguir una operación real dentro del programa: primero se hace un presupuesto, después se confirma el pedido, se registra la entrega y finalmente se emite la factura y se cobra. He conservado las referencias que asignó Odoo para que cada documento se pueda relacionar con el anterior.

## Vídeo del proceso

He preparado el recorrido de LOTO ROSA por las diferentes aplicaciones de Odoo. En él se muestran las cuentas de los empleados, la separación de permisos y la venta que termina con la factura `INV/2026/00010` y su pago.

**Vídeo:** pendiente de incorporar el archivo definitivo al repositorio y colocar su enlace.

### Índice del vídeo

Cuando esté disponible la versión definitiva, añadiré aquí los minutos reales del comienzo de cada parte. El orden seguido es el de la empresa, usuarios, grupo personalizado, pruebas de acceso, presupuesto, pedido, entrega y factura con el pago. No he añadido minutos aproximados porque podrían no coincidir con el montaje final.

| Apartado del vídeo | Momento de inicio |
| --- | --- |
| Presentación de LOTO ROSA | Por incorporar |
| Usuarios de la empresa | Por incorporar |
| Grupo comercial y derechos de acceso | Por incorporar |
| Pruebas de los permisos | Por incorporar |
| Presupuesto S00025 | Por incorporar |
| Confirmación de pedido S00025 | Por incorporar |
| Entrega de productos | Por incorporar |
| Factura INV/2026/00010 y pago | Por incorporar |

## Archivos y dónde encontrar cada parte

He organizado el repositorio por temas. El README sirve para entrar en el trabajo y localizar los documentos sin tener que recorrer todas las carpetas.

| Archivo | Información que contiene |
| --- | --- |
| [`empresa/logo.png`](empresa/logo.png) | Identidad gráfica utilizada por la empresa. |
| [`empresa/ficha-empresa.md`](empresa/ficha-empresa.md) | Datos ficticios, sector, actividad, colores, catálogo, clientes y almacén. |
| [`instalacion/instalacion-odoo.pdf`](instalacion/instalacion-odoo.pdf) | Resumen visual de la instalación y puesta en marcha, en dos páginas. |
| [`instalacion/errores-instalacion.md`](instalacion/errores-instalacion.md) | Error real de arranque de Docker, causa, solución y referencias utilizadas. |
| [`usuarios/usuarios-grupos-permisos.md`](usuarios/usuarios-grupos-permisos.md) | Puestos, tipos de usuario, permisos por aplicación, grupo personalizado y pruebas de acceso. |
| [`venta/proceso-venta.md`](venta/proceso-venta.md) | Seguimiento del presupuesto hasta el pago, con las referencias y el usuario de cada paso. |
| [`venta/presupuesto.pdf`](venta/presupuesto.pdf) | Copia del presupuesto de la venta, impresa desde Odoo. |
| [`venta/factura.pdf`](venta/factura.pdf) | Factura definitiva, impresa desde Odoo. |

La carpeta `capturas/` puede utilizarse como apoyo si hace falta enseñar una pantalla que no se aprecia bien en el vídeo. Las imágenes tienen que proceder de la instalación real. No he incluido contraseñas ni datos de clientes reales.

## La empresa que he configurado

Elegí el nombre **LOTO ROSA** para relacionarlo con una estética delicada y con un catálogo de productos de cuidado personal, relajación y artículos para parejas. No quería utilizar una compañía genérica de las que aparecen al abrir Odoo, así que preparé un nombre, un logotipo, tonos rosa y datos comerciales ficticios que se mantienen en los informes. El color principal es un rosa frambuesa y el secundario un rosa suave. También configuré el eslogan "Bienestar y cuidado personal" y el pie "Loto Rosa, Empresa ficticia de práctica, Sin validez comercial".

La empresa figura en Sevilla, trabaja en euros y tiene un NIF de ejemplo, correo y página web propios. El catálogo incluye cuatro productos distintos, cada uno con foto, precio de venta, coste e IVA del 21 %. La vela aromática **Calma Rosa** tiene control de existencias en `LR/Stock`. Registré 50 unidades antes de la operación que aparece en la venta. Los clientes que preparé fueron **Claudia Romero Vega**, como particular, y **Flor de Seda Eventos, S.L.**, como empresa. De esta manera podía diferenciar ambos tipos de contacto sin utilizar datos de personas reales.

Los precios y las referencias de los cuatro productos se encuentran en la [ficha de empresa](empresa/ficha-empresa.md), donde también se explica cómo encajan en la idea de negocio y qué información se introdujo en Odoo.

## Instalación de Odoo

Estoy utilizando **Odoo 19 Community** con la versión observada `19.0-20260926`. La aplicación funciona en Windows mediante **Docker Desktop**, con dos contenedores separados: `odoo-web` ejecuta Odoo y `odoo-db` guarda los datos en PostgreSQL 16. Accedo desde [http://localhost:8069](http://localhost:8069) a la base llamada `db`.

La instalación y la base de datos ya estaban preparadas cuando retomé el trabajo. Por eso no presento una instalación desde cero como si la hubiese realizado. Lo que hice fue poner en marcha Docker, arrancar los contenedores que ya existían, comprobar el puerto y entrar en Odoo. Durante esa puesta en marcha apareció un error porque Docker Desktop no estaba iniciado. Lo documenté con el mensaje exacto, la causa que pude comprobar, el comando utilizado y las fuentes que consulté.

El proceso está resumido en las [diapositivas de instalación](instalacion/instalacion-odoo.pdf) y desarrollado en [errores e incidencias](instalacion/errores-instalacion.md). Para gestionar LOTO ROSA utilicé las aplicaciones de **Ventas, Facturación, Inventario y Contactos**, además de Ajustes para los usuarios y las compañías.

## Cómo he repartido el trabajo entre los usuarios

No he dejado las operaciones de venta a cargo de la administradora. Preparé tres usuarios internos con permisos diferentes y elegí cada nivel según lo que necesitaban hacer:

| Usuario | Puesto | Qué necesita hacer | Qué no le corresponde |
| --- | --- | --- | --- |
| **Marta González González - Comercial** | Comercial | Crear presupuestos y trabajar con sus documentos de venta. | Administrar las ventas de otros empleados o entrar en Contabilidad. |
| **Laura Moreno Salas** | Responsable de Ventas | Revisar presupuestos de todos los comerciales, confirmar pedidos y gestionar entregas. | Llevar la facturación contable. |
| **Elena Ruiz Navarro** | Administración y Facturación | Revisar, publicar y cobrar facturas. | Administrar el departamento de Ventas o modificar el inventario. |

Para el puesto comercial configuré el grupo **LOTO ROSA / Comercial junior**. Hereda el acceso de usuario de Ventas con documentos propios e incluye derechos sobre los modelos `sale.order` y `sale.order.line`. En las dos filas configuré lectura, escritura y creación, sin conceder eliminación desde ese grupo. También tuve en cuenta que en Odoo los permisos se acumulan entre grupos, de modo que la prueba de una restricción no se puede dar por válida solo porque una casilla esté desmarcada.

Los correos de acceso, los grupos, las casillas **L/E/C/B** y las comprobaciones están recogidos en [usuarios, grupos y permisos](usuarios/usuarios-grupos-permisos.md). He distinguido además el usuario interno del portal y del público para no confundir a un empleado con un cliente que solo consulta documentos.

## La venta de Flor de Seda Eventos

Para comprobar que todo estaba relacionado entre sí utilicé el cliente ficticio **Flor de Seda Eventos, S.L.** La comercial preparó el presupuesto **`S00025`** con tres productos: dos velas Calma Rosa, un aceite Pétalo Suave y un antifaz Susurro Rosa. El aceite lleva un descuento del **10 %** aplicado solo a su línea, no un cambio permanente del precio del catálogo. Se utilizaron condiciones de pago a **30 días** y la lista de precios de LOTO ROSA en euros.

| Concepto | Importe |
| --- | ---: |
| Dos velas Calma Rosa | 39,80 € |
| Un aceite Pétalo Suave, con el 10 % de descuento | 15,21 € |
| Un antifaz Susurro Rosa | 14,90 € |
| Base imponible | **69,91 €** |
| IVA del 21 % | **14,68 €** |
| **Total** | **84,59 €** |

El presupuesto se confirmó como pedido **`S00025`** desde el usuario de Laura. En el pedido quedaron registradas las cantidades entregadas y facturadas. La factura vinculada tiene el número **`INV/2026/00010`** y el pago realizado por Elena es **`PBNK1/2026/00001`**, de **84,59 €**, con fecha **12 de noviembre de 2026**. En Odoo el pago figura en estado **Pagado**.

El recorrido de los documentos, las decisiones de cada puesto y lo que todavía hay que comprobar aparecen en [proceso de venta](venta/proceso-venta.md). Ahí he separado las operaciones verificadas de las que necesitan leer la referencia exacta del albarán o mirar un dato del PDF original. No tiene sentido inventar esos números porque son precisamente los que permiten relacionar el pedido con la entrega y la factura.

## Documentos y referencias principales

| Documento | Referencia |
| --- | --- |
| Presupuesto / pedido confirmado | `S00025` |
| Entrega | Número aún por consultar en el albarán asociado a `S00025` |
| Factura | `INV/2026/00010` |
| Pago | `PBNK1/2026/00001` |

El [presupuesto](venta/presupuesto.pdf) y la [factura](venta/factura.pdf) corresponden a la documentación original exportada desde Odoo. Los enlaces estarán disponibles cuando ambos PDF se incorporen a la carpeta `venta`.

## Cómo he mantenido el historial de Git

He separado los archivos por temas para poder modificar la instalación, la empresa, los usuarios y la venta de manera independiente. El primero conserva el mensaje exigido, `chore: estructura inicial UD7 Odoo`, y hay commits posteriores para las diapositivas y para el error real de Docker. La documentación restante se incorpora por bloques, manteniendo los mensajes convencionales y sin reescribir el historial.

El historial se puede consultar directamente en [Commits](https://github.com/mgg06/sge-ud7-odoo/commits/main).
