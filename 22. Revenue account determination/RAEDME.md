## Revenue account determination

* It is the process of determining the G/L account while posting invoice values into accounting.
* While creating invoice in background system creates an accounting document and the accounting entry is ***Customer A/C Debit to Revenue A/C Credit***
* For getting the revenue account system determines the G/L account from revenue account determination.
* Revenue account determination is an integration between SD and FI.
* Revenue account determination is also based on condition technique.


***What is the accounting entry when you create invoice?***

ans. Customer A/C debit to Revenue A/C credit


***What is the accounting entry when you create performa invoice?***

ans. No accounting entry

***What is the accounting entry when you create return invoice?***

ans. Revenue A/C debit to Customer account Credit


## Configuration


* ***Path: SPRO->Sales and distribution->Basic functions->Account assignment/Costing->Revenue account determination***

* Revenue account determination T code - ***VKOA***

* Goto the above SPRO path and click on ***Check master data relevant for account assigment***
* Here we can define Account assignment groups based of master data we would first use ***material master***, so click on it.
* Now define the account assignment group just as followed below.

<img width="930" height="467" alt="Image" src="https://github.com/user-attachments/assets/6f09375e-6cb5-4168-bfb7-9b89a236c514" />

---

* Now define the account group for customer master click on ***customers: account assignment group***

<img width="1160" height="530" alt="Image" src="https://github.com/user-attachments/assets/c7afdb03-8afe-4e24-b8a9-dd8493a82101" />

---

<img width="640" height="549" alt="Image" src="https://github.com/user-attachments/assets/fb5a0dcf-d07f-46e4-b6f2-d2d7d4bf28c1" />

---

***NEXT STEP: in the same SPRO path click on - define dependencies of revenue account determination***

* Firstly, we will create a table so click on ***Account determination: create table***
* Press enter then only the screen will change to (selection of fields) view.
* The combination for table which we would be using is

  * Account Key
  * Account assignment group (for material defined above) 
  * Account assignment group (for customer defined above)
  * Sales org

<img width="916" height="604" alt="Image" src="https://github.com/user-attachments/assets/ed0cded3-a926-4c99-a29d-08463c86d675" />

---

<img width="936" height="348" alt="Image" src="https://github.com/user-attachments/assets/d271d632-cf73-40e3-af0d-bf554ac55416" />

---

***NEXT STEP - Define an access sequence***

* In the same spro path click on ***Define access sequence and account determinatio type***
* Among the avialble options click on ***Maintain access sequence for account determination***
* Create a new access sequence and subsequently assign the table to tha access sequence

<img width="1110" height="422" alt="Image" src="https://github.com/user-attachments/assets/c73e6b6e-896e-487d-8d14-de6f07a55629" />

---

<img width="992" height="426" alt="Image" src="https://github.com/user-attachments/assets/099abdfb-8eff-4e55-acbc-ec0374d98d70" />

---

* In the same step we have an option of ***Define account determination type*** click on it.

<img width="1217" height="431" alt="Image" src="https://github.com/user-attachments/assets/eb8d883e-839b-46b5-a2b9-ecd119fd37d9" />

* Click on new and create a new accounting cond type ***CS01*** and assign it to access sequence ***CS01*** just as below.

<img width="901" height="425" alt="Image" src="https://github.com/user-attachments/assets/10a56d2e-6d1a-463d-91eb-b0eb23152b7f" />

---

***NEXT STEP- In the same SPRO Path we will define accounting procedure***

* Click on ***Define and assign account determination procedure***

<img width="953" height="461" alt="Image" src="https://github.com/user-attachments/assets/006b64e0-19da-4c03-8713-52b771f633fe" />

---

<img width="985" height="529" alt="Image" src="https://github.com/user-attachments/assets/b74eaf94-55bc-4034-b7d5-de387ff4a667" />

---

* Now got to ***Assign account determination procedure*** in the same step as above.

<img width="763" height="372" alt="Image" src="https://github.com/user-attachments/assets/79a9510f-65cc-4c2c-a6d3-624ac3b8e52c" />

---

* You can also assign the same in t code - ***VOFA***

<img width="841" height="437" alt="Image" src="https://github.com/user-attachments/assets/ea052eab-80ce-4dc1-abf2-48b885e2b683" />

---

***NEXT STEP - In same SPRO path define and assign an account key***

* An Account Key is a technical control key used by SAP to decide which type of G/L account a pricing condition should post to during billing (VF01 / VF04).

  * It does NOT contain a G/L account itself
  * It tells SAP what kind of account to look for in account determination

<img width="933" height="374" alt="Image" src="https://github.com/user-attachments/assets/ee2127c9-95e9-46a9-af53-5e0fe35e6e83" />

---

* Now in the same option click on ***Assign acoount key***

* Now assign the newly created account keys to your pricing procedure like below, was not able to do it for mine because of condition types missing..

<img width="524" height="323" alt="Image" src="https://github.com/user-attachments/assets/41049f5f-6cb2-4b11-9d77-b21b97a5d017" />

---

***NEXT STEP - In the same spro path click on assign GL accounts***





