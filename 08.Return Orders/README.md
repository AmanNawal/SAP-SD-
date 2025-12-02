## Return Orders

* Return orders allow customers to return previously purchased items for a refund or exchange.
* Return order type - RE

### Configuration


* Copy the standard return doc type ***RE*** from VOV8 to create your own ***CSRE*** return order type.

<img width="866" height="713" alt="Image" src="https://github.com/user-attachments/assets/fedce3db-be60-400f-ba84-46c16e729f41" />

---

* Setup the sales area corresponding to your return order type in t code ***OVAZ***.
* Now create your own item category ***CREN*** by copying standard return item category ***REN***.

<img width="929" height="332" alt="Image" src="https://github.com/user-attachments/assets/5a86e735-532c-47b8-bbe8-3e1bb7a60ab8" />

---

* In VOV4 do the item category determination for CSREN.

<img width="645" height="664" alt="Image" src="https://github.com/user-attachments/assets/9b3dc95b-1bf0-48db-890d-31f193655f0d" />

---

* Now copy the standard schedule line category ***DN*** and create your own schedule line category ***DQ*** in t code ***VOV6***.

<img width="649" height="362" alt="Image" src="https://github.com/user-attachments/assets/8ea44ff2-c7d7-4536-ab94-e79a5dacc57e" />

---

* Now do the schedule line determination for your return order type in t code ***VOV5***.

* Now we can create a return order in t code ***VA01*** using order type ***CSRE***.

***Create a delivery type to faciliate the return***

* Copy the standard delivery type ***LR*** to create your own return delivery type ***CSLR*** in t code ***OVLK***.

***Now create a billing type for return orders***

* Copy the standard billing type ***RE*** to create your own return billing type ***CSRE*** in t code ***VOFA***.

***To ensure that the delivery doc and billing doc types are automaticallly proposed maintain CSLR and CSRE in sales doc CSRE in t code VOV8***.

<img width="759" height="639" alt="Image" src="https://github.com/user-attachments/assets/fe0d4157-a521-46b4-b1dc-f730b4614dfe" />

---


***Setup copy control between sales doc to delivery and between delivery doc to billing doc***

* Goto ***VTAF*** and copy the standard control from RE to F2 and assign it to CSF2(sales order billing) and CSRE(return order) as we are creating return order with reference to Billing(F2)
* Check the same for Item category level if REN is being assigned to target CREN.

<img width="1362" height="711" alt="Image" src="https://github.com/user-attachments/assets/2e52e988-098a-4436-812e-0034628d0631" />
---

***Setup copy control between delivery doc to billing doc***

* Goto ***VTFL*** and copy the standard control from RE to F2 and assign it to CSLR(delivery doc) and CSRE(billing).

---

***After the following you can create return order, delivery and billing doc successfully***
