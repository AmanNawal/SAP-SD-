## BOM - Bill of material
 
* It is a structured list of components that make up a finished product or a sales kit.

* Example: Finished Product: Perfume Set

    * BOM components:

    * Bottle

    * Cap

    * Liquid

* BOM is primarily a MM/PP Object but it is used in sales process as well.

* T code to create BOM: **CS01**
* T code to display BOM: **CS03**
* T code to change BOM: **CS02**
* BOM Usage for Sales: **5** (Sales and Distribution)

* In SAP SD, pricing for a BOM (Bill of Material) can be handled in two standard ways:

  * Header Pricing (Pricing BOM)
  * Item Pricing (Component Pricing)



## Header Pricing


* Price is maintained ONLY on the BOM header material. BOM components are delivery relevant but nor priced.
* Customer sees one price for the full kit.
* Invoice will have only one material (BOM header material) with the total price.

***Only in case of header pricing***

| item category group | Main item category | Sub line item category |
|---------------------|--------------------|-----------------------|
| ERLA                | TAQ                | TAE                   |


## Configuration Steps:

* We have created 3 materials:

    * 3000000048A (main item)

    * 3000000047A (Sub item)

    * 3000000046A (Sub item)


<img width="1365" height="660" alt="Image" src="https://github.com/user-attachments/assets/8926cdf6-ca1b-4657-b6df-4e11b76cd685" />

---

* We will be using pre existing castrol sales order type ***CSOR*** for BOM usage.
* Make sure all the materials are of item category group **ERLA** otherwise item category determination will fail.
* Now copy the standard item category ***TAQ*** abd create your own main item category ***CTAQ***, similarly copy sub item category ***TAE*** and create your own sub item category ***CTAE***.

* Now do ietm category determination in ***VOV4***.

| Sales doc type | Item category group |     Item usage     |   Higher level item   | Item category |
|----------------|---------------------|--------------------|-----------------------|---------------|
| CSOR           | ERLA                | Blank              | Blank                 | CTAQ          |
| CSOR           | ERLA                | Blank              | CTAQ                  | CTAE          |


<img width="777" height="706" alt="Image" src="https://github.com/user-attachments/assets/bcea370c-360c-46fc-8195-90a9ee2d7e12" />

---

* Now you are good to create a sales order wrt BOM.

<img width="1364" height="714" alt="Image" src="https://github.com/user-attachments/assets/ca213235-1d8f-4258-81ea-b51333f5b44c" />

---

***We have a configuration to contract if we want to explode single level BOM or Multi level BOM or No explosion at all.***

* Goto to ***VOV7*** double click on ***CTAQ***

* Maintain ***structure scope*** as vacant and uncheck ***manual alternative***.

<img width="995" height="671" alt="Image" src="https://github.com/user-attachments/assets/0ce61646-a1cf-4d7f-aa31-9a8b22e153d3" />


* Now you will notice that the BOM is not exploded at all.

<img width="1346" height="672" alt="Image" src="https://github.com/user-attachments/assets/9ca7e9f7-af52-491b-b00e-01d2cfd84eac" />


## Item pricing

* Each BOM component is priced individually. Header item has no price and acts as a structure element only.
* For example- Selling spare parts as a kit, but each part has its own price.
* BOM header alongside sub items are delivery relevant but only sub items would be invoiced.


| Item category group | Main item category | Sub line item category |
|---------------------|--------------------|------------------------|
| LUMF                | TAP                | TAN                    |

## Configuration Steps:


* We have created 3 materials for whome we have changed the item category from ERLA to LUMF:

    * 3000000048A (main item)

    * 3000000047A (Sub item)

    * 3000000046A (Sub item)


* Create a new item category ***CTAP*** by copying standard item category ***TAP*** and similarly create sub item category ***CTNB*** by copying standard item category ***TAN***.
* Now do item category determination in ***VOV4***.

<img width="971" height="672" alt="Image" src="https://github.com/user-attachments/assets/1aeb7f8e-e265-48cc-aecc-cbc19cdcae13" />

---

* Now you are good to create a sales order wrt BOM you will notice that header item or the main item has no pricing carried over.
* Whereas the sub items have their individual prices.
* This configuration of allowing the items to be relevant for pricing is defined in VOV7.

<img width="1039" height="705" alt="Image" src="https://github.com/user-attachments/assets/9d4c108f-ae24-4562-8474-13fb1b0823b5" />

---


***Delivery***

<img width="1356" height="631" alt="Image" src="https://github.com/user-attachments/assets/8bc697ae-cf53-4b36-a2dd-8247127acdcc" />

---

***Invoice***


<img width="1129" height="634" alt="Image" src="https://github.com/user-attachments/assets/95524b12-e2c2-4e67-9f7b-520c71c6a592" />

---