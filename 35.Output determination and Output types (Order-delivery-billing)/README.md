## Output determination

It is a process of determining output types into sales document or delivery document or billing document.

Output determination is also will work based on condition technique.

* Inquiry – Printout
* Quotation – Printout
* Order – Printout
* Delivery – Pricing list printout, Packing list printout, Delivery challan printout
* Invoice – Printout

The common T-code for output determination is **NACE**.

The table for output determination is **NAST**.

**Standard output types**

* The standard output for order is **BA00**.
* The standard output for quotation is **AN00**.
* The standard output for packing list is **PL00**.
* The standard output delivery challan is **LD00**.
* The standard output type for cash sale is **RD03**.
* The standard output type for billing is **RD00**.

Here is the text exactly as mentioned in the image:

**Output determination PATH:**

**SPRO → Sales and distribution → basic functions → output control → output determination → output determination using condition technique**

* **Step 1:** Output tables
* **Step 2:** Output access sequence
* **Step 3:** Output type
* **Step 4:** Output procedure
* **Step 5:** Assign output procedure to document type

**Output condition records T-codes**

* **Order – V11**
* **Delivery – V21**
* **Invoice – V31**


### Output determination configuration


***Create a table***

<img width="668" height="677" alt="Image" src="https://github.com/user-attachments/assets/c018b58d-3ed1-4776-8278-bcef8125c73b" />

---

<img width="545" height="291" alt="Image" src="https://github.com/user-attachments/assets/15520610-540e-42ea-bcd2-e5a18f059687" />

---

<img width="802" height="513" alt="Image" src="https://github.com/user-attachments/assets/185eab64-ad73-4325-835a-84434cd7def3" />

---

<img width="638" height="299" alt="Image" src="https://github.com/user-attachments/assets/87a554b5-38d1-4597-9cb0-44ad55f27567" />

---

***Create an access sequence - ZCSO***

* Goto T code - ***NACE***, we select V1 as we are creating output for sales order. Incase of delivery select V2 and V3 incase of billing.

<img width="561" height="532" alt="Image" src="https://github.com/user-attachments/assets/40e84287-146d-470f-b0b4-29a16d82df05" />

---

<img width="864" height="355" alt="Image" src="https://github.com/user-attachments/assets/4e945265-e71a-4df6-acdd-9f0b281a4783" />

---

<img width="876" height="252" alt="Image" src="https://github.com/user-attachments/assets/34fe0853-7829-4de4-945c-ee7e0395640c" />

---

<img width="971" height="286" alt="Image" src="https://github.com/user-attachments/assets/ddfdba1c-c4e9-4f49-a45b-fbdb5915d7f1" />

---

***Create output type***

<img width="631" height="696" alt="Image" src="https://github.com/user-attachments/assets/a064232b-2779-441b-8478-cefc60ce34b3" />

---

* Copy the standard out type ***BA00*** and create your own order output type ***ZCB0***.

<img width="865" height="611" alt="Image" src="https://github.com/user-attachments/assets/6eed6667-92c0-4ff8-9dbc-ac0e55263d28" />

---

* In the output type screen click on ***processing routines*** to check the smartforms assigned to the output type.

<img width="1163" height="375" alt="Image" src="https://github.com/user-attachments/assets/6c1aea4c-ce52-4d80-a30c-d5e9e59d7b61" />

---



***Create an output procedure***

* Now create a new output procedure by clicking on ***procedure*** in T code NACE.

<img width="527" height="576" alt="Image" src="https://github.com/user-attachments/assets/16632854-dea9-47e9-81f8-275718a7bc67" />

---

* Copy the standard output procedure ***V10000*** and create your own procedure ***ZCS001***.

<img width="521" height="277" alt="Image" src="https://github.com/user-attachments/assets/d4c32432-56a1-4b69-80a6-53b73724bca5" />

---

<img width="839" height="396" alt="Image" src="https://github.com/user-attachments/assets/0033d131-0a33-4150-9e4d-f412a5bb39f9" />

---


***Assign output determination procedure to the document***

* Go to the followinng SPRO path and then select ***Assign output determination procedure***.

**SPRO → Sales and distribution → basic functions → output control → output determination → output determination using condition technique**

<img width="939" height="519" alt="Image" src="https://github.com/user-attachments/assets/e0787997-5aa4-4997-b01c-f5eea75d1f6d" />

---

***Create an order and manually add output condition records***

* After saving the output goto -> Extras -> output -> edit 

<img width="703" height="711" alt="Image" src="https://github.com/user-attachments/assets/c348ce68-25e2-4fe3-84a6-307df46e2922" />

---

<img width="868" height="610" alt="Image" src="https://github.com/user-attachments/assets/bdac544d-fbb7-4ab0-af00-218b8d7e7714" />

---

***Incase we don't want to manually add records for output***

* Use T code - VV11 to create an output record.

<img width="663" height="277" alt="Image" src="https://github.com/user-attachments/assets/a35539de-cd6b-49c4-8621-fc2ebe11bb60" />

---

<img width="658" height="299" alt="Image" src="https://github.com/user-attachments/assets/1802f01c-3ad9-4b90-9f03-0430ff1e34d5" />

---

<img width="688" height="635" alt="Image" src="https://github.com/user-attachments/assets/ee58f82d-6c02-4497-bb5f-4e918f9ee598" />

---

* Now the output condition records wil automatically flow into sales document.







