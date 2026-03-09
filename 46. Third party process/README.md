## Third party process

* The Third-Party Process in SAP SD is a sales process where the company sells goods to a customer, but the goods are delivered directly by a vendor (supplier) to the customer.

* In this process, the company does not store or ship the goods from its own warehouse.

* Third-Party Sales is a process where the sales order triggers a purchase order to a vendor, and the vendor delivers the goods directly to the customer.

* Your company acts as an intermediary between the customer and the vendor.


**Third party process:** Whenever order created in SAP automatically PR will generates backed after saved the order

and PR will convert to PO

and PO will be sent to vendor

and vendor delivers the goods to customer

and vendor will send the invoice to company

and company will raise invoice to customer.

1. **Standard item category:** TAS

* **Billing relevance ‘F’** standard. F means order related billing without MIRO system will not create billing.
* **Billing relevance ‘G’** standard. G means order related billing without MIGO system will not create billing.

2. **Schedule line category:** CS

* **Order type “NB”** – it will help to generate purchases requisition automatically in the background after save the sales order in third party process.

* **Item category [5]:** item category controls that even we do MIGO in third party system will treat as dummy MIGO and stock will not be update.

* **Account assignment category [1]:** It controls that whether to generates inventory accounting document or not while doing MIGO (this field controls the cost should be assigned to any special cost object or not).

* In copy control between order to invoice (**OR – F2**) **TAS** has billing quantity **‘F’** and it will help to copy the quantity from **MIRO** to invoice while creating invoice to customer in third party process. And **‘E’** which helps to copy the quantity from **MIGO** to invoice while creating invoice to customer in third party process.



### Configuration for thrid party process

* Create a sales document type ***Y1TS*** copy from standrd ***OR*** document.

* Copy the standard item category ***TAS*** to ***Y1TS*** item category and assign to sales document type ***Y1TS***.

* Create a schedule line category ***Y6*** by copying the standard schedule line category ***CS*** and assign to item category ***Y1TS***.

* Create a billing dcoument ***Y1TS*** by copying standrd billing document ***F2*** and assign to sales document type ***Y1TS***.

***In VOV8 assign the billing document Y1TS to order type Y1TS***

* This ensures we don't have to manually select the billing document when we are trying to invoice.
* Since this is a Third party sales process without shipping document it does not include any goods reciepts hence we are not expecting any delivery document to be created and the billing would be order related.

<img width="503" height="417" alt="Image" src="https://github.com/user-attachments/assets/70ee8071-eda3-4cb8-a00f-bdd48a6258f8" />

---

***DO THE ITEM CATEGORY DETERMINATION AND SCHEDULE LINE DETERMINATION in VOV4 and VOV5***

* In the scheulde line category Y6 ensure that the following configurations are done.

  * **Order type “NB”** – it will help to generate purchases requisition automatically in the background after save the sales order in third party process.

  * **Item category [5]:** item category controls that even we do MIGO in third party system will treat as dummy MIGO and stock will not be update.

  * **Account assignment category [1]:** It controls that whether to generates inventory accounting document or not while doing MIGO (this field controls the cost should be assigned to any special cost object or not).

<img width="500" height="361" alt="Image" src="https://github.com/user-attachments/assets/fb2ea13c-f4b0-4e22-b030-41a67f36ded3" />

---

* Now create a sales order, in the schedule line you will see category Y6 with purchase requision automatically generated in the background.

<img width="772" height="394" alt="Image" src="https://github.com/user-attachments/assets/8508a22c-0199-4fdf-9989-fab696167a6e" />

---

* Now The purchase requisition is created but the PO is still not created, we need to do some configuration which will convert the purchase requisition to purchase order automatically in the background.

SPRO -> Enterprise structure -> Definition -> Material management -> Maintain purchase organisation

* Create a new purchase organization YO10

<img width="474" height="337" alt="Image" src="https://github.com/user-attachments/assets/4b3851d9-f744-4cbf-a92a-212b3b37906a" />

* Now assign the purchase organization to company code

SPRO -> Enterprise structure -> Assignment -> Material management -> Assign purchase organisation to company code

* Now assign Purchase org to plant.

SPRO -> Enterprise structure -> Assignment -> Material management -> Assign purchase organisation to plant

* Now create a vendor customer ***XK01***

<img width="596" height="281" alt="Image" src="https://github.com/user-attachments/assets/01ba6c10-f1b8-4ade-87b4-d3da8b6aa13b" />

---

* Now create a PO T code - ME21N.
* Then do MIRO since its a thrid party process without shipping notification. T code - MIRO.

<img width="771" height="311" alt="Image" src="https://github.com/user-attachments/assets/49810cd0-78a8-4d55-8c90-3c8e086e7f16" />

---

<img width="766" height="427" alt="Image" src="https://github.com/user-attachments/assets/760550f0-7337-49b0-809b-a70a9fb037d9" />

---

* Goto invoice tab and maintain Tax code as ***V2*** which is a standrd tax.

<img width="719" height="369" alt="Image" src="https://github.com/user-attachments/assets/fa98f2f3-5c0d-4f45-a963-5b74f18faaf9" />

---

* Define copy condtrol from invoice to order ***VTFA***
* This config in copy condtrol copies the quantity from MIRO i.e. in invoice MIRO quanity will be copied to invoice to customer while creating invoice to customer in third party process.

<img width="698" height="305" alt="Image" src="https://github.com/user-attachments/assets/b5bcea69-e56d-4c6d-b011-a3c1e29a66b0" />

---

### Configuration without shipping notification

* Open VOV7 ***Y1TS*** item category and maintain the following configuration.
* In billing relevance maintain as ***G*** which means order related billing without MIGO system will not create billing.

<img width="617" height="334" alt="Image" src="https://github.com/user-attachments/assets/23eb035a-4c3e-49dc-9157-af1aa4ea8f82" />

---

* In copy control ***VTFA*** maintain ***E*** instead of F.

<img width="750" height="314" alt="Image" src="https://github.com/user-attachments/assets/28f0f3b4-0fc4-4fb2-9395-771c7d724cf9" />

---

* Now create a sales order and copy the purchase requisition document number to create PO alongside we will do goods issue.
* In ME21N i.e. when creating PO, ensure you check good issue and this third party sales include shipping notification.

<img width="768" height="295" alt="Image" src="https://github.com/user-attachments/assets/c23c0b4f-7bd5-467e-9a87-27fc34724038" />

---

* Copy the PO number and open the T code MIGO.

<img width="764" height="320" alt="Image" src="https://github.com/user-attachments/assets/c18b4c59-25ba-492c-b30c-f4f9f5cff5f9" />

---

<img width="711" height="421" alt="Image" src="https://github.com/user-attachments/assets/e00b4c58-93f6-4b14-bcdf-f8924d64e2a6" />

---

* There would be no update in stock for this MIGO as this is a dummy MIGO determi8ned by schedule line category configuration.

### Automatic conversion of purchase requisition to purchase order


* Check automatic PO in item category.

<img width="651" height="431" alt="Image" src="https://github.com/user-attachments/assets/f33de8c1-1b03-464a-9d63-89e3e155b026" />

---

* Check automatic PO in Material master.

<img width="558" height="430" alt="Image" src="https://github.com/user-attachments/assets/c1c38c6b-1166-44f8-8a51-7df8008285ae" />

---

* Check automatic PO in Vendor master (XK02).

<img width="583" height="416" alt="Image" src="https://github.com/user-attachments/assets/74d32c20-3bc0-4ab3-a0e5-9125790a48c3" />


---

* Maintain ALE data in sales org. ALE (Application Link Enabling) is a technology in SAP that allows different SAP systems to communicate and exchange data automatically. ALE allows SAP systems to send business documents (like sales orders, customers, materials) to other SAP systems.

SPRO -> Enterprise structure -> Definition -> Sales and distribution -> Define sales organization

<img width="629" height="393" alt="Image" src="https://github.com/user-attachments/assets/1b6bd8ba-5cd2-4458-ac2f-680afe41bb98" />

---

* Maintain source list (Tcode - ME01), A Source List is a record that defines which vendor (source of supply) can supply a particular material during a specific time period.

<img width="644" height="306" alt="Image" src="https://github.com/user-attachments/assets/a0c77c2d-f652-4822-bd50-79ada5e7c884" />

---

* Maintain info records (T code - ME11),A Purchasing Info Record stores information about the relationship between a vendor and a material.

  * It contains details such as:

  * Vendor supplying the material

  * Price from that vendor

  * Delivery time

  * Minimum order quantity

  * Purchasing conditions

<img width="597" height="439" alt="Image" src="https://github.com/user-attachments/assets/5ffb613b-507f-4691-a14a-51b73dc60ecf" />

---

* Now create an order and you will see purchase requisition is created and after saving the order purchase requisition will automatically convert to purchase order in the background.

