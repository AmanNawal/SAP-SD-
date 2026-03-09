## Pricing scales / Scale types

* In **SAP SD**, **Scales** are used in pricing to determine **different condition values based on quantity, value, or weight thresholds**.

* Scales allow you to apply variable pricing (or discounts/surcharges) depending on how much the customer buys.

---


### Example 1 – Quantity Scale (Most Common)

Condition Type: Discount (e.g., ZDIS)

| Quantity  | Discount % |
| --------- | ---------- |
| 1 – 99    | 5%         |
| 100 – 499 | 10%        |
| 500+      | 15%        |

If customer orders 600 units → 15% discount applied.

---

### Example 2 – Value Scale

| Order Value     | Discount |
| --------------- | -------- |
| 0 – 10,000      | 2%       |
| 10,001 – 50,000 | 5%       |
| 50,000+         | 8%       |

System calculates discount based on total order value.

---

### Types of Scales in SAP SD

When maintaining condition records (VK11), you can choose:

**Quantity Scale**

Based on ordered quantity.

**Value Scale**

Based on condition base value.

**Weight/Volume Scale**

Used in freight pricing.

---

### Configuration of Scales

* In V/06 for a condition type we can define on what basis the scale will be maintained so we have fields like ***scale basis*** and ***Scale types*** which helps us in configuration of scales.

* Scale basis: it defines the basis on which the scale will be maintained, it can be quantity, value or weight/volume.
* Scale type: Indicator that controls the validity of the scale value or percentage: From a certain quantity or value (base scale). Up to a certain quantity or value (to-scale)


***In the scale basis maintain a value***


<img width="789" height="690" alt="Image" src="https://github.com/user-attachments/assets/2299d17b-18db-4bd1-b718-7e713c913a42" />

---

***Now maintain a condition record with scale values in VK11***


<img width="983" height="323" alt="Image" src="https://github.com/user-attachments/assets/7a404da7-e921-4ed7-a244-2712cca12927" />

---

* In the snippet below the prices will flow based on the order quantity.

| Order quantity | Scale value |
| -------------- | ----------- |
|   25 to 49     |     200     |
|   50 to 74     |     175     |
|   75  to 99    |     150     |
|   100+         |     123     |

* Incase if the order placed is less than 25 then the condition will go in error state(red).

<img width="875" height="462" alt="Image" src="https://github.com/user-attachments/assets/c4b4b274-a1c6-4070-8e01-d08d3ce2c795" />

---

* When creating a sales order with quantity 59 then the system will apply the scale value of 175.
  
<img width="903" height="461" alt="Image" src="https://github.com/user-attachments/assets/d1fd522b-80ec-49f4-84d9-ec11b09897dc" />

---

<img width="840" height="621" alt="Image" src="https://github.com/user-attachments/assets/78cf00ac-40af-49a2-94d0-2b41d460a859" />

---

### Configuraing scales for freight condition type

* Freight condition type is a pricing element used to calculate and add transportation or delivery charges to a sales document (quotation, sales order, delivery, or billing).
* In this case the scale basis should be D which represents gross weight scale FYI gross weight is the total weight of the goods including packaging.
* As the weight of the product increases the freight charge would increse too.
* **Check value** - will determine of the scale values are to maintained in ascending or descending order.

<img width="889" height="716" alt="Image" src="https://github.com/user-attachments/assets/6c0d899d-5970-4dc7-ba4d-4b14d4695e53" />

---


***Scale type***

* In SAP SD Pricing, the Scale Type determines how the system applies pricing values when scale levels are defined in a condition record.
* When no values are maintained by default scale type uses a from scale in condition records.
* When maintained with B the 'from' scale changes to 'to' scale in condition records.

<img width="530" height="428" alt="Image" src="https://github.com/user-attachments/assets/62c557d9-2912-4e4d-ba0a-defaf0f971cb" />

* for example in the snippet below

* 1 1000 is applied
* 2 - 10 2000 is applied
* 11 - 20 3000 is applied
* 21 - 10000 4000 is applied

<img width="501" height="335" alt="Image" src="https://github.com/user-attachments/assets/faa345af-4836-4800-8f90-38e03e69ac80" />

***Graduated scale***

* In SAP SD Pricing, a Graduated Scale is a scale type where different rates are applied to different portions of the quantity/value rather than applying one rate to the entire quantity.

* For example in the snippet below. The quantity used in order is 50.
* For the first quantity the value would be 1000.
* For 2 - 10 (total 9 units) the value would be 2000.
* For 11 - 30 (total 20 units) the value would be 3000.
* For 31 - 40 (Total 10 units) the value would be 4000.
* For 41 - 50 (total 10 units) the value would be 5000.

<img width="777" height="376" alt="Image" src="https://github.com/user-attachments/assets/e8af159d-5ecf-464e-9ca7-7daa007765e5" />


* All of these values will be added together to get the total value for 50 units.

<img width="691" height="389" alt="Image" src="https://github.com/user-attachments/assets/56bbea13-2b3c-4d45-81e7-006516ae73bb" />

* In the snippet above we can see HL00 condition type is interfacing multiple times into sales document this is because Graduated scale maintained.

<img width="547" height="429" alt="Image" src="https://github.com/user-attachments/assets/719314ad-f5fc-4d75-b748-3326a92d2334" />



