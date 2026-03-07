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

