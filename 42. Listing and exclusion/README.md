## Listing and exclusion

### 1. Listing

**Definition**
**Listing** means that **only specific materials are allowed** to be sold to a customer.
If a material is **not listed**, it **cannot be entered** in sales documents for that customer.

* **SPRO -> Sales and distribution -> Basic functions -> Listing and exclusion**

**Purpose**

* Restrict customers to an approved assortment
* Control contract-based selling
* Enforce customer-specific product ranges

**Example**
Customer A is allowed to buy **only**:

* Material M1
* Material M2

If M3 is entered in a sales order → **system error**

**Key Characteristics**

* Positive control (allowed list)
* Strong restriction
* Material must be explicitly assigned to the customer

---

### 2. Exclusion

**Definition**
**Exclusion** means that **specific materials are blocked** for a customer.
All other materials can be sold **except** those excluded.

**Purpose**

* Block discontinued products
* Prevent sales due to legal or regulatory reasons
* Temporarily stop selling certain products

**Example**
Customer B can buy all materials **except**:

* Material M5

If M5 is entered in a sales order → **system error**

**Key Characteristics**

* Negative control (blocked list)
* Less restrictive than listing
* Only excluded materials are restricted

---

## 3. Comparison: Listing vs Exclusion

| Aspect                   | Listing                        | Exclusion               |
| ------------------------ | ------------------------------ | ----------------------- |
| Control type             | Positive (allowed only)        | Negative (blocked only) |
| Restrictiveness          | High                           | Low                     |
| Typical use              | Contract or assortment control | Product blocking        |
| Materials not maintained | Not allowed                    | Allowed                 |

---

## 4. Where Listing/Exclusion Is Maintained

### Master Data

* **Customer–Material Info Record**

  * Transaction: `VD51` / `VD52` / `VD53`

### Configuration of Listing/Exclusion


* Goto the specified path above and create a new condition table ***Maintain condition table for listing/exclusion***.

<img width="818" height="649" alt="Image" src="https://github.com/user-attachments/assets/23cab567-2c8c-4b60-9f07-a38ed8bf2838" />

---

<img width="726" height="251" alt="Image" src="https://github.com/user-attachments/assets/a9eb8dae-fdf2-4263-9843-c3b24d3137ce" />

---

* Now create an access sequence in the same SPRO path.

<img width="827" height="372" alt="Image" src="https://github.com/user-attachments/assets/cd994352-60b7-4498-977c-213d641dabdd" />

---

<img width="659" height="299" alt="Image" src="https://github.com/user-attachments/assets/200df764-77d3-4dde-a88d-b05eef0ce419" />

---

<img width="563" height="286" alt="Image" src="https://github.com/user-attachments/assets/bfc56e60-98d7-4e75-94fa-c14484632ea8" />

---

* Now in the same SPRO path create a new condition type for listing/exclusion by clicking on ***Maintain listing/exclusion types***. Assign the access sequence created to these condition types.


<img width="768" height="438" alt="Image" src="https://github.com/user-attachments/assets/8847f64d-f90d-48b5-b6f7-af40b52ca546" />

---

* Create a new procedure in the same SPRO path. Indivisually assign the condition types created to this procedures.

<img width="536" height="332" alt="Image" src="https://github.com/user-attachments/assets/8a6a6743-3784-4d64-a8d4-46fe45df7e01" />

---

<img width="700" height="397" alt="Image" src="https://github.com/user-attachments/assets/ec43707c-ee2a-4ee4-9c37-da373ec5f463" />

---

<img width="717" height="391" alt="Image" src="https://github.com/user-attachments/assets/a919cb3e-9eda-4885-a928-b1fcfe03aa96" />

---

* Next step would be to assign the procedure to sales document type, so click on ***Activate listing/exclusion by sales document type***

<img width="723" height="384" alt="Image" src="https://github.com/user-attachments/assets/4ed48c1b-5abb-494d-985b-ab003ccd1b92" />

---

* Next would be to create condition records for listing and exclusion T code - ***VB01***
* The list contains only 2 materials wi=hich are 43A and 50A, so if we try to enter any other material in the sales order for this customer, the system will throw an error message.

<img width="869" height="429" alt="Image" src="https://github.com/user-attachments/assets/2306af28-e797-4f16-803a-3ffde24eb3b5" />

---
