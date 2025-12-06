\## Quantity Contract



* It's an agreement between customer and company about supplying the goods of a certain quantity within a specific validity period.
* Document type - QC
* T code: VA41





\## Scheduling agreement



* It's an agreement between customer and company about supplying the goods of a particular quantity within a specific validity period with pre defined delivery dates.
* Document type - DS
* T Code: VA31



\### Configuration for quantity contract



* Create a new quantity contract type by copying standard quantity contract \*\*\*QC\*\*\* and then create new quantity contract  \*\*\*CSQC\*\*\*.
* Extends the new sales document to sales area in \*\*\*T code: OVAZ\*\*\*.
* Now create a new item category \*\*\*CKMN\*\*\* By copying the standard item category \*\*\*KMN\*\*\*.
* Now do item category determination in \*\*\*VOV4\*\*\*
* Now create a contract 



<img width="959" height="500" alt="Image" src="https://github.com/user-attachments/assets/ba730d33-8e59-44a2-9777-69170adb1235" />



---



* Now create a sales order referencing the contract.



<img width="958" height="500" alt="Image" src="https://github.com/user-attachments/assets/8a156050-dafc-4bfe-bb77-139073a5c0d8" />



---



* As we have created two sales orders one with quantity 1000 each material and one with 999 and 1999 another. We can see the same quantities on contract.



<img width="959" height="451" alt="Image" src="https://github.com/user-attachments/assets/600d200d-900b-4d90-87e5-d9a0bc413aba" />



---



\### Configuration for Scheduling agreement



* Create a new scheduling agreement doc type \*\*\*CSDS\*\*\* by copying standard scheduling agreement \*\*\*DS\*\*\* in VOV8.
* Extends the new sales document to sales area in \*\*\*T code: OVAZ\*\*\*.
* Now create a new item category \*\*\*CLPN\*\*\* By copying the standard item category \*\*\*LPN\*\*\*.
* Now do the item category determination in \*\*\*VOV4\*\*\*.
* Copy the standard schedule line category \*\*\*CN\*\*\* and create your own schedule line cat \*\*\*CC\*\*\*.
* Now do schedule line determination in \*\*\*VOV5\*\*\*.
* Now you can create a scheduling agreement and assign multiple delivery dates for material.



<img width="959" height="493" alt="Image" src="https://github.com/user-attachments/assets/854ae4a8-c744-4279-9069-11275000ddb2" />



---



<img width="961" height="511" alt="Image" src="https://github.com/user-attachments/assets/d4a92ed1-966a-478c-8ca6-0398fb46a975" />



---



* Create a new delivery directly from Scheduling agreement. A scheduling agreement already is the sales order + long-term plan combined.
* If you create a sales order referencing the SA, you will duplicate demand.
* Now in the delivery you can see that for date 06.12.2025 we have one delivery pending.



<img width="959" height="490" alt="Image" src="https://github.com/user-attachments/assets/1028da3c-8f01-4a4d-b819-9936a3de0763" />



---



* As we move ahead for the next delivery which is for date 06.06.2026 we again see one delivery pending.
* \*\*\*This means that we cannot deliver the goods until we arrive the delivery date or after delivery date\*\*\*.



\*\*\*FOR 06.06.2026\*\*\*



<img width="959" height="502" alt="Image" src="https://github.com/user-attachments/assets/30511441-2ac7-4982-b73f-3be742bddc48" />



---



\*\*\*FOR 06.12.2026\*\*\*



<img width="964" height="501" alt="Image" src="https://github.com/user-attachments/assets/3922f969-31cd-4624-a07f-55153c3bb90e" />

























