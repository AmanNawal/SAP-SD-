## Availability Check in Sales order

* Is a core function used to determine whether the required quantity of a material can be delivered on the requested delivery date.
* Availability check is carried out in different transactions like Sales order creation, delivery creation, Purchase order creation, goods issue and also in production order. 
* The point to be noted here is everywhere the availability check is carried out using two basic elements.

1. Checking rule

2. Checking group

***Types if availability check***  

- There are three types of availability check:

* Check on the basis of the ATP quantities

* Check against product allocation

* Check against planning

<img width="671" height="526" alt="Image" src="https://github.com/user-attachments/assets/9951b6a1-e37f-46be-9b7d-a210f1a49ea1" />

---

***In this example we are going to use the first type - Check on the basis of the ATP quantities***

***SPRO PATH - SPRO -> Sales and Distribution -> Basic Functions -> Availability Check and Transfer of Requirements -> Availiability Check -> Availability check with ATP logic or against planning***


### Configuration Steps  

***Define checking groups***  

*  The checking groups defines what type of requirements are passed on i.e., the daily requirements, weekly requirements or monthly requirements summed up.
* OR do we need indivisual requirements to be considered for availability check i.e., a line for each sales order.
* The system automatically uses individual requirements for special stock movements such as consignment stock, returnable packaging, etc., even if summarized requirements have been selected. 

    * 01 - Individual requirements
    * 02 - Daily requirements

<img width="1365" height="678" alt="Image" src="https://github.com/user-attachments/assets/4ee05a78-8317-4787-82cf-331668da3cd3" />

---

* Copy the standard Checking group ***01*** for daily requirement and create a new checking group ***C1***

<img width="866" height="658" alt="Image" src="https://github.com/user-attachments/assets/e49e0f26-a475-490a-aadd-aa5d185d598a" />

---

***Next step: Material Block for other users***

* This configuration ensures that if two customers places the orders at same time whosoever has placed the order first gets the available stock.

* Copy the standard config ***02*** and create a new entries as below. 

<img width="966" height="419" alt="Image" src="https://github.com/user-attachments/assets/3133ad00-ba26-4974-8caa-8664bb5354b0" />

---

***Next step: Define checking group default value***

* Whenever we create material master we have to maintain availability check parameter manually, this configuration ensures that whenever a material master of certain material type and plant is created the checking group is automatically populated.

<img width="916" height="384" alt="Image" src="https://github.com/user-attachments/assets/f50df6e0-753e-4060-bb3a-8eeb9e57683e" />

---

<img width="924" height="706" alt="Image" src="https://github.com/user-attachments/assets/20d99c2b-3041-4d53-ba08-2461775a0e21" />

---

***Next step: Carry out control for availability check***

* Controls at which document levels do we want to carry out availability check in this case sales order and delivery document levels.
* So we copy the standard order and delivery configs 02 -> A (Order) and 02 -> B(Delivery) and create new entries as below.

<img width="975" height="473" alt="Image" src="https://github.com/user-attachments/assets/d3941136-7382-4d9a-b942-0ffd702d0b2a" />


<img width="747" height="485" alt="Image" src="https://github.com/user-attachments/assets/ef9cea4d-f7dc-427e-a1b6-6e6976404512" /> 

---

***Some important points in above configuration***


<img width="794" height="707" alt="Image" src="https://github.com/user-attachments/assets/b8e6758f-7056-4afc-a576-3baa3c1bc837" />   


* ***Include sales req*** - When checked, the system open orders quantities for availability check in schedule line and confirms the quantity even when the same stock has already been ordered(but not delivered hence open order).
* ***Include deliv req*** - When checked, the system open delivery quantities for availability check in schedule line and confirms the quantity even when the same stock has already been considered but not PGI(but not yet goods issued hence open delivery).

* ***Stocks section*** - tells the system which stocks can be used for availability checks safety stock, transfer stock etc.

* ***Check without RLT*** - When checked ensures that the quantities are not confirmed if the stock is not available. If unchecked this, system will confirm the quantities based on future dates based on RLT. 

![Full information](https://www.slideshare.net/slideshow/availability-check-in-sap-sd-43046031/43046031)





