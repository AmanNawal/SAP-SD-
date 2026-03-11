## MTO Make to Order in SAP

* When customer places order then only starts the process of manufacturing finished products because the specification of the product is not standard. Every customer will place order with their own specification.

* Item category: **TAK**

* Special stock indicator: **E**

* Requirement type: **KE**

* Item category group: **0001**

* Strategy group: **20**


## Configuraion

* Create a new order type ***1MTO*** by copying the stnadrd sales order ***OR***. in T code ***VOV8***

<img width="603" height="367" alt="Image" src="https://github.com/user-attachments/assets/b40c8ce9-6fdb-40ce-90b4-058ca74917fe" />

---

* Create a new item category ***1MTO*** by copying the standard item category ***TAK*** in T code - ***VOV7*** also mark the special stock as **E**
  
<img width="581" height="412" alt="Image" src="https://github.com/user-attachments/assets/807be103-b720-4d92-9db9-838f932e509b" />

---

* Now do item category determination in T code ***VOV4***.

<img width="524" height="405" alt="Image" src="https://github.com/user-attachments/assets/c6f83fde-13f0-4053-b1dc-41ab1e8e6598" />

---

* Now create a delivery type ***1MTO*** in T code ***OVLK*** by copying standard delivery type ***LF***.
* Now create one billing type ***1MTO*** in T code ***VOFA*** by copying standard billing type ***F2***.
* Now goto ***VOV8*** and assign deliverty type as ***1MTO*** and billing type as ***1MTO***.

<img width="618" height="388" alt="Image" src="https://github.com/user-attachments/assets/4516422f-8b67-42b3-b28f-374ac9fb5b40" />

---

* Ensure that the material being used has a item category of ***0001***.

<img width="622" height="348" alt="Image" src="https://github.com/user-attachments/assets/3c69e32d-124f-44c3-858f-2e76afb8dbcd" />

---

* In MRP tab of material master the strategy group should be ***20***.

<img width="642" height="394" alt="Image" src="https://github.com/user-attachments/assets/e29e0170-8637-42c6-9661-dd7684909586" />

---


* Define requirement types goto **SPRO -> Sales and Distributions -> Basic functions -> Availability check and transfer of requirements -> Define requirement types.**

* Copy the standard requirement type ***KE*** to ***1MTO***.

<img width="517" height="177" alt="Image" src="https://github.com/user-attachments/assets/2e87af88-7f65-4426-b678-48466e1b4c3b" />

---

* In the same SPRO path as above click on ***determination of requirement type using transaction***
* Maintain origin period as 1 which ensures the first priority.

<img width="492" height="171" alt="Image" src="https://github.com/user-attachments/assets/690fa7ba-6704-4cf5-a02b-23b3a5b03443" />


* Now create one order in VA01 of type 1MTO.
* Before saving this order we can check in MMBE if there's any unrestricted stock available for the material. In this case its not.

<img width="762" height="341" alt="Image" src="https://github.com/user-attachments/assets/75c015f4-2983-4214-9d14-6da7facef08f" />
---

* Goto procurement type of sales order you will se 1MTO as requirement type.

<img width="762" height="343" alt="Image" src="https://github.com/user-attachments/assets/ecedbc61-2510-4209-b670-656d721c270e" />

---

* Now do the delivery and try to do PGI. It will throw the following error. It is failing because we would need special stock to fulfill this order as its a make to order.

<img width="530" height="166" alt="Image" src="https://github.com/user-attachments/assets/a5010ea5-bc12-4b25-bb35-8c5b42699143" />

---

* So now we need ot maintain special stock in T code - ***MB1C*** in S4 Hana(***MIGO***) with special stock as ***E***.

<img width="614" height="358" alt="Image" src="https://github.com/user-attachments/assets/950c502a-45d2-426c-97ee-134871129250" />

---

<img width="602" height="355" alt="Image" src="https://github.com/user-attachments/assets/1ed3e635-fea7-4f27-8104-dab9753f56c1" />

---
<img width="600" height="334" alt="Image" src="https://github.com/user-attachments/assets/a0fb3a36-ed45-4767-84dc-c25e9b442ebf" />

---

* Now do the delivery again, and do PGI. Now check MMBE you will see the stock restriced for sales order is now gone.

* Now create an invoice in VF01.

