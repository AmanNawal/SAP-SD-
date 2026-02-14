## Credit management in ECC


“It is a process of managing credit limits of the customers”

Credit management will be configured into two ways

* Simple credit check
* Automatic credit check

**Simple credit check**

* if customer credit limit exceed we can block only at order level.
* In this there is no concept of risk category.
* In simple check system considers only receivable while performing credit check. Receivable means open items (An accounting document exists, but the customer invoice has not yet been cleared by payment.)

**Automatic credit check**

* if customer credit limit exceed u can block it order level or delivery level or PGI level.
* Based on risk category of the customer i.e. High risk customer block at order level. Medium risk customer block at delivery level. Low risk customer block at PGI level
* In automatic system consider open order value, open delivery value, open invoice value and open item value while performing credit check.


**Static credit check**

* It updates all open order values, open delivery values, open invoice values and open item values in credit management.

**Dynamic credit check**

* It updates all open order values, open delivery values, open invoice values and open item values but any open order value if delivery creation date exceeds horizon date that value will not update in credit management.

**Update group:**

* **000012:** It updates all open order values, open delivery values, open invoice values and open item values.
* **000015:** It updates all open delivery values, open invoice values, and open item values. (We use update group 15 for those process in which we don’t have sales order i.e. delivery without order reference).
* **000018:** It updates all open order values, open invoice values and open item values. (We use this update group for those process in which we don’t have delivery i.e. service process and Third party process).


## Configuration

* Create credit control area
* Assign company code to credit control area
* Maintain “A” in subtotal in pricing procedure
* Check credit active in item category
* Define risk categories (not required for simple credit check)
* Define credit check groups (not required for simple credit check)
* Maintain credit checking groups in order and delivery document types (not required for simple credit check)
* Define automatic credit check (not required for simple credit check)
* Maintain credit limit in **FD32**
* OMO1
* VKM4


## For simple Credit check

### Define credit control area

* SPRO -> Enterprise structure -> Definition -> FInancial accounting -> Define creadit control area.

* Create a new credit control area ***ZCCA*** by copying the standard crredit control area ***1000***.

<img width="556" height="460" alt="Image" src="https://github.com/user-attachments/assets/fd435222-a371-446a-b9c1-651bed9b9817" />

---

<img width="512" height="316" alt="Image" src="https://github.com/user-attachments/assets/604f908e-5ff1-484c-96b3-6276b07a238d" />

---


### Assign company code to credit control area

SPRO -> Enterprise structure -> Assignment -> Financial accounting -> Assign company code to credit control area.

<img width="547" height="700" alt="Image" src="https://github.com/user-attachments/assets/75608d0d-77df-441f-b45c-e6c00a3af132" />

---

### Maintain “A” in subtotal in pricing procedure

* In the pricing procedure assign subtotal 'A' to net pricing.

<img width="1337" height="591" alt="Image" src="https://github.com/user-attachments/assets/b1b9143e-3de5-4b8c-a941-4f8097b07de8" />

---


### Check credit active in item category

<img width="832" height="476" alt="Image" src="https://github.com/user-attachments/assets/41521a21-7958-44d1-8b6e-18bb04976336" />

---

### Maintain credit limit in FD32 T Code

* We can use FD32 T code to track all the credit related information of the customer like credit limit, risk category.

<img width="557" height="525" alt="Image" src="https://github.com/user-attachments/assets/a8ff7a99-ee9b-4469-8500-7d6a2dd4f068" />

---

<img width="914" height="633" alt="Image" src="https://github.com/user-attachments/assets/ed930629-eeab-4ee8-8a21-dd081a03a5f2" />

---


### Assign credit check to sales document type

* In the SPRO path mentioned below, assigm sales document type CSOR to activate the simple credit check.

<img width="768" height="597" alt="Image" src="https://github.com/user-attachments/assets/d62792af-479c-4d5b-8be7-286a66b9aebb" />

---

<img width="916" height="390" alt="Image" src="https://github.com/user-attachments/assets/e8a08666-d094-4202-90ef-5984815b3968" />

---

### Now create a sales order

* Create a sales order and check if the net value exceeds the credit limit which is 10000 in our case, in that case the ystem will throw an error message and block the sales order.

<img width="1123" height="656" alt="Image" src="https://github.com/user-attachments/assets/457886af-97e7-41cc-84b6-152e867a3633" />

---
<img width="1083" height="720" alt="Image" src="https://github.com/user-attachments/assets/d24c5daa-ac02-4bac-a64a-0a3ebae6ee9d" />

---

## For automatic credit check

### Define Risk categories

SPRO -> Accounts receivable and accounts payable -> Credit Management -> Credit control account -> Define risk categories.

* Create 3 risk categories ***High risk, Medium risk and Low risk***.

<img width="539" height="300" alt="Image" src="https://github.com/user-attachments/assets/fe203ed0-c7b4-44b6-9397-0de000e24893" />

---

### Define credit check groups

SPRO -> Sales and distrinution -> Credit management/risk management -> Credit management -> Define credit groups.

<img width="456" height="314" alt="Image" src="https://github.com/user-attachments/assets/df368d6d-84ab-4558-9e40-727a83932190" />

---

### Assign document types and delivery documents

* D stands for "Credit management: automatic credit control" since this is a sales order we will assign sales order credit check group.

<img width="567" height="191" alt="Image" src="https://github.com/user-attachments/assets/0d310bac-aec8-494f-9e07-69dbd785e5db" />

---

* Similarly assign the delivery document type to delivery credit check group and at PGI level assign the PGI document type to PGI credit check group.

<img width="685" height="247" alt="Image" src="https://github.com/user-attachments/assets/7c77329e-f789-4742-b250-e304293e4159" />

---


### Define automatic credit check

* In the same spro path define automatic credit check.
* Copy the standard 0001/001/01.

* High priority we are blocking at order level, medium risk we are blocking at delivery level and low risk we are blocking at PGI level.

* ***Item check*** field ensures that a credit check happends everytime the user adds a material or new item in the sales order incase if the credit limit is already exceeded it will throw a warning message to the user.

***Static credit check***

* It updates all open order values, open delivery values, open invoice values and open item values in credit management.

***Dynamic credit check***

* It updates all open order values, open delivery values, open invoice values and open item values but any open order value if delivery creation date exceeds horizon date that value will not update in credit management.

<img width="801" height="628" alt="Image" src="https://github.com/user-attachments/assets/fd91a30a-28f1-48b1-af4b-2c1e19226ca4" />

---

<img width="780" height="662" alt="Image" src="https://github.com/user-attachments/assets/bae0f946-bdeb-4c47-a9c5-1e41af9783b1" />

---

<img width="725" height="649" alt="Image" src="https://github.com/user-attachments/assets/f4f1d928-da06-4a59-98ef-bf41b31ac4dc" />
---

### We create 3 customers master data for 3 different risk categories

High risk customer - 100410
Midium risk customer - 100411
Low risk customer - 100412

* Make sure you enter credit control area when creating customer master data.

<img width="1080" height="702" alt="Image" src="https://github.com/user-attachments/assets/737d35f7-b1e5-4c68-8241-a64fd22a90cd" />

---

### Assign risk categories to customer master in T code - ***FD32***


<img width="918" height="634" alt="Image" src="https://github.com/user-attachments/assets/6a55c04d-9890-4ca5-aa91-250532dd984f" />

---

<img width="792" height="630" alt="Image" src="https://github.com/user-attachments/assets/55bfd87a-fda0-4f53-a54a-01deaa7af8a4" />

---

<img width="830" height="480" alt="Image" src="https://github.com/user-attachments/assets/f210b348-0880-410c-9d24-073af4fef1f1" />

---
