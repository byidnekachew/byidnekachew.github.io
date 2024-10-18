# Chick-Fil-A ERD
 ```mermaid
erDiagram
 PRODUCT ||--|{ SALE: "is sold in"
 PRODUCT ||--|| INVENTORY: "is tracked in"
 CUSTOMER ||--o{ SALE: makes
 PRODUCT {
    string productid PK "Unique Product ID"
    string type  "Type of food"
    float price  "Price"
    string name  "Name of dish"
    int calories  "Number of Calories"
 }
 CUSTOMER {
    string customerid PK "Unique Customer ID"
    string name  "Customer Name"
    string email  "Email Address"
    int points  "Number of loyalty points"
 }
 SALE {
    string id PK "Sale ID"
    date date  "Sale Date"
    string customerid FK "Customer ID"
    string productid FK "Product ID"
    int quantity  "Quantity Sold"
    int pointsGiven  "Points awarded"
    string location  "Store Name"
 }
 INVENTORY {
    string productid FK "Product ID"
    int stock  "Current stock availible"
 }
 
```


# ERD Documentation
This ERD outlines the relationship between various data that Chick-Fil-A may need. They keep track of lots of data in order to ensure they have enough product and are correctly awarding loyalty points for customers. Therefore, various entities need to contain information from other entities (FK) and each order. customer, and product must be uniquely identifiable. 