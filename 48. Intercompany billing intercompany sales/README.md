## Intercompany billing intercompany sales

* Whenever customer places an order to company, if stock is not available in ordering company then we are informing to parent company to dispatch the goods to customer. Then parent company will send goods to customer and raising invoice to the ordering company then ordering company will raise invoice to customer.

In SAP while creating sales order we have to give delivering company plant, delivering company will dispatch goods to customer, delivering company will raise invoice to ordering company, then ordering company will raise invoice to customer.

Ordering company: **YO10**

Delivering company: **Rush**


* That means in sales order the copany code ***YO10*** will be used but the plant will be from ***RUSH*** company code, i.e. the plant would be assigned to ***RUSH*** company code is used in sales order.
* Delivery to the customer would be done by parent company.

**Master data and configuration**

* Extend the material to both the plants
* Create ordering company as customer with delivering sales area
* Delivering company plant we have to assign to ordering company sales line
* **SPRO → S&D → billing → intercompany billing → define order types for intercompany billing**
* Assign organisational unit to the plant: Assign delivering plant and delivering sales area
* Define internal customer number by sales org
* Place **PI01** condition type in ordering company pricing procedure
* Assign pricing procedure **ICA001** to the combination of delivering company
* Maintain condition record for **PI01** condition type


### Process flow

**VA01 -> VL01N -> VF01 -> VF04**

## Configuration

* Create ordering company as customer with delivering sales area.

<img width="516" height="369" alt="Image" src="https://github.com/user-attachments/assets/c0284d4b-5d1d-430c-a632-ca29cf1ed3c1" />

---

* Extend the material to both the plants

<img width="780" height="341" alt="Image" src="https://github.com/user-attachments/assets/f30de6cf-f2ba-4f0f-b2fa-9e06f1cf31ed" />

---

<img width="780" height="327" alt="Image" src="https://github.com/user-attachments/assets/9212da44-96a7-416c-93be-d288304aadb3" />

---

* Delivering company plant we have to assign to ordering company sales line


SPRO -> Enterprise structure -> assignment -> sales and dist -> assign sales - org distribution chnl - plant

<img width="580" height="469" alt="Image" src="https://github.com/user-attachments/assets/47b88886-6859-4c55-a94b-f389c4592e35" />

---

<img width="713" height="357" alt="Image" src="https://github.com/user-attachments/assets/36b31877-c26a-4f81-ae0b-789040d38ddf" />

---

* **SPRO → S&D → billing → intercompany billing → define order types for intercompany billing**

<img width="580" height="399" alt="Image" src="https://github.com/user-attachments/assets/98f8b7ad-52e1-4f75-875a-c07548fbd929" />

---

* In the same SPRO path as above, Assign organisational unit to the plant: Assign delivering plant and delivering sales area. Assign delivering plant with delivering sales area.

<img width="622" height="461" alt="Image" src="https://github.com/user-attachments/assets/c7c7e04e-9292-4772-affe-003a562cb71c" />

---

* In the same SPRO path as above, define internal customer number by sales org

<img width="640" height="386" alt="Image" src="https://github.com/user-attachments/assets/4368dea6-fb95-4fda-a959-b09855326d09" />

---

* Place **PI01** condition type in ordering company pricing procedure in V/08.

<img width="757" height="404" alt="Image" src="https://github.com/user-attachments/assets/f9b15721-baea-4a76-93cb-20b0faf8ae57" />

---

* Assign pricing procedure **ICA001** to the combination of delivering company in OVKK T code.

<img width="625" height="423" alt="Image" src="https://github.com/user-attachments/assets/80f22e4c-4f83-4607-87b0-c50e1d7b2fb0" />

---

* Maintain condition record for **PI01** condition type

<img width="788" height="366" alt="Image" src="https://github.com/user-attachments/assets/5a9f1625-4006-4d46-85b2-b53b4532280b" />

---


* Now create a sales order in T code - VA01. Give the delivering plant from delivering company in the sales order.

<img width="779" height="411" alt="Image" src="https://github.com/user-attachments/assets/7287004f-ca3b-4e5f-bcc5-1df775eecf2d" />

---

* Ensure IC condition is flowing into the sales order.

<img width="721" height="408" alt="Image" src="https://github.com/user-attachments/assets/9f6d04d9-9978-479d-849a-c9a92d419619" />

---

* Now do delivery, and post goods you will notice that the stock is reduced from plant RUSH which is the delivering plant in MMBE T code.

* Now create an invoice F2 in VF01, now in order to create IC billing doc open billing due list VF04, and paste the delivery there. Click on intercompany billing checkbox and the execute, now select indivisual billing to create an intercompany invoice.





