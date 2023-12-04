# Rakamin_Project
Final Project Virtual Internship BI Bank Muamalat

SELECT
  `plexiform-brand-405902.Rakamin_Project.Orders`.Date AS order_date,
  `plexiform-brand-405902.Rakamin_Project.ProductCategory`.CategoryName AS category_name,
  `plexiform-brand-405902.Rakamin_Project.Products`.ProdName AS product_name,
  `plexiform-brand-405902.Rakamin_Project.Products`.Price AS product_price,
  `plexiform-brand-405902.Rakamin_Project.Orders`.Quantity AS order_qty,
  (`plexiform-brand-405902.Rakamin_Project.Orders`.Quantity * `plexiform-brand-405902.Rakamin_Project.Products`.Price) AS total_sales,
  `plexiform-brand-405902.Rakamin_Project.Customers`.CustomerEmail AS cust_email,
  `plexiform-brand-405902.Rakamin_Project.Customers`.CustomerCity AS cust_city
FROM 
  `plexiform-brand-405902.Rakamin_Project.Customers`
INNER JOIN
  `plexiform-brand-405902.Rakamin_Project.Orders` ON `plexiform-brand-405902.Rakamin_Project.Customers`.CustomerID = `plexiform-brand-405902.Rakamin_Project.Orders`.CustomerID
INNER JOIN
  `plexiform-brand-405902.Rakamin_Project.Products` ON `plexiform-brand-405902.Rakamin_Project.Orders`.ProdNumber = `plexiform-brand-405902.Rakamin_Project.Products`.ProdNumber
INNER JOIN
  `plexiform-brand-405902.Rakamin_Project.ProductCategory` ON `plexiform-brand-405902.Rakamin_Project.Products`.Category = `plexiform-brand-405902.Rakamin_Project.ProductCategory`.CategoryID
ORDER BY order_date ASC;
