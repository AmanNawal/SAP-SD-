
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









## Rush Order

* Sales document type: RO
* Is a order in which a delivery document is created as soon as the sales order is created.
* There's still need to create the PGI and invoice documents.
* In VOV8, the shipping condition corresponding to rush orders is 10 (immediately). 