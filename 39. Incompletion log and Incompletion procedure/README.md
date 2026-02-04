## Incompletion log and Incompletion procedure

* Incompletion Procedure in SAP SD is a control mechanism that prevents you from saving or processing a document when important data is missing.

* In this document we are going to add PO number and storage location at item level as mandatory fields in sales order.

### Configuration steps for Incompletion procedure

* Spro Path -> SPRO -> Sales and Dist -> Basic functions -> Log of inomplete items -> Define incompletion procedure.

***For header PO number***

* Get the technical field name for PO number from the sales order header. Table name is VBKD and the technical name is BSTKD.

<img width="887" height="623" alt="Image" src="https://github.com/user-attachments/assets/8f51d8ac-c031-4d0d-9a36-e969d343f57b" />

---

* In the spro path stated above create a new incompletion procedure.
* Select A since we are creating an incimpletion procedure for sales header.

<img width="583" height="426" alt="Image" src="https://github.com/user-attachments/assets/63f41dfd-a2f7-4d16-aa86-66cca1d9735b" />

---

* Copy the standard incompletion procedure **11** for sales order and create your own incompletion procedure **Z9**.

<img width="540" height="370" alt="Image" src="https://github.com/user-attachments/assets/bb9f737d-ab25-4b57-baa8-5574cbae4276" />

---

* In the fields section create a new entry for PO number and enter the table VBKD and field name BSTKD, select the screen group from where the header PO number is and then select the sequence if the PO number is to be made mandatory at different stages like delivery and billing too.

* If you check the warning box the system will give a warnin pop up too along with incompletion log.

<img width="1328" height="502" alt="Image" src="https://github.com/user-attachments/assets/48098de1-c487-4f8e-8265-78206d1af77d" />

---

<img width="990" height="645" alt="Image" src="https://github.com/user-attachments/assets/adb955c4-807d-46ce-9105-98f3665bbd5c" />

---

<img width="867" height="234" alt="Image" src="https://github.com/user-attachments/assets/84330855-8bbe-4361-9843-2bfbfd3f0970" />

---

* Now assign the incompletion procedure to sales document, in same spro path ***Assign incompleteness procedure*** and then ***Assign procedures to sales document types***.
  
<img width="672" height="397" alt="Image" src="https://github.com/user-attachments/assets/0aa5d50b-bd8f-46b8-bfde-0d5177d3a234" />

---

* Now create a sales order and check if the PO number has become a mandatory field or not.
* Incoming warning message due to the warning check. 

<img width="677" height="714" alt="Image" src="https://github.com/user-attachments/assets/49bbae90-6793-48cb-9655-461d5d020935" />

---

<img width="526" height="381" alt="Image" src="https://github.com/user-attachments/assets/8a3b521e-538d-4668-abed-ad1093f86b03" />


***Configuration for item level field storage location***

* Create a incomplete procedure for item level in the same SPRO path stated above but this time select B for item level.

<img width="577" height="393" alt="Image" src="https://github.com/user-attachments/assets/0124769c-317b-4cc5-b97b-78dd5b0df78a" />

---

* Copy the standard item ***20*** and create your own procedure **A9**.
* Eneter the table VBAP and field LGORT for storage location. SCreen selection would be of shipping tab at level and sequence would be at sales order and delivery level.

<img width="1302" height="575" alt="Image" src="https://github.com/user-attachments/assets/b0b8954d-94fc-41e8-ad90-37ff4b0c025a" />

---

<img width="1248" height="616" alt="Image" src="https://github.com/user-attachments/assets/29800301-cea5-4ed5-9bdb-a99fc2ef6437" />

---

<img width="829" height="265" alt="Image" src="https://github.com/user-attachments/assets/ae3446b8-18f9-4d63-a5cb-8ddf8bb3d24e" />

---

* Now assign the incompletion procedure to sales document, in same spro path ***Assign incompleteness procedure*** and then ***Assign procedures to item categories***.

<img width="501" height="317" alt="Image" src="https://github.com/user-attachments/assets/c912fb14-a440-48f5-910d-084612243ad0" />

---

* Now create a sales order and check if the storage location has become a mandatory field or not.

<img width="914" height="718" alt="Image" src="https://github.com/user-attachments/assets/87fa3ec8-40da-4d83-9ca7-4ad7412dd08e" />

---

<img width="500" height="351" alt="Image" src="https://github.com/user-attachments/assets/6efa3074-874a-49a1-8a15-d282878ae150" />

---

***But what if we want to save the sales order without entering these mandatory fields?***

* We have these configurations at ***VOV8*** 
* Uncheck incomplete message in VOV8

<img width="728" height="689" alt="Image" src="https://github.com/user-attachments/assets/08043d61-7e7b-4cd2-8388-cc95d6e59414" />

---

* When the ***incomplete message*** is unchecked a dailog box would appear to save the sales order without entering the mandatory fields.

<img width="1210" height="642" alt="Image" src="https://github.com/user-attachments/assets/d3465f47-a733-40b1-8986-909b8ea74d24" />

---