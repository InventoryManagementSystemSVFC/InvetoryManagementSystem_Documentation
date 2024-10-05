### A. INTRODUCTION

Manually managing inventory is prone to human error, such as miscounts or misplaced records, leading to inaccuracies that can disrupt operations. The Inventory Management System is a critical tool used by businesses of all sizes to manage and control their inventory levels, orders, sales, and deliveries. The primary purpose of an Inventory Management System is to ensure that a business has the right amount of stock at the right time to meet customer demand without overstocking or under stocking. In today’s fast-paced and competitive business environment, an effective Inventory Management System is essential for managing resources efficiently and achieving long-term business success. With real-time data and analytics, owners and managers can make informed decisions about purchasing, sales strategies, and inventory management, leading to better overall business performance. 

An inventory management system's overall goal is to make inventory management more effective, economical, and customer-focused, which will increase a company's profitability and competitiveness. The system standardizes and simplifies inventory management processes, making it easier for staff to perform their duties with fewer errors and less confusion. Sales and customer service teams can quickly check inventory levels and provide accurate information to customers, ensuring that orders are fulfilled promptly and correctly. With comprehensive reports and analytics, businesses can identify patterns, forecast demand, and plan for seasonal fluctuations or market changes.



### B. Project Features and Characteristics

The proposed project Inventory Management System consist of the following features: 
1.	Product Management – add, update, delete products, manage product category – admin or owner
2.	Order Management – create, update, delete purchase orders, track order status – admin or owner
3.	User Management – assign roles with specific access levels.
4.	Reporting and Analytics - Generation of detailed reports on inventory levels.

### C. Project Scope

The scope of this project includes the design, development, and implementation of an Inventory Management System tailored to meet the needs of small to medium-sized businesses. The system will cover the following areas:

1. Order Management:
- Automation of purchase orders, sales orders, and order fulfillment processes.
- Integration of order processing with inventory updates to ensure accurate stock levels.

2. Reporting and Analytics:
- Generation of detailed reports on inventory levels, sales trends, and supplier performance.
- Tools for demand forecasting and trend analysis to support decision-making.

3. User Management:
- Role-based access control, allowing different levels of system access based on user roles (e.g., Admin, Inventory Manager, Sales Staff).
- Customizable dashboards and user interfaces tailored to specific roles.


### D. Work Breakdown Structure


![DiagramSIA2](https://github.com/user-attachments/assets/9a5539e5-9dcf-49a5-b4e0-52eb0fc2cf32)




### E. Functional Requirements

1. User Requirements

| USER ROLES AND PERMISSION | |
|------------|---------------|
| ADMIN    |Can access and manage all aspects of the system, including user management, inventory settings, and system configurations.  | 
|          |Can generate and view all reports and analytics.  | 
| INVENTORY MANAGER  | Can add, update, and delete inventory items.        | 
|                    | Can manage purchase orders and suppliers.       |
|                    | Can generate inventory reports and monitor stocklevels.       |
| SALES STAFFS| Can view available inventory levels.  |
|             | Can place sales orders and check order status.   |
|             | Can access customer information and order history.)  |
| SUPPLIER | Can access purchase orders sent by the Inventory Manager.  |
|          | Can update order statuses and provide estimated delivery times. |
|          | Can communicate with the Inventory Manager regarding stockavailability and order fulfillment. |


2. Use case
 
![image](https://github.com/user-attachments/assets/ac9b919b-3d91-4959-82c8-aa698022165a)




### F. DATA ARCHITECTURE
**A. Data Dictionary**

**Table 1: Product_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| Prod_Id    | Integer(INT)  | Unique Identification of Product.   | Primary Key,Auto Increment.
| Prod_Name  | Varchar       | Name of brand of the product. | Not Null, Max Length 50
| Category_Id| Integer(INT)  | Foreign Key From category table.    | Foreign Key to Category_tbl.Category_Id


**Table 2: User_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| User_Id    | Integer(INT)  | Unique Identification of User. | Primary Key, Auto Increment |
| User_Name  | Varchar       | Name of brand of the User. | Not Null, Max Length 50 |
| User_Email | Varchar  | Email of the User | Not Null|
| User_Passwod| Varchar | Password of the User | Not Null|
| User_Role | Varchar | Defines the role or access level of the User. | Not Null, Default 'user' |


**Table 3: Order_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| Order_Id    | Integer(INT)  | Unique Identification of Orders. | Primary Key, Auto Increment |
| Order_Date  | Date       | Date of order. | Not Null |
| Status | Varchar  | Status of the order (pending, cancelled, etc.). | Not Null, Default 'pending'|


**Table 4: Catergory_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| Category_Id    | Integer(INT)  | Unique Identification of Categories. | Primary Key, Auto Increment |
| Category_Name  | Varchar       | Name of the Category. | Not Null |

**Table 5: Sales_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| Sales_Id    | Integer(INT)  | Unique Identification of Sale. | Primary Key, Auto Increment |
| Order_Id  | Integer(INT)       | Foreign key from Order_tbl. | Foreign key to User_tbl.Order_Id |
| User_Id | Integer(INT)  | Foreign key from User_tbl | Foreign key to User_tbl.User_Id |
| Sale_Amount| Integer(INT) | The total monetary value of the sale transaction. | Not Null|
| Sale_Date | Date | The date when the sale transaction was completed. | Not Null |



**Table 6: Order_history_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| History_Id    | Integer(INT)  | Unique Identification of Order log. | Primary Key, Auto Increment |
| Order_Id  | Integer(INT)       | Foreign key from Order_tbl. | Foreign key to Order_tbl.Order_Id |
| Status | Varchar  | Order history status (delivered, canceled). | Not Null |
| Update_Date| Date | The date when the order's history was last updated or modified. | Not Null |




**Table 7: Delivery_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| Delivery_Id    | Integer(INT)  | Unique Identification of Delivery. | Primary Key, Auto Increment |
| Order_Id  | Integer(INT)       | Foreign key to Order_tbl. | Foreign key to Order_tbl.Order_Id,Not Null |
| Delivery_Date | Date  | Date of Delivery. | Not Null |


**Table 8: Sold_Item_tbl**
| Field Type | Data Type     | Description | Constraints |
|------------|---------------|-------------|-------------|
| ItemSold_Id    | Integer(INT)  | Unique Identification of Sold Items. | Primary Key, Auto Increment |
| Sale_Id  | Integer(INT)       | Foreign key to Sale_tbl. | Foreign key to Sale_tbl.Sale_Id, Not Null |
| Prod_Id | Integer(INT)  | Foreign key to Product_tbl. | Foreign key to Product_tbl.Product_Id, Not Null |
| Quantity | Integer(INT) | Quantity of each item sold. | Not Null |





**B. ERD**

![INVENTORY ERD](https://github.com/user-attachments/assets/52243da4-0211-4b0c-a4e8-e88247f30a6e)

**LUCID CHART LINK**
https://lucid.app/lucidchart/9f23ffdb-a867-4eaf-bebf-14281c6544ba/edit?viewport_loc=-2630%2C-970%2C2560%2C1184%2C0_0&invitationId=inv_77480624-94f3-4686-aac6-35a6fb594bb1

