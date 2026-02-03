## Revenue account determination (T code - VKOA)

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
* Generally accounting determination is done based on material types ex Finished goods, services, scraps etc.
* Now define the account assignment group just as followed below.

<img width="930" height="467" alt="Image" src="https://github.com/user-attachments/assets/6f09375e-6cb5-4168-bfb7-9b89a236c514" />

---

* Now define the account group for customer master click on ***customers: account assignment group***.
* In this case our clients has only two types of customer i.e. domestic customer and internationcal customer.

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

* These combinations would be used for hitting a GL account, for example when the sale org is IN0N, Account assignment group (material) is FG (Finished goods) and account assignment group (Customer) is domestic customer with account key ***ERL*** then a particular GL will hit.

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

* ***imp*** We SD consultants do not assign the account ket associated with TAX conditions as it is generally handled by FI consultants.

* An Account Key is a technical control key used by SAP to decide which type of G/L account a pricing condition should post to during billing (VF01 / VF04).

  * It does NOT contain a G/L account itself
  * It tells SAP what kind of account to look for in account determination

<img width="933" height="374" alt="Image" src="https://github.com/user-attachments/assets/ee2127c9-95e9-46a9-af53-5e0fe35e6e83" />

---

* Now in the same option click on ***Assign acoount key***

* Now assign the newly created account keys to your pricing procedure like below, you can also do the same in V/08

<img width="756" height="546" alt="Image" src="https://github.com/user-attachments/assets/eb87450b-1cf3-4a09-b4a0-302948a7196d" />

---

***NEXT STEP - In the same spro path click on assign GL accounts***

<img width="542" height="499" alt="Image" src="https://github.com/user-attachments/assets/6a833605-587f-4ae1-9c19-55e61700249d" />

---

* Assign the entries as per created above and ask FI team for GL

<img width="612" height="311" alt="Image" src="https://github.com/user-attachments/assets/f9206091-8df2-42ad-94d1-633091b1ca59" />

---

* In this case we will create out own GL accounts  Using T code ***FS00***.
* Enter the GL number you want to create along with the company code, click on template.
* In this case we are creating GL by taking reference to pre existing GL of company code 1000 of company code 1000.
* GL account ***7899*** for SERVICE, GL account ***7900*** for DISCOUNTS, GL account ***7901*** for FREIGHT

<img width="905" height="637" alt="Image" src="https://github.com/user-attachments/assets/172b65c3-cb0e-4c13-a186-4cb3016b25ac" />

---

<img width="808" height="581" alt="Image" src="https://github.com/user-attachments/assets/c4f5a0a8-b6a9-40fe-873e-77dc598e0ee3" />

---

<img width="819" height="551" alt="Image" src="https://github.com/user-attachments/assets/409464e6-7900-431f-8707-cd3064f8e40c" />

---

<img width="904" height="719" alt="Image" src="https://github.com/user-attachments/assets/fbd67e53-3fd5-4262-b4be-51eac009a280" />

---

* Now assign the GL accounts created above in T code ***VKOA*** as per below.

<img width="930" height="266" alt="Image" src="https://github.com/user-attachments/assets/bbc7eabc-5fb3-46f4-9cfa-85013d1e182d" />

---

* Make sure the account assignment group of both material and customer are maintained in respective manner.


***Define tax postings***

<img width="784" height="625" alt="Image" src="https://github.com/user-attachments/assets/2277288a-1448-4820-ad17-78413d227f68" />

---

<img width="1072" height="693" alt="Image" src="https://github.com/user-attachments/assets/91bb3e15-e7a0-46ac-ad39-a7d3cfb354d3" />

---









