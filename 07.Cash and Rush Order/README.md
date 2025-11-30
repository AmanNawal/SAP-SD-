
## Cash Sales

* Sales document type: CS
* Refers to the sales where a delivery is done immediately and the customer pays for the goods at the time of purchase i.e., no delay.
* Cash sales uses special customers known as one time customers.


### Configuration of cash sales

* Copy the standard cash sales order type (CS) from **VOV8 **to a new castrol cash **sales order type (CCS).**

<img width="750" height="346" alt="Image" src="https://github.com/user-attachments/assets/ae442fbe-f499-43db-8a2f-12d28e013fec" />

* Assign ***CCS*** order type to relevant sales areain ***T code - OVAZ***.

---

***Next step: create a Cash sales item category***

* Copy the standard cash sales item category ***BVN*** to create a new item category ***CBVN*** in ***T code - VOV7***.
* Do the item category determination for newly created created cash sales item category in ***T code VOV4***.

<img width="801" height="628" alt="Image" src="https://github.com/user-attachments/assets/2e037a5f-22cf-47e1-a179-6f2338a071f9" />

---

***Next step: create a cash sales schedule line category***

* Copy the standard cash sales schedule line category ***CN*** to create a new schedule line category ***CG*** in ***T code - VOV6***.
* Do the schedule line category determination for newly created cash sales schedule line category in ***T code VOV5***.

<img width="812" height="440" alt="Image" src="https://github.com/user-attachments/assets/35540745-f513-4e7f-b289-ac9c61c574f0" />

---

***Next step: create one delivery type specific for cash sales***

* From ***T code - OVLK***, copy the standard delivery type ***LF*** to create a new delivery type ***LC*** for cash sales.

<img width="879" height="460" alt="Image" src="https://github.com/user-attachments/assets/de02a3f7-05ff-4689-a14a-158565fc4964" />

---

***Next step: create a cash sales billing type***

* From ***T code - VOFA***, copy the standard billing for cash sales **BV** to create a new billing type ***CBV*** for cash sales.


<img width="490" height="319" alt="Image" src="https://github.com/user-attachments/assets/e29bcddb-e758-492c-bed6-5175a21600af" />

---

### IMPORTANT: Assign the newly created cash sales delivery and cash sales billing type to cash sales order type in VOV8 otherwise we would have to manually enter delivery and billing type every time we create a cash sales order.

<img width="984" height="720" alt="Image" src="https://github.com/user-attachments/assets/8ffb26b5-aa92-4625-bf80-9d209d3c79d7" />

---


***Now create a sales order, delivery and invoice***


<img width="1353" height="693" alt="Image" src="https://github.com/user-attachments/assets/a18618ff-38c7-43f2-9782-aa332eacf90f" />

---

<img width="1245" height="662" alt="Image" src="https://github.com/user-attachments/assets/4d20d65b-f21e-4433-904d-8c8b9529f650" />

---

* Make sure in VOV8, the shipping condition corresponding to cash sales is 01 (immediate).


<img width="1047" height="709" alt="Image" src="https://github.com/user-attachments/assets/71175f7c-d899-44b0-a5a5-82ca0794e831" />

---

### Copy controls for cash sales data copy to cash sales delivery and billing

* Go to ***T code - VTLA*** to define copy controls from cash sales order to cash sales delivery.
* Copy the standard copy control defined for cash sales order type ***CS*** to delivery type ***BV***.

<img width="1016" height="608" alt="Image" src="https://github.com/user-attachments/assets/816dde00-c80b-4a33-9ddc-56f924f51d6d" />

---

* Now go to item level and check if the item category is present in the copy control.

<img width="929" height="534" alt="Image" src="https://github.com/user-attachments/assets/0d4f080d-e847-45dc-9c9c-cd422e694dcb" />

---

***Once the delivery copy controls are set, SAP would automatically create delivery document when we create cash sales order.***


<img width="1364" height="710" alt="Image" src="https://github.com/user-attachments/assets/c5c3a6f9-9007-470e-a3da-f7d1ed265660" />

---

***Make sure in VOV7, we have billing relevance set to B (Order relative billing) for cash sales item category.***

* As Cash sales order requires immediate billing once the delivery is created, we do order based billing ***Billing relevance B***.

<img width="995" height="617" alt="Image" src="https://github.com/user-attachments/assets/3b5b9813-d631-40e7-987a-c6177d509981" />

---


* Since the Standard delivery type which was copied was ***LF*** we would have to again change copy control from delivery to billing in ***T code - VTLA***.
* Copy the standard billing type ***F2*** and delivery type ***LF***.
* Make sure the item category is present in the item level of copy control.

<img width="1015" height="522" alt="Image" src="https://github.com/user-attachments/assets/7dd8e7ce-cd95-455c-b4bb-74a60ab56074" />

---

***Now create an invoice***

<img width="1160" height="710" alt="Image" src="https://github.com/user-attachments/assets/20054aca-8d4e-4523-a225-cf6fe308889b" />





## Rush Order

* Sales document type: RO
* Is a order in which a delivery document is created as soon as the sales order is created.
* There's still need to create the PGI and invoice documents.
* In VOV8, the shipping condition corresponding to rush orders is 10 (immediately). 

### Configuration of rush order

***Copy the standard rush order sales order type (RO) from **VOV8 **to a new castrol rush order **sales order type (CSRO).***

* Now assign sales area to newly created rush order sales order type in ***T code - OVAZ***.
  
***Next step: create a rush order item category***  

* Copy the standard rush order item category ***TAN*** to create a new item category ***RTN*** in ***T code - VOV7***.
* Do the item category determination for newly created created rush order item category in ***T code VOV4***.

<img width="799" height="667" alt="Image" src="https://github.com/user-attachments/assets/5ad8ed36-fad5-4551-a789-fa146a2625f1" />

---  
  
***Next step: create a rush order schedule line category***

* You can use the cash sales schedule line cat ***CG*** as both cash sales and rush order use the same standard schedule line cat ***CN or CP*** as base.

---  


***Next step: Xreate delivery document type specific for rush order***

* You can use the cash sales delivery type ***LC*** as both cash sales and rush order use the same standard delivery type ***LCS*** as base.

---

***Next step: create a rush order billing type***

* From ***T code - VOFA***, copy the standard billing for rush order **F2** to create a new billing type ***ROF2*** for rush order.

<img width="583" height="621" alt="Image" src="https://github.com/user-attachments/assets/7e8bc5b9-c126-4df0-80d5-884b5023b710" />

---  

***Now assign the newly created rush order delivery and rush order billing type to rush order sales order type in VOV8 otherwise we would have to manually enter delivery and billing type every time we create a rush order sales order.***

<img width="1087" height="708" alt="Image" src="https://github.com/user-attachments/assets/268747c1-bcbf-499d-af4b-fdfe7eb1e67b" />

---

***Now create a rush order sales order, delivery(automatic) and invoice***

