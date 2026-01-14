## Group conditions / Group discounts in pricing

* **Group Condition:** Group condition nothing but a group discount, Discount will given on total document value or group of material value.
* Group Condition Pricing is an SD pricing feature in SAP that allows a pricing condition to be calculated collectively for a group of items or customers, instead of item by item.

### Group condition configuration

* Create a discount condition type ***ZCD5*** by copying standard condition type ***K005 - Material discount type*** in ***V/06*** transaction.
* Change the ***Scale basis - B***

---

<img width="849" height="660" alt="Image" src="https://github.com/user-attachments/assets/c3ca8c06-a443-4b38-8cf4-654a52f7af3a" />

---

<img width="894" height="678" alt="Image" src="https://github.com/user-attachments/assets/37c2cd14-4d4d-4a71-aa04-4f9aa8637d2e" />

---

* Now add the newly created condition type in pricing procedure.

<img width="1053" height="556" alt="Image" src="https://github.com/user-attachments/assets/659e89f4-495d-4183-89e0-ebe9a644a1ce" />

---

* Now create a condition record with scale condition, if the net value is **10000** then a discount of **100** is available.

<img width="1033" height="397" alt="Image" src="https://github.com/user-attachments/assets/ea49ddec-51fa-4080-bd31-df2490804f94" />

---

<img width="624" height="469" alt="Image" src="https://github.com/user-attachments/assets/e32fbae6-a265-4299-83b3-fa6f9cca5087" />

---

* The discount condition ***ZCD5*** will only interface based off header condition value, if it is greater than or equal to **10000** and the resulting discount is equally distributed to all the line items in the document.


<img width="1124" height="605" alt="Image" src="https://github.com/user-attachments/assets/851334fe-c5a8-4ec0-bd10-c5f5d3c75a8a" />

---

<img width="1103" height="627" alt="Image" src="https://github.com/user-attachments/assets/74f15fa5-8312-4048-98e7-22f2987e4715" />

---

* We can see the highlighted value adds up to ***100*** which is the group discount we provided at scale.

***Creating material specific group discounts***

* Create a new condition type ***ZCM5***

<img width="805" height="655" alt="Image" src="https://github.com/user-attachments/assets/665a0df8-42f0-4c88-903e-1ebbfaba246a" />

---

* Add the newly created condition type in pricing procedure.

<img width="1081" height="601" alt="Image" src="https://github.com/user-attachments/assets/2c45f56f-5410-4cb3-8dc7-68ed345d47c3" />

---

* Create a condition record for material specific group discount.

<img width="958" height="304" alt="Image" src="https://github.com/user-attachments/assets/c9e17a25-cf27-48a7-8d51-e26e1a7e4d8f" />

---

<img width="889" height="390" alt="Image" src="https://github.com/user-attachments/assets/6b58b00e-8ecd-4f8d-8b85-8aa95e6754fd" />

---

* Now create a sales order to check if the discount is being alloted based off material group value.

<img width="1142" height="650" alt="Image" src="https://github.com/user-attachments/assets/60f6dcd2-c144-4550-9989-98ddd1517171" />

---

<img width="1094" height="639" alt="Image" src="https://github.com/user-attachments/assets/d855526f-0065-48f3-8755-9a1dad427344" />

---