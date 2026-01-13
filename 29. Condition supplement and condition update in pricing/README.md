## Condition supplement / condition update in pricing


* **Condition supplement:** Condition supplement is concept of adding one condition record to another condition record. If the main condition record determine then only supplement condition record will be determine.

* **Group Condition:** Group condition nothing but a group discount, Discount will given on total document value or group of material value.

* **Condition update:** Restricting the condition record up to particular quantity or value or number of orders. It’s also called condition update.

* **Condition Index:** It will help to display or change all the combination of prices in a single window. If management ask to change the prices of all combination with immediate effect, then by using condition index concept, we change all the combination of prices in single window.

* **Exclusion group:** Grouping of multiple condition type into one and asking the system to propose to best discount or the least discount.


### Condition update configuration

***First scenario: Condition update based on quantity***

* Create a new condition type ***ZK04*** in ***V/06***, by copying standard condition type ***K004 - Material discount type***.
* Ensure that the condition update check is marked in the condition type.

---

<img width="720" height="719" alt="Image" src="https://github.com/user-attachments/assets/85abea89-f167-44b1-bc31-9aca076a9883" />

---

* Now place the newly create condition type in Pricing procedure.

---

<img width="1087" height="589" alt="Image" src="https://github.com/user-attachments/assets/a8de1887-d445-4a1a-a0cd-11da26622b49" />

---

* Now create a condition record and click on additional data at the top.

<img width="1052" height="419" alt="Image" src="https://github.com/user-attachments/assets/2651dd88-e6ff-40d5-a7bb-766a022f79de" />

---

* In the additional data maintain ***max condition base value*** as 10, this means the codition record is only valid for those orders which are put firstly and are requesting for less than 10 qty.

<img width="987" height="678" alt="Image" src="https://github.com/user-attachments/assets/76d085a4-0d4c-41d9-9893-b729efea9e55" />

---


* Now we create an order with quantity 5, so condition update value is 10-5 == 5.
* We create another order with quantity 4, so condition update value is 5-4 == 1.
* For the next order we place a quantity of 3 which greater than 1, so this case we get a discount for only 1 quantity while the other 2 quantity will not get any discount.

<img width="1202" height="678" alt="Image" src="https://github.com/user-attachments/assets/8847f4a0-e56a-445c-a431-eb73cfd02acb" />

---


***Second scenario: Condition update based on number of orders***

* Create another condition type ***ZCK5*** in ***V/06***, by copying standard condition type ***K005 - Material discount type***.
* Ensure that the condition update check is marked in the condition type.

---

<img width="1131" height="528" alt="Image" src="https://github.com/user-attachments/assets/d0d3364c-6e2d-49fe-a22d-c4338e890bd7" />

---

* Create a condition record and click on additional data at the top.

---

<img width="948" height="365" alt="Image" src="https://github.com/user-attachments/assets/52176446-9e1e-45a0-871a-1abee1deea26" />

---

<img width="964" height="638" alt="Image" src="https://github.com/user-attachments/assets/192bdd83-fb09-49b1-b447-97ccc433fe83" />

---

* Now we create three order and in all three orders we see the discount is applied.

---

<img width="1093" height="635" alt="Image" src="https://github.com/user-attachments/assets/cb91cd86-1f44-42a7-9ca2-04d12dc620c0" />

---

* For the fourth order no discount is applied as the condition update value is over.

---

<img width="1090" height="631" alt="Image" src="https://github.com/user-attachments/assets/e0dc873a-2a70-4ee8-9d24-a468b2b5954e" />

---


***Third scenario: based on net value***

* Create another condition type ***ZCK6*** in ***V/06***, by copying standard condition type ***K007 - Material discount type***.
* Ensure that the condition update check is marked in the condition type.

---

<img width="830" height="729" alt="Image" src="https://github.com/user-attachments/assets/7af711fe-8b1b-4274-8a5a-54ad6d2b08be" />

---

* Assign the condition type to pricing procedure.

---

<img width="1096" height="551" alt="Image" src="https://github.com/user-attachments/assets/f019da67-a786-4a13-b3f5-de82ed2796a1" />

---

* Create a condition record and click on additional data at the top.

---

<img width="1200" height="482" alt="Image" src="https://github.com/user-attachments/assets/c105a18d-4d05-47ad-89cb-b21b647fed97" />

---

<img width="726" height="669" alt="Image" src="https://github.com/user-attachments/assets/770c85b1-b5bf-4951-a233-a8c330b695c9" />

---

* As you can see the net value for condition update is maintained as 3000 whereas the value of out condition is 1500.
* So we can have discounts until this 3000 value is over.
* For example a single order will have 1500 value as a discount because it is maintained in the conditiond record. So technically we can have two orders with this discount until the net value of 3000 is over.
* First and second order get the discount value of 1500 each.

---

<img width="1108" height="633" alt="Image" src="https://github.com/user-attachments/assets/087629a8-9f11-4de4-96ec-de7a1f5dda5b" />

---

* Third order does not get any discount as the condition update value is over as previously 1500 + 1500 == 3000. 


### Condition Supplement Configuration

* Create a new condition type ***ZCSU*** for condition supplement by copying standard discount condition type ***K004 - Material discount type*** in ***V/06***.
* Now create a new procedure ***ZCSUPL*** and assign the new created condition type to the procedure along with other discount condition on which we want to apply the supplement.

<img width="982" height="411" alt="Image" src="https://github.com/user-attachments/assets/d9be84ac-d87c-4b1b-8e69-58f7c778d939" />

---

* Now assign the pricing procedure to discount condition ***ZCK4*** which is being supplemented by ***ZCSU*** in ***V/06***.

<img width="801" height="717" alt="Image" src="https://github.com/user-attachments/assets/0e0265b5-6a02-41b6-b727-4d875eeff447" />

---

* In the pricing procedure ***ZCSP***, assign the supplement condition type ***ZCSU***.

<img width="1041" height="582" alt="Image" src="https://github.com/user-attachments/assets/278e7c34-f921-4665-81e7-6adc07420f72" />

---

***Now create a condition record for discount condition type ZCK4***

<img width="1030" height="363" alt="Image" src="https://github.com/user-attachments/assets/9430f44c-977c-4b0b-8a13-0b60bb4a73f9" />

---

* Maintain ***ZCSU*** condition type along with the discount which we want to provide as supplement.

<img width="752" height="564" alt="Image" src="https://github.com/user-attachments/assets/ea0ac8a9-0931-4742-ba0e-0dd94a038333" />

---

* Now create a sales order and check if ***ZCSU*** supplement condition is incoming with discount condition type ***ZCK4***.

<img width="1080" height="630" alt="Image" src="https://github.com/user-attachments/assets/0309fc7d-c090-4157-a770-454726bcfcc3" />

---

* Now delete the condition record for ***ZCK4*** and check if supplement condition ***ZCSU*** is coming or not.

<img width="1095" height="626" alt="Image" src="https://github.com/user-attachments/assets/4cfd5fe2-65ef-4e2c-8a10-0e960f675384" />

---
