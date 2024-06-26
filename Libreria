-- Creación de la base de datos
CREATE DATABASE Libreria;

-- Uso de la base de datos
USE Libreria;

-- Tabla de Autores
CREATE TABLE Autores (
    AutorID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    FechaNacimiento DATE,
    Nacionalidad VARCHAR(50)
);

-- Tabla de Categorías
CREATE TABLE Categorias (
    CategoriaID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL
);

-- Tabla de Editoriales
CREATE TABLE Editoriales (
    EditorialID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Direccion VARCHAR(255),
    Telefono VARCHAR(15),
    Email VARCHAR(100)
);

-- Tabla de Libros
CREATE TABLE Libros (
    LibroID INT PRIMARY KEY AUTO_INCREMENT,
    Titulo VARCHAR(200) NOT NULL,
    AutorID INT,
    CategoriaID INT,
    EditorialID INT,
    FechaPublicacion DATE,
    Precio DECIMAL(10, 2),
    Stock INT,
    FOREIGN KEY (AutorID) REFERENCES Autores(AutorID),
    FOREIGN KEY (CategoriaID) REFERENCES Categorias(CategoriaID),
    FOREIGN KEY (EditorialID) REFERENCES Editoriales(EditorialID)
);

-- Tabla de Clientes
CREATE TABLE Clientes (
    ClienteID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Email VARCHAR(100),
    Telefono VARCHAR(15),
    Direccion VARCHAR(255)
);

-- Tabla de Ventas
CREATE TABLE Ventas (
    VentaID INT PRIMARY KEY AUTO_INCREMENT,
    ClienteID INT,
    FechaVenta DATE NOT NULL,
    Total DECIMAL(10, 2),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID)
);

-- Tabla de Detalles de Ventas
CREATE TABLE DetallesVentas (
    DetalleID INT PRIMARY KEY AUTO_INCREMENT,
    VentaID INT,
    LibroID INT,
    Cantidad INT NOT NULL,
    PrecioUnitario DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (VentaID) REFERENCES Ventas(VentaID),
    FOREIGN KEY (LibroID) REFERENCES Libros(LibroID)
);

-- Tabla de Proveedores
CREATE TABLE Proveedores (
    ProveedorID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Telefono VARCHAR(15),
    Email VARCHAR(100),
    Direccion VARCHAR(255)
);

-- Tabla de Compras
CREATE TABLE Compras (
    CompraID INT PRIMARY KEY AUTO_INCREMENT,
    ProveedorID INT,
    FechaCompra DATE NOT NULL,
    Total DECIMAL(10, 2),
    FOREIGN KEY (ProveedorID) REFERENCES Proveedores(ProveedorID)
);

-- Tabla de Detalles de Compras
CREATE TABLE DetallesCompras (
    DetalleID INT PRIMARY KEY AUTO_INCREMENT,
    CompraID INT,
    LibroID INT,
    Cantidad INT NOT NULL,
    PrecioUnitario DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (CompraID) REFERENCES Compras(CompraID),
    FOREIGN KEY (LibroID) REFERENCES Libros(LibroID)
);

-- Tabla de Empleados
CREATE TABLE Empleados (
    EmpleadoID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Telefono VARCHAR(15),
    Email VARCHAR(100),
    Direccion VARCHAR(255),
    FechaContratacion DATE
);

-- Tabla de Sucursales
CREATE TABLE Sucursales (
    SucursalID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Direccion VARCHAR(255),
    Telefono VARCHAR(15)
);

-- Tabla de Inventarios
CREATE TABLE Inventarios (
    InventarioID INT PRIMARY KEY AUTO_INCREMENT,
    SucursalID INT,
    LibroID INT,
    Cantidad INT NOT NULL,
    FOREIGN KEY (SucursalID) REFERENCES Sucursales(SucursalID),
    FOREIGN KEY (LibroID) REFERENCES Libros(LibroID)
);

-- Tabla de Roles
CREATE TABLE Roles (
    RolID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL
);

-- Tabla de EmpleadosRoles
CREATE TABLE EmpleadosRoles (
    EmpleadoID INT,
    RolID INT,
    PRIMARY KEY (EmpleadoID, RolID),
    FOREIGN KEY (EmpleadoID) REFERENCES Empleados(EmpleadoID),
    FOREIGN KEY (RolID) REFERENCES Roles(RolID)
);
