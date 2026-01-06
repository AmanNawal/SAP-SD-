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
* Give the country as IN and create a tax code ***ZC*** for IGST, ***ZG*** for SGST and ***ZP*** for UGST.
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
* Find the account key ***MWS*** double click on it and enter standard charts of account ***INT***.

---
<img width="773" height="684" alt="Image" src="https://github.com/user-attachments/assets/09e2d4f0-7a6c-4148-9f6d-3e975f51070a" />
---

* Now assign G/L account with respect to tax code created above.

---
<img width="704" height="654" alt="Image" src="https://github.com/user-attachments/assets/be76b048-1ef2-45b3-8a0b-d399c994b74f" />
---

### Step 4: SD Work create condition type/pricing procedure/condition table

* We need to create tax condition types similar to the one created for tax posting.
* SD condition types are created in pricing (V/06) and are used for:

  1. Pricing calculation in sales documents..
  2. Displaying tax amounts during order processing..
  3. Integrating tax into the pricing procedure.23.

* FI condition types are created in Tax Procedure customizing (FI) and are used for: ***Difference b/w sd and FI condition types***

   1. Legal tax calculation logic
   2. Tax code determination
   3. G/L account posting
   4. Country-specific tax rules

* Goto ***V/06*** and copy the standard tax condition type ***MWST*** to create new condition type ***ZZSG*** for SGST, ***ZZIG*** for IGST and ***ZZUG*** for UGST.

* Assign the new created condition type to pricing procedure ***ZCSP***, just like below.

---

<img width="1062" height="569" alt="Image" src="https://github.com/user-attachments/assets/f17d2536-8756-47c2-9e81-3f4199e6f91e" />

---

* Now create a condition table for which takes the following fields as an input.

---
<img width="961" height="682" alt="Image" src="https://github.com/user-attachments/assets/437fde28-a512-4400-89d3-62d59986be4d" />

---

<img width="888" height="343" alt="Image" src="https://github.com/user-attachments/assets/16c89f27-4600-41d1-8380-7a283208148c" />

---

* Create one access sequence ***ZCTX*** for tax condition types in ***V/07***.
* Now assign the access sequence to the condition types ***ZZSG, ZZIG, ZZUG*** created above in ***V/06***.

### Step 5: Define tax determination rule in SD

* SPRO -> IMG -> Sales and distribution -> Basic functions -> Taxes -> Define tax determination rules.
* Will determine which conditions are visible at customer and material master.

<img width="749" height="554" alt="Image" src="https://github.com/user-attachments/assets/ee95510b-0425-42c0-9a3c-fbd2866dde93" />

* ***Next step***: in the same spro path, click on ***Define Tax relevancy of Master records***.
* Click on customer taxes and maintain the condition types created for taxes earlier.

<img width="918" height="545" alt="Image" src="https://github.com/user-attachments/assets/685f898d-c518-484f-b384-dcaee752ee38" />

---

* Now repeate the same for material taxes.

---
<img width="573" height="378" alt="Image" src="https://github.com/user-attachments/assets/4a2849d8-2d06-4a6a-abfa-60fa4a6aada6" />
---

### Now we can see all the taxes we assigned to country IN in customer master and material master.


---

<img width="1087" height="675" alt="Image" src="https://github.com/user-attachments/assets/72158462-224e-4281-81b7-9d47eb824ba2" />

---

<img width="760" height="702" alt="Image" src="https://github.com/user-attachments/assets/27aa0f0b-5185-4f5a-9f6a-a24458744402" />

---


### Create an order

* Create a sales order and check the analysis tab for tax conditions. (Create control code using t code - J1ID).

* Click on maintain

<img width="876" height="544" alt="Image" src="https://github.com/user-attachments/assets/2f9552dc-2daf-43d0-9d6a-3b5ff8f96877" />

---

* copy any of the existing control code and create your own just like below. Then assign that control code material master data(Foreign trade export).

<img width="704" height="315" alt="Image" src="https://github.com/user-attachments/assets/3330fdf1-c589-4c11-9d61-05b4e50ec2f5" />

---

<img width="795" height="682" alt="Image" src="https://github.com/user-attachments/assets/702b03fa-be28-4706-8515-a74621bebd1a" />

---


* ***Maintain condition records*** for tax condition types created above using t code ***VK11***.


<img width="1089" height="626" alt="Image" src="https://github.com/user-attachments/assets/ad154cd9-5ce4-45b4-9bb8-0d97d61b8788" />






