## Credit Memo (Doc type - CR)

* Is a sales document that is used to credit a customer for returned goods, pricing errors or billing corrections.
* Substraction from customer outstanding.

* There is no delivery as there is no physical movements of goods involved.

### Configuration

* Create your own credit memo doc type ***CSCR*** by copying standard doc type ***CR*** in t code ***VOV8***.

<img width="1123" height="707" alt="Image" src="https://github.com/user-attachments/assets/89095141-4351-4e94-9370-9cdab67ffea9" />

---

* Setup the sales area corresponding to your credit memo doc type in t code ***OVAZ***.
* Copy the standard item category ***G2N*** to create your own item category ***CG2N*** in t code ***VOV7***.

<img width="891" height="533" alt="Image" src="https://github.com/user-attachments/assets/62c57436-2587-44d0-932c-044fc21c25cf" />

---

* Now do the item category determination for CSCR in t code ***VOV4***.
* Now create your own Billing document by copying standard billing type ***G2*** to ***CSG2*** in t code ***VOFA***.

<img width="891" height="533" alt="Image" src="https://github.com/user-attachments/assets/9367c3c4-69de-4f57-907d-0e465affc421" />

---

* Assign **CSG2** to sales doc type **CSCR** in t code VOV8 so that billing doc type is automatically proposed while creating billing for credit memo.

* We are planning to create a credit memo with reference to billing document(F2). So we need to setup copy control between sales doc to billing doc. In T code - ***VTAF*** copy the standard control from CR to F2 and assign it to CSCR(sales order) and CSG2(billing).
* Make sure you copy the item category level as well i.e G2N to CAN by copying TAN to G2.

***Now you can create a credit memo in t code VA01 using order type CSCR.***



## Debit Memo (Doc type - DR)

* Is a sales document that is used to charge a customer for under-billed amounts, pricing errors or additional services provided.
* We add amount to customer outstanding without any physical movement of goods.
* The reason for debit memo might be
    - User mistakenly undercharged the customer in previous invoice.
    - Charging interest to customer for the alte payment.

### Configuration

* In T code - ***VOV8*** create your own debit memo doc type ***CSDR*** by copying standard doc type ***DR***.
* Setup the sales area corresponding to your debit memo doc type in t code ***OVAZ***.
* Now create your item category by copying standard debit memo item category ***L2N*** and create your own item category ***CL2N*** in t code ***VOV7***.
* Now do the item category determination for CSDR in t code ***VOV4***.

<img width="669" height="490" alt="Image" src="https://github.com/user-attachments/assets/8a50df86-8b9f-41fd-a37f-8898e90036f2" />

---

* Now create your own Billing document by copying standard billing type ***L2*** to ***CL2*** in t code ***VOFA***.
* Assign **CL2** to sales doc type **CSDR** in t code VOV8 so that billing doc type is automatically proposed while creating billing for debit memo.