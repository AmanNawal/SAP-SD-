## Order to Cash Cycle


### Configuration Steps

### Inquiry document creation

* T code - VOV8.
* Copy the standard inquiry document type ***IN*** and create Castrol inquiry doc ***CSIN***.
* Make sure you extend the newly created inquiry doc type to sales area.
* **SPRO path - Sales and Distribution -> Sales -> Sales Documents -> Sales Document Header -> Define Sales Document Types -> Assign sales areas to sales document types.  OR  T-Code: OVAZ** 
* We have to assign an item category to the newly created inquiry document type otherwise it will appear with only header data.

---

<img width="1365" height="710" alt="Image" src="https://github.com/user-attachments/assets/787d9737-59a4-4da4-920b-053d0c7eabc1" />

---

* Now create a new item category for Castrol inquiry doc.
* T code - VOV7.
* Copy from standard item category ***AFN*** and create Castrol inquiry item category ***CSAN***.
* Now to atomatically determine the item category during inquiry creation we have to do an item category determination ***T code - VOV4***.

***imp - item category is determined based on***

* Sales Document Type (VOV4)
* Item Category Group (Material Master –> MM03 -> Sales: sales org 1 or 2 tab)

<img width="795" height="441" alt="Image" src="https://github.com/user-attachments/assets/c1f6fc13-c9b6-4998-af07-bcd18f2526e9" />

* Usage (optional)
* High-Level Item (optional)

<img width="549" height="295" alt="Image" src="https://github.com/user-attachments/assets/3457f7ee-87bc-45df-8a67-d9a62c3f26fc" />

---

***Next Step - create a schedule line category for inquiry item category***

* T code - VOV6.
* Satndard schedule line category for inquiry is ***AN***.
* Copy it and create Castrol inquiry schedule line category ***CM***.
* Now link this schedule line category ***AN*** to inquiry item category ***CSAN*** created in previous step.
* Now assign the newly created schedule line category ***CM*** to inquiry item category ***CSAN***. using **T code - VOV5**. So that when we create an inquiry with item category ***CSAN*** it will automatically pick schedule line category ***CM***.

<img width="571" height="336" alt="Image" src="https://github.com/user-attachments/assets/8b1a4e91-e63a-4e47-a097-50cbedb9eea4" />


---

***Schedule line category determination is done based on***

* Item Category
* Material Requirements Planning type (optional)


**Now create a inquiry document using T code - VA11.**

<img width="1365" height="716" alt="Image" src="https://github.com/user-attachments/assets/36ef3949-d1f1-4905-b926-ff5ee4ccfe70" />

<img width="1343" height="605" alt="Image" src="https://github.com/user-attachments/assets/de03c260-8320-41b1-a1d6-a45ed3cb0bed" />


---


### Create Quotation document 

* Create a quotation document type for Castrol by copying the standard docment type QT ***T code - VOV8, sales doc type - CQT***
* Assign this sales document type to sales area using **T code - OVAZ**.

<img width="723" height="370" alt="Image" src="https://github.com/user-attachments/assets/7cf41ce3-5251-4729-9168-4a6f9cebb143" />

---

***Next step - create item category for Castrol quotation doc***


* copy standard quotation item category ***AGN*** and create Castrol quotation item category ***ACS*** using **T code - VOV7**.  
  
  
<img width="462" height="298" alt="Image" src="https://github.com/user-attachments/assets/7669cddb-b15a-4e04-b8bb-506e31c05cfe" />

* Now do item category determination for quotation doc using **T code - VOV4**.

<img width="645" height="689" alt="Image" src="https://github.com/user-attachments/assets/d8eff9a1-526a-422a-b44f-738affe4fc42" />

---

***Next step - create schedule line category for quotation item category***  

* Copy the standard schedule line category ***BN*** and create Castrol quotation schedule line category ***CL*** using **T code - VOV6**.
* Now assign this schedule line category ***CL*** to quotation item category ***ACS*** using **T code - VOV5**.
    

<img width="496" height="300" alt="Image" src="https://github.com/user-attachments/assets/e785b3a7-40bc-45bf-ba09-65cf783557f0" />

---

<img width="1271" height="708" alt="Image" src="https://github.com/user-attachments/assets/d4a275ef-2cfe-47ac-b177-e3058f78514e" />

---

<img width="1270" height="627" alt="Image" src="https://github.com/user-attachments/assets/83bdab93-1ab9-4447-8bb0-59772dc63410" />

---

### Create Sales order document

* Create a sales order document type for Castrol by copying the standard docment type OR ***T code - VOV8, sales doc type - CSOR***
* Assign this sales document type to sales area using **T code - OVAZ**.

***Next step - create item category for Castrol sales order doc***

* Create a Castrol sales order item category ***CAN*** by copying standard sales order item category ***TAN*** using **T code - VOV7**.

---

***Do item category determination for sales order doc CSOR***

<img width="530" height="339" alt="Image" src="https://github.com/user-attachments/assets/f1167b54-dc31-40b3-839d-453babe1dfc6" />

---

***Next step - create schedule line category for sales order item category***

* Copy the standard schedule line category ***CN*** or ***CP*** and create Castrol sales order schedule line category ***CW*** using **T code - VOV6**.
* Now assign this schedule line category ***CW*** to sales order item category ***CAN*** using **T code - VOV5**.  



<img width="603" height="361" alt="Image" src="https://github.com/user-attachments/assets/c524b4c8-1666-4ad0-8160-e03f1f2a1ac9" />

---

***Now create a sales order using T code - VA01***

<img width="1365" height="713" alt="Image" src="https://github.com/user-attachments/assets/d162fa1e-b418-456e-82a9-bc11a0ba1abf" />

---

<img width="1344" height="655" alt="Image" src="https://github.com/user-attachments/assets/8cfccf5a-e7e6-421b-9a85-92cdc840424f" />

---


### Delivery Document creation

* Create a delivery document type by copying standard document type ***LF*** using **T code - OVLK, delivery doc type - CSLF**.

<img width="911" height="351" alt="Image" src="https://github.com/user-attachments/assets/f1641f2c-cc84-45da-b108-26292c3bb954" />

* Now assign this delivery doc type to sales order using **T code - VOV8**.
* ***imp*** - This assignment ensures that when we create a delivery for sales order type ***CSOR*** it picks delivery doc type ***CSLF*** automatically and we don’t have to manually select delivery doc type while creating delivery.

<img width="949" height="715" alt="Image" src="https://github.com/user-attachments/assets/e118f75c-61ca-4c49-894c-84e091f90f7c" />  

---

<img width="581" height="585" alt="Image" src="https://github.com/user-attachments/assets/abbdd084-5981-4545-bda1-6f7ee3adaacf" />


---

***Now create a delivery using T code - VL01N or directly from sales order using T code - VA01***

<img width="1365" height="713" alt="Image" src="https://github.com/user-attachments/assets/237974e4-20f9-459e-950b-3435c3dd3452" />  

---

### Billing Document creation

* Create a billing document type by copying standard document type ***F2*** using **T code - VOFA, billing doc type - CSF2**.

<img width="626" height="306" alt="Image" src="https://github.com/user-attachments/assets/d23067c2-3cb3-49d2-89cf-ed664464c720" />

---

* Now maintain the biiling type ***CSF2*** in sales order doc type ***CSOR*** using **T code - VOV8**. So that we don't have to manually enter billing type while creating billing document every time.

<img width="984" height="421" alt="Image" src="https://github.com/user-attachments/assets/f557f9a1-39c3-4e6a-8612-90181260c7ef" />

---

<img width="1010" height="723" alt="Image" src="https://github.com/user-attachments/assets/61f398fa-7007-4fd4-a497-56305c3bf4ab" />

---  

* Now create a billing document using T code - VF01.

<img width="1164" height="517" alt="Image" src="https://github.com/user-attachments/assets/76b749d9-edce-4b3c-953c-e4bf1316e188" />

---



