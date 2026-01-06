## Pricing Procedure

* A pricing procedure in SAP Sales and Distribution (SD) is a structured set of rules that defines how the system calculates the final price of a sales document (such as a quotation, sales order, delivery, or billing document).
* Which price components are considered (e.g. base price, discounts, surcharges, freight, taxes)
* In which sequence they are calculated
* How each component is calculated (manual, automatic, percentage, fixed value)
* How values are subtotaled and posted (e.g. to G/L accounts)

***Pricing procedures are determined via combination of factors including:***

* Sales area (sales organization, distribution channel, division)
* Document pricing procedure (defined in the sales document type)
* Customer pricing procedure (defined in the customer master record)

***T code: OVKK***


## 16 fields in pricing procedure

* ***Steps***- Step number will specify the sequence of calculation in pricing procedure. It is also used in "From" and "To" fields to calculate the value.
* ***Counter***- We use counter if there's no space between two steps to add one more condition type.
* ***Description***- We use description to describe the condition type in sales document pricing which will be useful for end users.
* ***From***- Is also know as "Standard Base". From field will help to determine the base value for calculation the condition type value in sales document pricing.
* ***To***- Is used to cumulate the value from "From" field to "To" field.
* ***Manual***- Any condition type in pricing procedure marked as manual will not be calculated automatically by the system. The user has to enter the value manually in sales document pricing.
* ***Required***- Any condition type in pricing procedure marked as required will have to be entered mandatorily in sales document pricing otherwise the document will be incomplete.
* ***Statistical***- Any condition type when marked statistical will have two effects

    1. The condition type value will not be considered in net value, i.e., it would have no effect on the net value.
    2. The value of condition type will not be posted in accounting document.


* In standard the statistical condition types are VPRS, SKTO, PI01 and KUKU.

* ***Print***- This field controls whether to print the condition type into output printout or not.

    * If you don't want to print then leave the field 'Blank'.
    * If you want to print either enter 'X' or 'S'.
    * 'X' means if you want to print at item level and 'S' means if you want to print at header level.
    * All header conditions we maintain print field as 'S'.

* ***Subtotal***- It will be used for storing the value of the condition type in some temporary table and fields for the purpose of further caluclation.

* We do calculation in alternate calculation type and alternate base type.
* Subtotal will also be used to update the sales document value into credit management.

    1. Subtotal for credit management is "A".
    2. Subtotal for rebate agreement is "7".
    3. Subtotal for VPRS condition type is "B".

* ***Requirement***- requirement is a condition which system will check everytime while determining condition type into sales document. If the condition is fulfilling, then only condition type will determine into sales document. If the condition is not fulfilled then condition type will not determine into sales document.

* The standard requirement is **“2”**. Requirement 2 checks that the Pricing field in item category should be maintained with **“X”** or **“B”**.
* The requirement for **“VPRS”** condition type is **“4”**. Requirement 4 checks that the **Determine cost field** in item category should be check.
* The requirement for **“SKTO”** condition type is **“9”**. Requirement 9 checks that the **Cash discount field** in material master accounting view should be check.
* The requirement for **“R100”** condition type is **“55”**. Requirement 55 checks that the Pricing field in item category should be only **“B”**. That is the reason R100 appears only for **TANN** item category only TANN will have pricing **“B”**.
* **NRAB** condition type determines in free goods without item generation. Requirement is **“59”**.
* The requirement for **P01** condition type is **“22”**. Requirement 22 checks that the ordering company and delivery company should be different.
* For all rebate condition type the requirement is **"24"**. Requirement **"24"** checks that the documents should be billing documents. That is the reason rebate condition will determine only in the billing document.

### Alternate calculation type

* We use alternate calculation type if calculation part of condition type is not standard.
* Alternate calculation type is a formula.
  
  1. If you maintain formula in alt calculation type then the system will calculate and proposes a value for the condition type.
  2. If you maintain formula in calculation type, then no need to maintain condition record because the system is directly proposing a value for the condition type.

### Alternate base type

* The standard base type is "From" field, we use alternate base type when the base value of the condition type is not standard.
* Alternate base type is also a formula.
  
  1. If you maintain formula in alt base type then the system will calculate and proposes a base value for the condition type.
  2. If you maintain formula in base type, then no need to maintain condition record because the system is directly proposing a value for the condition type.

**Example:** Freight is calculated based on the weight and not on the base price.
Hence we use the **“Routine No:13”** to calculate on **Gross Weight** & **“Routine No:12”** to calculate on the **Net Weight** to the freight condition type **KF00**.


### Account key

* Account key is one of the parameter to determine revenue G/L account while posting invoice values into accounting.

* Any conditions, if it is not statistical then you have to maintain account key otherwise system will not generate accounting document.

### Accruals 

* Keeping some money aside from each transaction into provisional account to meet the future requirement of rebate settlement.

