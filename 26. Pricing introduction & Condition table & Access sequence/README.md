## Pricing introduction & Condition table & Access sequence 


---

## PRICING

Pricing is based on **condition technique**.

Condition technique is a process of determining condition records into sales document.

1. Condition technique consists of condition records.
2. Condition records will be stored in condition table.
3. Condition table will be placed in access sequence from most specific to most general.
4. Access sequence will be assigned to condition type.
5. Condition type will be placed in pricing procedure.
6. Pricing will be assigned to Sales document type.

---

### **Condition records**

Condition record is the master data for pricing. We also call it as **“pricing master”**.

The T-code to create condition record is: **VK11**

---

### **Condition Table**

Condition table is the combination of fields which will help to maintain the condition record.

The T-code to create condition tables: **V/03**

---

### **Access sequence**

It is a search strategy which will search for the valid condition record from the most specific to most general.

The T-code to create access sequence: **V/07**

---

### **Condition type**

It controls the type of the price component, i.e. whether it is a base price or discount or surcharge.

The T-code to create condition type: **V/06**

---

Here is the **text converted from the image into clean, editable text**:

---

### **Pricing Procedure**

It is a procedure which consists of all the relevant condition types which will place in a sequence.

The T-code to create pricing procedure: **V/08**

---

### **Assign pricing procedure or pricing procedure determination**

We assign pricing procedure to a combination of **sales area / document pricing procedure / customer pricing procedure**.

The T-code to assign pricing procedure or pricing procedure determination: **OVKK**

---

### **Standard condition types**

* **Base price**: PR00 (base price condition)
* **The Standard material discount**: K004 (material specific discount)
* **The Standard customer / material discount**: K005 (customer and material both specific discount)
* **The Standard customer discount**: K007 (Customer specific discount)
* **The standard condition type for freight is**: KF00 (freight is the additional charges like charges for loading,packing,transportation)
* **Standard condition type for tax is**: MWST
* **Price group discount is**: K020  (we group the prices and then assign it to customer based of which K020 is determined)

---


## Steps to follow when creating a pricing process

***Create a condition table (V/03)***

* Press enter with providing any input(Table number) to the screen, this will allow you to create a new table.
* The fields on the left side are slected for table while the fields from right side are the options from which we can choose.

<img width="1018" height="660" alt="Image" src="https://github.com/user-attachments/assets/29eb2ec9-48f7-4780-8cb5-54c761a1b387" />

---

* To create a table click on generate.

<img width="1075" height="677" alt="Image" src="https://github.com/user-attachments/assets/658351f8-6cdb-4cc0-ad66-b3ff774c4d20" />

---

* The following condition table we can see in ***Se16n*** if there are any condition records maintained corresponding to it.

<img width="925" height="442" alt="Image" src="https://github.com/user-attachments/assets/dad18748-af55-4432-9c8e-855eae709239" />

---

***Place the condition table into an access sequence (V/07)***

* To create a new access sequence click on ***new entries*** in access sequence screen.
* Create a new access sequence ***ZCAS***

<img width="1004" height="431" alt="Image" src="https://github.com/user-attachments/assets/b90bb526-6deb-461c-99f5-0f692280035b" />

---

* Now assign the condition table created previously 584 to the table.

<img width="1024" height="505" alt="Image" src="https://github.com/user-attachments/assets/11c19a63-8c4e-4931-b89a-50ba2a30feb1" />

---

* After assignment of the condition table no we want to decide if the sales org and material field would be decided from header(KOMK) or item(KOMP) level of the sales document.

<img width="1229" height="613" alt="Image" src="https://github.com/user-attachments/assets/9a29285e-b662-4c00-8723-e710980ddbba" />

---

* To change from header to item or vice versa.

<img width="1055" height="687" alt="Image" src="https://github.com/user-attachments/assets/46921e13-aa9f-4eb9-a7a2-4f8bcc4761b9" />

---

***Assign the access sequence to the condition type (V/06)***

<img width="966" height="688" alt="Image" src="https://github.com/user-attachments/assets/b111ab44-03da-4aac-b15d-74692b737070" />

---

* Now if you check ***condition record - VK13*** you will see your condition sequence popping corresponding to the condition type PR00.

<img width="878" height="587" alt="Image" src="https://github.com/user-attachments/assets/3006771f-d791-4281-9ca7-35d87d0dc531" />

---

***Maintain condition records (VK11)***

* Create material and sales org cobdition records corresponding to whom you want the base price to be provided into your sales document.

<img width="1002" height="406" alt="Image" src="https://github.com/user-attachments/assets/70f8e7df-20dc-47b8-af52-8e31cc301f57" />

---

* Now create a sales order, where we can see that the Base condition has the values maintained as per condition record.

<img width="1260" height="640" alt="Image" src="https://github.com/user-attachments/assets/161a82c4-a800-49a8-9432-9af058f50e2f" />