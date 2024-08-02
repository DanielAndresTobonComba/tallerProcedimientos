# tallerProcedimientos

~~~ sql

CREATE TABLE clientes (
    id VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(40),
    apellidos VARCHAR(100),
    celular DECIMAL(10,0),
    direccion VARCHAR(80),
    correo_electronico VARCHAR(70)
);

CREATE TABLE categorias (
    id_categoria INT PRIMARY KEY,
    descripcion VARCHAR(45),
    estado int
);

CREATE TABLE productos (
    id_producto INT PRIMARY KEY,
    nombre VARCHAR(45),
    id_categoria INT REFERENCES categorias(id_categoria),
    codigo_barras VARCHAR(150),
    precio_venta DECIMAL(16,2),
    cantidad_stock INT,
    estado int
);

CREATE TABLE compras (
    id_compra INT PRIMARY KEY,
    id_cliente VARCHAR(20) REFERENCES clientes(id),
    fecha timestamp,
    medio_pago CHAR(1),
    comentario VARCHAR(300),
    estado int
);

CREATE TABLE compras_productos (
    id_compra INT REFERENCES compras(id_compra),
    id_producto INT REFERENCES productos(id_producto),
    cantidad INT,
    total DECIMAL(16,2),
    estado int,
    PRIMARY KEY (id_compra, id_producto) -- Composite primary key for many-to-many relationship
);
~~~

## EJERCICIOS 

Crear un procedimiento almacenado que permita insertar un nuevo cliente en la tabla
clientes . El procedimiento debe aceptar como parámetros el ID del cliente, nombre,
apellidos, número de celular, dirección y correo electrónico.

~~~ sql
~~~

Crear un procedimiento almacenado que permita actualizar la información de un cliente
existente en la tabla clientes . El procedimiento debe aceptar como parámetros el ID del
cliente, nombre, apellidos, número de celular, dirección y correo electrónico.
~~~ sql
~~~


Crear un procedimiento almacenado que permita eliminar un cliente de la tabla clientes . El
procedimiento debe aceptar como parámetro el ID del cliente.
~~~ sql
~~~

Crear un procedimiento almacenado que permita insertar una nueva compra en la tabla
compras . El procedimiento debe aceptar como parámetros el ID del cliente, fecha de la
compra, medio de pago, comentario y estado de la compra.
~~~ sql
~~~

Crear un procedimiento almacenado que permita insertar un producto en una compra
existente en la tabla compras_productos . El procedimiento debe aceptar como parámetros
el ID de la compra, ID del producto, cantidad, total y estado del producto en la compra.
~~~ sql
~~~

Crear un procedimiento almacenado que permita obtener la información de una compra
específica de la tabla compras . El procedimiento debe aceptar como parámetro el ID de la
compra y retornar los detalles de la compra, incluyendo el ID del cliente, fecha, medio de
pago, comentario y estado.
~~~ sql
~~~

Crear un procedimiento almacenado que permita insertar un nuevo producto en la tabla
productos . El procedimiento debe aceptar como parámetros el nombre del producto, ID de
la categoría, código de barras, precio de venta, cantidad en stock y estado del producto.
~~~ sql
~~~


Crear un procedimiento almacenado que permita actualizar la información de un producto
existente en la tabla productos . El procedimiento debe aceptar como parámetros el ID del
producto, nombre, ID de la categoría, código de barras, precio de venta, cantidad en stock y
estado del producto.
~~~ sql
~~~

Crear un procedimiento almacenado que permita obtener todos los productos de una
categoría específica en la tabla productos . El procedimiento debe aceptar como parámetro
el ID de la categoría y retornar los detalles de los productos, incluyendo el ID del producto,
nombre, precio de venta, cantidad en stock y estado.

~~~ sql
~~~
