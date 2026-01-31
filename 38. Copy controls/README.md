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
