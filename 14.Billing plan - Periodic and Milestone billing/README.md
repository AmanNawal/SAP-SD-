## Billing plan ![Billing Plan](https://www.slideshare.net/slideshow/sd-billing-plan/49890314?from_search=1)

* A billing plan is a schedule of indiviual billing dates for a single item in sales document. 
* You can define a billing plan at header level which is then valid for all the items.
* There are two types of billing plans:
  * Periodic billing plan
  * Milestone billing plan


## Periodic Billing

* Periodic billing means billing a total amount for each indivisual billing date in a plan. For e.g. if you are creating a rental contract the system can propose a schedule of monthly rental payments, according to length and conditions of the contract.
* Does not have delivery as periodic billing plans are designed for service contract, rental contract etc.

### Configuration


***Step 1:*** Define billing plan types

* Path: SPRO -> Sales and Distribution -> Billing -> Billing Plans -> Define Billing Plan Types.
* Copy the standard periodic billing ***02*** and create ***CP***.

<img width="1017" height="691" alt="Image" src="https://github.com/user-attachments/assets/1c6a96b3-2603-411a-bda8-ccb3c4897fdc" />

---

***Step 2:*** Define date descriptions

* We are going to use pre-existing billing date description ***002 - rent***.

***Step 3:*** Define and assign date category

* Copy the standard assignment of billing type. And assign CP as billing plan type.

<img width="941" height="658" alt="Image" src="https://github.com/user-attachments/assets/c19c31b0-1445-4e4b-8214-fa4b0b95ff2d" />


<img width="1011" height="539" alt="Image" src="https://github.com/user-attachments/assets/f1e35489-77e1-4984-9f9e-993cea6e9c39" />

---

* In the same step(sub part of our step above) allocate date cateogory.
  
<img width="829" height="652" alt="Image" src="https://github.com/user-attachments/assets/ab9957aa-0e87-4df3-baf4-74de1745760c" />

---

***Step 4:*** Maintain date proposal for billing plant types

* Is used specifically for milestone billing not periodic billing.

***Step 5:*** Assign billing plan to sales document type

* Create a new sales doc ***CPOR*** by copying standard OR.
* Assign billing plan type CP to sales doc type CPOR.

<img width="985" height="715" alt="Image" src="https://github.com/user-attachments/assets/000954d8-c7e8-41a7-838a-3ea11191835b" />

---

***Step 6:*** Create a new billing document(if not existing) for newly created sales order

* Create a new billing doc ***CPF2*** by copying standard F2.
* Assign the billing doc to sales doc type CPOR.

<img width="939" height="714" alt="Image" src="https://github.com/user-attachments/assets/212339cb-9fb1-47bb-9de4-3c0cdb8c185a" />

---

* Create a new item category in vov7 by copying ***TAN*** and create new item cat ***CPT***.  

<img width="993" height="677" alt="Image" src="https://github.com/user-attachments/assets/f9b6a379-f840-44bf-9bb6-ec935bd775ae" />

---

* Now assign Billing relevance as ***I*** and Billing plan as ***CP*** in item category CPT.

<img width="993" height="677" alt="Image" src="https://github.com/user-attachments/assets/6a2ecd74-3da8-406b-a296-840f489abff3" />

---

* In VOV4 do the item cat determination.

<img width="684" height="437" alt="Image" src="https://github.com/user-attachments/assets/c6d86695-b82f-40ea-9d3a-4e15cbb08f82" />

---

***NOW TRY TO CREATE A SALES ORDER***

<img width="1268" height="656" alt="Image" src="https://github.com/user-attachments/assets/33a30695-ffdc-4854-928c-07b896df1209" />


---

* Incase if we want all the billing dates to have a block by default then we following the following config

<img width="874" height="677" alt="Image" src="https://github.com/user-attachments/assets/4760a534-9fad-4ed0-b828-15736563aa3b" />

---

* Select double click CP billing type

<img width="1362" height="718" alt="Image" src="https://github.com/user-attachments/assets/95ec0e99-6ae3-46e1-beb4-11c889058809" />

---

<img width="1221" height="679" alt="Image" src="https://github.com/user-attachments/assets/538fce41-ea63-4c4d-b537-ba76ad60a81b" />

---

* If you want to manually do it for each item, you can go to item level and uncheck the header checkbox.

<img width="1064" height="698" alt="Image" src="https://github.com/user-attachments/assets/caa167c3-43a1-4280-8274-1497efefbcc8" />

---

* Each and every month the billing block would be removed and an invoice would be generated.


## Milestone Billing

* Milestone billing includes dividing the total billed amount in multiple billing dates that are defined in a billing plan.
* When there is a milestone reached as per defined in the system, customer is charged as per the project cost or a predefined amount as per the bill plan.
* Milestone billing is normally used for long term projects.

### Configuration milestone billing

* Path: SPRO -> Sales and Distribution -> Billing -> Billing Plans -> Define Billing Plan Types -> Milestone billing plan.
* Copy the standard ***01*** Milestone billing and create new billing plan type ***C1***.

<img width="1034" height="611" alt="Image" src="https://github.com/user-attachments/assets/f8632331-c0ed-4389-9078-9b899e891334" />

---

***Step 2:*** Define date descriptions

* In milestone billing we divide the cumulative billing amount into different percentages at different milestones. e.g. Contract signing, Engineering/Design, Closing invoice, SP: Down payment. We can use the following date descriptions.

<img width="1016" height="681" alt="Image" src="https://github.com/user-attachments/assets/6cd99968-a717-4f34-b786-f48caae81daf" />

---

***Step 3:*** Define and assign date category

* Copy the standard milestone billing record and assign C1 as billing plan type.

<img width="1066" height="454" alt="Image" src="https://github.com/user-attachments/assets/17d0ecdc-3d95-4028-9c26-0c5171f850f9" />

---

* In the same step(sub part of our step above) allocate date cateogory.

<img width="1040" height="711" alt="Image" src="https://github.com/user-attachments/assets/3e4abf57-ae21-4c9e-aafc-13a18d8d9648" />

---

***Step 4:*** Maintain date proposal for billing plant types

* Here we define when the billing dates are proposed by the system. e.g. if we want the first milestone to be proposed on order date we maintain it here.

* Double click on billing plan type C1 and click on ***Maintain date***. Here you would see the routine according to which the billing dates would be proposed.

* You can your own percentage and new date if you want to add more milestones.

<img width="1365" height="568" alt="Image" src="https://github.com/user-attachments/assets/19ed5ca2-e273-465e-ab75-555934cef7d3" />


---

***Step 5:*** Assign billing plan to sales document type

* For pre existing sales order created for perioid billing we can assign the milestone billing plan.
* In VOV8 assign billing plan type C1 to sales doc type CPOR.

<img width="1033" height="717" alt="Image" src="https://github.com/user-attachments/assets/977fa1ce-46bf-403a-b5ba-e8159e7d7b16" />

---

* Now create a sles order and check the billing plan in header and item level.

<img width="1365" height="593" alt="Image" src="https://github.com/user-attachments/assets/c5707134-890c-4a5e-b4a5-6862e955f4f7" />

---

<img width="1343" height="709" alt="Image" src="https://github.com/user-attachments/assets/a2b2ca59-f25d-48fa-8636-55c971e46332" />

---