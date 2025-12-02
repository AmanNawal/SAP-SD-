## Free of charge and subsequent delivery free of charge


### Free of charge (Sales doc - FD)

* In SAP SD free of charge is used when goods or services rae provided to a customer without any billing value, but the documents are still needed in the system for tracking purposes, inventory management, or reporting.
* Is used when we provide samples or promotional items to customers without charging them.
* Replacedment of defective goods.
* Marketing campaigns where free items are given to customers.
* Gift to the customers.


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
* Do item catgory determination for newly created free of charge order type in VOV4.