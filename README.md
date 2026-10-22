# app-para-tiendas

Repositorio de Shameless Company para el desarrollo de software ligero de punto de venta (POS), facturacion e inventario disenado para tiendas de barrio, minimercados y pequenos comercios locales.

## Objetivo del repositorio
Construir una aplicacion de escritorio y web simple, rapida y sin complicaciones tecnicas para comerciantes que no quieren pagar suscripciones mensuales abusivas de software en la nube ni lidiar con sistemas complejos. El software debe funcionar 100% de forma local sin depender de conexion a internet, almacenar los datos en una base de datos SQLite segura dentro del mismo computador y permitir cobrar en segundos mediante teclado, lector de codigo de barras y codigos QR de Nequi o Bancolombia.

Se monetiza mediante venta de licencia de pago unico (por ejemplo $30 a $50 USD en Payhip o transferencia bancaria directa), instalacion fisica y soporte en negocios locales, y personalizaciones bajo demanda.

---

## Modulos e ideas de proyectos con requisitos de MVP

### 1. Punto de venta rapido para mostrador (Caja registradora)
- Que es: Pantalla principal de cobro optimizada para despachar rapido a los clientes en mostrador usando solo el teclado o un lector de codigo de barras USB economico.
- Como genera dinero: Es el modulo principal de venta del software a tenderos y comerciantes locales.
- Requisitos de MVP:
  1. Pantalla de cobro limpia desarrollada en Electron, Tauri o Python (Flet/CustomTkinter) que abra en menos de 2 segundos.
  2. Busqueda instantanea de productos por nombre o lectura de codigo de barras USB.
  3. Calculadora de vueltas automatica: el tendero ingresa con cuanto paga el cliente y el sistema muestra en numeros grandes el cambio a devolver.
  4. Soporte para imprimir recibo en impresoras termicas POS (58mm o 80mm) mediante comandos ESC/POS y opcion de enviar recibo digital en PDF.
  5. Ventana emergente con el codigo QR de Nequi y Bancolombia del negocio para que el cliente pague desde su celular sin friccion.

### 2. Control de inventario y alertas de stock minimo
- Que es: Modulo de gestion de productos donde el comerciante registra compras a proveedores, costo, precio de venta al publico y cantidad disponible.
- Como genera dinero: Evita que el tendero pierda dinero por mercancia vencida o desabastecimiento, justificando el valor de compra del software.
- Requisitos de MVP:
  1. Tabla de inventario con filtros por categoria (granos, lacteos, aseo, bebidas, etc.).
  2. Campo de stock minimo: el sistema resalta en rojo los productos con pocas existencias y genera una lista de compras para el proveedor en un solo clic.
  3. Importacion y exportacion masiva de productos desde archivos Excel (.xlsx) o CSV para no tener que registrar todo a mano.
  4. Registro de historial de movimientos: quien modifico el stock y por que motivo (venta, merma, devolucion o ingreso).

### 3. Cierre de caja y reporte de ganancias del dia
- Que es: Panel de control que resume cuanto dinero entro en efectivo, cuanto por transferencias digitales (Nequi/Bancolombia) y cual fue la ganancia real del negocio restando los costos de compra.
- Como genera dinero: Le da claridad financiera al dueno del negocio al final del dia sin que tenga que hacer cuentas en papel.
- Requisitos de MVP:
  1. Boton de cierre de caja diario que compara el dinero esperado con el dinero contado en la gaveta.
  2. Grafica y resumen simple: total vendido, ganancia bruta estimada y producto mas vendido de la jornada.
  3. Exportacion del reporte diario en formato PDF o envio automatico por correo/WhatsApp al dueno al momento de cerrar turno.

### 4. Base de datos local y respaldo automatico anti-perdida
- Que es: Motor de datos basado en SQLite que no requiere instalar motores pesados como MySQL o PostgreSQL ni configurar servidores.
- Como genera dinero: Ofrece confiabilidad total al cliente; sus datos nunca se borran ni se filtran a terceros.
- Requisitos de MVP:
  1. Base de datos SQLite contenida en un unico archivo facil de mover o respaldar.
  2. Modulo de respaldo automatico que al cerrar el programa haga una copia con fecha y hora en una carpeta secundaria o memoria USB conectada.
  3. Script de restauracion rapida en caso de que el computador del cliente sufra fallas o se cambie de maquina.

### 5. Catalogo digital para pedidos por WhatsApp
- Que es: Generador de pagina web estatica ultraligera que toma el inventario de la tienda y crea un menu interactivo para que los vecinos del barrio puedan ver que hay disponible y armar su pedido para enviarlo directo al WhatsApp de la tienda.
- Como genera dinero: Se vende como un modulo adicional o servicio de pago recurrente ($5 a $10 USD/mes) alojado en Cloudflare Pages gratis.
- Requisitos de MVP:
  1. Script que tome los productos con fotos y precios de la base de datos y genere un catalogo estatico en HTML/Tailwind.
  2. Boton en cada producto para agregar a una canasta de compras.
  3. Boton final "Enviar pedido por WhatsApp" que arme un mensaje de texto formateado con la lista de productos, total a pagar y direccion de entrega del cliente.
