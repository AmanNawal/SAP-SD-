## Cross selling

* In cross selling the system automatically suggests complementary products to a customer who is already placing an order for a primary item.

### Configuration steps

* Goto the following path to configure cross selling

<img width="923" height="713" alt="Image" src="https://github.com/user-attachments/assets/e9ef3f6e-19e7-4041-aa5d-258b9935a4e4" />

---

<img width="1181" height="681" alt="Image" src="https://github.com/user-attachments/assets/1c7e7c05-741f-498e-9326-547981d27c5c" />


***Define determination procedure for cross-selling***

* Create a condition table in my case we created table ***685-Material/division and plant***.
* Create a new access sequence and assign the newly created table to it.

<img width="1053" height="645" alt="Image" src="https://github.com/user-attachments/assets/c172c12c-ac99-4d31-8aed-d8e1ed9d8f6b" />

---

<img width="944" height="410" alt="Image" src="https://github.com/user-attachments/assets/6e555fb1-3719-42ad-a41f-0c7e8a95dbcc" />

---

<img width="1019" height="429" alt="Image" src="https://github.com/user-attachments/assets/c6438a16-3cfd-47ab-9184-f5e2d3327b76" />

---

***Define condition type***

<img width="864" height="443" alt="Image" src="https://github.com/user-attachments/assets/386e8cff-c6ce-4a26-a1a0-8f4db997a03b" />

* Validity current date to infinity.

---

***Maintain procedure***

<img width="954" height="527" alt="Image" src="https://github.com/user-attachments/assets/871791a4-03e5-40fe-86d8-6c2177f00d0d" />


***Next step- maintain customer/document procedure for cros selling***

<img width="1340" height="642" alt="Image" src="https://github.com/user-attachments/assets/c6ee18f9-fd7d-48ae-9c93-5126dda1ade5" />

---

***Define customer procedure for Cross selling***

<img width="419" height="312" alt="Image" src="https://github.com/user-attachments/assets/055329f2-b985-4568-b708-868b6e7f402c" />

---

***define document procedure for Cross selling***

<img width="428" height="324" alt="Image" src="https://github.com/user-attachments/assets/f6bb9286-37af-4f44-8ab2-3aa348ac142b" />

---

***assign document cross selling procedure to sales document type***

<img width="652" height="344" alt="Image" src="https://github.com/user-attachments/assets/22c5de63-b057-4966-b6e9-a7ed5a1302cb" />

---


***Next step define and assign cross selling profile***

<img width="1099" height="615" alt="Image" src="https://github.com/user-attachments/assets/e4d15ca3-9676-4ad4-b545-fb7551138772" />

---

<img width="909" height="476" alt="Image" src="https://github.com/user-attachments/assets/79da5a24-ba84-460c-8ef8-cd1b368f4441" />

---

<img width="1014" height="385" alt="Image" src="https://github.com/user-attachments/assets/4eebdbdb-f396-4f46-9db8-4b147b902fd7" />


---

***Now assign the customer cross selling procedure to customer master data***

<img width="882" height="687" alt="Image" src="https://github.com/user-attachments/assets/b5aa3944-a846-4a41-b242-10083094373a" />


---

***Now create ondition record for cross selling***

* T code - VB41
* Created a new material for cross selling against primary material Material 300000024AA created.

<img width="981" height="645" alt="Image" src="https://github.com/user-attachments/assets/296c593b-f763-41cb-98a0-63570739d573" />

---

***Create a sales order to test cross selling functionality***

* while creating the sales order you will see a pop up suggesting cross sell material.

<img width="1333" height="682" alt="Image" src="https://github.com/user-attachments/assets/fd4c2659-272b-42cd-8874-f39276f17fa3" />


