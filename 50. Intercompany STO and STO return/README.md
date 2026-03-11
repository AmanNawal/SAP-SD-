## Intercompany STO and STO return

* Stock transferring between one company plant to another company plant.

* In Intercompany STO two step process 1st receiving plant will raise the PO to supplying company plant then supplying company plant will do delivery with reference to PO when we do delivery in supplying company plant then stock will be reduce from supplying company plant and stock will be displayed as stock in transit in receiving company plant. The control is in movement type **[643]**. When the goods reaches to receiving company plant then they do **MIGO** and when they do MIGO the actual stock update till then stock in transit.

Supplying plant company: **YU10**

Receiving plant company: **RUSH**

* **PO type in STO process is NB**
* **Delivery type in STO process is NLCC**
* **Delivery item category in STO process is NLC**
* **Schedule line category for STO is NC**
* **Movement types:** **643 two step**
  **645 one step**

## Configuration

* We have to create receiving company plant as customer with supplying company sales area
* Supplying company plant as vendor with receiving company purchase org
* Material has to be extended to both the plants
* define shipping data for plants: **SPRO → MM → purchasing → PO → setup stock transport order → define shipping data for plants**
* Assign delivery type and checking rule
* Assign delivery type with supplying plant and delivery plant
* Assign intercompany pricing procedure **ICA01** to the combination of supplying sales area + document pricing procedure + customer pricing procedure
* Billing type need to create for intercompany invoice
* Maintain condition records for **PI01**

## Steps

* We have to create receiving company plant as customer with supplying company sales area.
* Goto XD01 to create a customer in receiving company with supplying company sales area.

<img width="493" height="391" alt="Image" src="https://github.com/user-attachments/assets/f4f078ea-f111-4668-8787-0b0dfe987126" />

---

* Supplying company plant as vendor with receiving company purchase org
* Create a vendor of supplying company plant in receiving company code with purchasing org. in **T code - XK01**

<img width="533" height="293" alt="Image" src="https://github.com/user-attachments/assets/f941295f-749f-4455-81be-a38a3bdbcf14" />

---

Ensure you are assigning YO10 as a supplying plant for vendor master data. Or else shipping atb will not display 

<img width="669" height="400" alt="Image" src="https://github.com/user-attachments/assets/d0e9c98a-654b-4318-8ec9-c04c6a6f5bec" />

---

* Material has to be extended to both the plants

<img width="459" height="238" alt="Image" src="https://github.com/user-attachments/assets/13f459e5-de68-41d1-a07a-5479cf121ed5" />

---

* define shipping data for plants: **SPRO → MM → purchasing → PO → setup stock transport order → define shipping data for plants**

Assign supply sales area to receiving plant vustomer created in the above step.

<img width="589" height="404" alt="Image" src="https://github.com/user-attachments/assets/c9c80d6b-f60f-450e-ac07-8dd71209dc9d" />

---

<img width="622" height="399" alt="Image" src="https://github.com/user-attachments/assets/591262b2-9456-4b10-a9d6-9af48901a4d1" />

---

Assign suplying plant sales area to supplying plant.

<img width="556" height="382" alt="Image" src="https://github.com/user-attachments/assets/10c1893e-7770-467d-b729-74c413604890" />

---

<img width="514" height="376" alt="Image" src="https://github.com/user-attachments/assets/c4886d24-0676-48e4-8a41-5e49aef5eb1c" />

---

* Assign delivery type and checking rule **SPRO → MM → purchasing → PO → setup stock transport order -> Assign delivery type and checking rule**

Create a new entry if not pre existing.


<img width="697" height="240" alt="Image" src="https://github.com/user-attachments/assets/5d003a70-78d9-46b4-b96f-3e0c22ac013e" />

---


* Assign delivery type with supplying plant and delivery plant **SPRO → MM → purchasing → PO → setup stock transport order ->Assign document type, one step procedure, underdelivery tolerance**

<img width="652" height="283" alt="Image" src="https://github.com/user-attachments/assets/bb1fcfbc-6464-4e34-a6ef-800f44127dc1" />

---

* Assign intercompany pricing procedure **ICA01** to the combination of supplying sales area + document pricing procedure + customer pricing procedure in T code ***OVKK***

<img width="591" height="280" alt="Image" src="https://github.com/user-attachments/assets/27aea5d2-47c9-45ae-82ee-5c51a2b7ab2e" />

---

* Billing type need to create for intercompany invoice, copy the standard billing type ***F2*** and create your own ***IV01***

<img width="575" height="417" alt="Image" src="https://github.com/user-attachments/assets/660eeea3-43b3-43c9-98cf-a2d7510dd3f2" />

---

* Maintain condition records for **PI01**

<img width="732" height="271" alt="Image" src="https://github.com/user-attachments/assets/729ee743-0e43-40ca-a328-be5597c87e0e" />

---

We maintain condition record for PI01 because IV01 condition type references PI01.


<img width="562" height="447" alt="Image" src="https://github.com/user-attachments/assets/7c7c99c0-3627-46fb-acec-0e34dee94f65" />

---

* Now create a PO using ***T code - ME21N*** with PO type NB.

<img width="583" height="332" alt="Image" src="https://github.com/user-attachments/assets/e86304e3-7872-421e-a06d-1977c8719334" />

---

<img width="624" height="259" alt="Image" src="https://github.com/user-attachments/assets/7e5b2e58-e066-401b-a24b-6f90fc1b9fc1" />

---

<img width="715" height="325" alt="Image" src="https://github.com/user-attachments/assets/838b5d9f-3d1d-490e-9cfa-dc497ffa45a0" />

---

* Do the delivery in T code **VL10D**.

<img width="626" height="294" alt="Image" src="https://github.com/user-attachments/assets/d5c8c0eb-0731-4d7a-a918-de7d52d25805" />

---

* Do the PGI, you will now see the stock in transit for receving plant because of movement type 643.

* Create an invoice in T code - VF01 and select billing type ***IV01***.

<img width="783" height="318" alt="Image" src="https://github.com/user-attachments/assets/fe6fada8-e714-4c30-86da-b1ef64e34b1c" />

---

* Do the Goods receipt by doing MIGO.

<img width="773" height="334" alt="Image" src="https://github.com/user-attachments/assets/b19090b0-1efb-485e-bf7a-affd6c1667f0" />

---

<img width="661" height="419" alt="Image" src="https://github.com/user-attachments/assets/246a2ae4-bfa9-46b2-8243-75a9a392ae2f" />

---

Click on check and then on post at top left in MIGO.


* Now you will be able to see stock updated in receving plant.

* Now perform ***MIRO***.

<img width="713" height="370" alt="Image" src="https://github.com/user-attachments/assets/e5daa974-d609-4fd2-9bc5-abcd8e27cd53" />

---

<img width="716" height="426" alt="Image" src="https://github.com/user-attachments/assets/7b5bd9bd-e56a-43f0-8e3e-fce984d6cbdc" />

---

## Intercompany STO RETURN

* **PO type in STO process is NB**
* **Delivery type in STO process is NCR**
* **Delivery item category in STO process is NCRN**
* **Schedule line category for STO is NS**
* **Movement types:** **673 two step**
  **675 one step**

**Configuration**

* Return delivery type need assign to supplying plant: **SPRO → MM → purchasing → PO → Return order**

<img width="664" height="328" alt="Image" src="https://github.com/user-attachments/assets/127f8740-9adb-410d-987d-5e956dc9b622" />

---

* Now create one PO in ME21N.

<img width="760" height="393" alt="Image" src="https://github.com/user-attachments/assets/84bace26-f125-4314-ad17-2ce952e2b6d5" />

<img width="584" height="376" alt="Image" src="https://github.com/user-attachments/assets/e8f2aee1-b87b-49ca-aa62-498c88a3ef3d" />

<img width="782" height="414" alt="Image" src="https://github.com/user-attachments/assets/316c27c9-b648-443e-851d-886aad44034a" />


* Do delivery in T code ***VL10D***.

<img width="587" height="292" alt="Image" src="https://github.com/user-attachments/assets/e069a853-f335-454b-9f96-9e48ceef2929" />

---

* Before doing PGI we have to do ***MIGO*** first.


<img width="763" height="334" alt="Image" src="https://github.com/user-attachments/assets/b723d265-da95-47cb-9f05-1b205aaa1573" />

---

<img width="694" height="415" alt="Image" src="https://github.com/user-attachments/assets/4793a157-0131-422e-9f3b-2f023f94fc42" />

---

* Now to The PGR in delivery and check the return stock sucessfully received.



