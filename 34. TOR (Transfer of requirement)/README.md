## TOR (Transfer of requirement)


TOR will help to transfer the sales order requirement to **MRP**.

When you create sales orders requirement type will determine into sales document in procurement tab and requirement type will help to determine to requirement class and requirement class actually controls how to pass the sales order requirement to MRP.

**Prerequisite for TOR**

* In scheduling line category – check requirement assemble & availability check.
* In requirement class – Check Requirement and check Availability.
* Requirement type should be determine into sales document.

**The criteria for TOR**

The criteria for determining requirement type into sales document:
i) Strategy group, ii) MRP group, iii) Item category + MRP type.

**Standard requirement types**

* Standard requirement type is **[041 (When MRP type is PD) / 011 (When MRP type is ND)]**.
* Requirement type for Make to order is **[KE]**.
* Requirement type for IPO is **[KEB]**.

**Standard requirement class**

* Standard requirement class is **[041 / 011]**.
* Requirement class for Make to order is **[040]**.
* Requirement class for IPO is **[KEB]**.


## Configuration

***Firstly make changes in material master to make it relevant for TOR***

<img width="756" height="690" alt="Image" src="https://github.com/user-attachments/assets/512c7c49-2dcc-4df7-9413-15d5eba81222" />

---

<img width="701" height="689" alt="Image" src="https://github.com/user-attachments/assets/003c04b4-e6de-4f80-a999-f06df15d9dd3" />

---


***Now when you create a sales order you will notice that requirement type is determined into sales document***

<img width="1365" height="424" alt="Image" src="https://github.com/user-attachments/assets/81b072e2-97c2-491f-8cd8-7a89817f12eb" />

---

***SPRO PATH - SPRO -> Sales and Distribution -> Basic Functions -> Availability Check and Transfer of Requirements***

<img width="881" height="712" alt="Image" src="https://github.com/user-attachments/assets/4f79795b-1913-44b0-ac51-cec0ec2d7961" />

---

* Create a **requirement class** ny copying standard requirement class ***041*** and create a new requirement class ***ZDC - CASTROL requirement class***

<img width="1055" height="304" alt="Image" src="https://github.com/user-attachments/assets/7231f2bd-eb64-4af3-b717-3254f849d7af" />

---

* Create a **requirement type - ZCSR** and assign the above create requirement class to it.

<img width="836" height="198" alt="Image" src="https://github.com/user-attachments/assets/7ffea291-1d3e-4e79-acd8-a3a2c6ab03b8" />

---

* Now determine the requirement type using transaction. Maintaining ***1*** as original requirement type ensure that while determining requirement types in sales document, strategy group and MRP group are ignored and the determination is done based off Item category + MRP type.

<img width="668" height="639" alt="Image" src="https://github.com/user-attachments/assets/c27e5d51-a7f6-4a7d-b2c0-52b365cfb7c4" />

---

* In **VOV6** ensure that the availability check and requirement checkboxes are checked.

<img width="914" height="553" alt="Image" src="https://github.com/user-attachments/assets/d2685f12-290a-4985-87e4-faa7b6ec48a9" />

---


***Now create a sales order to check if the requirement type has successfully changed or not***

<img width="1330" height="621" alt="Image" src="https://github.com/user-attachments/assets/f802089b-24b8-4e0d-aa5f-4e5f6867a3f1" />

---
