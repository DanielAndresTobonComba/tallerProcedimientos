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

~~~ sql
~~~
