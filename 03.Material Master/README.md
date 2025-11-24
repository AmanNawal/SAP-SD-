## Creating Material Master Records


***It is possible that your newly created company code does not have company codes maintained for material management. In that case, you need to assign your company code with approprite fiscal year.***

***Path:*** SPRO-> Logistics General -> Material master -> Basic settings -> Maintain company code for material management


---

### Material type

* Material type controls the attributes of a material. For example, whether the material is to be managed in batches, whether the material is valuated at the plant level or at the company code level, and so on.
* ***T Code - OMS2***

***Types of material***

* Finished Product (FERT) - A material type used for materials that are produced in-house or procured and then sold to customers. These materials are typically the end products of a manufacturing process and are ready for sale.
* Raw Material (ROH) - A material type used for materials that are procured from
* Semi-Finished Product (HALB) - A material type used for materials that have undergone some processing but are not yet in their final form. These materials are typically used as components or sub-assemblies in the production of finished products.
* Trading Goods (HAWA) - A material type used for materials that are purchased and resold without any significant processing or transformation. These materials are typically bought from suppliers and sold to customers in the same condition.

---

### Material master number range

* T code to create material master number range - ***MMNR***
* Assign the number range to the material type using T code - ***OMS2***


---

### Material master Tabs from SD perspective

* Basic Data 1
* Basic Data 2
* Sales: Sales Org. 1
* Sales: Sales Org. 2
* Sales: General/Plant
* Foreign Trade export data
* Sales and distribution text
* Purchasing
* Foreign trade import data
* Purchase order text
* MRP 1
* MRP 2
* MRP 3
* MRP 4
* General Plant Data/Storage 1
* General Plant Data/Storage 2
* Quality Management
* Accounting 1
* Accounting 2
* Costing 1
* Costing 2

***Material Created***

* ***Material 120000000000100299 created***

---

### See all materials available based off plant, material type and material group

* T code - ***MM60***

<img width="852" height="470" alt="Image" src="https://github.com/user-attachments/assets/ed391839-3a29-4696-9ca4-7e8db67f6476" />

---


### Material master tables

* MARA - General Material Data
* MVKE - Sales Data for Material
* MARC - Plant Data for Material
* MAKT - Material Descriptions
* MLAN - Material Master Tax Classification
* MBEW - Material Valuation




