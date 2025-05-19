Question 1
-- Total payment amount for each payment date, sorted by latest, top 5 only
SELECT 
    paymentDate, 
    SUM(amount) AS totalAmount
FROM 
    payments
GROUP BY 
    paymentDate
ORDER BY 
    paymentDate DESC
LIMIT 5;

-- Question 2
-- Average credit limit grouped by customer name and country
SELECT 
    customerName, 
    country, 
    AVG(creditLimit) AS averageCreditLimit
FROM 
    customers
GROUP BY 
    customerName, country;

-- Question 3
-- Total price for each product and quantity ordered
SELECT 
    productCode, 
    quantityOrdered, 
    quantityOrdered * priceEach AS totalPrice
FROM 
    orderdetails
GROUP BY 
    productCode, quantityOrdered, priceEach;

-- Question 4
-- Highest payment amount for each check number
SELECT 
    checkNumber, 
    MAX(amount) AS highestAmount
FROM 
    payments
GROUP BY 
    checkNumber;
