
##  Delivery scheduling and route determination

Here is the text exactly as mentioned in the image:

**Delivery Scheduling**

It is the process of determining delivery dates & confirms quantities into sales document.

Process of delivery scheduling: Whenever we are creating sales order 1st system will perform **Backward scheduling**. If backward scheduling fails then system will perform **Forward scheduling**.

* **Backward scheduling** always based on customer requested delivery date.
* **Forward scheduling** always based on today’s date.

**The below parameter system consider while performing delivery schedule:**

1. **Pick pack time:** (We maintain this in shipping point). It is the time taken to pick the material from storage location and to pack it.
2. **Loading time:** (We maintain this in shipping point). It is a time taken to do the process of loading the goods into trucks for dispatch.
3. **RLT:** (Replenishment lead time – we maintain this in material master MRP 3). It is the time taken to manufacture the product. System considers RLT if stock is not available.
4. **Transit time:** (we maintain this in route). It is time taken to deliver the goods from plant to customer.
5. **Transportation lead time:** (We maintain this in route). It is the time taken to arrange the mode of transportation (Trucks) for dispatching it to customer.

If stock is not available, then system consider either of (**RLT + PP**) or (**TLT**) whichever is higher.

If stock is available, then system consider either of (**PP**) or (**TLT**) whichever is higher.


### To check the proposed delivery date in sales order:

* In shipping point maintain the pick pack time and loading time. ***T code - OVXD***

<img width="859" height="702" alt="Image" src="https://github.com/user-attachments/assets/82e7ac4f-b6a8-4afb-a9b4-54ef44fa4314" />

---

* In material master maintain the RLT in MRP 3 tab. ***T code - MM02***


<img width="906" height="689" alt="Image" src="https://github.com/user-attachments/assets/4ec807bf-d7a2-4687-9e72-7223a8f21e28" />

---

* In the sales order the order confirmation would be done on the basis of ***Pick pack time, Loading time, RLT**.

* System considers Pick pack time, Loading time and RLT only when route is not determined.

### With Route determination

* With route ***transit time*** and ***transportation lead time*** will also be considered along with Pick pack time, Loading time and RLT.

Here is the text exactly as mentioned in the image:

If stock is available, then system consider either of (**PP**) or (**TLT**) whichever is higher.

**Configure for route determination Path**

* SPRO → logistic execution → transportation → basic transportation function → routes → define routes → define routes & stages
* Copy the standard route ***000001*** and create a new route ***ZCS001 - Route for UP***

<img width="856" height="619" alt="Image" src="https://github.com/user-attachments/assets/159d7368-6fcc-40b0-8089-dd2644549c8a" />

---

* SPRO → logistic execution → transportation → basic transportation function → routes → define routes → define transportation zones

<img width="512" height="376" alt="Image" src="https://github.com/user-attachments/assets/fc8ead56-0d05-4d5c-9b9d-929fd752ccff" />

---

* SPRO → logistic execution → transportation → basic transportation function → routes → define routes → route determination → Maintain route determination

<img width="1010" height="550" alt="Image" src="https://github.com/user-attachments/assets/ae1b237c-478a-4829-8ae0-cc96b2c232e4" />

---

<img width="1078" height="622" alt="Image" src="https://github.com/user-attachments/assets/0340202c-dbf0-4363-aea9-d7aaaf1caf16" />

---

* SPRO → logistic execution → transportation → basic transportation function → routes → define routes → route determination → Maintain country and transportation zone for shipping point

<img width="687" height="314" alt="Image" src="https://github.com/user-attachments/assets/02c19303-b4fa-4488-94ff-4fa5f93033d4" />

---

**Configuration for delivery scheduling**

* SPRO → S&D → basic function → delivery scheduling & transportation scheduling → define scheduling by sales document type → go to CSOR mention (X) and TL check

<img width="655" height="657" alt="Image" src="https://github.com/user-attachments/assets/a7051c5d-5e78-4a47-9fa4-56b5b227d9ec" />

---

* SPRO → S&D → basic function → delivery scheduling & transportation scheduling → define scheduling by shipping point

<img width="703" height="441" alt="Image" src="https://github.com/user-attachments/assets/99a1126b-c5ea-4b52-9730-ed0b0bfcb9fb" />

---

* SPRO → S&D → basic function → delivery scheduling & transportation scheduling → Maintain duration

You can maintain pick pack time and loading time other then shipping point i.e. Route dependent.

In customer master transportation zone we need to maintain destination zone.

<img width="998" height="335" alt="Image" src="https://github.com/user-attachments/assets/9623dbb7-5ee8-4084-9842-9bd3024be21f" />

---

<img width="972" height="300" alt="Image" src="https://github.com/user-attachments/assets/3a5af2c3-d5c8-4492-9fed-2fe83786f97c" />

---

<img width="1260" height="307" alt="Image" src="https://github.com/user-attachments/assets/78678a1d-0ab9-4a12-832a-82452a5cdbd6" />

---

* Assign transportation group to customer master general data

<img width="806" height="685" alt="Image" src="https://github.com/user-attachments/assets/988d5b82-d30c-4aee-a4ae-342a36383333" />