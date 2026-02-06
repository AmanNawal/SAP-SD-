## Free goods and free goods determination

**Free goods**

Offering the goods free of cost to the customer in relation to the main item.

Ex.: Any customer if he purchases “X” material of 100 quantities he will get “Y” material 20 quantities free.

Or any customer if he purchases “X” material of 10 quantities he will get “X” material 1 quantities free.

A free goods is two types: -

1. Inclusive
2. Exclusive

**Inclusive:** In inclusive the free goods quantity included in order quantity.

* In inclusive you can offer only same material as free goods
* Ex.: Offer is, if customer purchases “X” material of 23 qty he will get 6 qty of x material free included in the total 23 quantity, so he need to pay only for 17 quantity price instead of paying for 23 quantity.

**Exclusive:** The free goods quantity excludes from order quantity.

* Ex.: if customer purchases “X” material of 100 qty he will get “Y” material 10 qty free, so he need to pay only for 100 quantity he will get 110 quantity.
* In exclusive you can offer same material or different material as free goods.

**Path for configuration free goods**

**SPRO → S&D → basic function → free goods → condition technique free goods**

**Inclusive again further classified into two types:**

* **Free goods with item generation:**
  In inclusive with item generation the free goods item determine as separate line item and here **R100** comes into picture and make the free goods line-item value is zero. **R100** we need to assign our pricing procedure.

* **Free goods without item generation:**
  In free goods without item generation the free goods item will not determine as separate line item. Here **NRAB** condition type determines and deducts the value of free goods from main item value. **NRAB** we need to assign our pricing procedure.

---

**Item category determination for Free goods**

Main material: **OR → NORM → → TAN**

Automatic Free Goods: **OR → NORM → FREE → TAN → TANN**

**T-code for Free goods condition records:** **VBN1**

* **PRORATA:** In prorate basis system calculate the free goods quantity proportionally based on order quantity and from quantity.
  Ex.: Offer is minimum order quantity is 10 and after each 4 qty get 1 qty as free goods, so in this calculation rule if purchases 22 qty then get 6 qty free. That means for the left over 2 qty also system will propose 1 qty free even though it is not exactly 4 qty.

* **Unit reference:** In unit reference system consider from quantity as 1 unit and system checks the number of units in order quantity and on that system will propose free goods quantity.
  Ex.: Offer is minimum order quantity is 10 and after each 4 qty get 1 qty as free goods, so in this calculation rule if purchases 22 qty then get 5 qty free. That means for the left over 2 qty system will not propose free goods because it is not exactly 4 qty.

* **Whole unit:** If order quantity is exactly divisible by from then only system will propose free goods.
  Ex.: If order is 23 qty which is not exactly divisible by 4 so free goods is 0. The order quantity has to be a divisible by 4 to get free goods.

* **Free goods:** this fields control whether the free goods is inclusive or exclusive and it also control whether the free goods is inclusive with item generation or without item generation.

* **Free goods delivery:** this field controls the free goods qty should be deliver in relation to the main item qty **[E]**.


## Configuration for free goods determination


***SPRO -> Sales and distribution -> Basic functions -> Free goods -> Condition technique for free goods -> All the options available in this path***

* Firstly we create a condition table ***503*** for free goods. Goto the specified SPRO path above.

<img width="806" height="498" alt="Image" src="https://github.com/user-attachments/assets/f3947832-dc7e-4a7e-9afc-cde7c37f3242" />

---

<img width="803" height="230" alt="Image" src="https://github.com/user-attachments/assets/d34b1a28-f9cd-4caf-9ef7-4e3795a84c31" />

---

* In the same SPRO path goto Access sequence and create one and add your newly created table in that access sequence.

<img width="861" height="340" alt="Image" src="https://github.com/user-attachments/assets/98cc529d-a55c-4a1e-b901-6fa352df27a4" />

---

<img width="527" height="276" alt="Image" src="https://github.com/user-attachments/assets/8f8b114b-e9df-4b89-aa1c-175c6c9cab1e" />

---

<img width="990" height="347" alt="Image" src="https://github.com/user-attachments/assets/95d1657f-f773-46cc-95c5-4463c229260e" />

---

* In the same SPRO path goto ***Maintain condition type*** and copy the standard condition type ***NA00*** to create ***ZCSF*** new condition type and assign it to ***ZCSF*** access sequence.

<img width="663" height="275" alt="Image" src="https://github.com/user-attachments/assets/44885f46-d6aa-4973-a794-ad4ad3fdd012" />

---

* In the same screen create your own free goods procedure ***ZCSFP***.

<img width="517" height="340" alt="Image" src="https://github.com/user-attachments/assets/62541053-2bf7-4e89-9c6c-3dc97406b68f" />

---

<img width="804" height="403" alt="Image" src="https://github.com/user-attachments/assets/4d308f59-5bb9-4b40-a760-c42d514451ea" />

---

* Now assign your newly created free goods procedure to your sales document type in the same SPRO path based off sales area and document and customer procedure assign free goods procedure.

<img width="471" height="256" alt="Image" src="https://github.com/user-attachments/assets/9e485998-dbb0-4ee1-a59d-6000db76dcf0" />

---

* Now goto to your pricing procedure(sales) ***ZCSP*** in ***V/08*** and assign ***R100*** and ***NRAB*** condition type in the pricing procedure.

<img width="1043" height="424" alt="Image" src="https://github.com/user-attachments/assets/8efd7bba-6d36-40c9-b908-9d930bbe1cbd" />

---

* Now do item category determination in ***VOV4*** for free goods.

<img width="576" height="289" alt="Image" src="https://github.com/user-attachments/assets/5c1f0e91-2111-4e3f-b48f-37ff3ab20dbd" />

---

* Now create a condition record for condition type ***ZCSF*** in T code ***VBN1***.
* In the snippet below material represents the material which the customer is buying, min qty 10 represents when is the free goods offer applicable which is once the customer buy minimum 10 qty.
*  From represents after each 4 qty purchased how many qty free goods is applicable.
* Free goods qty represents how many qty free goods is applicable which is 1 qty that means after each 4 qty purchased customer will get 1 qty free goods.
* Calculationtypefreegoods represents the calculation rule for free goods determination which is unit reference in this case 1 represents prorata, 2 represents unit reference and 3 whole unit.
* Then comes free goods 1 represents inclusive witrh item generation , 2 represents exclusive and 3 inclusive without item generation.

<img width="1111" height="334" alt="Image" src="https://github.com/user-attachments/assets/78d4d4f1-1b25-4d2a-9d59-0e205579e35b" />

---

* Now create a sales order and check the free goods determination.

<img width="1229" height="493" alt="Image" src="https://github.com/user-attachments/assets/074ebb61-e446-4e88-a2d7-1bbdc7a0c8ec" />

---

* Condition type ***R100*** providing 100% discount on 6 quantity of free goods ensuring the net value is zero for this item.

<img width="1122" height="643" alt="Image" src="https://github.com/user-attachments/assets/0fca2b61-4a0b-47c9-935b-53bf5b935b31" />

---


* If we change the free goods from 1 to 3 we can see that instead of creating a separate line item for free goods the system includes the free goods quantity in the main item line and deducts the value of free goods from main item value. 

* In the sales order below we can see that the free goods are included in the main item with overall quantity haveing 6 qty free goods and 17 qty main item and the value of free goods 6*15 = 90 is deducted from main item value.

<img width="1154" height="451" alt="Image" src="https://github.com/user-attachments/assets/bd3c0d99-745f-4da6-a544-8810b5ef7f6d" />

---

<img width="1134" height="562" alt="Image" src="https://github.com/user-attachments/assets/d00466b7-4a60-4e75-bdee-a41e0c83fb55" />








