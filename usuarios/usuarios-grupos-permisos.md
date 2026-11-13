# USUARIOS, GRUPOS Y PERMISOS DE LOTO ROSA

## PLANTILLA DE USUARIOS Y PERMISOS

| Empleada | Puesto | Correo de inicio de sesión | Tipo | Ventas | Contabilidad | Inventario |
| --- | --- | --- | --- | --- | --- | --- |
| Marta González González - Comercial | Comercial | `marta.comercial@example.com` | Interno | Usuario: solo mostrar documentos propios | No | No |
| Laura Moreno Salas | Responsable de Ventas | `laura.ventas@example.com` | Interno | Administrador | No | Usuario |
| Elena Ruiz Navarro | Administración y Facturación | `elena.facturacion@example.com` | Interno | No | Facturación | No |

Las tres cuentas tienen nombre, correo de acceso, avatar y LOTO ROSA como compañía. En sus fichas aparece el rol general Usuario, no el rol de administrador del sistema. Los correos son ficticios y sirven para identificar las sesiones sin publicar contraseñas

### OTROS PRIVILEGIOS DE LOS PERFILES

| Apartado de Odoo | Marta Comercial | Laura Ventas | Elena Facturación |
| --- | --- | --- | --- |
| Compañías permitidas | LOTO ROSA | LOTO ROSA | LOTO ROSA |
| Compañía predeterminada | LOTO ROSA | LOTO ROSA | LOTO ROSA |
| Productos | View | View | View |
| Contacto | No | No | No |
| Exportar | No | No | No |
| Banco | No | No | No |
| Administración del sistema | No | No | No |

La tabla recoge los permisos que aparecen en la ficha de cada usuario

## POR QUÉ PUSE ESOS PERMISOS

Para hacer el presupuesto con mi cuenta me bastaba con ver mis documentos de Ventas. Laura sí tenía que abrir un presupuesto de otra persona para confirmarlo. También tenía que entrar en Inventario para sacar el pedido del almacén. A Elena le dejé Facturación porque era quien iba a revisar la factura y apuntar el cobro

Para el grupo Comercial junior marqué lectura, escritura y creación porque desde la cuenta comercial tengo que abrir mis pedidos, corregir sus líneas y preparar otros. Dejé el borrado sin marcar en los dos modelos porque para hacer el presupuesto no necesitaba eliminar pedidos ni líneas desde ese grupo

## TIPOS DE USUARIO DE ODOO

He tenido en cuenta tres tipos de acceso, porque una persona que trabaja dentro de LOTO ROSA no debe tener el mismo papel que un cliente que consulta sus documentos desde fuera

Usuario interno. Es una persona que inicia sesión para trabajar con las aplicaciones de Odoo. Sus menús dependen de los grupos y privilegios que le haya concedido la administración. Marta, Laura y Elena pertenecen a este tipo. Lo que diferencia sus cuentas no es que una tenga más importancia que otra, sino la función que deben desarrollar

Usuario portal. Claudia Romero Vega figura como usuaria de tipo Portal. Desde esa zona puede consultar los documentos que tenga habilitados

Usuario público. Es quien entra en la web sin iniciar sesión

## CÓMO HE CONFIGURADO EL GRUPO PERSONALIZADO

Además de los permisos que se seleccionan en las fichas, activé el modo desarrollador para trabajar con un grupo propio desde Ajustes > Usuarios y compañías > Grupos. El grupo se llama `LOTO ROSA / Comercial junior` y está pensado para los permisos que se necesitan al preparar presupuestos y sus líneas. Elegí ese nombre para que se pudiera diferenciar de los grupos generales del programa

| Configuración | Valor |
| --- | --- |
| Grupo | LOTO ROSA / Comercial junior |
| Usuario asignado confirmado | Marta González González - Comercial |
| Grupo heredado | Ventas / Usuario: solo mostrar documentos propios |
| Modelo con derecho de acceso 1 | `sale.order` |
| Modelo con derecho de acceso 2 | `sale.order.line` |
| Administración completa de Ventas | No concedida desde este grupo |

### CASILLAS DEL GRUPO

| Nombre del acceso | Modelo | L: Leer | E: Escribir | C: Crear | B: Borrar |
| --- | --- | :---: | :---: | :---: | :---: |
| LOTO ROSA - Comercial junior - Pedidos | `sale.order` | Sí | Sí | Sí | No |
| LOTO ROSA - Comercial junior - Líneas de pedido | `sale.order.line` | Sí | Sí | Sí | No |

## COMPROBACIÓN DE LOS PERFILES

En Ajustes comprobé que Marta tiene Ventas limitado a documentos propios, Laura tiene Ventas como administradora e Inventario como usuaria y Elena tiene Facturación. Marta y Laura tienen Contabilidad en "No". Elena tiene Ventas en "No". En el vídeo aparecen las fichas de usuario

La lista del grupo `LOTO ROSA / Comercial junior` incluye a Marta Comercial y a Hugo Martín Salcedo. En las dos filas de permisos del grupo aparecen marcadas lectura, escritura y creación. La casilla de eliminación está vacía en ambas

## SEGURIDAD DE LAS CUENTAS

No he incluido contraseñas en ningún archivo del repositorio ni las he utilizado como prueba documental. Los correos de acceso son ficticios y la información que interesa para revisar los permisos es el tipo de usuario, el puesto, el grupo y los módulos que cada uno puede utilizar

En el proceso de venta, las cuentas se emplean según el trabajo de cada persona. La comercial inicia el presupuesto, Laura confirma el pedido y gestiona la entrega y Elena interviene en la fase de Facturación. Las referencias y estados de esa operación se pueden consultar en `../venta/proceso-venta.md`

## CAPTURAS DEL GRUPO

| Qué comprobé | Archivo |
| --- | --- |
| Marta y Hugo figuran en el grupo | capturas/grupo-comercial-junior-usuarios.jpg |
| El grupo hereda Ventas para documentos propios | capturas/grupo-comercial-junior-herencia.jpg |
| Lectura, escritura y creación en pedidos y líneas | capturas/grupo-comercial-junior-permisos.jpg |
