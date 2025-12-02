## Free of charge and subsequent delivery free of charge


### Free of charge (Sales doc - FD)

* In SAP SD free of charge is used when goods or services rae provided to a customer without any billing value, but the documents are still needed in the system for tracking purposes, inventory management, or reporting.
* Is used when we provide samples or promotional items to customers without charging them.
* Replacedment of defective goods.
* Marketing campaigns where free items are given to customers.
* Gift to the customers.
* Since there's a possibility that we are providing the goods free of charge maybe for samples or promotion, there could be a situation where we can provide the base price of the material for free but the taxes and freight can be charged to the customer. 


### Configuraion


* Copy the standard sales doc type ***FD*** from VOV8 to create your own free of charge order type ***CFD***.
  
<img width="1365" height="710" alt="Image" src="https://github.com/user-attachments/assets/a0734f0e-7439-4ff9-b454-1c8c7ef0e92d" />

---

* Setup the sales area corresponding to your free of charge order type in t code ***OVAZ***.
* Now copy the standard item category ***KLN*** and create your own item category ***CKLN*** in t code ***VOV7***.

---

* Now create a new billing type for proforma invoice in t code ***VOFA*** by copying standard billing type ***F8 (delivery based)* or F5 (Order based)**.


***When we do free of charge process we do not want to bill the customer for the free items, in that case we create proforma invoice. Whose control is available in item category BILLING RELEVANCE - D (Proforma invoice) and the second control is the billing doc type itself in VOFA we can check billing doc type F5 and F8 in which we can find SALES DOCUMENT CATEGORY - U(Proforma invoice)***


<img width="1192" height="724" alt="Image" src="https://github.com/user-attachments/assets/21393559-31dc-4ed7-b4da-954bfddd156b" />


<img width="949" height="708" alt="Image" src="https://github.com/user-attachments/assets/ce45c215-8102-42bc-89c8-228036bfcbd4" />

---

* Now create a new delivery type for free of charge delivery in t code ***OVLK*** by copying standard delivery type ***LF (Standard delivery)*** and creating a new delivery type ***CSFL***.

---

* Now assign the billing and delivery document to sales order in VOV8.

<img width="847" height="699" alt="Image" src="https://github.com/user-attachments/assets/5540d3f7-0082-4572-8496-7819d7bb29e9" />

---

* Do item catgory determination for newly created free of charge order type in VOV4.

<img width="577" height="390" alt="Image" src="https://github.com/user-attachments/assets/5d1b13ff-962d-48c7-9553-2268fafdab49" />

---

### Subsequent delivery free of charge

* Unlike, Free of charge delivery subsequent delivery free of charge delivery is used to send goods to the customer as compensation. Because seomthing was wrong with original. Basically we replace or resend the goods to the customer without any charge.

* Subsequent delivery free of chatge must reference a previous order or delivery.

## Configuration

* Create a new sales document type for subsequent delivery free of charge by copying standard sales doc type ***SDF*** in t code ***VOV8*** and create your own sales doc type ***CSDF***.
* Use previously created free of charge item delivery document ***CSFL*** in this sales doc type as the concept of subsequent delivery free of charge is based on free of charge delivery.
* Now assign the delivery document and billing document to newly created sales doc type in VOV8 ***CSFL*** and ***CF8***.
* Make sure that the sales area is setup in t code ***OVAZ*** for newly created sales doc type.
* We have a new sales doc type so we would have to determined item in VOV4 and schdule line in VOV5.
* Now define the copy control parameters in ***VTAF*** copy the pre existing configut=ration between ***CR*** and ***F2*** because similar how credit memo request is created wrt a invoice we have to reference the invoice and create a SDF sales document.
* Assign **G2N** intem cat target to source **CKLN** in the item cat section of copy control in .

* Now you can create subsequent delivery free of charge sales document by referencing the original invoice or delivery document.

