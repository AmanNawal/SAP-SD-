## Material determination ( T code - VB11)

* “Material Determination” It is process of substituting one product in place of other product.

* Spro path: -> Sales and Distribution -> Basic Functions -> Material Determination -> Maintain pre requisites for material determination

* Material determinarion follows conditio tenchniques which means we would ahve to define condition table, access sequence and condition type for material determination. We can also define the reason for substitution in the material determination process.

**Reason for substitution:**

* If the product is determined and coming with new product.
* If the product is not available.
* Combo packs (promotional activity).

Material determination is of two types:

1. **Manual** – In manual user will manually substitute the item.
2. **Automatic** – In automatic system automatically determine the substitute item.

Auto replacement substituted item will be displayed as sub item.

**Sub item again classified into two types:**

* Header pricing
* Item pricing

**Item category determination**

* Based on the outcome value maintained in substitutionr eason the system determines if the pricing is header ot item level.

If it header pricing

**Main material**

* Document type: **OR**
* Item category group: **NORM**
* Item usage: **PSHP**
* Higher level item categories: **Blank**
* Item category: **TAX**

**Sub material**

* Document type: **OR**
* Item category group: **NORM**
* Item usage: **PSEL**
* Higher level item categories: **TAX**
* Item category: **TAPS**


**If it is item price**

**Main material**

* Document type: **OR**
* Item category group: **Norm**
* Item usage: **PSA1**
* Higher level item categories: **Blank**
* Item category: **TAPA**

**Sub material**

* Document type: **OR**
* Item category group: **NORM**
* Item usage: **PSA2**
* Higher level item categories: **TAPA**
* Item category: **TAN**




### Configuration for material determination

* In the SPRO path specified above create a new table ***503***.

<img width="860" height="647" alt="Image" src="https://github.com/user-attachments/assets/d45a5ae6-a0d9-4fea-8dcc-3e82690e89bc" />

---

<img width="697" height="367" alt="Image" src="https://github.com/user-attachments/assets/5c83eca2-93e5-4d4e-a394-0a659d026a16" />

---

* Now create your own access sequence ***ZCSM***.

<img width="861" height="304" alt="Image" src="https://github.com/user-attachments/assets/a52cf0a5-041d-44d4-9a8e-40e52fdc6c72" />

---

<img width="550" height="270" alt="Image" src="https://github.com/user-attachments/assets/06f7b032-2ba4-439d-a2b8-5c3430899f3a" />

---

<img width="998" height="428" alt="Image" src="https://github.com/user-attachments/assets/1e0c4d9a-6f6e-4132-b9ec-67cf71c22d38" />

---

* Now create a condition type ***ZCSM*** for material determination.

<img width="745" height="364" alt="Image" src="https://github.com/user-attachments/assets/88c51db8-2ca5-49af-b7ca-9e7b536f4b22" />

---

* Create a procedure ***ZCSM*** as assign condition type to the procedure.

<img width="527" height="383" alt="Image" src="https://github.com/user-attachments/assets/b87da983-2697-4552-80ed-d78ad48afa94" />

---

<img width="823" height="407" alt="Image" src="https://github.com/user-attachments/assets/3d11f7ea-d240-4057-aba4-3944463a35e8" />

---

* In the same SPRO path assign procedure to sales document type.

<img width="604" height="574" alt="Image" src="https://github.com/user-attachments/assets/86ecb3df-22d5-4f31-bfc4-8785e8ee976f" />

---


* In the same SPRO path click on define substitution reason. CLick on new entries ***ZSCM***, here the entry field controls which material has to take the print out is it substited material or main material. Whereas, .the warning checkbox decides if a warning message should be pop up when the substitution happens.
 
* Strategy field controls what type of substitution is it, is it automatic or manual. 

<img width="853" height="401" alt="Image" src="https://github.com/user-attachments/assets/1b12f254-487e-4205-97ff-5409f50d9ef0" />

---

* Create a material determination T code ***VB11***

<img width="946" height="347" alt="Image" src="https://github.com/user-attachments/assets/9cd27d2b-86d3-4fbf-b20a-3020b1c474c7" />


---


* Now create a sales order with material ***3000000050A*** which would be substituted with ***3000000043A***.

<img width="940" height="715" alt="Image" src="https://github.com/user-attachments/assets/37beea83-7e46-403a-8d3d-27117ca7d586" />

---

<img width="829" height="655" alt="Image" src="https://github.com/user-attachments/assets/8a2e8aa4-10f4-4608-8c79-cbf8c9684673" />

---


***But what if there is a requirement in which we want to see both the substituded material and the main material in the sales order?***

* In the same SPRO path goto to ***define substitution reason*** and change the outcome from blank to A.

<img width="1089" height="595" alt="Image" src="https://github.com/user-attachments/assets/adbb9a27-4632-4e8f-be76-55c1ae0e7b17" />

---

* Now we have to do item category determination for the substituted item in ***VOV4***.
* 
<img width="509" height="392" alt="Image" src="https://github.com/user-attachments/assets/0d00923a-5b5c-4b50-8a8e-849b27dfa8ba" />

---

<img width="532" height="300" alt="Image" src="https://github.com/user-attachments/assets/2ab51f14-6d2c-480f-92a5-3969e491d48e" />

---

* Now create sales order again.

<img width="1161" height="564" alt="Image" src="https://github.com/user-attachments/assets/7cf217a8-a417-4c81-8636-fe2588151b3b" />

---

* Here TAX is the item which is relevant for billing whereas TAPS is not relevant for billing.
* The reason why first item has net value and the secondcond does not have any net values is because we have maintaine outcome as A in susbstitution reason which means header price(main item).

* Incase if the client does not want to show the main material we can keep the outcome as blank.
  
***Incase the user wants only the substituded item to be priced but wants to see both the materials in sales order***


* In the same SPRO path goto to ***define substitution reason*** and change the outcome from A to B.

<img width="1045" height="604" alt="Image" src="https://github.com/user-attachments/assets/ae9606a5-8f0e-4ced-91b9-f9e41d734eaa" />

---

* Ensure that the following item category determination is maintained in ***VOV4*** for the substitution reason.

<img width="547" height="212" alt="Image" src="https://github.com/user-attachments/assets/ea8eae89-07f7-49e2-b945-26a6e2cd66eb" />
---

<img width="531" height="238" alt="Image" src="https://github.com/user-attachments/assets/744c658c-2434-4f98-bc59-0dc588c879f6" />

---

* Create a sales order, in this case the substitute material with item category TAN is relevant for billing. Whereas, the main item with item category TAPA is not relevant for billing.

<img width="1134" height="687" alt="Image" src="https://github.com/user-attachments/assets/02184f14-d947-49bf-97f0-6c474207c2a5" />

---

<img width="1181" height="559" alt="Image" src="https://github.com/user-attachments/assets/34e27219-76e5-4b07-9dfb-8ab97a99db2e" />

---
