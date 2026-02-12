## Status profile and approval strategy

In **SAP SD**, a **Status Profile** is a **set of user-defined statuses** that controls and tracks the **business lifecycle of a sales document or item** beyond the standard SAP system statuses.

It is mainly used to **control business processes**, **restrict activities**, and **monitor progress** in Sales and Distribution.

---

### 1. What Is a Status Profile?

A **Status Profile** defines:

* A sequence of **user statuses**
* Allowed **status transitions**
* Which **business transactions are permitted or blocked** at each status

It works **in addition to** SAP’s standard system statuses (e.g. Open, Completed, Delivered).

---

### 2. Why Status Profile Is Used in SAP SD

Status profiles are used to:

* Control the **approval process**, its not like if a quotation is created we can dirctly start order creation and delivery creation. We can have a status profile which will restrict the order creation and delivery creation until the quotation is approved.
* Prevent actions until certain conditions are met
* Track document progress clearly
* Enforce company-specific sales processes

**Example**
A sales order must be **approved** before delivery or billing is allowed.

---

### 3. Typical SD Business Example

Sales Order Lifecycle using a Status Profile:

1. **CREATED**
2. **UNDER_REVIEW**
3. **APPROVED**
4. **REJECTED**
5. **COMPLETED**

* Delivery creation allowed only in **APPROVED**
* Billing blocked in **CREATED / UNDER_REVIEW**
* Order locked if **REJECTED**


## Configuration of status profile

* SPRO -> Sales and distribution -> Sales -> Sales document -> Define and assign status profile.

* Firstly, we will define a status profile ***ZCSSP***

<img width="957" height="580" alt="Image" src="https://github.com/user-attachments/assets/cfffb630-e164-4883-8f0b-b5a68de386fe" />

---

<img width="1064" height="563" alt="Image" src="https://github.com/user-attachments/assets/a1aec13b-1864-4a36-8921-596059a69771" />

---

* Now double click on ***ZCSSP*** status profile, and then click on obect type, object type links the status profile to a specific SAP document or item.

<img width="557" height="520" alt="Image" src="https://github.com/user-attachments/assets/0249a0d9-b03b-404f-94d0-861cca79e08c" />

---

<img width="523" height="676" alt="Image" src="https://github.com/user-attachments/assets/a4ce608d-c60a-4d8a-9807-fa74643b80ce" />

---

* Now again click on user status, to create users status. In this case we will create 2 user status one will block the delivery creation and another will allow delivery creation.

<img width="584" height="571" alt="Image" src="https://github.com/user-attachments/assets/eecd72d1-b1ce-4324-b5ac-de2cc5adcc6e" />

---

* Double click on ***ZCSP*** which is blocked for delivery and click on create new.

<img width="597" height="558" alt="Image" src="https://github.com/user-attachments/assets/a5628861-e116-4036-b770-4bcbd5562abc" />

---

* Forbid delivery as we don't want delivery creation until the order is approved.

<img width="755" height="611" alt="Image" src="https://github.com/user-attachments/assets/1713e9a6-de72-49f6-add3-92d3b14188c1" />

---

* Now go back and click on ***ZCOR*** which is order release status and create new.

* Allow create delivery for this status as we want delivery creation when the order is approved.
* 
<img width="682" height="613" alt="Image" src="https://github.com/user-attachments/assets/9f5b5005-297b-45fb-9320-740a941cb436" />

---

* Now go back and click on ***assign order types/ status profiles***

<img width="1098" height="594" alt="Image" src="https://github.com/user-attachments/assets/ab33f154-932e-479e-b8d3-6d7167ab7d65" />

---

* Double click on ***CSOR*** and asisgn the status profile under transaction flow tab.

<img width="837" height="705" alt="Image" src="https://github.com/user-attachments/assets/e462b6b8-7bb9-4602-ad31-372b5e46a5cd" />

---

* Now create one sales order. But when you try to deliver the order, the system will give and error.

<img width="472" height="240" alt="Image" src="https://github.com/user-attachments/assets/143e24e3-36cc-4457-a56e-069b0a4ac460" />

---

* To remove this error, an authorized user has to goto header -> status -> obect status -> click on order release.

<img width="713" height="645" alt="Image" src="https://github.com/user-attachments/assets/f1f43718-eec7-4d0d-bbeb-e79941583771" />

---

* Now we can successfully create delivery for this order.

***BUT what if the client wants the PGI to be blocked too once a delivery is created?***

* In this case we will edit Order release ***ZCOR*** as it allows delivery creation but simultaneously we want to block PGI too. So, double click on it and click on create new.


<img width="665" height="502" alt="Image" src="https://github.com/user-attachments/assets/beff80ce-fbf4-4c78-b2db-e1fcfc79424f" />

---

<img width="615" height="307" alt="Image" src="https://github.com/user-attachments/assets/97082a84-d457-4134-a556-65a8aa293378" />

---

* Now create a new status number for PGI release, where we will release PGI. As this step is dependent on step 20 we have eneter lower number as 20.

<img width="652" height="386" alt="Image" src="https://github.com/user-attachments/assets/2a2696a6-b8a6-4e84-a98e-0dad9bfb2cb4" />

---

* Now create an order and try to create deliver and subsequently try to do PGI. The system will give an error while doing PGI.

* Now in sales order header you will see multiple release options to choose from. Suppose we want to release only delivery in that case we will select only delivery release and click on ok after delivery is done we will again goto sales order header and select PGI release and click on ok to do PGI.

<img width="668" height="551" alt="Image" src="https://github.com/user-attachments/assets/dd0eb05a-4de7-4fc3-9ec9-08bb2a3d90b5" />

---

* But when we try to do PGI, the system will give an error.

<img width="893" height="323" alt="Image" src="https://github.com/user-attachments/assets/3519003d-1018-4f98-9584-7a7e811c7e1e" />

---

* SO we again have to goto sales order header and select PGI release and click on ok to do PGI.

<img width="660" height="472" alt="Image" src="https://github.com/user-attachments/assets/061f7f14-08ac-423b-bb90-b6a8958ec371" />

---

* Now we can do PGI successfully.












