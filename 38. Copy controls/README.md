## Copy controls

* Copy control comes into picture if you are creating a document with reference to another document.

**Purpose of copy control**

i. It will help to copy the data from source document to target document.
ii. It controls whether to create a document with reference to another document or not.

**We have different types of copy controls**

* **IN – QT** ---- Inquiry to Order
* **QT – OR** ---- Order to Order
* **OR – LF** ---- Order to delivery
* **LF – F2** ---- Delivery to invoice
* **F2 – S1** ---- Invoice to invoice
* **OR – F2** ---- Order to invoice
* **F2 – RE** ---- Invoice to Order

Order → **A**
Delivery → **L**
Invoice → **F**

**T-codes of copy controls**

* Order to Order ----- **VTAA**
* Order to delivery ----- **VTLA**
* Delivery to invoice ----- **VTFL**
* Invoice to invoice ----- **VTFF**
* Order to invoice ----- **VTFA**
* Invoice to Order ----- **VTAF**


### ***Order to Order copy requirements***

**Order to Order copy requirements**

**Header Requirement 001 checks that**

1. Is the reference document complete or not?
2. Is the currency is same or not
3. Check the validity period of reference document.
4. customer copy’s same
5. Is the sales area same or not?

**Header Requirement 002 Checks**

* If you want to change target customer, then we have to maintain **002**.

**Item requirement 301 checks**

* The requirement 301 checks that do not copy the items which are fully referenced or rejected.



### Copy control working

* Here we will take example of data copy from Quotation ***CQT*** and Sales order ***CSOR***.
* The copy target is Sales order which represents ***A*** and the source is quotation which represents ***A***, so T code to used will be ***VTAA***.

<img width="878" height="482" alt="Image" src="https://github.com/user-attachments/assets/e116e2f9-6b0f-4950-825a-704b4f9ff2ca" />

---

* ***General header data*** - will copy the general header data from the source header. Controls copying of general header fields, such as:

  * Sales area
  * Document date
  * Pricing date
  * Currency
  * Incoterms
  * Typical table: VBAK

* ***Business data header*** - Controls copying of business-related data, such as:

  * Payment terms
  * Shipping conditions
  * Billing block
  * Customer group
  * Also stored mainly in VBAK / VBKD

* ***Partner header*** - Controls copying of partner functions:

  * Sold-to
  * Ship-to
  * Bill-to
  * Payer
  * Table involved: VBPA

* ***Copying requirement -001*** - Will check if the reference document is completed or not.

    * Is the currency same or not.
    * Checks the validity period of the reference document.
    * The customer being copied is same or not.
    * Is the same area similar.

* ***Copy item number check*** - ensures that the item number from source to target is kept same, it is possible that quotation may have item numbers in format 5,10,15 whereas sales order may have it in the following sequence 10,20,30. To ensure the same item number is copied to sales order 5,10,15 we have to check this flag.

* ***Complete reference*** - If checked, does not allows the item in the destination document to be deleted.

<img width="1193" height="684" alt="Image" src="https://github.com/user-attachments/assets/189efb47-2430-4b3a-91d8-31a44be140c0" />

---


### Copying configuration at item level


<img width="921" height="509" alt="Image" src="https://github.com/user-attachments/assets/f0888645-ef8a-4f86-8900-a958dbfcfb89" />

---



### **DataT 151 – General item data**

Copies:

* Material
* Description
* Plant
* Storage location
* Item texts
* Item-level flags

---

### **DataT 102 – Business data / item completion**

Copies:

* Shipping data
* Delivery relevance
* Item completion indicators
* Sales-related item status


---

### **DataT 002 – Partner item**

Copies:

* Item-level partners (e.g. ship-to if item-specific)

📌 If not copied → partners are redetermined from header

---

### **FPLA 251 – Conditions**

Copies:

* Pricing conditions
* Discounts / surcharges
* Manual pricing (depending on pricing type)


---


### **Copying requirements: 301**

This is a **requirement routine** that checks whether copying is allowed.

Typical checks:

* Reference document status (e.g. quotation still valid)
* Item not fully referenced. which means quotation had 100 quantity for which sales order worth 100 quantity have already been created so there's nothing to copying now because 100 quantity is already completed.
* No rejection reason, if there's a reason of reection for a item then it won't be copied.


---


###  **Copy schedule lines**

* Copies:

  * Requested delivery date
  * Confirmed quantities
  * Schedule line categories


---

###  **Update document flow**

* **X (checked)** = Document flow is updated
* Creates linkage in **VBFA**
* Required for:

  * Status updates
  * Subsequent processing
  * Reference tracking

Never deactivate in productive systems.

---

### **Do not copy batch**

* Prevents batch numbers from being copied
* Used when:

  * Batch determination must run again
  * Source batch is not valid for target

---

### **Configuration**

* Relevant for **configurable materials (VC)**
* Copies configuration characteristics
* Needed for KMAT scenarios

---

### **Reexplode structure / free goods**

* Re-determines:

  * BOM explosion
  * Free goods
* Used when conditions or material determination must be recalculated

---

##  Quantity & Pricing Control

### **Pos./neg. quantity**

* When we completely use the quantitites of the parent document lets take quotation (100 quantity) so if we create sales orders worth of 100 quantity in total the quotation will show status as complete in document flow this is when the value ***+*** is maintained, which means all the sales order quantities are being added and compared to quoatation quantity which will be complated once quantity is matched.
* In case ***-*** is maintained then the quoattion would show status open even when quantity is completely referenced.
* When maintained with ***-*** also allows us to exceed the reference quantity of quotation, that means you can create sales order worth more quantity in total then quotation quantity. 
* Rarely used in standard sales scenarios

---

### **Pricing type (A)**

* This field would tell us to carry out new pricing or not based of quotation or parent document, in case we want the conditio type values to be exact same as parent document or we would like them to be updated with latest value when copied.

**Pricing Type A = Copy pricing elements and re-determine taxes**

* Prices copied from quotation
* Taxes recalculated
* Manual conditions retained

Common alternatives:

* **B** – Carry out new pricing
* **C** – Copy manual pricing only
* **G** – Copy pricing exactly

---

## Sales order to Delivery copy requirements


 <img width="874" height="437" alt="Image" src="https://github.com/user-attachments/assets/d9584113-e953-402b-8c95-66493f450c8b" />

 ---


**Order to Delivery copy requirements**

**Header Requirement 001 checks that is complete or not only then it proceeds with copying**

* The reference document should be an order.
* Order should not block for credit.
* Status profile

**Header Requirement 051 checks the following only then it proceeds with copying**

* Delivery type should be same for all the orders.
* Billing type should be same for all the orders.
* Sales organisation should be same for all the orders.

**Item Requirement 101 checks the following only then it proceeds with copying**

* Shipping point
* Delivery status
* Item status profile


### Delivery to invoice copying requirement


<img width="287" height="246" alt="Image" src="https://github.com/user-attachments/assets/5e8a71ff-b4ba-4913-83f7-dc7d7115189c" />

---


**Delivery to Invoice copy requirements**

**Header Requirement 003 checks that the following requirements are completed only then it proceeds with copying**

* Billing block
* Billing status
* PGI status
* POD status
* Incomplete status

**Header Requirement 011 checks that**

* Create invoice without PGI

**Header Requirement 009 checks that**

* Proforma invoice

**Item Requirement 004 checks that**

* Billing block
* Billing status

***Assignment and reference number*** - are the 2 fields in billing document header data which rae referenced from parent documents, these two fields allws us to choose from document do we want to copy assignment number and reference number.


### Billing copying configuration at item level


* ***Bill quantity*** - it tells us against which document are we creating billing doc for example delivery and sales order.

* ***price source*** - prices are to be copied from order, delivery or from PO. This fields decides that.

