\## Value Contract General



* It's an agreement between company and the customer about supplying the goods of particular value within a specific validity period. Value contract is not specific to one material, it's for group of materials.
* Doc type - WK1
* T - code: VA41



\## Value contract material specific 



* It's an agreement between company and the customer for supplying the goods of a particular material and value within a specific validity period.
* Doc type - WK2
* T - Code: VA41





\### Configuration Value contract general



* In T code: VOV8 copy the standard doc type \*\*\*WK1\*\*\* and create you own value contract named \*\*\*CWK1\*\*\*
* Extend the sales area for sales doc type ZWK1.
* Now create your own contract item category by copying the standard category \*\*\*WKN\*\*\* and create \*\*\*CWKN\*\*\*  





* \*\*\*Contract release control - B\*\*\* ensures that an error pops up incase if the value exceeds the contract overall value.  



<img width="810" height="479" alt="Image" src="https://github.com/user-attachments/assets/ccea278d-e8ad-4af3-81b5-1bef5cc06ce2" />



<img width="853" height="443" alt="Image" src="https://github.com/user-attachments/assets/55a1555a-4089-406b-b51f-c52020a2b2d3" />



---



* Now do item category determination in VOV4 and assign Castrol item category \*\*\*CWKN\*\*\* to combination of \*\*\*CWK1\*\*\* and \*\*\*NORM\*\*\*.









\### Checking the configuration workings



* Create a contract \*\*\*CWK1\*\*\*



<img width="959" height="503" alt="Image" src="https://github.com/user-attachments/assets/e289ef58-b314-4800-8276-7eb5ca7999e7" />



---



* Now create a order wrt contract created previously.



<img width="959" height="465" alt="Image" src="https://github.com/user-attachments/assets/d80315a9-f6a1-443a-a8f8-6f878603a433" />



---



* Since we have already placed an order worth of 1000 INR. You can see in the contract the value released is nor equal to the target value.



<img width="959" height="490" alt="Image" src="https://github.com/user-attachments/assets/0d34248b-d930-4957-b51c-12296204a4a2" />



---



\### Configuration Value contract material specific



* In T code - VOV8 copy the standard contract \*\*\*WK2\*\*\* and create your own contract type \*\*\*CWK2\*\*\*
* Go to \*\*\*T code - OVAZ\*\*\* and assign the sales area for the newly created contract type \*\*\*CWK2\*\*\*.
* Now create your own contract item category by copying the standard category \*\*\*WKN\*\*\* and create \*\*\*CWK2\*\*\*.
* Now do item category determination in VOV4 and assign Castrol item category \*\*\*CWK2\*\*\* to combination of \*\*\*CWK2(Sales doc)\*\*\* and \*\*\*NORM\*\*\*.



\### Checking the configuration working



* Now create a new material specific value contract.
* \*\*\*NOTE\*\*\* in material specific contract it is mandatory to enter a material alongside the target value.



<img width="959" height="506" alt="Image" src="https://github.com/user-attachments/assets/6c32dc5c-7dfb-4087-a24a-142204132587" />



---



<img width="959" height="499" alt="Image" src="https://github.com/user-attachments/assets/3e8d2f65-963b-41a7-b8aa-a743e9f7eeae" />



---

















