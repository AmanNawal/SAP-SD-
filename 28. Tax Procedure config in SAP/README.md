## Tax Procedure config in SAP

* Is the integration between SD and FI for tax calculation in sales documents.


### Step 1: Create a tax procedure

* Path: SPRO -> IMG -> Financial accounting -> Financial accounting global settings -> Tax on sales/purchases -> Basic settings -> Check calculation procedure.
* ***First step***: Create an access sequence, standard tax access sequence ***MWST***.
* Copy it and create a new access sequence ***ZCMW***.
* ***Next step***: In the same path, go to define condition types.
* Copy the standard condition type ***MWAS*** and create a new condition type ***ZZSG***.

---

<img width="935" height="274" alt="Image" src="https://github.com/user-attachments/assets/142ea341-0b96-4099-a018-9ab8979aafaa" />

---

<img width="871" height="312" alt="Image" src="https://github.com/user-attachments/assets/e7a57bf0-d4e9-4c34-b50c-cd25234f66ad" />

---

* Similary create tax condition types for ***IGST -- ZZIG*** and ***UGST - ZZUG*** tax condition types.

<img width="677" height="306" alt="Image" src="https://github.com/user-attachments/assets/543ecfae-e7ba-4b7b-adbf-765a19cf77c9" />

---

* ***Next step***: In the same path, go to Define procedure.
* Copy the standard tax procedure ***TAXINJ*** Sales tax india and create your own pricing procedure ***ZCTXIN***
* Assign the newly created condition types ***ZZSG ZZUG ZZIG*** to tax procedure.
* Assign account ket to ***MWS***

---

<img width="1017" height="532" alt="Image" src="https://github.com/user-attachments/assets/42cae455-dcbe-4e38-9291-874b245a118e" />

---

### Step 2: Assign tax procedure to country

* In the same SPRO path ***Assign country to calculation procedure***.

---

<img width="603" height="552" alt="Image" src="https://github.com/user-attachments/assets/840f8998-bcd3-4bca-bb3d-101811d5f627" />

---

### Define tax codes for sales and purchases

* Path: SPRO -> IMG -> Financial accounting -> Financial accounting global settings -> Tax on sales/purchases -> Calculation -> Define tax codes for sales and purchases.
* Give the country as IN and create a tax code ***ZC*** for IGST.
* Give the tax type as ***A*** Sales output tax, V stands for input mainly purchase related.

---
<img width="937" height="533" alt="Image" src="https://github.com/user-attachments/assets/0f9fd886-402e-44a5-ab35-adea4ac92f79" />
---

<img width="825" height="677" alt="Image" src="https://github.com/user-attachments/assets/afa2f05f-043b-42f7-ac96-b075bf33bf2c" />
---

<img width="828" height="642" alt="Image" src="https://github.com/user-attachments/assets/7e903637-e97f-49c1-b66b-25bb3768f31d" />

---

<img width="967" height="638" alt="Image" src="https://github.com/user-attachments/assets/06d2b422-50ec-48d1-b6af-80bd8580056d" />

---


### Step 3: Define tax accounts

* SPRO -> IMG -> Financial accounting -> Financial accounting global settings -> Tax on sales/purchases -> Posting -> Define tax accounts.