## Enterprise structure


## Information

| Sl.no | Organizational Unit  | Length | Transaction Code | Personal Responsible |
| ----- | -------------------- | ------ | ---------------- | -------------------- |
| 1     | Company Code         | 4      | OX02             | FI Consultant        |
| 2     | Sales Organization   | 4      | OVX5             | SD Consultant        |
| 3     | Distribution Channel | 2      | OVXI             | SD Consultant        |
| 4     | Division             | 2      | OVXB             | SD Consultant        |
| 5     | Sales Office         | 4      | OVX1             | SD Consultant        |
| 6     | Sales Group          | 3      | OVX4             | SD Consultant        |
| 7     | Plant                | 4      | OX10             | MM Consultant        |
| 8     | Storage Location     | 4      | OX09             | MM Consultant        |
| 9     | Shipping point       | 4      | OVXD             | SD Consultant        |

---

## Creating a company code

***Path***

<img width="827" height="559" alt="Image" src="https://github.com/user-attachments/assets/43845794-7488-4ef9-a1ae-f04e5815cff0" />

* Click on edit company code data
* Enter the required details and click on save

<img width="927" height="443" alt="Image" src="https://github.com/user-attachments/assets/9fe833eb-813d-41a4-ba14-0feeb89ab29c" />

Table - T001 (Check IN0N)

---

## Create a sales organization

***Path***

<img width="862" height="644" alt="Image" src="https://github.com/user-attachments/assets/2b444a80-5608-41df-a6e9-aaf0a1f0b174" />

* Click on new entries
* Enter the required details and click on save

<img width="945" height="597" alt="Image" src="https://github.com/user-attachments/assets/bda6b8fd-99ec-4bc4-94f2-901a3ba0563d" />

Table - TVKO (Check IN0N and IN01)

---

## Create a distribution channel

***Path***

<img width="587" height="504" alt="Image" src="https://github.com/user-attachments/assets/9e3b017d-9b62-494f-a631-5b5c458a4ee6" />

* Click on new entries

<img width="415" height="359" alt="Image" src="https://github.com/user-attachments/assets/a77ede7b-8269-4537-b85a-bb86d3bb5ca5" />

* Got to TVTW and check ZA, ZB and ZC.

---

## Create a division

***Path***

<img width="700" height="556" alt="Image" src="https://github.com/user-attachments/assets/17be7e34-a229-48cb-9f49-a87f295664e1" />

* The reason why division is in logistics general is because it is used in MM and PP also which are logistics modules included in SD.
* Logistics general stores data which is used across logistics modules.

<img width="634" height="274" alt="Image" src="https://github.com/user-attachments/assets/b36b6fd8-c4fc-48b0-a539-fe7075cd5d5a" />

* Click on new entries

<img width="648" height="379" alt="Image" src="https://github.com/user-attachments/assets/20033bd3-b6cd-4ffd-9d9f-404ffaa69e67" />

* Now check ZT, ZD and ZY in table TSPA.

---

### Create a sales office

***Path***

* SPRO -> Enterprise structure -> Definition -> Sales and Distribution -> Define, copy, delete, check sales office

<img width="545" height="284" alt="Image" src="https://github.com/user-attachments/assets/90e81f5d-9bf9-41b7-8127-731bdc78129d" />

* After maintaining the entries and address click on save

* Check in table TVBUR for IN0N and IN01.

---


### Create a sales group

***Path***

* SPRO -> Enterprise structure -> Definition -> Sales and Distribution -> Define, copy, delete, check sales group

<img width="421" height="347" alt="Image" src="https://github.com/user-attachments/assets/0e277dc2-48cc-4ccf-b109-47387237e995" />

* After maintaining the entries click on save

* Check in table TVKGR for INN and IN1.

<img width="730" height="392" alt="Image" src="https://github.com/user-attachments/assets/77d07227-7471-400d-8503-91193b81a547" />


---

## Create a plant

***Path***

* SPRO -> Enterprise structure -> Definition -> Logistics - General -> Define, copy, delete, check plant
* The plant is created in logistics general because it is used across logistics modules like MM, PP and SD.
  
<img width="897" height="670" alt="Image" src="https://github.com/user-attachments/assets/d5fa7407-2b67-4682-9abf-80033d9a76be" />

* Now, check in table T001W for 0010, 020 and 0030.

<img width="1231" height="512" alt="Image" src="https://github.com/user-attachments/assets/2fa262cd-865f-42e8-9ce2-2486dab50a52" />

---

## Create a storage location

***Path***

* SPRO -> Enterprise structure -> Definition -> Materials Management -> Maintain storage location.
* Normally, the ystem will ask for the plant for which the storage location is to be created.

<img width="904" height="359" alt="Image" src="https://github.com/user-attachments/assets/06bea793-6be5-4040-869d-3d9d04e3217c" />

* Click on new entries and enter the required details and click on save
* After maintaining check the entries on table T001L for 0010, 0020 and 0030.

<img width="711" height="610" alt="Image" src="https://github.com/user-attachments/assets/d86aa898-83e9-4b1b-95fa-579a86cff7ed" />

---

## Set up shipping point

***Path***

* SPRO -> Enterprise structure -> Definition -> Logistics Execution -> Define, copy, delete, check shipping point

<img width="869" height="721" alt="Image" src="https://github.com/user-attachments/assets/d180dbb2-8e8c-4023-ab1d-3e8b8fe36631" />


<img width="955" height="515" alt="Image" src="https://github.com/user-attachments/assets/c586d195-ebfb-491c-b9ec-2efd23fccd35" />

* check the entries in table TVST for ZZBH, ZZKA and ZZUP.



