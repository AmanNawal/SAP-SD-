## Common Division

* We use common division concept if the client is having many divisions. Common division will help in saving the user's time and also save the sapce in the database.
* If you don't have the concept of common division then you have to create customer for each and every division.
* For example: If you have 100 different divisions and you have to create customer for each division then you have to create 100 customers for same customer. In that case we will create 1 common division and assign that common division to all 100 divisions.
* Now you don't need to extend a single customer to all 100 divisions. You can just create it with one common division.


### Configuration Steps:


* Define common division: SPRO -> Enterprise structure -> Definition -> Logistics general -> Define, copy, delete, check division.

<img width="851" height="678" alt="Image" src="https://github.com/user-attachments/assets/7e909b30-66a4-4bdb-92ba-302a06759a10" />

---

* Define a new Division **ZK** and save it.

<img width="901" height="487" alt="Image" src="https://github.com/user-attachments/assets/2bb67e2e-5ff9-4404-94e8-52462155f71e" />

---


* Now assign the division to sales org. Extend it for ***IN01*** as well.

<img width="960" height="717" alt="Image" src="https://github.com/user-attachments/assets/6aff4ec8-3b50-420a-ab40-83ff2e1686f9" />

---

<img width="790" height="597" alt="Image" src="https://github.com/user-attachments/assets/a16b7f56-d20a-40f2-8aa6-6e0042c83043" />

---

* Now click on setup sales area.

<img width="976" height="463" alt="Image" src="https://github.com/user-attachments/assets/b3769d58-9027-478b-bee6-c903c563d946" />

---

* Now define a common division for sales area in path SPRO -> Sales and sitribution -> Master data -> Define common divisions for sales area.

<img width="1025" height="682" alt="Image" src="https://github.com/user-attachments/assets/0d519d68-3ba3-42d7-915e-43c2e8fd0968" />

---

* Now you can create a customer with common division and subsequently use it for the child divisions to create sales orders.

* Now you will notice even if the division is ZY or ZT or ZD if the customer is created for ZK it will be valid for all the divisions assigned to that sales area.

 

