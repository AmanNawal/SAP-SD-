## Service order, Value order and text order


### Service Order

* Is used for selling services, not physical materials.
* Uses material type DIEN (Service). 
* No delivery is created (because a service cannot be shipped).    
* Billing is done directly from the order (billing relevance = ‘C’ Order-related billing) in ***VOV7***.


### Configuration service order

* Copy the standard sales order type ***OR*** and create your own sales order type for service orders ***CORS***.
* Extend the sales order ***CORS*** to sales area in T code - ***OVAZ***.
* Copy the standard item category ***TAD*** (service item) to your own item category ***CTAD*** in T code - ***VOV7***.
* Now do the item category determination for your sales order type ***CORS*** in T code - ***VOV7***.
* We will use standard schedule line category for this case i.e., ***CD*** and billing type doc would be standard too i,e., ***F2*** (standard invoice).
* We can now create a invoice directly from the sales order.

***But what if we are in a situation where we want to do delivery before invoicing for service order?***

* In that case firstly, make the item relevant for delivery in ***VOV7***.

<img width="1210" height="724" alt="Image" src="https://github.com/user-attachments/assets/aa257bbd-020f-4551-a7d6-4b198c2c0de3" />  

---

* Now create on delivery line item by copying standard delivery item category ***TAN*** to your own delivery item category ***CTAD*** in T code - ***0VLP***.  

<img width="1116" height="721" alt="Image" src="https://github.com/user-attachments/assets/a1473e0e-803a-4c17-86f4-c2970572f69e" />

---

* ***Relevant for picking*** should be unchecked as service items do not require picking.
* Now goto ***VOV6*** mark the schedule line as relevant for delivery.

<img width="1084" height="711" alt="Image" src="https://github.com/user-attachments/assets/e4f87fc4-dd12-40e4-9551-bb8e5e7e4834" />

---

* Now create a delivery and subsequently create an invoice(didn't worked for me as it is missing loading group/plant compbination).

***Delivery is never needed in service order but if required we can follow the above steps to create delivery for service order.***


## Same applies for Value order and Text order
