## IPO (Indivisual purchase orders)

* An Individual Purchase Order (IPO) is a purchase order created specifically for one particular sales order.
* This means the material is purchased only for that specific customer order, not for general stock.
* In this the vendor delivers the goods to the company and then the company delivers the goods to the customer.

**IPO process:** Whenever order created in SAP automatically PR will generates backed after saved the order (**VA01**)

and PR will convert to PO (**ME21N**)

and vendor will send the Goods receipt (**MIGO**) to company

and vendor will send the Invoice (**MIRO**) to company

and company will send the goods to customer (**VL01N**)

and company will raise invoice (**VF01**) to customer

1. **Standard item category:** TAB

* **Billing relevance ‘A’**
* **Special stock “E”**

2. **Schedule line category:** CB

* **Order type “NB”** – it will help to generate purchases requisition automatically in the background after save the sales order in third party process.

* **Item category [0]:** item category controls that even we do MIGO in IPO process system will treat as actual MIGO and stock will be update.

* **Account assignment category [E]:** controls that in IPO process while doing MIGO and delivery system will not generate inventory accounting document. In IPO process the cost will assigned to the sales order.

1. **Item category group in material master:** BANC

2. **TOR:**

   * Requirement type: **KEB**
   * Requirement class: **KEB**

3. **Create Purchase org**

4. **Assign purchase org assignment to company code**

5. **Assign purchase org assignment to plant**


## Configuration for IPO

* Create a purchase org ***Puchase Org -IPO*** SPRO -> Enterprise structure -> definition -> Material management -> Maintain purchasing organization.
* Assign purchase org to company code SPRO -> Enterprise structure -> assignment -> Material management -> Assign purchasing organization to company code.
* Assign purchase org to plant SPRO -> Enterprise structure -> assignment -> Material management -> Assign purchasing organization to plant.

* Create a new item category ***YTAB*** by copying standrd item category ***TAB***.
* Create a new order type ***ZTAB*** by copying the standard order type ***OR***
* Do the item category determination in VOV4 and assign the item category ***YTAB*** to order type ***ZTAB*** and item category group ***BANC***.
* Now create a new schedule line category ***1B*** in VOV6 by copying the standard schedule line category ***CB*** and assign to item category ***YTAB*** in VOV5 with MRP type ND.
* In T code **OVLK **create a new delivery document ***YTAB*** by copying standrd delivery document ***LF***.
* In T code - VOFA create a new billing document ***YTAB*** by copying standard billing document ***F2***.
* Now assign delivery type ***YTAB*** to order type ***ZTAB*** in VOV8 and assign billing document ***YTAB*** to order type ***ZTAB*** in VOV8.

* Now goto masterial master the item category group should be **BANC**.

<img width="654" height="401" alt="Image" src="https://github.com/user-attachments/assets/8daed22d-d589-4814-b185-c2c3396c6310" />

---

* Now create an order and copy the purchase requisition to create PO later.

<img width="767" height="385" alt="Image" src="https://github.com/user-attachments/assets/1cf5689e-d1fd-42ff-9699-90b7402f8be1" />

---

* Now create a PO in T code ME21N.

<img width="736" height="457" alt="Image" src="https://github.com/user-attachments/assets/ce5916f1-34c4-46f8-a0e1-ef5518be4a89" />

---

* Now do the goods receipt in T code MIGO.

<img width="694" height="477" alt="Image" src="https://github.com/user-attachments/assets/d4f57150-b10e-4fe2-a381-7c84c68336a7" />

---

* Now goto MMBE to check the stick unline third party process the stock will be updated in IPO process. This is becasue in schedule line category we have assigned item category 0 which is actual MIGO and stock will be updated.

* Now do MIRO based on PO and create a vendor invoice.

<img width="718" height="461" alt="Image" src="https://github.com/user-attachments/assets/e6951e33-1468-473c-9588-a1aa41c195e9" />

---

* Now create a delivery document in T code VL01N and do PGI. After doing PGI stick would be reduced and now the stock will be updated in MMBE.

* Now create an invoice to customer in T code VF01 and check the invoice document.



