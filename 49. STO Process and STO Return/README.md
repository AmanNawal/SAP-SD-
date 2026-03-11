## STO Process and STO return

* There are 2 types of STO 

1. Intercompany STO (Stock is transferred from one plant to another plant but both plants are in different company code)
2. Intracompany STO (Stock is transferred from one plant to another plant but both plants are in same company code)

* In this session we will discuss about **Intracompany STO.**

**STO process and STO return**

* Transfer the stock from one plant to another plant within a company.

* STO is a two step process, 1st receiving plant will raise the PO to supplying plant, then supplying plant will do delivery with reference to PO. When we do delivery in supplying plant then stock will be reduce from supplying plant and stock will be displayed as stock in transit in receiving plant. The control is in movement type **[641]**. When the goods reaches to receiving plant then they do **MIGO** and when they do MIGO then actual stock update till then stock in transit.

* PO type in STO process is **UB**
* Delivery type in STO process is **NL**
* Delivery item category in STO process is **NLN**
* Schedule line category for STO is **NN**
* Movement types: **641 two step** (Stock in transit) i.e. we have done the delivery but at the receiving end MIGO is yet to be done.
  **647 one step** 


**STO RETURN**

* PO type in STO process is **UB**
* Delivery type in STO process is **NLR**
* Delivery item category in STO process is **NLRN**
* Schedule line category for STO is **NR**
* Movement types: **671 two step**
  **677 one step**


### Process STO Process

**Create a PO -> Delivery -> Proforma Invoice -> MIGO**

## Configuration

* Ensure that 2 plants are created in same company code and assign shipping point to both the plants.
* Assign plant to sales line i.e. sales org and distribution channel.
* Now assign purchasing organisation to supplying plant and receiving plant.
* We have to create receiving plant as customer with supplying sales area

<img width="463" height="380" alt="Image" src="https://github.com/user-attachments/assets/96896e3d-8a98-4cd8-912f-efb91293d650" />

---

* Material has to be extended to both the plants.

***YO20*** is receiving plant and ***YO10*** is supplying plant.

<img width="703" height="356" alt="Image" src="https://github.com/user-attachments/assets/ce437f33-695b-422a-938b-8ffba4a49ea3" />

---

* define shipping data for plants: **SPRO → MM → purchasing → Purchasing order → setup stock transport order → define shipping data for plants**

<img width="506" height="361" alt="Image" src="https://github.com/user-attachments/assets/1b18b381-2b86-4fee-8fb9-fb752ab0f3df" />

---

<img width="524" height="370" alt="Image" src="https://github.com/user-attachments/assets/c486a875-d281-4c28-b924-d0d5481d0560" />

---


* Assign delivery type and checking rule.

  * PO type in STO process is **UB**
  * Delivery type in STO process is **NL**

<img width="593" height="342" alt="Image" src="https://github.com/user-attachments/assets/2d5c4232-6218-48fd-bc2e-f38199634be7" />

---

* Assign delivery type with supplying plant and delivery plant. In the same SPRO path as mentioned above assign delivery type, one step procedure and underdelivery tolerance.
* Here if you check one step checkbox system would consider 647 otherwise it would consider 641 movement type.

<img width="538" height="376" alt="Image" src="https://github.com/user-attachments/assets/ef30a7ef-0673-4353-b095-e64edefc495f" />

---


* Now check the configuration by creating a PO using **T code - ME21N**. Also create supplying plant as a vendor in T code - XK01 so that we can use that vendor in ME21N PO creation.

<img width="529" height="283" alt="Image" src="https://github.com/user-attachments/assets/a2d5e3ec-806b-4a5e-8c0a-2427e054d9f3" />

---


<img width="768" height="297" alt="Image" src="https://github.com/user-attachments/assets/372cf657-08f3-464a-973c-09a033796bec" />

---

<img width="574" height="337" alt="Image" src="https://github.com/user-attachments/assets/6a37bbe7-6e21-4fd0-902c-1169355e3316" />

---

Ensure that shipping tab is visible in PO. Only then we will be able to create a delivery.

<img width="694" height="394" alt="Image" src="https://github.com/user-attachments/assets/833583f8-a98d-44fc-a5bd-529280caa2cc" />

---

* Now do the delivery using **T code - VL10B**, paste the PO number and click on execute.

<img width="559" height="275" alt="Image" src="https://github.com/user-attachments/assets/36173d41-4745-4f0f-9a35-7358ac73705f" />

---

<img width="541" height="199" alt="Image" src="https://github.com/user-attachments/assets/1812db64-759e-4d8a-bc62-900e906e047a" />

---

<img width="459" height="240" alt="Image" src="https://github.com/user-attachments/assets/26c139cf-4eb6-402a-9f3e-953f0f845a54" />

---

<img width="570" height="251" alt="Image" src="https://github.com/user-attachments/assets/6ebe5738-35ed-4ec9-bf03-fedbe4e99753" />

---

Is the document created for delivery.

<img width="471" height="195" alt="Image" src="https://github.com/user-attachments/assets/8799c9ab-0e0d-4d7b-8310-9ce3412bc805" />

---

* Do the PGI to move th stock from supplying plant and it would be moved to transit.

<img width="699" height="300" alt="Image" src="https://github.com/user-attachments/assets/e5dd1571-3a3d-4199-941e-17da27310989" />

---

* Now create a proforma invoice using **T code - VF01** with reference to delivery. **Billing doc type - F8**. Which would be provided to truck driver.

* Now perform ***MIGO*** 

<img width="742" height="318" alt="Image" src="https://github.com/user-attachments/assets/1d6e9891-0e65-4d8d-bd76-799fd0acff80" />

---

<img width="578" height="457" alt="Image" src="https://github.com/user-attachments/assets/b58c7b00-d773-4463-83e0-845e3df48fef" />

---

* Now in MMBE you will see that plant YO20 is having stock which was transferred from plant YO10.

### Process STO Return

* Incase if the stock is damaged or there is some issue with the stock we have to return the stock .
* It includes one additional configuration on the top of pre existing configurations defined above.

SPRO -> Material management -> puchasing -> purchase order -> return order -> store return/ return plant to plant

  * PO type in STO process is **UB**
  * Delivery type in STO process is **NLR**
  * Delivery item category in STO process is **NLRN**
  * Schedule line category for STO is **NR**
  * Movement types: **671 two step**
    **677 one step**

<img width="596" height="268" alt="Image" src="https://github.com/user-attachments/assets/2ec6b7d8-7715-400b-8c0a-c955c5bd5ac2" />

---

### Check the STO return configuration

***PROCESS - PO -> MIGO ->VL10D (Delivery)***


* Create a PO using ME21N.

<img width="569" height="316" alt="Image" src="https://github.com/user-attachments/assets/60b307b5-cf0e-4f5f-92c3-25b52262ef76" />

---

<img width="553" height="341" alt="Image" src="https://github.com/user-attachments/assets/e4546d70-8325-4aa3-88bf-4f47a73d45c8" />

---

Ensure you click on return item as this is a PO creted for returns. Also the shipping tab should be visible otherwis we won't be able to do delivery.

<img width="555" height="349" alt="Image" src="https://github.com/user-attachments/assets/fc4fbbfc-54b0-46d6-a378-14e1bc648409" />

---

* Now do ***MIGO***, paste the PO number and click on check item. Now to save click on check and post at the top left corner.

<img width="767" height="308" alt="Image" src="https://github.com/user-attachments/assets/59c5819a-eb17-42dd-886d-33741854c4dc" />

---

<img width="723" height="418" alt="Image" src="https://github.com/user-attachments/assets/2403aa3f-fd56-41b6-9697-8409d9c350ac" />

---

* After MIGO the stock will be in transit and then we have to do delivery using **VL10D**.

<img width="703" height="338" alt="Image" src="https://github.com/user-attachments/assets/d3560481-e563-4589-a61f-82a94989bb99" />

---


<img width="513" height="216" alt="Image" src="https://github.com/user-attachments/assets/5a8fbc7e-3280-4351-b7a6-e70607052110" />

---


<img width="442" height="214" alt="Image" src="https://github.com/user-attachments/assets/b8f9d477-ad5d-40eb-b239-f808d6ec0870" />

---


* Now do PGR (Post Goods Receipt) to move the stock from transit to receiving plant.

<img width="641" height="374" alt="Image" src="https://github.com/user-attachments/assets/8f0d8983-4385-4233-8128-c14944852877" />

---
