# bda-modulo-1-evaluacion-final-maria99ariza

# TiendaOnline

`TiendaOnline` es una clase que permite la gestión de un sistema de inventario y ventas para una tienda en línea. Esta clase proporciona las funcionalidades necesarias para gestionar productos, clientes y ventas de manera eficiente.

## Características

### Atributos

1. **`inventario` (lista de diccionarios)**: Almacena los productos disponibles en la tienda. Cada producto es representado por un diccionario con las claves `'nombre'`, `'precio'`, y `'cantidad'`. Inicialmente es una lista vacía.
   
   - Ejemplo de un inventario:
     ```python
     [{'nombre': 'Camisa', 'precio': 20, 'cantidad': 40},
     {'nombre': 'Pantalón', 'precio': 30, 'cantidad': 30}]
     ```

2. **`clientes` (diccionario)**: Registra a los clientes de la tienda, cada cliente tiene su `'nombre'`, `'email'` y un historial de compras. Inicialmente es un diccionario vacío.
   
   - Ejemplo de registro de clientes:
     ```python
     {'Cliente1': {'email': 'cliente1@email.com', 'compras': []},
     'Cliente2': {'email': 'cliente2@email.com', 'compras': []}}
     ```

3. **`ventas_totales` (float)**: Lleva un registro de las ventas totales realizadas por la tienda. Inicialmente es 0.

---

### Métodos

1. **`agregar_producto(self, nombre, precio, cantidad)`**:
   - Agrega un producto al inventario o actualiza su cantidad si ya existe.
   - Parámetros: `nombre` (str), `precio` (float), `cantidad` (int).

2. **`ver_inventario(self)`**:
   - Muestra los detalles de los productos en el inventario (nombre, precio y cantidad).
   - Ejemplo de salida:
     ```
     Nombre: Camisa, Precio: 20€, Cantidad: 50
     Nombre: Pantalón, Precio: 30€, Cantidad: 30
     ```

3. **`buscar_producto(self, nombre)`**:
   - Busca un producto por su nombre y muestra sus detalles.
   - Parámetros: `nombre` (str).
   - Ejemplo de salida:
     ```
     Nombre: Camisa, Precio: 20€, Cantidad: 40
     ```

4. **`actualizar_stock(self, nombre, cantidad)`**:
   - Actualiza la cantidad de un producto en el inventario.
   - Parámetros: `nombre` (str), `cantidad` (int).
   - Si el producto no existe, muestra un mensaje.

5. **`eliminar_producto(self, nombre)`**:
   - Elimina un producto del inventario.
   - Parámetros: `nombre` (str).
   - Si el producto no existe, muestra un mensaje.

6. **`calcular_valor_inventario(self)`**:
   - Calcula y devuelve el valor total del inventario.
   - Ejemplo:
     ```python
     valor_total = (precio_camisas * cantidad_camisas) + (precio_calcetines * cantidad_calcetines)
     ```

7. **`realizar_compra(self)`**:
   - Permite a un cliente seleccionar productos del inventario, agregarlos a su carrito y calcular el costo total de la compra.

8. **`procesar_pago(self)`**:
   - Procesa el pago de una compra, calcula el cambio, y maneja errores en caso de pago insuficiente.
   - Utiliza `try...except` para el manejo de excepciones.

9. **`agregar_cliente(self, nombre, email)`**:
   - Agrega un nuevo cliente al registro.
   - Parámetros: `nombre` (str), `email` (str).

10. **`ver_clientes(self)`**:
    - Muestra la lista de clientes registrados con sus nombres y correos electrónicos.

---

## Ejemplo de Uso

```python
# Crear una instancia de la tienda
la_tienda = TiendaOnline()

# Agregar productos
la_tienda.agregar_producto('Camisa', 20, 40)
la_tienda.agregar_producto('Pantalón', 30, 30)

# Ver inventario
la_tienda.ver_inventario()

# Buscar un producto
la_tienda.buscar_producto('Camisa')

# Actualizar stock
la_tienda.actualizar_stock('Camisa', 10)

# Eliminar un producto
la_tienda.eliminar_producto('Pantalón')

# Calcular el valor total del inventario
la_tienda.calcular_valor_inventario()

# Realizar una compra
la_tienda.realizar_compra()

# Procesar el pago
la_tienda.procesar_pago()

# Agregar un cliente
la_tienda.agregar_cliente('Marta Gómez', 'marta@email.com')

# Ver lista de clientes
la_tienda.ver_clientes()
