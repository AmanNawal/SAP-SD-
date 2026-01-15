## Exclusion group in pricing / Condition Exclusion in pricing

* **Exclusion group:** Grouping of multiple condition type into one and asking the system to propose to best discount or the least discount.

### Configuraion of Exclusion group in pricing

* Create 3 discount condition types ***ZZC4*** and ***ZZC5*** and ***ZZC6*** in ***V/06***, by copying standard conditointypes ***K004***, ***K005*** and ***K006***.

* Now maintain the newly created condition types in the pricing procedure.

<img width="1054" height="548" alt="Image" src="https://github.com/user-attachments/assets/8cc5e161-cb2f-4c7f-aef0-fdba1f8a0131" />

---

* Now create a sales order where we can see that the total net value is in negative mostly because of multiple discounts applied.
* We want the best possible discount to be applied instead of all discounts.

***SPRO -> Sales and Distribution -> Basic Functions -> Pricing -> Condition exclusion -> Condition exclusion for group condition***

<img width="627" height="528" alt="Image" src="https://github.com/user-attachments/assets/076120bb-40e6-4188-9394-c1a651cf0b21" />

---

* Click on step 1 and create a new exclusion group ***ZCSE***.

<img width="546" height="472" alt="Image" src="https://github.com/user-attachments/assets/5d64bbb4-c67c-43f8-ad81-f35f1170afd7" />

---

* Click on step 2 and assign condition exclusion to discount condition types.

<img width="530" height="266" alt="Image" src="https://github.com/user-attachments/assets/1ae3b3a7-5608-451d-b098-01cf8e7a5523" />

---

* Click on step 3 and maintain condition exclusion group for pricing procedure.

<img width="1365" height="507" alt="Image" src="https://github.com/user-attachments/assets/364ed0d5-7889-4b69-b08b-b0688bb773eb" />

---

<img width="934" height="561" alt="Image" src="https://github.com/user-attachments/assets/ddc3c89e-8b08-44ad-bc32-56d64f274aa5" />

---

* Now create a sales order and check which condition type is providing the best discount among the three cobdition types included in the condition exclusion group.

<img width="1099" height="658" alt="Image" src="https://github.com/user-attachments/assets/b0ea9b4e-1b08-488f-a2d9-978c965c2073" />

---

* In case if want the cobdition type with least discount we change conditione exclusion group for pricing procedure.

<img width="857" height="540" alt="Image" src="https://github.com/user-attachments/assets/b1b4e09c-8273-41d8-a447-d1a7b341e32d" />

---

* Now create a sales order where we can see that the condition type with least discount is applied among the three cobdition types included in the condition exclusion group.

<img width="1076" height="651" alt="Image" src="https://github.com/user-attachments/assets/57bcc10c-2a4b-46f3-81b8-53169e406c7d" />

---


### Picking the best between two exclusion groups

* Create a exclusion group ***ZCS2*** just as above.
* Assign condition exclusion to condition types.

<img width="583" height="459" alt="Image" src="https://github.com/user-attachments/assets/4c7e2911-8a90-498e-bec0-8071a5591d56" />

---

* Now assign the second exclusion group to pricing procedure along with the first exclusion group and change ***condition exclusion procedure***.

<img width="951" height="582" alt="Image" src="https://github.com/user-attachments/assets/116e67bb-6183-4a32-9ea9-34be13f18fc3" />

---

* Now create a sales order and check which condition type is providing the best discount among the two cobdition exclusion groups included in the condition exclusion procedure.

* The reason why ZZC4 and ZZC5 are considered is because adding both gives better discount than ZZC6 and ZCK4.


<img width="1094" height="638" alt="Image" src="https://github.com/user-attachments/assets/add30ba1-c9c3-4c88-bea8-6bcd717b1435" />

---





