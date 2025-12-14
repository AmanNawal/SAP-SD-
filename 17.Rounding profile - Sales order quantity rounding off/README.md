## Rounding profile - Sales order quantity rounding off

* A rounding profile controls how order quantities are rounded off in sales order to comply with logistical or packaging constraints.

* For example - Customer gives an order for material in decimals (e.g. 6.7 Kg), such ordered quantity cannot be delivered to the customers. So business requirement is to Round up the ordered quantity in sales order to next whole number (e,g, 7 Kg).

* T code for creating rounding profile Execute ****OWD1***.

* Or you can use Path:- SPRO-> SAP Customizing Implementation Guide -> Materials Management-> Purchasing-> Order Optimizing -> Quantity Optimizing and Allowed Logistics Units of Measure-> Maintain Rounding Profile.

### Configuration Static Rounding Profile

* A **Static** rounding profile is the most simple and straightforward. You establish one or more sets of Threshold Values and Rounding Values. Once your order meets the Threshold Value, SAP will automatically round up to the Rounding Value.

* Create a rounding profile by going to T code **OWD1** and the clicking of static.

<img width="845" height="422" alt="Image" src="https://github.com/user-attachments/assets/82d8dfd5-2c5e-467e-a8f3-32fc74696436" />

---

* Now create a rounding profile which would convert 1 value to 10 quantity.

<img width="881" height="605" alt="Image" src="https://github.com/user-attachments/assets/b23a0dc8-8c27-4575-ba06-93e876328ae5" />

---

* Now assign this rounding profile to the material master. Assign rounding profile in sales:sales org 1 view.

<img width="1019" height="690" alt="Image" src="https://github.com/user-attachments/assets/6bf2acac-76b2-4f91-a2f6-09e66bebabe6" />

---

* Make sure that the ***rounding off*** is allowed in ***VOV7***.

<img width="1077" height="712" alt="Image" src="https://github.com/user-attachments/assets/b3824e80-0dfa-40cf-b699-3bb59fba3b1f" />

---


* Now create a sales order and pass 1 L and quantity which would be rounded off to 10 L.

<img width="1365" height="649" alt="Image" src="https://github.com/user-attachments/assets/c81158f7-1122-42f0-9918-7f88ba09bd4b" />

---

***Property***

* Once the threshold value is met i.e. the quantity > 10, the system will round off to the next rounding value which is 20 in this case.
* Foe example if the quantity 21 is entered in sales order, the system will round it off to 30. In case if the quantity is 41, the system will round it off to 50.

<img width="1337" height="707" alt="Image" src="https://github.com/user-attachments/assets/344c1862-0bf0-4989-9609-70b1797b7c2e" />

---

### Configuration Dynamic Rounding Profile

* **Dynamic rounding profile** gives different features. Rounding Rules plays very important role in Dynamic rounding profile. Dynamic rounding profile is calculated based on percentage.
* 