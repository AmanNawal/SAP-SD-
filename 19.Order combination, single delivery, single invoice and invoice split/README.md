## Order combination, single delivery, single invoice and invoice split

* Order combination allows us to combine multiple sales orders into a single delivery.

### Pre-requisites

* In customer master the ***Order combination*** should be checked.

<img width="984" height="681" alt="Image" src="https://github.com/user-attachments/assets/e420395d-dca8-4fe3-86a8-6d70fc34b388" />

---

* Ship to party should be same for all the orders.
* Incoterms should be same for all the orders.
* Shipping point of all the orders should be same.


## Configuration to create a single delivery for multiple orders

* We use T code ***VL10A*** to create a single delivery for multiple orders.
* Create two order keeping the prerequisites in mind.


<img width="957" height="644" alt="Image" src="https://github.com/user-attachments/assets/854c0da4-592a-461d-aa3e-89074f1d3a15" />

---

* Select the orders to combine for a single delivery.

<img width="1047" height="353" alt="Image" src="https://github.com/user-attachments/assets/f3de086a-82b2-4c71-984f-5e9638d43502" />

---

* Now click on ***Background***, after this the delivery is created but we dont know the number.

<img width="1042" height="446" alt="Image" src="https://github.com/user-attachments/assets/e81d645f-2465-4cb5-92aa-07faa9767fa0" />

---

* Again select all and now click on ***log for delivery creation*** to see your delivery document.

<img width="1031" height="398" alt="Image" src="https://github.com/user-attachments/assets/08057733-35d3-48c6-a732-3cf3eaac8fd6" />

---

* Now select one parameter in screen and click on documents.

<img width="1289" height="584" alt="Image" src="https://github.com/user-attachments/assets/c91d0118-e702-4cf1-888a-e6fd25132393" />


---

* Here you can see your document number.

<img width="1008" height="335" alt="Image" src="https://github.com/user-attachments/assets/488ca8c4-bdd3-4310-911e-12888db8a737" />

---


* You can see items of both the orders being included in the delivery.

<img width="1364" height="644" alt="Image" src="https://github.com/user-attachments/assets/0ecc9103-9b98-45b5-9ac6-43d1b4bd1fdc" />


***Note - incase if the VL10A does not work, we would see 2 delivery documents in the logs instead of 1***


## Multiple deliveries and single invoice

***Pre-requisites - ***

* Billing date, payer and payment terms should be same. To do collective billing.
* We can perform collective billing using ***VF01*** or even ***VF04***.
* Go to ***VF04*** and click on collective billing

<img width="1365" height="508" alt="Image" src="https://github.com/user-attachments/assets/fe7748ef-4585-4aac-8354-368bf0b2e563" />

## Multiple deliveries single invoice not working as we have account determination error


## Single delivery multiple invoices

* Create a sales order with 2 different items.
* Now do delivery and PGI
* In invoice, select each item seperately and invoice them indivisually. By clicking on selection list

<img width="1220" height="552" alt="Image" src="https://github.com/user-attachments/assets/61357979-b0ac-4a9f-8792-4e485fdcc601" />


---

* Now select the item and click on copy and then save which would create a seperate invoice for the item.

<img width="906" height="672" alt="Image" src="https://github.com/user-attachments/assets/6462bb90-60ce-4d22-ba32-13c34807a17d" />

---

* Multiple invoices created for a single delivery

<img width="967" height="457" alt="Image" src="https://github.com/user-attachments/assets/aeb92c62-102a-4489-9e80-aa5a7ef21dd9" />

---

***We have routines in VTFL copy control which allows invoice split***


<img width="1082" height="644" alt="Image" src="https://github.com/user-attachments/assets/5bc9915c-feb9-4536-98ab-3bceb36b88cd" />





