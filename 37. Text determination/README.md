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

***Customer master text successfully flowing into sales order***

* Goto header and then click on text.
  
<img width="890" height="370" alt="Image" src="https://github.com/user-attachments/assets/a57124f1-1557-4ea6-9f67-25ed84c76c19" />

---

### Text configuration for delivery

* Go to t code - VOTXN nad  create a text type ***ZCT2***

<img width="558" height="281" alt="Image" src="https://github.com/user-attachments/assets/c03e7a85-dc1e-4141-bf42-f934e88ad642" />

---

* Now create one text procedure ***ZT***

<img width="537" height="308" alt="Image" src="https://github.com/user-attachments/assets/b81c3620-34ed-43b0-94df-32e57f02c7e2" />

---

<img width="904" height="290" alt="Image" src="https://github.com/user-attachments/assets/32f2a98f-1bae-4bed-9788-75185287093e" />

---

* Create a new access sequnece ***333***

<img width="527" height="292" alt="Image" src="https://github.com/user-attachments/assets/8a0959f2-1ced-4766-aacd-47d19fe4fa54" />

* Make sure you assign the access equnece after creation

<img width="982" height="596" alt="Image" src="https://github.com/user-attachments/assets/4276d2b4-17fa-4e19-b507-82350ad533e3" />

---


* We need to copy the text from sales order with text id ***ZCST*** so assign it.


<img width="899" height="300" alt="Image" src="https://github.com/user-attachments/assets/6939b16b-37c2-4836-bccd-9af61ce6f7e0" />

* Assign the delivery type to text procedure.

<img width="606" height="351" alt="Image" src="https://github.com/user-attachments/assets/d1f89fc5-c637-4122-9477-27ffb962e0e5" />


* Now try to create a delivery and see if the text is flowing in the header -> text section of delivery

<img width="619" height="357" alt="Image" src="https://github.com/user-attachments/assets/83680243-991f-495d-b629-7e3b43b1f7f9" />

---

### Billing text configuration


* Goto T - code: VOTXN and create a text id ***ZCT3***.

<img width="564" height="587" alt="Image" src="https://github.com/user-attachments/assets/829b14b9-27c8-4179-aa18-5bf368858b01" />

---

<img width="467" height="277" alt="Image" src="https://github.com/user-attachments/assets/2463b7e2-eaee-4870-a40e-3c3da69de8e4" />

---

* Now create a text procedure ***ZD*** and a new access sequence ***555***

<img width="559" height="548" alt="Image" src="https://github.com/user-attachments/assets/71138ee3-89f0-4a3e-bbe7-7f56643af292" />

---

<img width="608" height="393" alt="Image" src="https://github.com/user-attachments/assets/0d520aed-a993-43d0-9c7a-e2648c8e4670" />

---

<img width="945" height="345" alt="Image" src="https://github.com/user-attachments/assets/6fc411b6-e733-46f1-a1e0-407ac856b626" />

---

<img width="522" height="313" alt="Image" src="https://github.com/user-attachments/assets/64b44031-72c8-411c-9a35-1941673583fb" />

---

* ***imp*** incase if the text is to be copied from delivery instead of sales order just change the text id from ***ZCST*** to ***ZCT3***.

* Ensure that when copying from delivery doc the delivery text check in ***VOFA*** is checked. In this case we  won't need it as we are copying from sales order.

<img width="648" height="699" alt="Image" src="https://github.com/user-attachments/assets/9d1e59db-fc69-4b8d-bf1d-184b94c870ff" />

<img width="911" height="284" alt="Image" src="https://github.com/user-attachments/assets/542625a1-cb53-4eb4-869b-62da3c501c44" />

---

<img width="643" height="331" alt="Image" src="https://github.com/user-attachments/assets/01f613ea-585e-4fae-8b84-2671a9b04d30" />

---

* Now create a billing doc and check if the sales document text is being configured in billing document.

<img width="720" height="353" alt="Image" src="https://github.com/user-attachments/assets/1dd36632-75d0-46dc-8262-7ad70d2560c8" />

---

### Material master text configutaion

* Maintain a text in ***sales text*** tab of material master.

<img width="900" height="637" alt="Image" src="https://github.com/user-attachments/assets/d720faa1-7da1-4ffc-a88f-f6f085f1ba3f" />

---


* Now go to ***VOTXN*** and select item this time.

<img width="524" height="624" alt="Image" src="https://github.com/user-attachments/assets/d106e16d-60ad-4884-9eb1-275e0b7322bf" />

---

* Now create a text type ***ZCST***

<img width="371" height="261" alt="Image" src="https://github.com/user-attachments/assets/cf65bafc-356f-4e57-85a9-39de408ba8d0" />

---

* Create a procedure and assign access sequence and everything.

<img width="647" height="309" alt="Image" src="https://github.com/user-attachments/assets/02156b6a-cb70-491e-b69a-672ebb75ee43" />

---

<img width="966" height="322" alt="Image" src="https://github.com/user-attachments/assets/58c84137-10ff-4615-b51a-98c173f880a3" />

---

<img width="707" height="421" alt="Image" src="https://github.com/user-attachments/assets/caf886fe-ffc6-4e50-ad40-949e0a12489d" />

---

<img width="951" height="291" alt="Image" src="https://github.com/user-attachments/assets/1a4f8bfa-8b7d-4ddf-adce-e37f7c5d48fd" />

---

<img width="544" height="331" alt="Image" src="https://github.com/user-attachments/assets/094e95de-8fc4-4986-a7e0-45c14ea25a26" />

---

<img width="828" height="355" alt="Image" src="https://github.com/user-attachments/assets/3569c64e-bf09-42ed-9a44-05a822a913de" />

---

* SAME PROCESS APPLIES FOR DELIVERY AN THEN FOR BILLING ITEM LEVEL.
