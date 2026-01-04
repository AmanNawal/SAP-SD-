## Condition type fields

---

<img width="860" height="653" alt="Image" src="https://github.com/user-attachments/assets/7a7e259d-550f-4e4a-b3fe-8d5ac33ce97c" />

---

### Condition class

* Condition class defines the business role of a condition type and controls how SAP processes it in pricing, taxes, and accounting.
* Condition class represents the type of condition, whether it is a price, discount/surcharge, tax, freight, etc.
* It helps in categorizing the condition types based on their functionality in pricing.

Hello 👋

In **SAP SD pricing**, the **Condition Class** in **Condition Type (V/06)** defines the **business meaning and technical behavior** of a condition. It tells SAP **what kind of pricing element** the condition is and **how it should be treated** in pricing, account determination, and follow-on processes.

### Common Condition Classes and Their Meaning

| Condition Class              | Meaning                 | Typical Use        |
| ---------------------------- | ----------------------- | ------------------ |
| **A – Price**                | Base price              | PR00               |
| **B – Discount / Surcharge** | Discounts or surcharges | K004, ZDIS         |
| **C – Freight**              | Freight charges         | KF00               |
| **D – Taxes**                | Tax conditions          | MWST               |
| **E – Costs**                | Internal cost           | VPRS               |
| **F – Rebate**               | Rebate conditions       | BO01               |
| **G – Cash Discount**        | Cash discount           | SKTO               |
| **H – Statistical**          | Statistical values      | Informational only |


### Calculation type

* It defines how the condition value is calculated.
* It can be a percentage, fixed amount, or quantity-based etc.
* For example the base price value for our order is ***100/L***, so when we create a sales order worth of quantity 20L the total base price will be calculated as ***100 * 20 = 2000***.
* This is because we have a Calculation type maintained as ***C*** which stands for quantity base calculation.

---

<img width="1159" height="641" alt="Image" src="https://github.com/user-attachments/assets/2a5f1f24-f562-4cf8-bb22-af0d9ce7afdb" />

---

* Similarly for our discount the calculation type is ***A*** which stands for percentage base calculation.
* So the discount would be calculated taking base price into consideration, moreover the discount percentage is ***10%*** so the discount value would be calculated as ***2000 * 10 / 100 = 200***.

---

<img width="1257" height="666" alt="Image" src="https://github.com/user-attachments/assets/5dd10186-19b9-4d6d-bb03-f440243f446b" />

---

### Plus minus

* It defines whether the condition value is to be added or subtracted in the pricing procedure.
* A base price condition will have the ***plus minus*** value as ***A*** or vacant which means the value will be added to the total price.
* A discount condition will have the ***plus minus*** value as ***B*** which means the value will be subtracted from the total price in the pricing section.

---

<img width="717" height="392" alt="Image" src="https://github.com/user-attachments/assets/1da3a3c4-89aa-4379-98b3-85a60d3091ee" />

---

<img width="901" height="332" alt="Image" src="https://github.com/user-attachments/assets/4b0ff495-12fa-49fe-b651-51b37edcbd0c" />


---

### Condition category

* Condition category identifies special pricing conditions and activates predefined SAP logic such as tax, freight, rebate, or cash discount handling.

* Identifies special condition types
* Activates specific SAP standard logic
* Controls integration with:
* Taxes
* Freight
* Rebates
* Cash discounts
* Cost conditions


### Rounding rule

* It defines how the condition value is rounded off.

---

<img width="1046" height="651" alt="Image" src="https://github.com/user-attachments/assets/fd2d1f7c-ca2e-4337-84c8-7d41b35f8735" />

---


### Manual entry

* It defines whether the condition value can be manually changed during document processing.

---

<img width="963" height="706" alt="Image" src="https://github.com/user-attachments/assets/d13a5195-937f-4acf-ad6f-8867e0b3524a" />

---

* When the entry is changed from ***C - Manual entry has priority*** to ***D - Not possible to process manually*** we can see that the condition section is no longer accepting manual entries, it's referring only the condition records maintained for that condition type.

---

<img width="1085" height="656" alt="Image" src="https://github.com/user-attachments/assets/6a05a9cf-a4e8-4465-a466-4b728a4f5776" />

---

### Header and item condition

* The following checkboxes define whether the condition type is applicable at header level or item level in sales documents.

* As we can see below initially the conbdition is only applicable at item level and when we enter this condition type at header level it throws an error.

---

<img width="720" height="684" alt="Image" src="https://github.com/user-attachments/assets/2af0e6c2-9710-4615-a158-73761be72b95" />

---

<img width="710" height="715" alt="Image" src="https://github.com/user-attachments/assets/870cd8f5-63e6-4c9d-b864-3ee54cdf8b80" />

---

* But when we change the settings to make it applicable at header level also we can see that the condition is accepted at header level.

---

<img width="740" height="690" alt="Image" src="https://github.com/user-attachments/assets/d2abfbc1-d4e8-49f8-9c90-78addeac2c1a" />


---

<img width="1100" height="593" alt="Image" src="https://github.com/user-attachments/assets/029c9d51-bfdc-4f19-9014-38133c6cbb55" />

---


* ***Delete*** -  allows us to delete the condition type from pricing section, for example initialy delete was not marked in condition type and when we tried to delete the condition from pricing section it threw an error.


---

<img width="1142" height="628" alt="Image" src="https://github.com/user-attachments/assets/f0d13169-f4cd-4b61-b8a4-7b331300fd6f" />

---

* But when we mark the delete checkbox in condition type and try to delete the condition from pricing section it allows us to delete the condition.

---


* ***Amount/percent*** - allows us to change the condition amount in the pricing section if checked.

---
<img width="1325" height="665" alt="Image" src="https://github.com/user-attachments/assets/75f64f0a-ab10-4239-8adc-0e095e41ab6d" />
---


* ***Value*** - allows us to change the condition value in the pricing section if checked.

---
<img width="1325" height="665" alt="Image" src="https://github.com/user-attachments/assets/f7866188-e74d-46d3-8b34-8116ce642ec7" />
---

***Applies for qty relation and calculation types as well***