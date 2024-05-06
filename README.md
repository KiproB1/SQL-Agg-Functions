# SQL-Agg-Functions
CREATE DATABASE MyStore;

USE MyStore;

CREATE TABLE Orders (
  OrderID INT PRIMARY KEY,
  ProductID INT NOT NULL,
  Quantity INT NOT NULL,
  Price DECIMAL(10,2) NOT NULL
);
INSERT INTO Orders (ProductID, Quantity, Price)
VALUES (101, 2, 12.50),
       (102, 1, 35.00),
       (101, 3, 12.50),
       (103, 1, 20.00),
       (102, 2, 35.00),
       (104, 4, 10.00);
SELECT SUM(Quantity) AS TotalQuantitySold
FROM Orders;
SELECT AVG(Price) AS AveragePrice
FROM Orders;
SELECT ProductID, Price
FROM Orders
WHERE Price = (SELECT MAX(Price) FROM Orders);
