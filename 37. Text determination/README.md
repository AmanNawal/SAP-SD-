## Text determination


“It is a process of determining text into sales document”.

Every customer will have their own specific text information. Ex.: Packing instruction, Payment instruction, Terms & condition instruction etc.

These text we maintain in customer master, from there we copied into sales order and then delivery and invoice.

**Configuration for text determination PATH:**
**SPRO → S&D → basic function → text control**

T-code for text determination is **VOTXN**.

* **Step 1:** Text types need to create
* **Step 2:** Text procedure need to create
* **Step 3:** Text types need to place in text procedure
* **Step 4:** Text Access sequence need to create
* **Step 5:** Text types (Text ID) need to assign access sequence
* **Step 6:** Text procedure need to assign document types

Customer → Sales order header → Delivery header → Invoice header

Customer → Sales order header → Delivery header

Customer → Sales order header → Invoice header

Material → Sales order item → Delivery item → Invoice item


### Configuration of text determination


### Customer master text configuation

* Create a text in t code - VOTXN

<img width="611" height="612" alt="Image" src="https://github.com/user-attachments/assets/766c2f36-ac51-47bb-b6fc-4d40aa8da354" />

---

* Create a new text ***ZCST***.

<img width="953" height="325" alt="Image" src="https://github.com/user-attachments/assets/8cda482a-02da-4e69-8da1-19a61a726529" />

---

* Create a new text procedure ***ZC***

<img width="557" height="466" alt="Image" src="https://github.com/user-attachments/assets/a4410131-2e70-4514-bc49-29e1a683859b" />

---

<img width="540" height="302" alt="Image" src="https://github.com/user-attachments/assets/ae3648b1-af16-4862-adf1-fca72311639a" />

---

<img width="595" height="346" alt="Image" src="https://github.com/user-attachments/assets/9e8498f8-7ff6-4d5d-acd7-7e3d5f883ef1" />

---

<img width="873" height="322" alt="Image" src="https://github.com/user-attachments/assets/fc8a1433-b520-408f-ba63-ac9963944264" />

---

* Create a customer and check if you can add text to it. Yes, after assignment of ZC with ZMSP we are able to add text to ZMSP account group customer master data.

<img width="671" height="669" alt="Image" src="https://github.com/user-attachments/assets/c6d902db-9d14-4ed2-a345-f92773d5b551" />

---

<img width="845" height="407" alt="Image" src="https://github.com/user-attachments/assets/fdad50f4-dae8-41c3-a13b-98995f244f0e" />

---

<img width="873" height="244" alt="Image" src="https://github.com/user-attachments/assets/91e5ffbe-c5ca-4d2a-acb5-01acaed42ead" />

---


### Sales document text config

* Now go to T code - ***VOTXN*** and asles document header -> text type -> new entries 

<img width="723" height="471" alt="Image" src="https://github.com/user-attachments/assets/3d04d4ed-216f-4702-8050-108ce64ebac3" />

---

* Create a text type ***ZCST*** for sales document header.

<img width="566" height="334" alt="Image" src="https://github.com/user-attachments/assets/3bdc8c35-7561-4182-ab3a-39c8e466493a" />

---

* Create a text procedure ***ZC*** for sales document header.

<img width="468" height="439" alt="Image" src="https://github.com/user-attachments/assets/02505ca2-2cde-4cc7-987d-52c5e7ccca51" />

---

<img width="567" height="326" alt="Image" src="https://github.com/user-attachments/assets/9d5492f1-4069-46f8-97c9-27222bdb6fd8" />

---

<img width="925" height="426" alt="Image" src="https://github.com/user-attachments/assets/17a46962-5c5a-4429-a224-1e3cb4a14956" />

---

* Create an access sequence.

<img width="611" height="297" alt="Image" src="https://github.com/user-attachments/assets/6e1e612e-29c6-49c8-bb54-e49b36db6579" />

---

<img width="928" height="397" alt="Image" src="https://github.com/user-attachments/assets/c7f254a8-cfa0-404c-87a2-8b0dab776495" />

---


* Assign the access sequence.

<img width="941" height="693" alt="Image" src="https://github.com/user-attachments/assets/6a413b9c-f924-4acb-8f1b-fc0919c4eb32" />


* From which text source the text would be copied to sales order, to define that we need to assign customer text in the below configuration.

<img width="984" height="350" alt="Image" src="https://github.com/user-attachments/assets/b4a713e2-db21-4281-99ad-82b68c3089d7" />

---

* Assign the sales order type to text id.

<img width="769" height="315" alt="Image" src="https://github.com/user-attachments/assets/6c248b3f-a8fa-4772-ba10-38d6fb7c7a70" />

---

* Now create a sales order ***CSOR*** and check if the text maintained in the customer master is sucessfully flowing into sals order ot not.


***Customer master text***

<img width="878" height="458" alt="Image" src="https://github.com/user-attachments/assets/4a1ac670-3a33-4d08-8a08-41f7dc8b6ec1" />

---

***Customer amster text successfully flowing into sales order***

* Goto header and then click on text.
  
<img width="890" height="370" alt="Image" src="https://github.com/user-attachments/assets/a57124f1-1557-4ea6-9f67-25ed84c76c19" />

---
