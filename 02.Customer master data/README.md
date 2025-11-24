## Creating a customer master data

* The following sales areas are avaialble for us to create customer master data.

<img width="1133" height="440" alt="Image" src="https://github.com/user-attachments/assets/b7d45b1e-2617-4044-82c3-b79335a5abec" />

---

## Creating an account group

* Account group is created in FI module because it is related to financial accounting.
* When you create a customer master record, the system knows which fields are relevant (and so which fields to turn “on” and “off” in the screens) by using the assigned account group.
* You generally do not need all of the fields provided by SAP and you can use the account group to switch off irrelevant fields. For example, the Ship to Party account group does not need the Payment Terms field, so you can switch off this field for the Ship to Party account
group (0002 in SAP standard).
* Account group also controls the number range for the customer master record.

***Path***

* Menu Path SAP Customizing Implementation Guide | Financial Accounting | Accounts Receivable and Accounts Payable | Customer Accounts | Master Records | Preparations for Creating Customer Master Records | Define Account Groups with Screen Layout (Customers) [OBD2] OR 
* **Use t code OVT0**
* To create a new number range use **XDN1** Transaction code.
* To assign the number range to the account group, use the menu path: SAP Customizing Implementation Guide | Financial Accounting | Accounts Receivable and Accounts Payable | Customer Accounts | Master Records | Preparations for Creating Customer Master Records | Define Number Ranges for Customer Accounts 

---

## Create a customer master record

***Reconciliation account***

* The reconciliation account serves as a control link that connects the detailed individual customer accounts within the Accounts Receivable (AR) sub-ledger to a summarized General Ledger (G/L) account in the company code's financial statements.

* T code FS00 is used to create a G/L account in the chart of accounts and assign it as a reconciliation account.

<img width="913" height="686" alt="Image" src="https://github.com/user-attachments/assets/da687261-2609-4faf-9e6f-d8ef1d717d9c" />

* Table SKB1 holds the details of the G/L account created along with the company code details.

---


## Partner determination procedure

* Menu Path SAP Customizing Implementation Guide | Sales and Distribution | Basic Functions | Partner Determination | Set Up Partner Determination. T code - VOPAN
  
***Steps to create a partner determination procedure***

* Goto T code **VOPAN**.
* Create a new entry for partner determination procedure ZMSP.

<img width="914" height="398" alt="Image" src="https://github.com/user-attachments/assets/4529a861-07dc-4760-b95d-ac1dab546de5" />

* Now assign partner functions to the procedure. This would help us in formulating the rules of which partner funtions would be present in customer master record and if they are mandatory and non modifiable.

<img width="1059" height="341" alt="Image" src="https://github.com/user-attachments/assets/27936b09-f6bd-4a8d-80ae-70dd265adb74" />

* Now assign partner procedure to to account group.

<img width="994" height="508" alt="Image" src="https://github.com/user-attachments/assets/f8a73dcc-7fa7-4a07-b201-bcd4fa0f4add" />

* Initially all the partner function associated with SP will be sold to party customer itself. So we assigned the following below.

<img width="1104" height="473" alt="Image" src="https://github.com/user-attachments/assets/68fb54a1-a9fa-4ecc-b045-8b5c7763606f" />

* Now we will create a customer master record using T code XD01 and notice the partner functions assigned to the customer.

---

***DO the same for ZMSH***

<img width="626" height="432" alt="Image" src="https://github.com/user-attachments/assets/acadcab2-5a5b-44ed-9dc0-1284f73842f0" />


<img width="684" height="418" alt="Image" src="https://github.com/user-attachments/assets/ad595bee-1e9d-4ee2-9bb8-69edba62fd97" />

<img width="944" height="515" alt="Image" src="https://github.com/user-attachments/assets/15933594-c901-4ae2-b370-b4e5ef27c5de" />

---

***DO the same for ZMPY***


<img width="974" height="387" alt="Image" src="https://github.com/user-attachments/assets/c640dc51-6b97-469f-94f4-6ae7763af0a0" />

<img width="985" height="465" alt="Image" src="https://github.com/user-attachments/assets/d7003915-d776-484d-b70a-81d4923cee1a" />

<img width="880" height="517" alt="Image" src="https://github.com/user-attachments/assets/ba2f789d-9698-45a7-8a57-dc73520441e4" />

<img width="983" height="456" alt="Image" src="https://github.com/user-attachments/assets/edef246d-6a05-47ce-9947-54ad9758e2a2" />

---

***DO the same for ZMBP***

<img width="801" height="440" alt="Image" src="https://github.com/user-attachments/assets/18bf9669-7a49-4431-ab26-9afe5d5a4de5" />

<img width="828" height="365" alt="Image" src="https://github.com/user-attachments/assets/d91e5abb-c025-4841-941f-5a4024e86fea" />

<img width="935" height="644" alt="Image" src="https://github.com/user-attachments/assets/36785b23-1e17-4527-9722-9efaa871b657" />

<img width="899" height="438" alt="Image" src="https://github.com/user-attachments/assets/2df4d4be-c0fd-4b83-828d-3c0757da73e5" />



