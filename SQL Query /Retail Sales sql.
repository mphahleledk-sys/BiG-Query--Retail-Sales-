SELECT * 
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY` LIMIT 1000;


-- QUESTION 1 WHERE Clause

SELECT * 
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
WHERE EXTRACT(YEAR FROM date) = 2023;


-- QUESTION 2 Filtering + Conditions


SELECT * FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
WHERE `Total Amount` > (SELECT AVG(`Total Amount`) 
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`);



--QUESTION 3 Calculate the total revenue (sum of Total Amount)


SELECT SUM(`Total Amount`) AS Total_Revenue
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`;



--QUESTION 4 DISTINCT PRODUCT CATERGORY

SELECT DISTINCT `Product Category`
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`;



--QUESTION 5 TOTAL QUANTITY PER PRODUCT CATERGORY

SELECT `Product Category`,
SUM(`Quantity`) AS Total_Quantity
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
GROUP BY `Product Category`;



--QUESTION 6 CLASSIFY THE AGE GROUP
SELECT `Customer ID`,
`Age`,
CASE
 WHEN `Age` < 30 THEN 'Youth'
 WHEN `Age` BETWEEN 30 AND 59 THEN 'Adult'
 ELSE 'Senior'
END AS Age_Group
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`;


--QUESTION 7 CHECK HIGHEST VALUE LOOKING AT GENDER

SELECT `Gender`,
 COUNT(*) AS High_Value_Transactions
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
WHERE `Total Amount` > 500
GROUP BY `Gender`;



--QUESTION 8 CHECKING PRODUCT CATERGORY WITH GREATER THAN 5000

SELECT `Product Category`,
SUM(`Total Amount`) AS Total_Revenue
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
GROUP BY `Product Category`
HAVING SUM(`Total Amount`) > 5000;


--QUESTION 9 UNIT COST PER PRODUCT CATERGORY

SELECT `Transaction ID`,
`Price per Unit`,
CASE
WHEN `Price per Unit` < 50 THEN 'Cheap'
WHEN `Price per Unit` BETWEEN 50 AND 200 THEN 'Moderate'
ELSE 'Expensive'
END AS Unit_Cost_Category
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`;


---Q10 checking customers above 40 plus and their spend level

SELECT `Customer ID`,
`Age`,
`Total Amount`,
CASE
 WHEN `Total Amount` > 1000 THEN 'High'
ELSE 'Low'
END AS Spending_Level
FROM `practical-3-big-query-494712.DATA.RETAIL SALE BIG  QUERY`
WHERE `Age` >= 40;
