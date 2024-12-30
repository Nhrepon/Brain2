## Store procedure
```sql
CREATE DATABASE [ProductManagementSystem_DB];

CREATE TABLE [dbo].[Products](
 [Id] [int] IDENTITY(1,1) NOT NULL,
 [ProductName] [nvarchar](255) NOT NULL,
 [Address] [nvarchar](255) NULL,
 [Country] [nvarchar](255) NOT NULL,
 [State] [nvarchar](255) NOT NULL,
 [City] [nvarchar](255) NOT NULL,
 [ProductionDocument] [nvarchar](255) NULL,
 [CraetedOn] [datetime] NULL);

CREATE PROCEDURE [dbo].[sp_DeleteProduct]
    @Id INT
AS
BEGIN
    DELETE FROM Products
    WHERE Id = @Id;
END;

CREATE PROCEDURE [dbo].[sp_GetAllProducts]
AS
BEGIN
    SELECT * FROM Products;
END;

CREATE PROCEDURE [dbo].[sp_GetProductById]
    @Id INT
AS
BEGIN
    SELECT * FROM Products
    WHERE Id = @Id;
END;

CREATE PROCEDURE [dbo].[sp_InsertProduct]
    @ProductName NVARCHAR(255),
    @Address NVARCHAR(255) = NULL,
    @Country NVARCHAR(255),
    @State NVARCHAR(255),
    @City NVARCHAR(255),
    @ProductionDocument NVARCHAR(255) = NULL
AS
BEGIN
    -- Check for duplicate ProductName
    IF EXISTS (SELECT 1 FROM Products WHERE ProductName = @ProductName)
    BEGIN
        PRINT 'Duplicate ProductName exists';
        RETURN;
    END

    INSERT INTO Products (ProductName, Address, Country, State, City, ProductionDocument)
    VALUES (@ProductName, @Address, @Country, @State, @City, @ProductionDocument);
    
    SELECT SCOPE_IDENTITY() AS NewProductId;
END;

CREATE PROCEDURE [dbo].[sp_UpdateProduct]
    @Id INT,
    @ProductName NVARCHAR(255),
    @Address NVARCHAR(255) = NULL,
    @Country NVARCHAR(255),
    @State NVARCHAR(255),
    @City NVARCHAR(255),
    @ProductionDocument NVARCHAR(255) = NULL
AS
BEGIN
    -- Check for duplicate ProductName excluding the current record
    IF EXISTS (SELECT 1 FROM Products WHERE ProductName = @ProductName AND Id != @Id)
    BEGIN
        PRINT 'Duplicate ProductName exists';
        RETURN;
    END

    UPDATE Products
    SET ProductName = @ProductName,
        Address = @Address,
        Country = @Country,
        State = @State,
        City = @City,
        ProductionDocument = @ProductionDocument,
        CraetedOn = GETDATE()
    WHERE Id = @Id;
END;


```