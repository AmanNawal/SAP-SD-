## Item proposal and CMIR


### CMIR(Customer Material Info Record)

* T code: VD01, VD02, VD03
* Stands for customer material info record.
* We use CMIR if the customers are placing orders with their own material numbers.
* By using CMIR we link the customer material number to our internal material number then while creating sales order if the user enters the customer material number system automatically fetches our internal material number. 
* For example: 
  * Customer A places an order for material number CUSTMAT001 which is their internal material number for the product "Laptop Model X".
  * In our system, we have the same product listed under our internal material number "PROD1001".
  * By creating a CMIR, we link "CUSTMAT001" to "PROD1001".
  * When Customer A places an order using "CUSTMAT001", the system automatically recognizes it as "PROD1001" and processes the order accordingly.


<img width="907" height="351" alt="Image" src="https://github.com/user-attachments/assets/96f284ba-0def-46df-95de-705bc01635b9" />

---

***Configuration in VOV8***

* Make sure ***Read info record*** is checked. 

<img width="964" height="720" alt="Image" src="https://github.com/user-attachments/assets/239824d9-af37-43bf-b9d8-318365a1a256" />

---

***Sales Order***

<img width="988" height="687" alt="Image" src="https://github.com/user-attachments/assets/0f969509-8b29-412a-a966-c2b99a9f7851" />


## Item Proposal

* ***T code to create an item proposal- VA51***
* Standard item proposal document type is ***PV***.
* Is a list of material which are frequently ordered by a particular customer.
* Using this list while creating the sales order saves the time of the end users as they do not have to search for the material every time.

---

***Assign item proposal to sales area T code - OVAZ***

* SPRO - S&D-SALES-SALES DOC HEADER-ASSIGN SALES AREA TO ALES DOCUMENT TYEPES -

* 1.COMBINE SALES ORG. - MAINTAIN YOUR SALES ORG.& REF SALES ORG.SHOULD BE SAME

* 2.COMBINE DIST.CHNL - MAINTAIN YOUR DIS. CHNL & REF. DIS.CHNL. SHOULD BE SAME

* 3.COMBINE DIVISION - MAINTAIN YOUR DIVISION & REFERNCE DIVISION SHOULDBE SAME

* 4.ASSIGN SALES DOC TYPES PERMITTED FOR SALES AREAS - ASSIGN YOUR SALESA REA TO YOUR SALES DOCUMENT TYPES.

---

<img width="1182" height="482" alt="Image" src="https://github.com/user-attachments/assets/58a5deff-9ec4-4556-bc02-58428f4f50a5" />


---

<img width="1049" height="393" alt="Image" src="https://github.com/user-attachments/assets/eff029b3-5c7e-4966-b12f-f80c15821f84" />


---

<img width="761" height="716" alt="Image" src="https://github.com/user-attachments/assets/988abd96-1dee-4400-85ce-08ce77ae0465" />


* ***imp-*** Similarly maintain other sales document types for sales area like OR(sales order).

---

***Item Proposal 50000041 has been saved***

* assign the item proposal to the customer.

<img width="827" height="671" alt="Image" src="https://github.com/user-attachments/assets/ec116c1e-898c-4de9-b9b2-8eec9e1a9dcc" />

* ***Now while creating the sales order click on item proposal button***

<img width="1356" height="718" alt="Image" src="https://github.com/user-attachments/assets/441e5f9e-adc8-4f78-89aa-6f592a354b3e" />

---

***imp T code VA55 would show list of item proposals created based off materials***

<img width="962" height="410" alt="Image" src="https://github.com/user-attachments/assets/773613da-c5fa-4df6-9425-80e44601ff62" />

---

<img width="1086" height="407" alt="Image" src="https://github.com/user-attachments/assets/163c862d-6660-4b83-90c2-2d5329c10a02" />
