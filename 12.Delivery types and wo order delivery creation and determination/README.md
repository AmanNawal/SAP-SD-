## Delivery types and controls



* Delivery document is divided into two parts.



1. Delivery Header
2. Delivery item



* Header data is controlled by delivery types.
* Item data is controlled by delivery item category.



***Delivery Tables***



* The tables for header data is ***LIKP***.
* The table for item data is ***LIPS***.



---



***The T code for defining delivery types is OVLK***  





* The path for defining delivery types is: ***SPRO -> Logistics execution -> Shipping -> Delivery -> Define delivery types.***  



***Delivery Types***  



* The standard delivery type is: ***LF***
* Cash sales delivery type is: ***BV***
* Return Delivery type: ***LR***
* STO delivery type is: ***NL***
* STO return delivery type is: ***NLR***
* Intercompany STO delivery type is: ***NLCC***
* Intercompany STO return delivery type is: ***NCR***
* Delivery without order reference is: ***LO***



---



***We can create a delivery wrt and order or even without referencing order.





<img width="676" height="397" alt="Image" src="https://github.com/user-attachments/assets/13dd4114-66e2-406b-84ba-ef005ea4fb0d" />



---



* You can use delivery type ***LO*** to create a delivery without referencing an order.



<img width="717" height="398" alt="Image" src="https://github.com/user-attachments/assets/b9eeaa22-5c7d-4e9e-90bc-1fc3e2e14075" />



---



## Creating delivery without sales order.





* In T code - ***OVLK*** copy the standard delivery type ***LO*** and create your own delivery type ***CSLO***.
* No create a delivery in ***VL01N***
* We can see in the snippet below that the delivery item category is **DLN**



<img width="959" height="463" alt="Image" src="https://github.com/user-attachments/assets/20a21c7a-8055-4a14-8d2d-8aa8fcc9aa1a" />



---



* Create your own item category by copying standard delivery item category ***LO*** and create a new delivery item category ***CSLO**.
* Also copy the standard delivery item category ***DLN*** in VOV7 and create a new item category ***CDLN***.
* Now check in ***OVLP*** if the item category ***CDLN*** is present or not



<img width="694" height="254" alt="Image" src="https://github.com/user-attachments/assets/2b9e1bd2-9b13-49bc-8c08-d1165fe5c4ee" />



---



* Now do delivery item determination ***T code - 0184***



<img width="646" height="477" alt="Image" src="https://github.com/user-attachments/assets/a31236cc-c7a9-480f-b500-d1df64d4b19c" />



---



* When we create a new delivery without referencing a sales order i.e., delivery type ***CSLO*** we can see that the new item category proposed is ***CDLN***.



<img width="959" height="464" alt="Image" src="https://github.com/user-attachments/assets/3b328742-6a67-4bba-b70f-2c28708e93e4" />



---





## Delivery item category customization (T code - 0VLP or OVLP)



* We can use 0VLP/OVLP to copy delivery item categories and create our own delivery item categories.  



<img width="701" height="452" alt="Image" src="https://github.com/user-attachments/assets/c03b8676-9f41-42de-9038-9e2fb5888acf" />



---





## Delivery Item category determination (T code - 0184)



* The item categories for delivery are automatically determined via T code ***0184***



<img width="701" height="452" alt="Image" src="https://github.com/user-attachments/assets/9abb9fd2-9089-46f7-9443-68dbf4590a41" />



---



* ***NOTE*** - The delivery item category comes into play only if the order is being create without referencing any sales order, incase if the order is being referenced then the item category of the order would be considered. For ex the below delivery uses ***CAN*** because the sales order it references uses ***CAN*** as item category.





<img width="950" height="457" alt="Image" src="https://github.com/user-attachments/assets/3016e36c-62e3-4d3b-8a01-1e94b0ab6f0f" />



---



<img width="938" height="503" alt="Image" src="https://github.com/user-attachments/assets/74ba88f0-2790-4dae-b2a3-45eb15628abc" />



---






